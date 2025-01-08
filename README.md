Here is the `README.md` file for your **Real Estate Management System** project, including setup instructions:

---

# Real Estate Management System (REMS)

## Overview

The **Real Estate Management System (REMS)** is a comprehensive database solution designed for managing properties, transactions, agents, and customers. The system tracks property listings, handles customer inquiries, records transactions, and manages agent commissions. The solution also includes triggers and stored procedures to automate tasks and ensure smooth operation.

## Features

1. **Customer Management**:
   - Add and manage customers with details like name, email, phone, and address.
   
2. **Agent Management**:
   - Add and manage agents with details like name, email, phone, and commission rate.
   
3. **Property Listings**:
   - Register properties for sale or rent with detailed information such as location, size, price, and type (Residential, Commercial, Industrial, Land).

4. **Transactions**:
   - Record property transactions, linking customers, agents, and properties. Track transaction status such as 'Completed', 'Pending', or 'Cancelled'.

5. **Inquiries**:
   - Manage customer inquiries related to specific properties, with status tracking (New, In Progress, Closed).

6. **Agent Commission Calculation**:
   - Automatically update agent commission rates based on completed transactions.

7. **Triggers & Procedures**:
   - Automate common tasks such as updating commission rates, tracking inquiry status changes, and retrieving transaction history for customers.

## Database Schema

### Tables

- **Customers**:
  - `CustomerID` (Primary Key)
  - `Name`
  - `Email` (Unique)
  - `Phone`
  - `Address`
  - `CreatedDate`

- **Agents**:
  - `AgentID` (Primary Key)
  - `Name`
  - `Email`
  - `Phone`
  - `CommissionRate`

- **Properties**:
  - `PropertyID` (Primary Key)
  - `Name`
  - `Location`
  - `Type` (Residential, Commercial, Industrial, Land)
  - `Size` (in square feet)
  - `Price`
  - `Description`
  - `AgentID` (Foreign Key referencing Agents)

- **Transactions**:
  - `TransactionID` (Primary Key)
  - `PropertyID` (Foreign Key referencing Properties)
  - `CustomerID` (Foreign Key referencing Customers)
  - `AgentID` (Foreign Key referencing Agents)
  - `TransactionDate`
  - `Amount`
  - `Status` (Pending, Completed, Cancelled)

- **Inquiries**:
  - `InquiryID` (Primary Key)
  - `CustomerID` (Foreign Key referencing Customers)
  - `PropertyID` (Foreign Key referencing Properties)
  - `InquiryDate`
  - `Status` (New, In Progress, Closed)
  - `Notes`

### Sequences

- **Ownership_Transfer_SEQ**: Used for generating unique Transfer_ID values.

### Stored Procedures

1. **Create_Customer**: Adds a new customer to the database.
2. **Create_Agent**: Adds a new agent to the database.
3. **Create_Property**: Adds a new property to the database.
4. **Create_Transaction**: Records a transaction for a property.
5. **Create_Inquiry**: Records a new customer inquiry.
6. **Update_Property_Price**: Updates the price of a property by a given percentage.

### Triggers

1. **UpdateCommissionRate**: Automatically updates agent commission rate after a completed transaction.
2. **TrackInquiryUpdates**: Logs changes in inquiry statuses (New, In Progress, Closed).
   
## Setup Instructions





1. **Clone the Repository**:
   - Clone the repository to your local machine using Git.
   
   ```bash
   git clone https://github.com/your-username/PL-SQL-project.git
   cd PL-SQL-project
   ```

