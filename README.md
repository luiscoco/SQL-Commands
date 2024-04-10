# Learn SQL commands with sample queries

## 1. Prerequisites

### 1.1. Pull and run SQL Server Docker image 

```
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=Luiscoco123456" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2022-latest
```

### 1.2. Install SQL Server Management Studio (SSMS)


### 1.3. Create the database, tables and data for executing the samples

Let's create a simple database scenario to illustrate SQL commands and queries. We will work with a database for a bookstore, which includes tables for Books, Authors, and Sales

I'll provide you with the SQL commands to create the database, tables, and insert some data. Then, I'll show you a few queries to interact with this data

**Step 1: Create Database**

First, let's create a database called Bookstore.

```sql
CREATE DATABASE Bookstore;
```

**Step 2: Create Tables**

Now, we will create three tables: Authors, Books, and Sales.

**Authors Table**

```sql
CREATE TABLE Authors (
    AuthorID INT PRIMARY KEY,
    Name VARCHAR(100),
    Country VARCHAR(50)
);
```

**Books Table**

```sql
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(100),
    AuthorID INT,
    Price DECIMAL(10,2),
    YearPublished INT, -- Changed from YEAR to INT
    FOREIGN KEY (AuthorID) REFERENCES Authors(AuthorID)
);
```

**Sales Table**

```sql
CREATE TABLE Sales (
    SaleID INT PRIMARY KEY,
    BookID INT,
    QuantitySold INT,
    SaleDate DATE,
    FOREIGN KEY (BookID) REFERENCES Books(BookID)
);
```
**Insert Data**

Let's insert some sample data into these tables.

**Insert Authors**

```sql
INSERT INTO Authors (AuthorID, Name, Country) VALUES
(1, 'George Orwell', 'United Kingdom'),
(2, 'J.K. Rowling', 'United Kingdom'),
(3, 'Harper Lee', 'United States');
```

**Insert Books**

```sql
INSERT INTO Books (BookID, Title, AuthorID, Price, YearPublished) VALUES
(1, '1984', 1, 8.99, '1949'),
(2, 'Animal Farm', 1, 6.99, '1945'),
(3, 'Harry Potter and the Sorcerer''s Stone', 2, 10.99, '1997'),
(4, 'To Kill a Mockingbird', 3, 7.99, '1960');
```

**Insert Sales**

```sql
INSERT INTO Sales (SaleID, BookID, QuantitySold, SaleDate) VALUES
(1, 1, 500, '2023-01-01'),
(2, 2, 300, '2023-02-01'),
(3, 3, 800, '2023-03-01'),
(4, 4, 400, '2023-04-01');
```

We can see the tables relation in the following diagram

![image](https://github.com/luiscoco/SQL-Commands/assets/32194879/f8821aad-e698-42ea-9ce7-1796aa586c4b)


## 2. SQL commands samples


### 2.1. SQL JOINS

![image](https://github.com/luiscoco/SQL-Commands/assets/32194879/640d6a46-3603-4cd4-baf9-6287ab0e42f7)

