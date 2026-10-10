# NEXUS - Student Developer Community Platform

> **Connect. Learn. Collaborate. Build.**  
> *"Your next breakthrough starts with your people."*

NEXUS is a full-stack student developer community platform built with **Java 17**, **Spring Boot 3**, and **MySQL**. It enables students to discover compatible builders, exchange skills, showcase projects, join study circles, and track student activities and academic achievements.

---

## 🚀 Key Features

- **Personal Student Dashboard**:
  - Live activity statistics (Total activities, projects, skills, circles, comments, achievements).
  - Activity trend analytics over time (Weekly, Monthly, All-time).
  - Chronological real-time activity stream.
  - Academic achievements hub (certifications, coursework, honors).
- **Builder Discovery & Skill Matching**:
  - Compatibility scoring algorithm based on complementary skills and interests.
  - Search and filter students by skills and interests.
- **Project Showcase & Collaboration**:
  - Publish side projects with GitHub repository links and live demos.
  - Send and manage collaboration requests.
  - Project likes, comments, and discussions.
- **Study Circles**:
  - Topic-focused learning circles with discussion threads.
- **Secure Authentication**:
  - Session-based authentication with Spring Security 6 and BCrypt password hashing.

---

## 🛠️ Technology Stack

- **Backend**: Java 17, Spring Boot 3.3.0, Spring Data JPA, Hibernate, Spring Security 6
- **Database**: MySQL 8.x
- **Build Tool**: Maven Wrapper (`mvnw` / `mvnw.cmd`)
- **Frontend**: HTML5, CSS3, Vanilla JavaScript (Fetch API) — located in `src/main/resources/static/`
- **Testing**: JUnit 5, Mockito

---

## ⚙️ Prerequisites

1. **Java JDK 17** or higher
2. **MySQL Server** (running locally on default port 3306)
3. **Git**

---

## 📦 How to Run Locally

### 1. Configure the Database
Create the MySQL database:
```sql
CREATE DATABASE IF NOT EXISTS nexus_db;
```

Check `src/main/resources/application.properties` to ensure your MySQL username and password match. You can also configure them via environment variables:
```properties
spring.datasource.url=${SPRING_DATASOURCE_URL:jdbc:mysql://localhost:3306/nexus_db?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME:root}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD:your_mysql_password}
```

### 2. Build and Run
Open your terminal in the project root directory and run:

**On Windows:**
```powershell
.\mvnw.cmd spring-boot:run
```

**On Linux / macOS:**
```bash
./mvnw spring-boot:run
```

### 3. Access the Application
Open your browser and navigate to:
```
http://localhost:8080/
```

**Pre-seeded Demo Accounts:**
- **Aarav Sharma (Admin):** `aarav@nexus.dev` / `password123`
- **Rohan Deshmukh:** `rohan@nexus.dev` / `password123`
- **Ananya Patel:** `ananya@nexus.dev` / `password123`
- **Priya Kulkarni:** `priya@nexus.dev` / `password123`

You can also register any new student account directly at `/register.html` using your own email and password!

---

## 🧪 Running Tests

To run the automated test suite:
```powershell
.\mvnw.cmd test
```

---

## 📂 Project Structure

```
nexus/
├── .gitignore                      # Git ignore rules for build and IDE files
├── README.md                       # Project documentation
├── pom.xml                         # Maven dependencies & build configuration
├── mvnw / mvnw.cmd                 # Maven wrapper scripts
├── .mvn/                           # Maven wrapper binaries
└── src/
    ├── main/
    │   ├── java/com/nexus/         # Java Spring Boot backend
    │   │   ├── config/             # Security & seed data initializers
    │   │   ├── controller/         # REST API Controllers
    │   │   ├── dto/                # Data Transfer Objects
    │   │   ├── entity/             # JPA Entities
    │   │   ├── exception/          # Global error handling
    │   │   ├── repository/         # Spring Data JPA Repositories
    │   │   └── service/            # Business logic & algorithms
    │   └── resources/
    │       ├── application.properties
    │       └── static/             # Frontend single-page views, CSS & JS
    │           ├── index.html
    │           ├── dashboard.html
    │           ├── discover.html
    │           ├── projects.html
    │           ├── circles.html
    │           ├── login.html
    │           ├── register.html
    │           ├── favicon.ico
    │           ├── css/
    │           └── js/
    └── test/                       # Unit and integration tests
```
