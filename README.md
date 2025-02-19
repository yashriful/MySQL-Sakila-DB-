🎬 Sakila Database Project

A MySQL Sample Database for a Video Rental Store

📌 Introduction
The Sakila Database is a sample MySQL database representing a DVD rental store. It contains data about films, actors, customers, staff, payments, and rentals. This project explores various SQL queries to analyze business operations.

📁 Database Schema
Below is a visual representation of the Sakila Database Schema:


(This schema illustrates table relationships in Sakila DB.)

🔍 Key SQL Queries & Screenshots
1️⃣ Retrieve the Top 5 Customers by Rental Count
sql
Copy
Edit
SELECT c.customer_id, CONCAT(c.first_name, ' ', c.last_name) AS Customer, 
       COUNT(r.rental_id) AS Total_Rentals
FROM customer c
JOIN rental r ON c.customer_id = r.customer_id
GROUP BY c.customer_id
ORDER BY Total_Rentals DESC
LIMIT 5;
Output:

(Displays the top 5 customers who rented the most DVDs.)

2️⃣ Find the Most Popular Movies
sql
Copy
Edit
SELECT f.film_id, f.title, COUNT(r.rental_id) AS Rental_Count
FROM film f
JOIN inventory i ON f.film_id = i.film_id
JOIN rental r ON i.inventory_id = r.inventory_id
GROUP BY f.film_id, f.title
ORDER BY Rental_Count DESC
LIMIT 5;
Output:

(Lists the top 5 most rented movies.)

3️⃣ Staff Performance: Who Processed the Most Rentals?
sql
Copy
Edit
SELECT s.staff_id, CONCAT(s.first_name, ' ', s.last_name) AS Staff, 
       COUNT(r.rental_id) AS Total_Rentals
FROM staff s
JOIN rental r ON s.staff_id = r.staff_id
GROUP BY s.staff_id
ORDER BY Total_Rentals DESC;
Output:

(Shows which staff members processed the most rentals.)

🛠️ How to Set Up the Sakila Database
1️⃣ Download & Install MySQL
2️⃣ Load the Sakila Database

bash
Copy
Edit
mysql -u root -p < sakila-schema.sql
mysql -u root -p < sakila-data.sql
3️⃣ Verify the Database

sql
Copy
Edit
SHOW DATABASES;
USE sakila;
SHOW TABLES;
📊 Future Improvements
✅ Implement views and stored procedures
✅ Create interactive dashboards
✅ Perform advanced data analysis using Python & SQL

📌 Conclusion
This project demonstrates SQL queries and database operations using MySQL’s Sakila Database. It's a great resource for learning database design, queries, and business analysis.

🔹 Built with MySQL 🔹
