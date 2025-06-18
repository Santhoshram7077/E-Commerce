# Ecommerce Application

## Module Overview

The **Ecommerce Application** is a Spring Boot-based RESTful web service designed to manage products in an e-commerce platform. It provides endpoints for CRUD (Create, Read, Update, Delete) operations on products and integrates with a Eureka Discovery Service for service registration and discovery. The application uses MySQL as the database and follows a layered architecture for better maintainability and scalability.

## Architecture

The project follows a **layered architecture**:

* **Controller Layer:** Handles HTTP requests and responses.
* **Service Layer:** Contains business logic and interacts with the repository layer.
* **Repository Layer:** Manages database operations using Spring Data JPA.
* **Model Layer:** Defines the data structure for the application.

## Key Features:

* **Spring Boot:** Simplifies application setup and development.
* **Spring Data JPA:** Provides easy integration with the MySQL database.
* **Eureka Client:** Registers the service with a Eureka Discovery Server.
* **RESTful Endpoints:** Exposes endpoints for managing products.
* **Swagger/OpenAPI:** Provides API documentation using SpringDoc.

## Database Table

The application uses a single table, `Product`, in the MySQL database. The table structure is as follows:

| Column Name | Data Type | Description                   |
| :---------- | :-------- | :---------------------------- |
| `productId` | `BIGINT`  | Primary key, auto-generated.  |
| `name`      | `VARCHAR` | Name of the product.          |
| `description` | `VARCHAR` | Description of the product.   |
| `price`     | `DOUBLE`  | Price of the product.         |
| `category`  | `VARCHAR` | Category of the product.      |
| `imageURL`  | `VARCHAR` | URL of the product image.     |
| `quantity`  | `INT`     | Quantity available.           |

## Endpoints

The application exposes the following RESTful endpoints for managing products:

**Base URL:** `http://localhost:8087/api/products`

### Endpoints and Controllers

#### 1. Get All Products

* **Endpoint:** `GET /api/products`
* **Description:** Retrieves a list of all products.
* **Controller Method:** `ProductController.getAllProducts()`

#### 2. Get Product by ID

* **Endpoint:** `GET /api/products/{id}`
* **Description:** Retrieves a product by its ID.
* **Controller Method:** `ProductController.getProductById(Long id)`

#### 3. Create a New Product

* **Endpoint:** `POST /api/products`
* **Description:** Creates a new product.
* **Request Body:**

    ```json
    {
      "name": "Product Name",
      "description": "Product Description",
      "price": 100.0,
      "category": "Category Name",
      "imageURL": "[http://example.com/image.jpg](http://example.com/image.jpg)",
      "quantity": 10
    }
    ```
* **Controller Method:** `ProductController.createProduct(Product product)`

#### 4. Update an Existing Product

* **Endpoint:** `PUT /api/products/{id}`
* **Description:** Updates an existing product by its ID.
* **Request Body:**

    ```json
    {
      "name": "Updated Name",
      "description": "Updated Description",
      "price": 120.0,
      "category": "Updated Category",
      "imageURL": "[http://example.com/updated-image.jpg](http://example.com/updated-image.jpg)",
      "quantity": 15
    }
    ```
* **Controller Method:** `ProductController.updateProduct(Long id, Product product)`

#### 5. Delete a Product

* **Endpoint:** `DELETE /api/products/{id}`
* **Description:** Deletes a product by its ID.
* **Controller Method:** `ProductController.deleteProduct(Long id)`

##  File Structure

```
ecommerce/
├── src/
│   ├── main/
│       ├── java/
│       │   └── com.example.ecommerce/
│       │       ├── controller/       # REST Controllers
│       │       ├── model/            # Entity Classes
│       │       ├── repository/       # JPA Repositories
│       │       └── service/          # Business Logic
│       └── resources/
│           ├── application.properties # Configuration
│           ├── static/               # Static Resources
│           └── templates/            # Templates 
├── pom.xml                            # Maven Configuration
└── README.md
```
