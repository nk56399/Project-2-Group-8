# MIST 4610 Project 2 Group 8
# Team Name:
Group 8
# Team Members:
1. Neha Kanakamedala [@nk56399](https://github.com/nk56399/Project-2-Group-8)
2. Mason Lee [@mlee1921](https://github.com/mlee1921/MIST4610-Project-2-Group-8)
3. Vivienne Lin [@vivi0404]
4. Daniel Mok [@dlm90284-ai]
5. Austin Middlebrooks [@Amiddlebrooks]
   
# Scenario Description:

Our team is designing a Bookstore Management Database System that supports operations such as tracking books, authors, customer activity, employee management, orders, payments, inventory levels, and book reviews. The system stores detailed information about each book, including its authors, genres, publisher, inventory, and sales performance. Customers can place orders for books, submit reviews, and make payments, all of which are recorded in the database. The database also supports storing employee records, supervisor relationships, and revenue information. The system helps identify best-selling authors, monitor unpaid orders, review customer engagement, identify top-rated books, evaluate publisher performance, and detect low inventory risks. Overall, this relational database focuses on library and bookstore operations while supporting strategic decision-making and customer engagement tracking.

# Data Model

This database supports storage of book information like titles, authors, publishers, genres, and publication years. It has customer and order information like customer details, orders, order items, payments. It has inventory stock, pricing, order processing by employees, and manager structures. There is data like book reviews, ratings, and total reviews. Lastly there are genre classifications.
This database does not support full textbook content like PDFs, employee payroll, customer addresses, payment methods like credit cards, shipment tracking, or marketing and loyalty programs.

<img width="974" height="925" alt="project2datamodel" src="https://github.com/user-attachments/assets/342c3a66-01bb-4ab0-a798-82f5fa1d20bd" />

- Author:
The author entity stores details about authors such as their name and rating. Each author can write many books, forming a one-to-many relationship with the book entity.

- Book:
The book entity contains information like title, publication year, pricing, sales, revenue, and foreign keys linking to its author and publisher. Books can belong to multiple genres and can appear in many orders.

- Publisher:
The publisher entity contains contact details and identifiers for publishers. Each publisher can produce many books.

- Customer:
The customer entity stores information for customers including name, email, and age. Customers can place many orders and write reviews.

- Orders:
The orders entity stores a single customer order, including date, total amount, and the employee who processed the order. Each order may contain multiple books through orders_item.

- Orders_Item:
This is an associative entity that records each book purchased in each order, including quantity and price paid per book.

- Payments:
The payments entity records transactions linked to an order and customer. Each payment is linked to one order, forming a one-to-one relationship between Orders and Payment.

- Reviews:
The reviews entity stores customer reviews for books including rating, review date, average rating, and total reviews.

- Inventory:
The inventory entity tracks the quantity in stock for each book, item price, and total inventory value. Book and Inventory have a one-to-many relationship.

- Genre:
The genre entity has book genres. Genres can have parent-child hierarchical relationships. 

- Book_Has_Genre:
An associative entity linking books and genres to support the many-to-many relationship between them.

- Employee:
Employees who process orders. It contains details like employee first name, last name, and job title. There is a one-to-many recursive relationship (Manager–Supervisor) that allows employees to report to other employees.

# Data Dictionary:

### Author
<img width="1496" height="294" alt="image" src="https://github.com/user-attachments/assets/8fe82762-f64a-45d5-9c90-276d4cf0a1af" />

### Book
<img width="1540" height="486" alt="image" src="https://github.com/user-attachments/assets/9f8d3c40-637e-4554-8b86-a9709f80cdd9" />

### Publisher
<img width="1392" height="290" alt="image" src="https://github.com/user-attachments/assets/fd16562f-db56-4633-bc81-8e8966b5630b" />

### Customer
<img width="1554" height="400" alt="image" src="https://github.com/user-attachments/assets/930f3c07-8b5b-4608-b1c8-df6bd37bb6e9" />

### Orders
<img width="1676" height="442" alt="image" src="https://github.com/user-attachments/assets/6f8203e1-6bf8-40ba-8bc5-5c1314848092" />

### Orders_Item
<img width="1254" height="346" alt="image" src="https://github.com/user-attachments/assets/8538cd1e-5dcf-4b5a-9fa7-fd6f70b9b612" />

### Payments
<img width="1580" height="390" alt="image" src="https://github.com/user-attachments/assets/91c5dd7f-e7aa-4bd0-8abe-607d1f7bfdac" />

### Reviews
<img width="1492" height="440" alt="image" src="https://github.com/user-attachments/assets/2376563f-a26b-495c-b2f5-22036feea43f" />

### Inventory
<img width="1504" height="340" alt="image" src="https://github.com/user-attachments/assets/3bdb491f-2a43-4629-8299-521a333e5cab" />

### Genre
<img width="1602" height="296" alt="image" src="https://github.com/user-attachments/assets/811464e7-1e8e-4853-afbb-7e4fdad393c7" />

### Book_Has_Genre
<img width="1184" height="194" alt="image" src="https://github.com/user-attachments/assets/7ee3a1b1-0faf-460c-8787-4e551615c333" />

### Employee
<img width="1488" height="340" alt="image" src="https://github.com/user-attachments/assets/162910fb-8654-4ae0-8c35-b9fc245ba54b" />

# Queries:

<img width="1181" height="496" alt="image" src="https://github.com/user-attachments/assets/b6077c97-378f-48ca-9292-feed9e3d8364" />

### Query 1
Which books are currently low in inventory and how many of them are left? 

<img width="1952" height="1125" alt="image" src="https://github.com/user-attachments/assets/8003ace6-03d7-493b-9602-d1d2e3cf32c2" />

Query 1 allows managers to see which books are currently at risk of running out by identifying all book titles as low stock. By isolating the books with low inventory levels, managers can quickly determine which books need to be reordered. Sorting the results in descending order of quantity remaining shows which books should be a priority in restocking.  

Managerial Justification: Helps identify which books are low in inventory and which books need to be restocked. 

### Query 2
Can you gather a full list of all customers and orders? 

<img width="1797" height="1176" alt="image" src="https://github.com/user-attachments/assets/d281d6ef-08f0-4685-8a9d-04c4f32d825c" />

Query 2 allows manager to view a complete history of each customer’s orders including the details of their payments and the employee involved in processing the order. By combining customers and orders into one table, managers are able to see which customers have placed orders or have placed an order and haven’t paid yet. This query makes it easier for managers to track customer purchasing behavior and easily access full customer order histories. 

Managerial Justification: Helps managers view each customer’s order and payment history. 

### Query 3
What are the top 5 highest average rated books? 

<img width="1010" height="824" alt="image" src="https://github.com/user-attachments/assets/ecccee43-80ed-40f5-aeb5-9c0e2d01ccdc" />

Query 3 allows managers to identify which books are the best based on customer reviews by selecting only books with an average rating of 4.5 or higher. By joining author, book, and reviews, the query shows which authors are producing the highest rated books. Limiting the results to the top five and ordering them by rating makes it easy for managers to showcase their highest quality books.  

Managerial Justification: Helps managers identify the highest-rated books and their authors so they can prioritize featuring and promoting these books. 

### Query 4
Who does each employee report to and what is each employee’s level in the organization? 

<img width="1642" height="1148" alt="image" src="https://github.com/user-attachments/assets/242c22b8-9585-4b24-9550-c14e11bfbdf8" />

Query 4 allows managers to understand the organizational hierarchy by labeling each employee’s job level based on who they report to. Using the case statement, managers are able to categorize the level and see how each employee fits into the company structure. Sorting by job level makes it easy to view the hierarchy from top to bottom. 

Managerial Justification: Helps managers with a clear view of the entire organization and helps them understand reporting relationships. 

### Query 5
Which book genre generates the most revenue? 

<img width="928" height="1070" alt="image" src="https://github.com/user-attachments/assets/b519be2a-a72b-49a4-88e4-cbfdb5e07ff5" />

Query 5 allows managers to identify which book genre generates the most revenue by summing the publisher revenue for all books within each genre. By joining genre, book_has_genre, and book tables, it provides a complete view of revenue contributions across genres. Using the group by with rollup allows managers to see the overall total revenue that is being generated.   

Managerial Justification: Helps managers determine which book genres are the most profitable supporting the decisions on inventory and strategic investment.

# Database Information:

Name of the Database: cs_mhl67797 or cs_jam37624

# Tableau Visualizations
<img width="2134" height="642" alt="image" src="https://github.com/user-attachments/assets/31e9522f-5dfd-4445-a717-579d35afd0bb" />
<img width="2132" height="600" alt="image" src="https://github.com/user-attachments/assets/6f088d96-cab3-4d77-b83e-532db479fbdb" />
<img width="2132" height="1290" alt="image" src="https://github.com/user-attachments/assets/1010f0b1-8ec6-452c-b68a-13434f604b61" />

### Top 10 Selling Authors:

- Purpose: This chart shows the top ten authors who generate the highest total sales.
- Relevance: Helps managers identify which authors consistently bring revenue, and deserve space and priority in the online bookstore.

### Revenue by Publisher:

- Purpose: This chart shows which publishers contribute the most financially.
- Relevance: Helps managers evaluate publisher performance, plan partnerships strategically, and negotiate future contracts with the most popular publishers.

### Sales Trend by Publication Year:

- Purpose: This chart shows how book sale differ across publication years.
- Relevance: Reveals whether older or newer books drive revenue, and gives a clear view of demand, revenue, and trends.






