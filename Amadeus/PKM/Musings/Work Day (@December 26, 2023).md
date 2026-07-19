---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "December 27, 2023 7:24 PM"
Status: "Unprocessed"
Created time: "December 26, 2023 6:41 AM"
---

# Work Day (@December 26, 2023)

## Today's Tasks

[Untitled](Work%20Day%20(@December%2026,%202023)/Untitled%203a1730fe7cd7402c9caeb76521d80c36.csv)

## Today's Thoughts

- I need to create a new `TransactionFilters` component for our transaction log.
- It is composed by
    - `AddTransactionsFilterButton` , a component that toggles the filters panel.
    - `TransactionsFilterPanel` , a component that is used to *select* the filters to be applied.
- The *button + panel* behavior can be easily done with `headlessui`.
- `AddFilterButton`
- `TransactionsFilterPanel`
    - This panel has has master + detail interface where each master item is a `Tab`.
    - Both master and detail need to be scrollable.
    - The `onChange` event of any control inside the detail updates the url.
- Application Filters Standard:
    - These filters are inspired in the same functionality shown in [demo.mercury.com](http://demo.mercury.com).
    - This feature is intended to provide filtering capabilities throughout the application in components like tables and lists.
    - This type of feature is better suited to be a “*global*” or “*shared*” feature. For this reason we are assigning it a dedicated scope (`ui-filters`) in our code base which can be imported by consumers.
    - Filters API:
        - `addFilter`: A function that receives the name of the filter and a value. It will push the given value to the filtered values.
        - `removeFilter`: A function that receives the name of the filter and a value. It will remove the given value from the filtered values.
        - `resetFilter` : A function that receives the name of the filter and its new value. It will remove all filtered values.
        - `getFilter` : A function that receives the name of the filter and returns its filtered values.
    - Filters API Internals:
        - `filters`: A key-value object that represents the currently applied filters of the application. Each key in the object is unique and represents the name of the filter, while the value is a collection of the values which represent the predicate.
        - URL Representation:
            - A common pattern in web development is to have these type of filters visible in the query string of the URL.
            - The filters of the application will be assigned to a `q` search parameter.
            - The `q` search parameter contents should be a valid serialized object.
            - The URL should be updated once the `filters` state object is modified with a swallow update.
            - Any *falsy* / empty properties of the `filters` shouldn't will not be displayed.
            - Consumers of the API do not need to update the URL by themselves as it may cause undesired side effects.
            - Example of generated URL with filter: [`https://demo.mercury.com/transactions?q={"filters"%3A{"accountPartyIds"%3A["credit-acct-txn-party-id"]}}`](https://demo.mercury.com/transactions?q=%7B%22filters%22%3A%7B%22accountPartyIds%22%3A%5B%22credit-acct-txn-party-id%22%5D%7D%7D)
                - Encoded `q` search parameter:
                    
                    ```json
                    {"filters"%3A{"accountPartyIds"%3A["credit-acct-txn-party-id"]}}
                    ```
                    
                - Decoded `q` search parameter:
                    
                    ```json
                    {
                      "filters": {
                        "accountPartyIds": [
                          "credit-acct-txn-party-id"
                        ]
                      }
                    }
                    ```
                    
        - Restoration Process:
            - The restoration process is performed as soon as the current page is loaded.
            - During the process we need verify the existence of the `q` search parameter and deserialize its contents.
            - Since the process of restoring the filters is sync, there is no need for boolean flags to signal a loading status.
            - If the `q` search parameter happens to be an invalid JSON, we should not apply any filter and use an empty object instead as a fallback `{}`.