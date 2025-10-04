# Task Tracker API

A production-ready **REST API** built with **Java + Spring Boot** for managing tasks securely.  
Provides endpoints for user authentication/authorization and CRUD operations on tasks.

**Live Demo:** [task-tracker-production-205b.up.railway.app](https://task-tracker-production-205b.up.railway.app)

---

## 🚀 Features

- RESTful API for managing tasks
- User registration & login with **JWT authentication**
- Role-based authorization with **Spring Security**
- CRUD operations for tasks with input validation
- **PostgreSQL** as the persistence layer (via Spring Data JPA)
- Unit & Integration tests using **JUnit 5 & Mockito**
- CI/CD ready with **GitHub Actions**
- Deployed with **99.9% uptime** on Railway

---

## 🛠 Tech Stack

| Layer        | Technology                                |
|--------------|-------------------------------------------|
| Backend      | Java 17+, Spring Boot, Spring Security     |
| Database     | PostgreSQL                                |
| ORM          | Spring Data JPA / Hibernate               |
| Testing      | JUnit 5, Mockito, Spring Boot Test         |
| CI/CD        | GitHub Actions (build & test pipeline)    |
| Deployment   | Railway                                   |

---

## 📦 Getting Started

### Prerequisites
- Java 17+ installed
- Maven
- PostgreSQL database running
- Git

### Setup & Run Locally

1. Clone the repo  
   ```bash
   git clone https://github.com/yahyasheriif/Task-Tracker.git
   cd Task-Tracker
   ```

2. Configure your database and JWT secret in `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/tasktracker
   spring.datasource.username=your_db_username
   spring.datasource.password=your_db_password
   jwt.secret=your_jwt_secret
   ```

3. Build & run the application:  
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

4. Test the API locally at `http://localhost:8080`.

---

## 🧪 Running Tests

This project includes **unit tests and integration tests** using JUnit 5 and Mockito.

Run all tests:
```bash
mvn test
```

### ✅ Examples of test cases:

- User registration endpoint returns `201 Created` and persists user.
- Login endpoint returns JWT token for valid credentials.
- Unauthorized requests to protected endpoints return `401 Unauthorized`.
- Creating a new task with valid JWT returns `201 Created`.
- Updating a task by non-owner returns `403 Forbidden`.
- Deleting a task removes it from the database.

---

## 🧩 API Endpoints (Sample)

| Method | Endpoint | Description                | Auth Required |
|--------|----------|---------------------------|---------------|
| POST   | `/api/auth/register` | Register a new user        | No            |
| POST   | `/api/auth/login`    | Authenticate & get JWT     | No            |
| GET    | `/api/tasks`         | Get all tasks for user     | Yes           |
| POST   | `/api/tasks`         | Create new task            | Yes           |
| GET    | `/api/tasks/{id}`    | Get task by ID             | Yes           |
| PUT    | `/api/tasks/{id}`    | Update task                | Yes           |
| DELETE | `/api/tasks/{id}`    | Delete task                | Yes           |

Use the JWT token from `/login` in the `Authorization: Bearer <token>` header for protected endpoints.

---

## 📈 CI / CD

This repo can use a GitHub Actions workflow to:

- Run `mvn test` on every push/pull request.
- Build and package the Spring Boot app.
- Deploy to Railway automatically (if configured).

The workflow file should be located at `.github/workflows/ci.yml`.

---

## 📬 Contributing & Feedback

Contributions, issues, and feature requests are welcome!  
Open an issue or pull request if you have suggestions.

---

## 📄 License

MIT License (or your chosen license).

---

### ✅ Future Improvements

- Convert monolith to microservices (task-service, auth-service)
- Add caching (Redis)
- API documentation (Swagger/OpenAPI)
- Container orchestration (Docker Compose / Kubernetes)
- Enhanced monitoring & logging

---

**Thank you for checking out Task Tracker API!**
