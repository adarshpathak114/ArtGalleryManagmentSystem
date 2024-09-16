# ArtGalleryManagmentSystem
Art Gallery Management system is database project with implementation of triggers and stored procedures



# Art Gallery Management System

## Overview
This project implements a comprehensive **Art Gallery Management System** using advanced concepts of Database Management Systems (DBMS). It includes functionalities to manage galleries, exhibitions, artists, customers, orders, and artworks. The project showcases the use of **SQL triggers**, **stored procedures**, **functions**, and **views** to enhance the efficiency and interactivity of the system.

## Key Features
- **User Creation & Grant Management**: A dedicated user is created (`Gallry_Admin`) with required privileges for database operations.
- **Tables**: Multiple tables are created for entities such as `Customer`, `Gallery`, `Exhibition`, `Artist`, `Artwork`, and `Orders`.
- **Stored Procedures**: Used to insert data into the database, ensuring organized and efficient data entry.
- **Triggers**: Added to automate tasks such as date formatting, enforcing upper case for certain fields, and ensuring data integrity.
- **Functions**: Implemented to calculate important metrics such as the number of days an exhibition is open or the time taken for an order to be delivered.
- **Views**: Created to retrieve insightful data including unsold artwork, top customers, and the highest sales by month.

## Database Schema
The schema includes the following tables:
1. **Customer Directory**
2. **Gallery**
3. **Customer**
4. **Exhibition**
5. **Artist**
6. **Artwork**
7. **Orders**

### Dependencies
- Oracle DBMS or any database that supports PL/SQL.
- Basic SQL knowledge to execute queries and procedures.

## Setup Instructions
### Step 1: Create User and Grant Privileges
Run the following block to create a user and grant the necessary privileges:
```sql
create user Gallry_Admin identified by Artgallerymgt123#;
GRANT CONNECT, RESOURCE, CREATE VIEW, CREATE TRIGGER TO Gallry_Admin;
ALTER USER Gallry_Admin quota 100M on Users;
```

### Step 2: Create Tables and Insert Data
You can find SQL commands to create the tables and procedures, as well as insert sample data, in the repository under the `tables.sql` file. Each table is equipped with corresponding stored procedures for easy insertion.

### Step 3: Run Triggers and Procedures
To ensure automatic date formatting and enforce data integrity, triggers are created for the `Customer`, `Gallery`, `Exhibition`, and `Orders` tables. Triggers will automatically format dates and convert text fields to uppercase.

### Step 4: Retrieve Data with Views
Several views are created for easy data retrieval:
1. **Total Orders Per Customer**: Number of orders placed by each customer.
2. **Artwork Not in Exhibition**: Lists all artworks that are not part of any exhibitions.
3. **Artwork Never Sold**: Displays artworks that have never been sold.
4. **Artist Not in Exhibition**: Artists whose works have not been included in any exhibitions.
5. **Highest Valuation Country**: Shows the countries with the highest total artwork valuations.
6. **Top 3 Customers by Spending**: Displays the top 3 customers based on their total spending.
7. **Highest Sale per Month**: Displays the highest sale in each month.

## Key Procedures and Functions
### Stored Procedures
- **Add Customer, Gallery, Exhibition, Artist, Artwork, and Orders**: Each entity has its own stored procedure to add records.
  
### Functions
- **Event Opened for Days**: Calculates how many days an exhibition is open.
- **Days to Get Shipped**: Determines how many days it took for an order to be delivered.

## Sample Queries
```sql
-- View customer directory
SELECT * FROM Customer_Directory;

-- Find total orders per customer
SELECT * FROM Total_Orders_Per_Customer;

-- View artworks not in any exhibition
SELECT * FROM Artwork_Not_In_Exhibition;
```

## Future Enhancements
- **Additional Views**: Create more complex views for sales trends and customer analysis.
- **Security**: Implement role-based access control for different types of users.
- **UI/UX Interface**: Develop a frontend to interact with the database.

## Conclusion
This Art Gallery Management System is an efficient and scalable solution to manage gallery operations, exhibitions, and customer interactions. The system leverages advanced DBMS features, making it both practical and easy to manage.
