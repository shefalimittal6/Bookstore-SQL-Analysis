# 📚 Online Bookstore Customer & Sales Analysis (SQL)

## 📌 Project Overview
This project analyzes customer purchasing behavior, sales performance, and inventory trends for an online bookstore using SQL.

The objective is to simulate a real-world e-commerce system and extract actionable insights that can help improve revenue, customer retention, and inventory management.



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
- A small percentage of books contribute to a large share of total revenue  
- Repeat customers place multiple orders, indicating higher lifetime value  
- Certain genres consistently perform better in terms of sales volume  
- Some books show low stock despite frequent orders, highlighting potential inventory issues  
- High-spending customers contribute significantly to overall revenue

## 📈 Business Impact
- Helps identify high-performing books and genres to improve sales strategy  
- Enables customer segmentation for targeted marketing  
- Highlights inventory gaps to prevent stock shortages  
- Supports data-driven decision making in e-commerce operations  

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

## 🚀 Advanced Analysis

### Monthly Revenue Trend
SELECT DATE_TRUNC('month', order_date) AS month,
SUM(total_amount) AS monthly_revenue
FROM orders
GROUP BY month
ORDER BY month;

### Top Customers by Spending 
SELECT c.name, SUM(o.total_amount) AS total_spent
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
GROUP BY c.name
ORDER BY total_spent DESC;


👩‍💻 Author

Shefali Mittal
