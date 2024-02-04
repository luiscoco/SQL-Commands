# SQL Commands explanation with samples

## 1. Prerequisites

### 1.1. Pull and run SQL Server Docker image 


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
    YearPublished YEAR,
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


## 2. SQL commands samples


### 2.1. 
