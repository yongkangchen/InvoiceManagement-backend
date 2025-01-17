# Invoice Management

1.  User Registration and Login: The system should allow users to register and log in w
their email and password.
2. Invoice Creation: The system should enable users to create invoices by providing d
   such as customer information, product description, quantity, price, and tax.
3. Invoice Management: The system should allow users to view, edit, and delete invoi
   Users should also be able to search invoices by customer name, date,
   and other relevant filters.
4. Payment Management: The system should include a payment management module
   track invoice payments, including partial payments,
   overdue payments, and payment history.
5. Reminder and Notification: The system should provide tools to send reminders and
   notifications to customers for overdue payments, pending
   invoices, and payment receipts.

Based on the above requirements, we can design the following table structures:


1. **User Table**:

   - `UserID` (Primary Key, INT)
   - `Email` (VARCHAR)
   - `Password` (VARCHAR)
   - `FirstName` (VARCHAR)
   - `LastName` (VARCHAR)
   - Other personal information fields (e.g., Address, ContactNumber, etc.)

2. **Invoice Table**:

   - `InvoiceID` (Primary Key, INT)
   - `CustomerID` (Foreign Key, referencing Customer table, INT)
   - `ProductDescription` (VARCHAR)
   - `Quantity` (INT)
   - `Price` (DECIMAL)
   - `Tax` (DECIMAL)
   - `CreationDate` (DATE)
   - `ModificationDate` (DATE)

3. **Customer Table**:

   - `CustomerID` (Primary Key, INT)
   - `FirstName` (VARCHAR)
   - `LastName` (VARCHAR)
   - `Email` (VARCHAR)
   - Other contact information fields

4. **Payment Table**:

   - `PaymentID` (Primary Key, INT)
   - `InvoiceID` (Foreign Key, referencing Invoice table, INT)
   - `Amount` (DECIMAL)
   - `PaymentDate` (DATE)
   - `PaymentStatus` (VARCHAR, e.g., 'Partial Payment', 'Overdue Payment', etc.)

5. **Reminder Table**:

   - `ReminderID` (Primary Key, INT)
   - `CustomerID` (Foreign Key, referencing Customer table, INT)
   - `InvoiceID` (Foreign Key, referencing Invoice table, INT)
   - `ReminderType` (VARCHAR, e.g., 'Overdue Reminder', 'Pending Reminder', etc.)
   - `ReminderDate` (DATE)
   - `SendStatus` (VARCHAR, e.g., 'Sent', 'Not Sent', etc.)
