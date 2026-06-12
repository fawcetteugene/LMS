# Library Management System (LMS)

A full-stack web application for managing library operations with separate **Admin** and **Customer** portals. Built with Node.js, Express, EJS, and MySQL.

## Overview

This Library Management System lets librarians manage books, customers, and book lending workflows, while registered customers can browse the catalog, request books, view borrowed titles, and manage their profiles. Session-based authentication protects all routes except login and signup.

## 💰 Support the Project

If you find this project valuable, please consider supporting its continued development.

[![Donate-Paystack](https://img.shields.io/badge/Donate-Paystack-00BFFF?style=for-the-badge&logo=paystack&logoColor=white)](https://paystack.shop/pay/fawcettdonations)

**Contact:**

- WhatsApp: +254794689731
- LinkedIn: [fawcetteugene](https://www.linkedin.com/in/fawcetteugene/)

## Features

### Admin Portal (`/admin`)

- Dashboard with user, book, and borrowing statistics
- Manage books: add, edit, delete, search, and issue to customers
- Manage customers: add, edit, delete, and view profiles
- View issued books and process book requests
- Admin profile management and password change

### Customer Portal (`/customer`)

- Personal dashboard with borrowing summary
- Browse available books and request titles
- View currently borrowed books and borrow history
- Profile editing and password change

### Authentication

- User signup and login
- Session-based access control
- Separate admin and customer sessions

## Tech Stack

| Layer | Technology |
|-------|------------|
| Runtime | Node.js |
| Web framework | Express.js |
| Templating | EJS |
| Database | MySQL / MariaDB |
| Session management | express-session |
| Validation | async-validator-2 |
| HTTP logging | morgan |
| Dev server | nodemon |

## Project Structure

```
LMS/
├── app.js                      # Application entry point
├── controllers/                # Route handlers (admin, customer, auth)
├── models/                     # Database models and MySQL config
├── views/                      # EJS templates (admin & customer)
├── css/                        # Stylesheets
├── images/                     # Static images
├── validation_rules/           # Form validation rules
└── library_management_system.sql  # Database schema and seed data
```

## Prerequisites

- [Node.js](https://nodejs.org/) (v10+ recommended)
- [MySQL](https://www.mysql.com/) or MariaDB
- npm (included with Node.js)

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/fawcetteugene/LMS.git
   cd LMS
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Set up the database**

   Create a MySQL database and import the schema:

   ```bash
   mysql -u root -p < library_management_system.sql
   ```

   Or import `library_management_system.sql` via phpMyAdmin or your preferred MySQL client.

4. **Configure database connection**

   Update `models/config.js` with your MySQL credentials:

   ```javascript
   var connection = mysql.createConnection({
     host     : 'localhost',
     user     : 'root',
     password : 'your_password',
     database : 'library_management_system'
   });
   ```

## Running the Application

Start the development server:

```bash
npm start
```

The app runs on **http://localhost:3000** by default.

- Login: `/login`
- Signup: `/signup`
- Admin area: `/admin/home` (after admin login)
- Customer area: `/customer/home` (after customer login)

## Database Schema

The SQL dump includes tables for:

- `users` — admin and customer accounts
- `books` — library catalog and issue status
- `books_request` — customer book requests

## License

ISC (see `package.json`)

## Author

Fawcett Simiyu ([@fawcetteugene](https://github.com/fawcetteugene))
