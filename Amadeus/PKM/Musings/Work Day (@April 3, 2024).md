---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "April 4, 2024 12:44 PM"
Status: "Unprocessed"
Created time: "April 3, 2024 5:00 AM"
---

# Work Day (@April 3, 2024)

## Today's Tasks

[Untitled](Work%20Day%20(@April%203,%202024)/Untitled%2078636bec9e1040938f473ca13fd66a01.csv)

## Today's Thoughts

Jot down your thoughts here…

- Create new feature flag for bridge integration.
- Update Data Panel API
    - As part of our Bridge integration, we found we need to reuse the DataPanel component and for that reason we need to extend its API to make it more flexible for customization.
- Implement Add Or Receive Funds > ACH/Wire On-Ramp Flow
    - Update AddOrReceiveFunds journey to display on-ramp option.
        - As part of our Bridge integration, we need to display a new option that says “ Wire/ACH On-Ramp” in our add-or-receive-funds journey.
    - Update add-or-receive-funds journey navigation.
        - As part of our Bridge integration, we need to display a new screen once the “Wire/ACH On-Ramp” option is selected in the “Deposit Method” screen.
    - Create the “ACH/Wire On-Ramp Details Screen”
        - As part of our Bridge integration, we need to create the new “ACH/Wire On-Ramp Details” Screen.
        - Once a user reaches this screen they will be prompted with:
            - A data panel with their bridge account information
                - This information will always remain the same.
                - This information should come from Bridge itself.
                - There will be no reference to Bridge from the OneSafe’s user perspective.
            - A tuple of BankingAccount + Network selector.
                - Users use this section to change their preference regarding what to do with the received fiat money.
                - This preference must be persisted somehow.
- Update all withdrawal pages with falg to do that on the flow component instead.