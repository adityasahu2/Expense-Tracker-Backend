# Expense Tracker Application

This is a personal expense tracker application built with Spring Boot for the backend and HTML/CSS/JavaScript for the frontend.

## Project Structure

```
expense-tracker/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── example/
│       │           └── expensetracker/
│       │               ├── config/
│       │               ├── controller/
│       │               ├── exception/
│       │               ├── model/
│       │               ├── repository/
│       │               ├── service/
│       │               ├── DataInitializer.java
│       │               └── ExpenseTrackerApplication.java
│       └── resources/
│           ├── static/
│           │   ├── index.html
│           │   ├── styles.css
│           │   └── app.js
│           ├── application.properties
│           └── schema.sql
├── pom.xml
└── README.md
```

## Features

- Create, read, update and delete expenses
- Filter expenses by category
- Responsive design for mobile and desktop
- Form validation
- Visual categorization of expenses
- Total expense calculation

## Prerequisites

- Java 21
- Maven
- MySQL (running on port 3306)

## Setup Instructions

### Database Setup

1. Make sure MySQL is running on port 3306
2. The application will automatically create a database named `expense_tracker` if it doesn't exist

### Backend Setup

1. Clone the repository
2. Navigate to the project directory
3. Update `application.properties` if needed (database credentials)
4. Build the project:
   ```
   mvn clean install
   ```
5. Run the Spring Boot application:
   ```
   mvn spring-boot:run
   ```
   or
   ```
   java -jar target/expense-tracker-0.0.1-SNAPSHOT.jar
   ```

### Frontend Setup

1. Place the `index.html`, `styles.css`, and `app.js` files in the `src/main/resources/static` directory of your Spring Boot project
2. The frontend will be automatically served when the Spring Boot application is running
3. Access the application at http://localhost:8080

## API Endpoints

| Method | URL                        | Description                |
|--------|----------------------------|----------------------------|
| GET    | /api/expenses              | Get all expenses           |
| GET    | /api/expenses/{id}         | Get expense by ID          |
| GET    | /api/expenses/category/{category} | Get expenses by category |
| POST   | /api/expenses              | Create a new expense       |
| PUT    | /api/expenses/{id}         | Update an expense          |
| DELETE | /api/expenses/{id}         | Delete an expense          |

## Frontend-Backend Integration

The frontend uses JavaScript fetch API to communicate with the backend REST endpoints. The communication is handled by the app.js file, which defines functions to create, read, update, and delete expenses.

### CORS Configuration

The application includes CORS configuration to allow frontend-backend communication when running on different domains or ports. This is set up in `WebConfig.java`.

## Sample Data

The application includes a data initializer (`DataInitializer.java`) that populates the database with sample expenses when the application starts, if the database is empty.

## Technology Stack

- Backend:
  - Spring Boot 3.4.5
  - Spring JDBC
  - MySQL
  - Java 21
  - Lombok
  
- Frontend:
  - HTML5
  - CSS3
  - JavaScript (ES6+)
  - Font Awesome for icons

## Troubleshooting

- If you encounter database connection issues, check the MySQL credentials in `application.properties`
- Make sure port 8080 is not in use by another application
- If CORS errors occur, verify the CORS configuration in `WebConfig.java`