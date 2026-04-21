# 📚 Online Bookstore Customer & Sales Analysis (SQL)

## 📌 Project Overview
This project focuses on analyzing customer behavior, sales performance, and inventory management for an online bookstore using SQL.

The goal is to simulate real-world e-commerce operations and extract meaningful insights from structured transactional data.



## 🗂️ Database Schema

The project is based on a relational database with three main tables:

### 📖 Books
- Book_ID (Primary Key)
- Title
- Author
- Genre
- Published_Year
- Price
- Stock

### 👤 Customers
- Customer_ID (Primary Key)
- Name
- Email
- Phone
- City
- Country

### 🛒 Orders
- Order_ID (Primary Key)
- Customer_ID (Foreign Key)
- Book_ID (Foreign Key)
- Order_Date
- Quantity
- Total_Amount

---

## 🔗 Entity Relationships
- Each order is linked to a specific customer and book
- Enables analysis of:
  - Customer purchasing behavior
  - Book sales performance
  - Inventory tracking

---

## 🛠️ Tools & Technologies
- SQL (PostgreSQL)
- Relational Database Design

---

## 🔍 Key SQL Concepts Used
- SELECT, WHERE, ORDER BY
- GROUP BY & Aggregations
- INNER JOIN, LEFT JOIN
- Subqueries
- HAVING clause
- Data filtering and sorting

---

## 📊 Key Business Questions Solved
- What are the top-selling books and genres?
- Which customers have placed the most orders?
- What is the total revenue generated?
- Which books have the lowest stock levels?
- Which customers spend the most?
- What is the total quantity of books sold by each author?

---

## 💡 Key Insights
- A small number of books contribute significantly to overall revenue  
- Certain genres dominate total sales volume  
- Repeat customers generate higher order frequency  
- Some books show low stock despite consistent demand (inventory gap)  
- High-value customers contribute a major portion of revenue  

---

## 📁 Project Structure
- `Books.csv` → Book dataset  
- `Customers.csv` → Customer dataset  
- `Orders.csv` → Orders dataset  
- `queries.sql` → All SQL queries and analysis  

---

## 🚀 How to Run

1. Create Database
CREATE DATABASE OnlineBookstore;

2. Create Tables
Run the table creation queries provided in the project.

3. Import Data
Use the COPY command to import CSV files:

COPY Books(Book_ID, Title, Author, Genre, Published_Year, Price)
FROM 'path_to_books.csv'
CSV HEADER;

COPY Customers(Customer_ID, Name, Email, Phone, City, Country)
FROM 'path_to_customers.csv'
CSV HEADER;

COPY Orders(Order_ID, Customer_ID, Book_ID, Order_Date, Quantity, Total_Amount)
FROM 'path_to_orders.csv'
CSV HEADER;

4. Run Queries
📈 Sample Analysis Performed
Total revenue calculation using SUM(total_amount)
Genre-wise sales distribution
Customer order frequency analysis
Identification of most frequently ordered books
Inventory analysis (stock vs orders)



👩‍💻 Author
Shefali Mittal
