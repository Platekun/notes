---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "November 25, 2023 2:46 AM"
Status: "Processed"
Created time: "November 24, 2023 9:35 PM"
---

# Multiple Checking Accounts

- Update the data access layer to hold multiple accounts in users
    - **Overview**: As a part of our multiple checking accounts feature, we need to update our data access layer to hold these new resources.
    - **Discussion**:
        - We need to create a data access resource to hold accounts. They have the following properties:
            - account status.
            - account name.
            - account type.
            - account number (obfuscated, value).
        - We need to update the banking balance resource to hold an `accountId`.
        - We shouldn't use from the `/me` endpoint to retrieve the account anymore.
- Create a `enableMultipleCheckingAccounts` feature flag.
    - **Overview**: As a part of our multiple checking accounts feature, we need to hide the new functionality behind a feature flag until ready.
- Update sidebar component:
    - **Overview**: As a part of our multiple checking accounts feature, we need to update the sidebar of our application.
    - **Discussion**:
        - The dashboard links are now padded and have rounded borders.
        - The sidebar itself now have grey borders around.
            - The sidebar should have an accounts item.
                - When pressed it should display the list of accounts the user has associated.
                - The list of accounts should be scrollable.
        - The sidebar footer should now display the company name instead of the “*View Profile*” link it used to have.
- Create the accounts index page scope.
    - **Overview**: As part of our multiple checking accounts feature, we need to create the scope associated to the accounts index page.
    - **Discussions:**
        - Create a new package in the monorepo with the name of `ui-accounts-index-page`.
- Create the accounts table component
    - **Overview**: As part of our multiple checking accounts feature, we need to create a table component that renders the information from an account resource.
    - **Discussion**:
        - It should display the account name.
        - It should display the account type.
        - It should display a home icon when the account is from us.
        - It should display a globe icon when the account is intl.
        - It should display the total balance of the account.
- Create the accounts index page
    - **Overview**: As part of our multiple checking accounts feature, we need to create a page that serves as index for all the accounts a user may have associated.
    - **Discussion**:
        - It should have an summary balance panel as a header with the total balance, the banking balance, the crypto balance (Do not include the Account transfer button for now).
        - It should have an accounts table.
- Update the crypto balance breakdown component
    - **Overview**: As part of our multiple checking accounts feature, we need to update the styles of our crypto balance breakdown component.
- Update the balance distribution chart component
    - **Overview**: As part of our multiple checking accounts feature, we need to update the styles of our crypto balance distribution chart component.
    - **Discussion**:
        - **Note**: We need to make sure the component does not break what is located on the multi sig safes dashboard.
- Create the account page scope
    - **Overview**: As part of our multiple checking accounts feature, we need to create the scope associated to the accounts page.
    - **Discussions:**
        - Create a new package in the monorepo with the name of `ui-account-page`.
- Create the account page
    - **Overview**: As part of our multiple checking accounts feature, we need to create a page that serves as a place to display the details of a user's account.
        - **Discussion**:
            - It should have the account type.
            - It should have the account name.
            - It should have an updated version of the balance distribution chart component.
            - It should have an updated version of the crypto breakdown component.
- Create the account page options component
    - **Overview:** As part of our multiple checking accounts feature, we need to create a helper menu to serve shortcuts to the user while on the account page.
        - **Discussion**:
            - It should have an “*Edit Account Name*” button that triggers the edition mode of the header.
            - It should have a “See Transactions” button that redirects the user to the transactions page.
            - It should have a "*Crypto Deposit Details*” button that takes the user to the add-or-receive-funds > crypto flow with the specific account.
            - It should have a "*Wire Deposit Details*” button that takes the user to the add-or-receive-funds > wire flow with the specific account.
            - It should have a “*Download Statement*” account that generates a downloadable statement to the user about the selected account.
- Create the add checking account modal
    - **Overview**: As part of our multiple checking accounts feature, we need to create a modal to let users create new accounts for them.
        - **Discussion**:
            - We need to add an “*Add Checking Account*” link button to the accounts index page. That when pressed will trigger a new modal.
            - The new “Add a Checking Account” modal:
                - It should have a radio option to create a US crypto account.
                - It should have a radio option to create an intl foreign account.
                - It should have a label to warn users about the max number of accounts they can hold (5 in this case).
                - It should have a close and submit (Create Account) button.
            - When the “Create Account” button is pressed, we should display a spinner while requesting the account creation.
            - After the request is created we need to update the accounts table to hold the new pending account.
            - The new account must have a “processing” status and should be disabled.
            - We should disable the “*Add Checking Account*” link button in case we reach 5 accounts in total.