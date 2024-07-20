# my-database

The database consists of multiple tables representing different entities.

## Tables

- **Customers**: Stores customer information.
- **Product**: Stores product information.
- **Orders**: Stores order details.

## Creating Tables

Here are the SQL commands to create the tables:

```sql

CREATE TABLE Customer (
    Customer_id VARCHAR(10) PRIMARY KEY,
    Customer_Name VARCHAR(50),
    Customer_Tel VARCHAR(15)
);

CREATE TABLE Product (
    Product_id VARCHAR(10) PRIMARY KEY,
    Product_Name VARCHAR(50),
    Category VARCHAR(50),
    Price DECIMAL(10, 2)
);

CREATE TABLE Orders (
    Customer_id VARCHAR(10),
    Product_id VARCHAR(10),
    OrderDate DATE,
    Quantity INT,
    Total_amount DECIMAL(10, 2),
    PRIMARY KEY (Customer_id, Product_id),
    FOREIGN KEY (Customer_id) REFERENCES Customer(Customer_id),
    FOREIGN KEY (Product_id) REFERENCES Product(Product_id)
);


## Data Insertion

The following SQL commands insert sample data into the tables:

```sql

-- Insert data into Customer table
INSERT INTO Customer (Customer_id, Customer_Name, Customer_Tel) VALUES
('C01', 'ALI', '71321009'),
('C02', 'ASMA', '77345823');

-- Insert data into Product table
INSERT INTO Product (Product_id, Product_Name, Category, Price) VALUES
('P01', 'Samsung Galaxy S20', 'Smartphone', 3299),
('P02', 'ASUS Notebook', 'PC', 4599);

-- Insert data into Orders table
INSERT INTO Orders (Customer_id, Product_id, OrderDate, Quantity, Total_amount) VALUES
('C01', 'P02', NULL, 2, 9198),
('C02', 'P01', '2020-05-28', 1, 3299);
