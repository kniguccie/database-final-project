# Inventory Tracking Database

## Overview
This repository contains the SQL schema for an **Inventory Tracking** database designed to manage products, suppliers, orders, and order details. The database supports a relational structure with appropriate constraints and relationships to ensure data integrity.

### Use Case
The database is intended for tracking inventory in a business setting, including managing product stock, supplier information, and order processing.

## Database Schema
### Tables
1. **Suppliers**
   - `SupplierID` (PK): Unique identifier for each supplier.
   - `SupplierName`: Name of the supplier.
   - `ContactEmail`: Email for supplier contact.
   - `Phone`: Phone number of the supplier.

2. **Products**
   - `ProductID` (PK): Unique identifier for each product.
   - `ProductName`: Name of the product.
   - `UnitPrice`: Price per unit of the product.
   - `StockQuantity`: Current stock level.

3. **Orders**
   - `OrderID` (PK): Unique identifier for each order.
   - `ProductID` (FK): References the product being ordered.
   - `SupplierID` (FK): References the supplier.
   - `OrderDate`: Date the order was placed.
   - `Quantity`: Number of units ordered.

4. **OrderDetails**
   - `OrderDetailID` (PK): Unique identifier for each order detail entry.
   - `OrderID` (FK): References the order.
   - `ProductID` (FK): References the product.
   - `UnitPrice`: Price per unit at the time of order.
   - `Quantity`: Number of units in this order detail.

### Relationships
- **One-to-Many**: One Supplier to Many Orders.
- **One-to-Many**: One Product to Many Orders.
- **Many-to-Many**: Orders to Products (resolved via OrderDetails table).

### Constraints
- Primary Keys (PK) ensure uniqueness.
- Foreign Keys (FK) maintain referential integrity.
- NOT NULL constraints ensure essential fields are populated.

## Setup Instructions
1. **Install a Database Management System (DBMS)**:
   - Use MySQL, PostgreSQL, or any SQL-compatible DBMS.
