# 🛒 E-Commerce Platform

A full-stack e-commerce web application built with **Django REST Framework and React.js**, allowing users to browse products, manage their shopping cart, place orders, and make secure online payments.

The project demonstrates real-world full-stack development using REST APIs, JWT authentication, PostgreSQL, payment integration, and cloud-based media management.

---

## 🚀 Features

### 👤 User Authentication
- User registration and login
- JWT-based authentication
- Protected API endpoints
- User profile management
- Secure password handling

### 🛍️ Product Management
- Browse products
- Product details
- Product categories
- Search and filtering
- Product image management
- Stock availability

### 🛒 Shopping Cart
- Add products to cart
- Update product quantities
- Remove products
- Automatic total calculation
- Persistent cart management

### 📦 Order Management
- Create orders from cart
- View order history
- View order details
- Track order status
- Manage customer orders

### 💳 Payment Integration
- Stripe payment integration
- Secure checkout
- Payment status verification
- Order creation after successful payment

### 🔐 Security
- JWT authentication
- Role-based access control
- Protected REST APIs
- Environment-based configuration
- Secure credential management

---

## 🛠️ Tech Stack

### Frontend
- React.js
- JavaScript
- HTML5
- CSS3
- Axios

### Backend
- Python
- Django
- Django REST Framework
- REST APIs

### Database
- PostgreSQL

### Authentication & Payments
- JWT
- Stripe

### Media & DevOps
- Cloudinary
- Docker
- Git
- GitHub
- Postman

---

## 🏗️ System Architecture

```text
                    USER
                      │
                      ▼
             ┌─────────────────┐
             │    React.js     │
             │    Frontend     │
             └────────┬────────┘
                      │
                  REST APIs
                      │
                      ▼
             ┌─────────────────┐
             │     Django      │
             │      DRF        │
             └───────┬─────────┘
                     │
          ┌──────────┼──────────┐
          │          │          │
          ▼          ▼          ▼
     PostgreSQL    Stripe   Cloudinary
      Database     Payment     Media
```

---

## 📂 Project Structure

```text
ecommerce-platform/
│
├── backend/
│   ├── manage.py
│   ├── requirements.txt
│   ├── config/
│   ├── users/
│   ├── products/
│   ├── cart/
│   ├── orders/
│   └── payments/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── context/
│   │   └── App.jsx
│   ├── public/
│   └── package.json
│
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ecommerce-platform.git

cd ecommerce-platform
```

---

## 🔧 Backend Setup

Create a Python virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🗄️ PostgreSQL Configuration

Create a PostgreSQL database:

```sql
CREATE DATABASE ecommerce_db;
```

Create a `.env` file:

```env
SECRET_KEY=your_secret_key
DEBUG=True

DB_NAME=ecommerce_db
DB_USER=postgres
DB_PASSWORD=your_postgresql_password
DB_HOST=localhost
DB_PORT=5432

STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

---

## 🔄 Database Migration

Run Django migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

Create an admin account:

```bash
python manage.py createsuperuser
```

Start the Django server:

```bash
python manage.py runserver
```

Backend:

```text
http://127.0.0.1:8000/
```

---

## 💻 Frontend Setup

Open another terminal:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Frontend:

```text
http://localhost:5173/
```

---

## 🔌 API Endpoints

### Authentication

```text
POST   /api/auth/register/
POST   /api/auth/login/
POST   /api/auth/refresh/
GET    /api/auth/profile/
```

### Products

```text
GET    /api/products/
GET    /api/products/<id>/
POST   /api/products/
PUT    /api/products/<id>/
DELETE /api/products/<id>/
```

### Cart

```text
GET    /api/cart/
POST   /api/cart/add/
PUT    /api/cart/update/
DELETE /api/cart/remove/
```

### Orders

```text
GET    /api/orders/
POST   /api/orders/
GET    /api/orders/<id>/
```

### Payments

```text
POST   /api/payments/create/
POST   /api/payments/confirm/
```

> Update the endpoint paths according to your actual Django URL configuration.

---

## 🔄 Application Workflow

```text
                 USER
                   │
                   ▼
             Register/Login
                   │
                   ▼
             Browse Products
                   │
                   ▼
             Product Details
                   │
                   ▼
              Add to Cart
                   │
                   ▼
              View Cart
                   │
                   ▼
               Checkout
                   │
                   ▼
             Stripe Payment
                   │
              ┌────┴────┐
              │         │
           Success    Failed
              │         │
              ▼         ▼
        Create Order   Retry
              │
              ▼
          Order History
```

---

## 🧠 Key Technical Concepts

### REST API Architecture

The React frontend communicates with Django through RESTful APIs.

```text
React.js
   │
   │ HTTP Request
   ▼
Django REST Framework
   │
   ▼
Business Logic
   │
   ▼
PostgreSQL
```

### JWT Authentication

```text
Login
  ↓
Credential Verification
  ↓
JWT Token Generated
  ↓
Token Sent With Requests
  ↓
Protected API Access
```

### Shopping Cart

The cart maintains the relationship between users and products:

```text
User
 │
 └── Cart
      │
      ├── Product A
      ├── Product B
      └── Product C
```

### Order Processing

```text
Cart
 ↓
Checkout
 ↓
Stripe Payment
 ↓
Payment Verification
 ↓
Create Order
 ↓
Update Stock
 ↓
Clear Cart
```

---

## 🧪 Testing

Run Django tests:

```bash
python manage.py test
```

API endpoints can be tested using **Postman**.

---

## 🐳 Docker

Build and start the application:

```bash
docker-compose up --build
```

Stop the containers:

```bash
docker-compose down
```
---

## 🔮 Future Improvements

- ⭐ Product reviews and ratings
- 🔍 Advanced product search
- 🏷️ Coupon and discount system
- 📦 Advanced inventory management
- 📧 Email order notifications
- 🔔 Real-time order updates
- ❤️ Wishlist functionality
- 📊 Sales analytics dashboard
- ☁️ AWS deployment
- 🔄 GitHub Actions CI/CD
- 📱 Improved mobile responsiveness

---

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- Full-stack web development
- Python and Django
- Django REST Framework
- React.js
- REST API development
- JWT authentication
- PostgreSQL database management
- Database relationships
- Shopping cart implementation
- Order processing
- Payment gateway integration
- Cloud media storage
- Docker containerization
- Git and GitHub
- API testing

---

## 👨‍💻 Author

**Aryan Saroj**

---

## ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.
