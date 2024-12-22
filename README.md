# 💳 Bank Analysis Using SQL 🏦

The Bank Analysis Using SQL project provides a robust relational database for banking operations. It highlights key aspects like customer profiling, transactional insights, loan management, and credit card analysis. SQL queries drive actionable insights for real-world banking solutions.
---

## 📂 Project Overview

This project implements a structured database system with the following tables:

### **📋 Tables and Column Details**
#### 1. Customers
- **Purpose**: Stores customer details.
- **Columns**:
  - `CustomerID` *(INT)*: Unique identifier.
  - `FirstName`, `LastName` *(VARCHAR)*: Name of the customer.
  - `DateOfBirth` *(DATE)*: Customer's birth date.
  - `Gender` *(ENUM)*: Male/Female.
  - `Email`, `PhoneNumber` *(VARCHAR)*: Contact details.
  - `Address`, `City`, `State`, `PostalCode`, `Country` *(VARCHAR)*: Location details.

#### 2. Branches
- **Purpose**: Captures information about bank branches.
- **Columns**:
  - `BranchID` *(INT)*: Unique branch ID.
  - `BranchName` *(VARCHAR)*: Branch name.
  - `Location` *(VARCHAR)*: Location of the branch.

#### 3. Accounts
- **Purpose**: Tracks account details.
- **Columns**:
  - `AccountID` *(INT)*: Unique account number.
  - `CustomerID` *(INT)*: Linked to `Customers`.
  - `BranchID` *(INT)*: Linked to `Branches`.
  - `Balance` *(DECIMAL)*: Current account balance.

#### 4. Transactions
- **Purpose**: Records all account transactions.
- **Columns**:
  - `TransactionID` *(INT)*: Unique identifier.
  - `AccountID` *(INT)*: Linked to `Accounts`.
  - `TransactionType` *(ENUM)*: Deposit/Withdrawal.
  - `Amount` *(DECIMAL)*: Transaction amount.
  - `TransactionDate` *(DATE)*: Date of transaction.

#### 5. Loans
- **Purpose**: Tracks customer loans.
- **Columns**:
  - `LoanID` *(INT)*: Unique loan ID.
  - `CustomerID` *(INT)*: Linked to `Customers`.
  - `LoanAmount` *(DECIMAL)*: Total loan amount.
  - `InterestRate` *(DECIMAL)*: Interest rate applied.
  - `LoanStatus` *(ENUM)*: Active/Closed.

#### 6. CreditCards
- **Purpose**: Tracks issued credit cards.
- **Columns**:
  - `CardID` *(INT)*: Unique card ID.
  - `CustomerID` *(INT)*: Linked to `Customers`.
  - `CardType` *(ENUM)*: Debit/Credit.
  - `ExpiryDate` *(DATE)*: Card expiration date.
  - `CreditLimit` *(DECIMAL)*: Card credit limit.

---

## 💻 How to Use

### 1️⃣ **Setup the Database**
Copy and execute the following SQL code to create the `BANK` database:
```sql
CREATE DATABASE BANK;
USE BANK;
```

### 2️⃣ **Create Tables**
Run the table creation scripts:
```sql
-- Example: Create the Customers table
CREATE TABLE Customers (
    CustomerID INT AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    DateOfBirth DATE,
    Gender ENUM('Male', 'Female'),
    Email VARCHAR(100),
    PhoneNumber VARCHAR(15),
    Address VARCHAR(255),
    City VARCHAR(50),
    State VARCHAR(50),
    PostalCode VARCHAR(10),
    Country VARCHAR(50)
);
```

### 3️⃣ **Insert Data**
Populate the tables with sample data:
```sql
INSERT INTO Customers (FirstName, LastName, DateOfBirth, Gender, Email, PhoneNumber, Address, City, State, PostalCode, Country)
VALUES 
('John', 'Doe', '1980-05-15', 'Male', 'john.doe@example.com', '555-1234', '123 Main St.', 'New York', 'NY', '10001', 'USA'),
('Jane', 'Smith', '1975-09-23', 'Female', 'jane.smith@example.com', '555-5678', '456 Oak St.', 'Los Angeles', 'CA', '90001', 'USA');
```

### 4️⃣ **Run Queries**
Perform insightful queries to analyze the data:
```sql
-- Example: Get all transactions over $1000
SELECT * 
FROM Transactions 
WHERE Amount > 1000;
```

---

## 🌟 Highlights

- **Efficiency**: Normalized tables ensure minimal redundancy.
- **Insights**: Advanced queries uncover key banking trends.
- **Performance**: Indexing boosts query execution speed.

---

## ❌ Challenges Encountered

- Balancing normalization and query complexity.
- Designing a schema to mimic real-world scenarios.
- Optimizing performance for large datasets.

---

## ✅ Results

- Streamlined banking operations with well-structured data.
- Simplified customer insights for targeted services.
- Enhanced understanding of branch and loan performance.

---

## 📌 Future Enhancements

- Integrate fraud detection algorithms.
- Automate interest calculations using stored procedures.
- Expand the schema to include investment products.

---

## ✨ Project Credits

- **Developer**: Ayush Tiwari  
- **Tools**: SQL Server/MySQL
