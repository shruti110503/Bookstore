# 📚 Bookstore 

A **Java-based Bookstore Application** that allows users to **browse books, add them to a cart, and purchase them.**  
Built using **JavaFX** for the GUI and **MySQL/PostgreSQL** as the database.

---

## 📌 Features
✅ **Browse Books** – View available books with details like title, author, and price.  
✅ **Add to Cart** – Users can select books and add them to a shopping cart.  
✅ **Purchase Books** – Complete transactions securely.  
✅ **User Authentication** – Register and log in to track orders.  
✅ **Database Integration** – Stores book inventory and purchase history.  

---

## 🚀 Installation Guide

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/bookstore.git
cd bookstore
```

### 2️⃣ Set Up the Database
Open MySQL/PostgreSQL and create a new database:
```sh
CREATE DATABASE bookstore;
```
Create required tables:
``` sh
CREATE TABLE books (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author VARCHAR(255) NOT NULL,
    price DECIMAL(10,2) NOT NULL
);

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);

CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(id),
    book_id INT REFERENCES books(id),
    quantity INT NOT NULL,
    total_price DECIMAL(10,2) NOT NULL
);
```
### 3️⃣ Configure Database Connection
Modify database.properties (or relevant config file):

```sh
db.url=jdbc:mysql://localhost:3306/bookstore
db.user=root
db.password=yourpassword
```

### 4️⃣ Run the Application
Compile and run:
```sh
javac -d bin src/*.java
java -cp bin Main
```
OR 

if using Maven:
```sh
mvn clean install
mvn javafx:run
```
🎉 The Bookstore App will now launch!

### 🔗 Contributing
Want to improve this project? Follow these steps:

Fork the repository

Create a new branch (git checkout -b feature-name)

Commit your changes (git commit -m "Added a new feature")

Push to the branch (git push origin feature-name)

Open a Pull Request

### 📄 License
This project is open-source and available under the MIT License.

### 👩‍💻 Author

Shruti

📧 Contact: [shrutishukla297@gmail.com]
