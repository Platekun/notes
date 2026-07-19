---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Work"
Last edited time: "February 20, 2024 10:29 PM"
Status: "Unprocessed"
Created time: "February 20, 2024 5:38 AM"
---

# Work Day (@February 20, 2024)

## Today's Tasks

[Untitled](Work%20Day%20(@February%2020,%202024)/Untitled%205a19bea06fa84151af99ca346dfb6fde.csv)

## Today's Thoughts

- Create Invoice
    - [x]  Create “Create Invoice” Scope, Route and Page.
    - [x]  Modify “Add Or Receive Funds” Journey To Link “Create Invoice” Journey.
    - [ ]  Create “Create Invoice” Skeleton (Provider, Navigation, Layout, Content and SideBar).
    - [x]  Create CreateInvoicePage
        - [x]  Make RecipientComboBox reusable.
        - [x]  Review AmountField styles.
        - [x]  Review BankingAccountSelectField styles.
        - [x]  Create NotesField.
        - [x]  Create NewInvoiceForm.
    - [x]  Create CreateInvoiceConfirmationPage.
    - [ ]  Integrate with “Create Invoice API”.
- Invoices Index Page
    - [ ]  Create “Create Invoice” Scope, Route and Page.
    - [x]  Add a “View All Requests” Button to the CreateInvoiceConfirmationPage.
    - [x]  Update API Access Layer To Support Invoices
        
        ```json
        type InvoiceDto = {
          createdAt: string;
          updatedAt: string;
        	contactName: string;
          contactEmail: string;
        	status: "active" | "cancelled" | "paid";
          amount: FormattedAndPlain;
          bankingAccountId: string;
          paymentUrl: string;
        	notes: string;
        }
        ```
        
    - [ ]  Create invoices index page.
        - [x]  Add “Create Invoice” button to the invoices index page.
        - [x]  Create invoices table.
        - [ ]  Create invoice detail popover panel.
        - [ ]  Integrate with “Delete Invoice API".
        - [ ]  Integrate with “Update Invoice API”.
    - feat/THR-2719/modularize-design-system