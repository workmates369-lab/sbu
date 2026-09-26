# SpazaExpress – Online Spaza Shop Ordering System

## 1. Project Overview

SpazaExpress is a Java-based Online Spaza Shop Ordering System designed to digitise the ordering and management processes of a local South African spaza shop.

The system allows customers to browse products, search for items, add products to a shopping cart, place orders and track their order status. Administrators can manage products, categories, stock, customers and orders.

---

## 2. System Users

### Customer
- Register and log in
- Browse products
- Search for products
- View prices and availability
- Add products to a shopping cart
- Place orders
- View order history
- Track order status

### Administrator
- Log in to the admin dashboard
- Add, edit and delete products
- Manage product categories
- Update stock quantities
- View customers
- View and process orders
- Update order statuses
- View basic sales information


## 3. System Design Flow

             DigiTuck Online Ordering System 
                           |
              +------------+------------+
              |                         |
       student/customers             Vendors 
              |                         |
       Register / Login              Login
              |                         |
              v                         v
       Product Catalogue          vendor's Dashboard
              |                         |
       Search Products       +---------+---------+
              |               |         |         |
              v             Products   Stock    Orders
        Shopping Cart          |         |         |
              |                +---------+---------+
              v                         |
           Checkout                     |
              |                         |
              v                         |
        Place Order                     |
              |                         |
              +------------+------------+
                           |
                           v
                    MySQL Database
                           |
                           v
                    Order Processing
                           |
                           v
                  Update Order Status
                           |
                           v
                  Customer Tracking

---

## 4. System Architecture

The project follows an MVC + DAO architecture.

+------------------------------+
|       Java User Interface    |
|          JavaFX              |
+--------------+---------------+
               |
               v
+------------------------------+
|          Controllers         |
+--------------+---------------+
               |
               v
+------------------------------+
|       Business Services      |
+--------------+---------------+
               |
               v
+------------------------------+
|             DAO              |
|     Database Operations      |
+--------------+---------------+
               |
               v
+------------------------------+
|          JDBC Layer          |
+--------------+---------------+
               |
               v
+------------------------------+
|          MySQL DB            |
+------------------------------+

---

## 5. Main System Modules

### Customer Module
Handles registration, authentication, product browsing, search, shopping cart, checkout, orders and order tracking.

### Administrator Module
Handles products, categories, inventory, customers, orders and sales information.

### Authentication Module
Controls login, logout and role-based access.

### Product Module
Manages product names, descriptions, categories, prices, stock and availability.

### Order Module
Creates orders, stores order items and manages order statuses.

### Inventory Module
Tracks available product quantities and product availability.

### Database Module
Provides JDBC connectivity between the Java application and MySQL.

---

## 6. Database Design

### Users

users
----------------
user_id PK
name
email
phone
password
role
```

### Categories

categories
----------------
category_id PK
category_name

### Products

products
----------------
product_id PK
category_id FK
product_name
description
price
stock_quantity
availability

### Orders

orders
----------------
order_id PK
user_id FK
order_date
total_amount
status
```

### Order Items
order_items
----------------
order_item_id PK
order_id FK
product_id FK
quantity
unit_price
subtotal
```

### Relationships

USER 1 -------- MANY ORDERS

ORDER 1 ------- MANY ORDER_ITEMS

PRODUCT 1 ----- MANY ORDER_ITEMS

CATEGORY 1 ---- MANY PRODUCTS
```

---

## 7. Recommended Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Java |
| User Interface | JavaFX |
| Database | MySQL |
| Database Connectivity | JDBC |
| Architecture | MVC + DAO |
| Build Tool | Maven |
| IDE | IntelliJ IDEA / NetBeans |
| Version Control | Git / GitHub |

---

## 8. Recommended Project Structure

SpazaExpress/
|
+-- README.md
+-- .gitignore
+-- pom.xml
|
+-- docs/
|   +-- system-design.md
|   +-- database-design.md
|
+-- src/
    +-- main/
        +-- java/
        |   +-- za/co/spazaexpress/
        |       +-- Main.java
        |       |
        |       +-- model/
        |       |   +-- User.java
        |       |   +-- Product.java
        |       |   +-- Category.java
        |       |   +-- Order.java
        |       |   +-- OrderItem.java
        |       |
        |       +-- dao/
        |       |   +-- UserDAO.java
        |       |   +-- ProductDAO.java
        |       |   +-- CategoryDAO.java
        |       |   +-- OrderDAO.java
        |       |   +-- OrderItemDAO.java
        |       |
        |       +-- service/
        |       |   +-- AuthenticationService.java
        |       |   +-- ProductService.java
        |       |   +-- OrderService.java
        |       |
        |       +-- controller/
        |       |   +-- LoginController.java
        |       |   +-- ProductController.java
        |       |   +-- CartController.java
        |       |   +-- OrderController.java
        |       |
        |       +-- database/
        |           +-- DatabaseConnection.java
        |
        +-- resources/
            +-- images/
            +-- css/
```

---

## 9. Order Processing Flow

Customer Login
      |
      v
Browse Products
      |
      v
Select Product
      |
      v
Add to Cart
      |
      v
Review Cart
      |
      v
Checkout
      |
      v
Place Order
      |
      v
Validate Stock
      |
      +---- Stock unavailable ----> Show Error
      |
      v
Create Order
      |
      v
Reduce Stock
      |
      v
Save Order in MySQL
      |
      v
Admin Receives Order
      |
      v
Confirm Order
      |
      v
Prepare Order
      |
      v
Mark Ready
      |
      v
Complete Order
      |
      v
Customer Views Completed Order
```

---

## 10. Development Phases

1. Create GitHub repository and Maven project.
2. Configure MySQL database and JDBC.
3. Create database tables.
4. Implement Java model classes.
5. Implement registration and login.
6. Implement customer product catalogue.
7. Implement shopping cart.
8. Implement checkout and order creation.
9. Implement administrator dashboard.
10. Implement product and category management.
11. Implement inventory management.
12. Implement order management.
13. Implement order tracking and history.
14. Add sales information and reports.
15. Test the complete system.
16. Document and prepare the final project.

---

## 11. Future Enhancements

Possible future versions can include:

- Online payment integration
- Delivery management
- Multiple spaza shops
- Customer reviews and ratings
- Promotional discounts
- SMS/email notifications
- Mobile application
- Web-based version
- Sales analytics dashboard

---

## 12. Project Goal

The goal of SpazaExpress is to provide a practical digital ordering solution that reduces dependence on manual ordering methods, improves order accuracy, simplifies inventory management and provides customers with a convenient way to purchase everyday products from a local spaza shop.
