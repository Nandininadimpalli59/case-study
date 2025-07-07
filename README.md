# case-study

# Order Management System (Spring Boot)
A microservice-based Spring Boot application that manages product inventory and order processing in an e-commerce platform.

# Overview
This system replaces a monolithic Order Management System with a scalable microservice that:
- Places orders after checking inventory
- Updates order status (Pending → Shipped)
- Manages product inventory with race-condition handling
- Uses REST APIs, MySQL, and Spring Boot

# Technologies Used
- Java 17
- Spring Boot
- Spring Data JPA
- RESTful APIs
- Maven
- MySQL
- Lombok

# Git Instructions
git init
git remote add origin https://github.com/your-username/OrderManagementSystem.git
git add .
git commit -m "Order Management System Initial commit"
git branch main
git push -u origin main

# DDL Commands
CREATE TABLE product_inventory (
    product_id BIGINT PRIMARY KEY,
    product_name VARCHAR(100) NOT NULL,
    quantity INT NOT NULL
);

CREATE TABLE orders (
    order_id BIGINT PRIMARY KEY AUTO_INCREMENT,
    product_id BIGINT,
    quantity INT,
    status ENUM('PENDING', 'CONFIRMED', 'SHIPPED', 'CANCELLED')
);
