# 🛒 E-Commerce Web Application

This is a simple **E-Commerce Web Application** built using **Java (JSP, Servlets, JDBC, MySQL)**.  
It allows users to register, log in, view products, add them to cart, and place orders.

---

## 🚀 Features
- 👤 User Authentication (Register, Login, Logout)
- 🛍️ View Products (from MySQL database)
- 🔍 Search Products by name/description
- 🛒 Shopping Cart (add, update, remove products)
- ✅ Checkout & Place Orders
- 📦 My Orders (view past orders)
- 🎨 Modern UI with **Bootstrap 5** + custom CSS

---

## 🛠️ Tech Stack
- **Frontend:** JSP, HTML5, CSS3, Bootstrap 5
- **Backend:** Java Servlets (JDK 8+)
- **Database:** MySQL 8
- **Server:** Apache Tomcat 8.5
- **IDE:** NetBeans

---

## 📂 Project Structure
ECommerceApp/
│── nbproject/ # NetBeans config files
│── src/ # Java source files (Servlets, DAO, Models)
│ └── com.ecommerce/
│ ├── dao/ # Database access classes
│ ├── model/ # POJOs (User, Product, CartItem, Order)
│ ├── servlets/ # Servlets (Login, Register, Cart, Checkout, etc.)
│ └── utils/ # DBUtil (database connection helper)
│── web/ # JSP pages, assets
│ ├── assets/
│ │ ├── css/ # Custom styles
│ │ ├── js/ # Scripts
│ │ └── images/ # Images (if any)
│ ├── index.jsp # Homepage
│ ├── login.jsp # Login page
│ ├── register.jsp # Registration page
│ ├── products.jsp # Products listing
│ ├── cart.jsp # Cart page
│ ├── checkout.jsp # Checkout page
│ ├── my_orders.jsp # My Orders page
│ ├── header.jsp # Navbar
│ └── footer.jsp # Footer
└── README.md # Project documentation

yaml

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/ECommerceApp.git
2️⃣ Import into NetBeans
Open NetBeans → File → Open Project → Select ECommerceApp.

3️⃣ Setup Database
Run this SQL in MySQL:

CREATE DATABASE ecommerce;
USE ecommerce;

CREATE TABLE users (
   id INT AUTO_INCREMENT PRIMARY KEY,
   username VARCHAR(50),
   email VARCHAR(100) UNIQUE,
   password VARCHAR(255),
   role VARCHAR(20) DEFAULT 'user'
);

CREATE TABLE products (
   id INT AUTO_INCREMENT PRIMARY KEY,
   name VARCHAR(100) NOT NULL,
   description TEXT,
   price DECIMAL(10,2) NOT NULL,
   created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE orders (
   id INT AUTO_INCREMENT PRIMARY KEY,
   user_email VARCHAR(100),
   order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE order_items (
   id INT AUTO_INCREMENT PRIMARY KEY,
   order_id INT,
   product_id INT,
   quantity INT,
   price DECIMAL(10,2),
   FOREIGN KEY (order_id) REFERENCES orders(id)
);
4️⃣ Configure DB Connection
Update DBUtil.java with your MySQL username & password:

private static final String URL = "jdbc:mysql://localhost:3306/ecommerce";
private static final String USER = "root";  
private static final String PASS = "yourpassword";
5️⃣ Deploy
Start Apache Tomcat 8.5 in NetBeans.

Run the project.

👉 Open in browser:
http://localhost:8080/ECommerceApp

👨‍💻 Author
Bikash (GIET University, B.Tech CSE)

📜 License
This project is for educational purposes only.

---
