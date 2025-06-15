# BookStore DBMS Project

## Overview

This project is a comprehensive Bookstore Management System designed to showcase advanced skills in **Database Design**, **MySQL**, and **DBMS concepts**. The focus is on robust schema design, normalization, complex SQL queries, and real-world data modeling for a multi-role bookstore platform.

---

## 🏗️ Core DBMS Features

- **Relational Database Design:**  
  - Well-structured schema for Customers, Vendors, Books, Orders, Warehouses, Delivery Agents, and Admins.
- **Normalization:**  
  - All tables normalized to 3NF for data integrity and efficiency.
- **ER Diagram & Documentation:**  
  - Complete ER diagram and schema documentation included.
- **Advanced SQL Queries:**  
  - Complex queries for analytics, reporting, and business logic (see `queries.sql`).
- **Stored Procedures & Triggers:**  
  - Demonstrates automation and enforcement of business rules at the DB level.
- **Role-Based Access:**  
  - Secure, role-specific data access and operations.
- **Transaction Management:**  
  - Ensures atomicity and consistency for critical operations (orders, inventory updates, etc.).

---

## 🛠️ Tech Stack

- **Database:**  
  - MySQL (primary), SQLite (for prototyping)
- **SQL Tools:**  
  - SQL scripts for schema, data population, and queries
- **Supporting Tools:**  
  - ERD tools (draw.io, dbdiagram.io), SQL Workbench

---

## 📂 Key Files & Structure

```
BookStore_DBMS/
│
├── Entry_BookStore.sql       # MySQL schema: tables, constraints, triggers, procedures
├── queries.sql               # Sample and advanced SQL queries
├── 02ER_Diagram.pdf          # Entity-Relationship Diagram
├── userguide.md              # DB usage and query documentation
└── README.md                 # Project overview (this file)
```

---

## 📊 DBMS Concepts Demonstrated

- **Schema Design:**  
  - Realistic modeling of bookstore operations, multi-role access, inventory, and logistics.
- **Normalization:**  
  - All tables in 3NF, with clear primary/foreign keys and constraints.
- **Complex Queries:**  
  - Joins, aggregations, subqueries, window functions, and analytics.
- **Stored Procedures & Triggers:**  
  - Automated stock updates, order processing, and audit logging.
- **Transaction Control:**  
  - COMMIT/ROLLBACK for safe, consistent updates.
- **Security:**  
  - Role-based privileges and data access.

---

## 📖 Example SQL Snippets

```sql
-- Example: Get top 5 best-selling books
SELECT b.title, SUM(o.quantity) AS total_sold
FROM Books b
JOIN Orders o ON b.book_id = o.book_id
GROUP BY b.book_id
ORDER BY total_sold DESC
LIMIT 5;
```

```sql
-- Example: Trigger to update inventory after order
DELIMITER $$
CREATE TRIGGER after_order_insert
AFTER INSERT ON Orders
FOR EACH ROW
BEGIN
  UPDATE Books
  SET stock = stock - NEW.quantity
  WHERE book_id = NEW.book_id;
END $$
DELIMITER ;
```

---

## 🏆 Key Strengths Demonstrated

- **Strong MySQL & SQL Skills:**  
  - Designed, implemented, and optimized a complex relational schema.
- **DBMS Expertise:**  
  - Deep understanding of normalization, constraints, transactions, and business logic in SQL.
- **Real-World Modeling:**  
  - Accurately modeled a multi-role, multi-entity business scenario.
- **Documentation:**  
  - Clear ER diagrams, schema docs, and query explanations.

---

## 📄 Documentation

- [ER Diagram](BookStore_DBMS/02ER_Diagram.pdf)
- [Schema & Triggers](BookStore_DBMS/Entry_BookStore.sql)
- [Sample Queries](BookStore_DBMS/queries.sql)
- [User Guide](BookStore_DBMS/userguide.md)

---

## 🏁 Getting Started

1. Import `Entry_BookStore.sql` into your MySQL server.
2. Run queries from `queries.sql` to test features and analytics.
3. Review the ER diagram and documentation for schema understanding.

---

**Thank you for reviewing my DBMS project! I am eager to bring my database expertise to your