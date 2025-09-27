# Comprehensive Restaurant Management REST API

This project is a complete and comprehensive REST API for managing a restaurant, developed in **Go** using the **Gin** framework. The system covers all core restaurant operations, from user and menu management to order processing and invoicing.

## ✨ Features

-   **Complete Authentication System**: Secure user registration and login using **JWT** tokens and **Bcrypt** for password hashing.
-   **Full Restaurant Management (CRUD)**:
    -   Manage **Menus** (e.g., Lunch Menu, Dinner Menu).
    -   Manage **Food** items and assign them to menus.
    -   Manage restaurant **Tables**.
    -   Manage system **Users**.
-   **Transactional Order Processing**: The ability to create complex orders (with multiple items) using **database transactions** to ensure data integrity and atomicity. For the MongoDB version, this is achieved with **Multi-Document ACID Transactions**.
-   **Invoicing System**: Create and manage invoices linked to each order, with complete details.
-   **Layered Architecture**: Implemented following a clean architecture (Controller, Service, Repository) to separate concerns.
-   **Input Validation**: Uses the `validator` library to validate incoming request data and prevent errors.

## 🛠️ Tech Stack

-   **Language**: Go
-   **Web Framework**: Gin
-   **Database**: **MongoDB**
-   **Authentication**: JWT (JSON Web Tokens)
-   **Password Security**: Bcrypt
-   **Validation**: Go-playground/validator

## 📄 API Endpoints

Here is a list of the main API endpoints:

| Method | Path                               | Description                        | Auth Required |
| :----- | :--------------------------------- | :--------------------------------- | :-----------: |
| `POST` | `/users/signup`                    | Register a new user                |      No       |
| `POST` | `/users/login`                     | Log in a user and get a token      |      No       |
| `POST` | `/orders`                          | Create a new order with its items  |      Yes      |
| `GET`  | `/orders`                          | Get a list of all orders           |      Yes      |
| `GET`  | `/orders/:order_id`                | Get details of a specific order    |      Yes      |
| `POST` | `/foods`                           | Create a new food item             |      Yes      |
| `GET`  | `/foods`                           | Get a list of all food items       |      Yes      |
| `GET`  | `/invoices/:invoice_id`            | Get details of an invoice          |      Yes      |
| ...    | ...                                | ...                                |      ...      |

## 🚀 Getting Started

**Prerequisites:**
-   Go (version 1.18 or later)
-   Git

**Instructions:**
1.  Clone the repository:
    ```bash
    git clone https://github.com/AryaTabani/RestaurantManagement-MongoDB-.git
    cd RestaurantManagement-MongoDB
    ```
2.  Install dependencies:
    ```bash
    go mod tidy
    ```
3.  Set up environment variables (if any, e.g., for `JWT_SECRET`):
    ```bash
    export JWT_SECRET="your-secret-key"
    ```
4.  Run the application:
    ```bash
    go run main.go
    ```
    The service will run on the default port.
