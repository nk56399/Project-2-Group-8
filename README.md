# Project-2-Group-8
# Team Name:
Group 8
# Team Members:
1. Neha Kanakamedala @nk56399
2. Mason Lee @mlee1921
3. Vivienne Lin @vivi0404
4. Daniel Mok @dlm90284-ai
5. James Middlebrooks
# Scenario Description:

Our team is designing a Bookstore Management Database System that supports operations such as tracking books, authors, customer activity, employee management, orders, payments, inventory levels, and book reviews. The system stores detailed information about each book, including its authors, genres, publisher, inventory, and sales performance. Customers can place orders for books, submit reviews, and make payments, all of which are recorded in the database. The database also supports storing employee records, supervisor relationships, and revenue information. The system helps identify best-selling authors, monitor unpaid orders, review customer engagement, identify top-rated books, evaluate publisher performance, and detect low inventory risks. Overall, this relational database focuses on library and bookstore operations while supporting strategic decision-making and customer engagement tracking.

# Data Model

Author:
The author entity stores details about authors such as their name and rating. Each author can write many books, forming a one-to-many relationship with the book entity.

Book:
The book entity contains information like title, publication year, pricing, sales, revenue, and foreign keys linking to its author and publisher. Books can belong to multiple genres and can appear in many orders.

Publisher:
The publisher entity contains contact details and identifiers for publishers. Each publisher can produce many books.

Customer:
The customer entity stores information for customers including name, email, and age. Customers can place many orders and write reviews.

Orders:
The orders entity stores a single customer order, including date, total amount, and the employee who processed the order. Each order may contain multiple books through orders_item.

Orders_Item:
This is an associative entity that records each book purchased in each order, including quantity and price paid per book.

Payments:
The payments entity records transactions linked to an order and customer. Each payment is linked to one order, forming a one-to-one relationship between Orders and Payment.

Reviews:
The reviews entity stores customer reviews for books including rating, review date, average rating, and total reviews.

Inventory:
The inventory entity tracks the quantity in stock for each book, item price, and total inventory value. Book and Inventory have a one-to-many relationship.

Genre:
The genre entity has book genres. Genres can have parent-child hierarchical relationships. 

Book_Has_Genre:
An associative entity linking books and genres to support the many-to-many relationship between them.

Employee:
Employees who process orders. It contains details like employee first name, last name, and job title. There is a one-to-many recursive relationship (Manager–Supervisor) that allows employees to report to other employees.

This database supports storage of book information like titles, authors, publishers, genres, and publication years. It has customer and order information like customer details, orders, order items, payments. It has inventory stock, pricing, order processing by employees, and manager structures. There is data like book reviews, ratings, and total reviews. Lastly there are genre classifications.
This database does not support full textbook content like PDFs, employee payroll, customer addresses, payment methods like credit cards, shipment tracking, or marketing and loyalty programs.
 
<img width="974" height="905" alt="image" src="https://github.com/user-attachments/assets/7941d7a0-09eb-4923-af1f-4c861d92466a" />

# Data Dictionary:

### Author
<img width="1496" height="294" alt="image" src="https://github.com/user-attachments/assets/8fe82762-f64a-45d5-9c90-276d4cf0a1af" />

### Book
<img width="1540" height="486" alt="image" src="https://github.com/user-attachments/assets/9f8d3c40-637e-4554-8b86-a9709f80cdd9" />

### Publisher

### Customer

### Orders

### Orders_Item

### Payments

### Reviews

### Inventory

### Genre

### Book_Has_Genre

### Employee


# Queries:


# Database Information:

# Tableau Visualizations


Name of the Database: cs_mhl67797
