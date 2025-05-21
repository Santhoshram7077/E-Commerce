# E-Commerce

This is a Java-based web application of an e-commerce website; customers can browse items, manage carts and orders, and update delivery information; admin can manage products/orders.

## Technologies

**Front-end**: React.js, HTML, CSS

**Back-end**: Java, SpringBoot, JPA(Hibernate), MySQL

## Features

### Users
- Sign up for a new user account.
- Change user information (e.g., delivery address/email).
- Search items by name and category; browse items and their detail page.
- Add items to Cart; Submit Order by selecting items on Cart.
- Manage orders: keep track of orders' details, including delivery status, and take action on orders.

### Admin
- Register for a new user account.
- Manage goods, including creating a new item, revising an existing item, or deleting an item.
- Manage orders, including tracking order status and taking delivery actions.

# Project Structure

## Frontend 
 
```
frontend/                      # React frontend
├── public/                   # Static files (index.html, images)
├── src/
│   ├── components/          # Reusable UI components
│   ├── pages/               # Main pages (Home, Product, Cart, etc.)
│   ├── api/                 # API calls 
│   ├── hooks/               # Custom hooks
│   ├── contexts/            # Global state (React Context)
│   ├── routes/              # Routing setup
│   ├── services/            # Business logic (e.g., auth)
│   ├── styles/              # Global styles
│   ├── App.js               # Root component
│   └── index.js             # Entry point
├── .env
└── package.json
```

## Backend
 
```
backend/                      # Spring Boot backend
├── src/
│   ├── main/
│   │   ├── java/com/ecommerce/
│   │   │   ├── EcommerceApplication.java
│   │   │   ├── config/         # App & security configs
│   │   │   ├── controller/     # API endpoints
│   │   │   ├── model/          # JPA entities
│   │   │   ├── repository/     # Data access
│   │   │   ├── service/        # Business logic
│   │   │   └── dto/            # Request/response objects
│   │   └── resources/
│   │       └── application.properties
├── test/                      # Unit tests
└── pom.xml
```

