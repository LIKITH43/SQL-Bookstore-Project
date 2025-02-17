# SQL-Bookstore-Project

## Overview

This project is built using PostgreSQL and analyzes data from three CSV files: `orders_1.csv`, `customers_1.csv`, and `books.csv`. It provides insights into customer purchases, book details, and order trends by utilizing SQL queries for data extraction and analysis.

## Dataset Description

The project includes the following datasets:

- **[`orders_1.csv`](./Orders_1.csv)**: Contains order-related information such as order ID, customer ID, book ID, quantity, order date, and price.
- **[`customers_1.csv`](./Customers_1.csv)**: Stores customer details, including customer ID, name, email, and location.
- **[`books.csv`](./Books.csv)**: Lists book details like book ID, title, author, genre, and price.

## Features

- Data import into PostgreSQL tables
- Querying and filtering data using SQL
- Generating insights into customer behavior and purchasing trends
- Using SQL joins and aggregations for deeper analysis

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/your-repo-name.git
   ```
2. Install PostgreSQL and set up a database.
3. Load the CSV files into PostgreSQL tables using the `COPY` command or `pgAdmin`.

## Usage

1. Create and connect to the PostgreSQL database:
   ```sql
   CREATE DATABASE book_store;
   ```
2. Create tables and import data:
   ```sql
   CREATE TABLE orders_1 (
       order_id SERIAL PRIMARY KEY,
       customer_id INT,
       book_id INT,
       quantity INT,
       order_date DATE,
       price DECIMAL(10,2)
   );
   
   CREATE TABLE customers_1 (
       customer_id SERIAL PRIMARY KEY,
       name VARCHAR(255),
       email VARCHAR(255),
       location VARCHAR(255)
   );
   
   CREATE TABLE books (
       book_id SERIAL PRIMARY KEY,
       title VARCHAR(255),
       author VARCHAR(255),
       genre VARCHAR(100),
       price DECIMAL(10,2)
   );
   ```
3. Load the data into the tables:
   ```sql
   COPY orders FROM '/path/to/orders_1.csv' DELIMITER ',' CSV HEADER;
   COPY customers FROM '/path/to/customers_1.csv' DELIMITER ',' CSV HEADER;
   COPY books FROM '/path/to/books.csv' DELIMITER ',' CSV HEADER;
   ```
4. Run SQL queries to analyze data, for example:
   ```sql
   SELECT customers.name, books.title, orders.quantity, orders.price 
   FROM orders
   JOIN customers ON orders.customer_id = customers.customer_id
   JOIN books ON orders.book_id = books.book_id;
   ```

## Dependencies

- PostgreSQL
- pgAdmin (optional for managing the database)

## Contributing

Feel free to fork this repository, make enhancements, and submit a pull request.

## For more data insights connect with me 
[LinkedIn](https://www.linkedin.com/in/likith-kanumuri-5b0529287/)




