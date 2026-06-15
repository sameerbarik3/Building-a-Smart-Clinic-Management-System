
# Smart Clinic Management System

## Overview

This is the capstone project for the **IBM Java Developer Certification Course on Coursera**. It is a robust healthcare application designed to streamline the management of doctors, patients, appointments, and prescriptions.

By leveraging a **Java/Spring Boot** backend and a relational database, this project showcases enterprise-ready skills in building scalable backend solutions, designing RESTful APIs, and integrating interactive front-end dashboards.

---

## Features

* **Java Backend:** Core business logic managed via Spring Boot, adhering to object-oriented programming (OOP) principles.
* **Database Integration:** Seamless CRUD operations (Create, Read, Update, Delete) utilizing JDBC/JPA with a relational database.
* **REST API Layer:** Exposes dedicated endpoints for tracking appointments, doctors, patients, and prescriptions.
* **Front-End Dashboards:** Fully responsive user interfaces built with HTML, CSS, and JavaScript tailored for three user roles: Admin, Doctor, and Patient.
* **Security & Auth:** Implements secure access control and authorization patterns (via `SecurityConfig.java` and `TokenService.java`).
* **Clean Architecture:** Modeled strictly around the Model-View-Controller (MVC) architectural pattern to ensure codebase scalability and separation of concerns.

---

## Technologies Used

* **Language:** Java (JDK 17+)
* **Framework:** Spring Boot (REST APIs, Spring Data JPA, Spring Security)
* **Build & Dependency Management:** Maven
* **Database:** Relational Database (MySQL / PostgreSQL / H2 Embedded)
* **Front-End:** HTML5, CSS3, JavaScript (ES6)
* **DevOps & CI/CD:** Docker (Containerization) & GitHub Actions

---

## Project Structure

```text
java-database-capstone/
├── .github/                    # GitHub workflows for CI/CD
│   └── workflows/              # Workflow files for compilation and linting
│       ├── compile-backend.yml
│       ├── lint-backend.yml
│       ├── lint-docker.yml
│       ├── lint-frontend.yml
├── app/                        # Main application directory
│   ├── src/                    # Source code
│   │   ├── main/               # Main application code
│   │   │   ├── java/           # Java source files
│   │   │   │   └── com/project/back_end/
│   │   │   │       ├── config/             # Security and application configuration
│   │   │   │       ├── controllers/        # REST API controllers
│   │   │   │       ├── DTO/                # Data Transfer Objects
│   │   │   │       ├── models/             # Database Entity models
│   │   │   │       ├── mvc/                # MVC View controllers
│   │   │   │       ├── repo/               # Spring Data JPA Repository interfaces
│   │   │   │       ├── services/           # Business logic service layer
│   │   │   │       └── BackEndApplication.java
│   │   │   └── resources/      # Static assets and templates
│   │   │       ├── static/     # UI assets (CSS, JS, Images)
│   │   │       ├── templates/  # Dynamic HTML dashboards
│   │   │       └── application.properties
│   │   └── test/               # Unit and Integration tests
│   │       └── java/com/project/back_end/
│   │           └── BackEndApplicationTests.java
│   ├── target/                 # Compiled build output
│   ├── Dockerfile              # Docker container configuration
│   ├── HELP-DB.md              # Database setup and help documentation
│   ├── mvnw                    # Maven wrapper script (Unix)
│   ├── mvnw.cmd                # Maven wrapper script (Windows)
│   └── pom.xml                 # Maven project configuration
├── curl-tests/                 # JSON Payloads for testing API endpoints
│   ├── appointments.json
│   ├── doctor-filter.json
│   ├── doctors.json
│   ├── patient-data.json
│   ├── patient-login.json
├── sql-tests/                  # Analytical SQL validation scripts
│   ├── GetDailyAppointmentReportByDoctor.sql
│   ├── GetDoctorWithMostPatientsByMonth.sql
│   ├── GetDoctorWithMostPatientsByYear.sql
│   ├── patients.sql
│   └── tables.sql
├── user_stories/               # Agile methodology documentation
│   ├── user_stories_admin.md
│   ├── user_stories_doctor.md
│   ├── user_stories_patient.md
│   └── user_stories_template.md
├── .gitignore                  # Git ignore rules
├── LICENSE                     # Project License file
├── README.md                   # Main documentation
├── schema-architecture.md      # Architectural design flow documentation
└── schema-design.md            # Entity-Relationship and Schema design

```

---

## Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/java-database-capstone.git
cd java-database-capstone

```

### 2. Install Dependencies

Make sure you have **Java JDK 17** (or higher) and **Maven** installed. Run the following command to download project dependencies:

* **Unix/macOS:** `./mvnw install`
* **Windows:** `mvnw.cmd install`

### 3. Configure the Database

1. Open `app/src/main/resources/application.properties`.
2. Update the connection string, username, and password to match your local relational database instance (e.g., MySQL or PostgreSQL):
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/clinic_db
spring.datasource.username=your_username
spring.datasource.password=your_password

```


3. Check `app/HELP-DB.md` for specific schema scripts and initialization steps.

### 4. Run the Application

Build and package the executable JAR file:

```bash
./mvnw clean package

```

Launch the Spring Boot server:

```bash
java -jar app/target/java-database-capstone.jar

```

The application will be accessible locally at `http://localhost:8080`.

---

## Testing

* **API Endpoints:** Use the configurations inside the `curl-tests/` directory with `curl` or import them into Postman to test backend endpoints (e.g., `GET /api/appointments`).
* **Database Queries:** Run the scripts inside `sql-tests/` directly in your database terminal or workbench to check aggregate reporting logic.

### Running with Docker

If you prefer running the application inside a containerized environment:

```bash
# Build the Docker Image
docker build -t smart-clinic-app .

# Run the Container
docker run -p 8080:8080 smart-clinic-app

```

---

## Learning Outcomes

* **Enterprise Architecture:** Mastered backend development patterns using Java and the Spring Boot framework.
* **Data Persistence:** Modeled database schemas and handled advanced data relations utilizing JDBC and Hibernate/JPA.
* **API Design:** Designed clean, predictable, and modular RESTful endpoints for healthcare resource management.
* **Full-Stack Integration:** Connected frontend Javascript state management seamlessly with backend Rest APIs.
* **DevOps Practices:** Containerized multi-layered applications using Docker and automated code health checks through GitHub Actions CI pipelines.

---

## About Me

I am **Sameer**, a Computer Science and Engineering student focused on building robust, scalable backend architectures. This capstone serves as a demonstration of my skills in Java enterprise technologies, relational database optimization, and microservice patterns.

* **GitHub:** [github.com/YOUR_GITHUB_USERNAME](https://www.google.com/search?q=https://github.com/sameerbarik3)
* **LinkedIn:** [linkedin.com/in/YOUR_LINKEDIN_USERNAME](https://www.google.com/search?q=https://linkedin.com/in/sameerbarik)

---

## License

This project is licensed under the Apache License 2.0. See the `LICENSE` file for details.
