# 🌦️ Weather Report Management System

Weather Report Management System is a **Spring Boot-based REST API application** designed to provide weather information along with automated weather reporting and client subscription management.

The application allows clients to access weather information through REST APIs and supports **international weather data, email-based weather reports, scheduled report delivery, OTP verification, PDF report generation, auditing, and caching**. It follows a layered architecture with dedicated controllers, services, repositories, DTOs, exception handling, event listeners, and configuration components.

The project also demonstrates the use of advanced Spring Boot features such as **Spring Events, Scheduling, AOP, global exception handling, and service-oriented architecture**, making it a practical implementation of a production-style REST API.

### Key Capabilities

* 🌤️ Weather information through REST APIs
* 🌍 International weather information
* 👤 Client registration and management
* 📧 Email-based weather reports
* 🔐 OTP-based verification
* 📅 Scheduled weather report delivery
* 📄 PDF weather report generation
* 📝 Audit logging
* ⚡ Weather data caching
* 🔔 Client subscription management
* 🛡️ Global exception handling
* 🔄 Event-driven operations
* 📊 REST API response handling

## 📂 Project Structure

```text
src/
├── main/
│   ├── java/
│   │   └── com/qsp/
│   │       ├── aspect/
│   │       │   └── WeatherReportAspect.java
│   │       │
│   │       ├── configuration/
│   │       │   ├── GlobalCorsConfig.java
│   │       │   └── LibraryBeanCreationConfiguration.java
│   │       │
│   │       ├── controller/
│   │       │   ├── AuditController.java
│   │       │   ├── ClientController.java
│   │       │   ├── InternationalWeatherController.java
│   │       │   ├── PdfGenerateController.java
│   │       │   └── WeatherController.java
│   │       │
│   │       ├── entity/
│   │       │   ├── Audit.java
│   │       │   ├── Client.java
│   │       │   ├── EmailLogReport.java
│   │       │   └── WeatherReport.java
│   │       │
│   │       ├── event/
│   │       ├── exception/
│   │       │   ├── custom/
│   │       │   └── handler/
│   │       ├── listener/
│   │       ├── modelmapper/
│   │       ├── repository/
│   │       ├── requestdto/
│   │       ├── responsedto/
│   │       ├── runner/
│   │       ├── scheduling/
│   │       ├── service/
│   │       ├── serviceimplement/
│   │       └── util/
│   │
│   └── resources/
│       ├── application.properties
│       └── templates/
│           └── weather-report.html
│
└── test/
    └── java/
        └── com/qsp/
            └── SpringBootRestApplicationTests.java
```

### Package Responsibilities

| Package            | Responsibility                                                                   |
| ------------------ | -------------------------------------------------------------------------------- |
| `controller`       | Exposes REST APIs and handles HTTP requests and responses                        |
| `service`          | Defines the application's business-service interfaces                            |
| `serviceimplement` | Contains implementations of the service interfaces                               |
| `repository`       | Handles database access through Spring Data JPA                                  |
| `entity`           | Contains JPA entity classes representing application data                        |
| `requestdto`       | Contains DTOs used for incoming API requests                                     |
| `responsedto`      | Contains DTOs used for API responses                                             |
| `modelmapper`      | Handles conversion between entities and DTOs                                     |
| `exception`        | Contains custom exceptions and global exception handling                         |
| `configuration`    | Contains application-specific Spring configuration                               |
| `aspect`           | Contains AOP functionality, including weather report-related cross-cutting logic |
| `event`            | Defines application events                                                       |
| `listener`         | Handles application events                                                       |
| `scheduling`       | Contains scheduled weather-report operations                                     |
| `runner`           | Contains application startup/initialization logic                                |
| `util`             | Contains utility classes, converters, caching utilities, and enums               |
| `templates`        | Contains the HTML template used for weather reports                              |


## ✨ Features

* 🌤️ **Weather Information** — Provides weather information through REST APIs.
* 🌍 **International Weather Support** — Supports retrieving weather information for international locations.
* 👤 **Client Management** — Allows clients to be created, updated, and managed through REST APIs.
* 📧 **Email Weather Reports** — Sends weather reports to subscribed clients through email.
* 🔐 **OTP Verification** — Provides OTP generation and verification with handling for expired, mismatched, and excessive OTP attempts.
* 📅 **Scheduled Weather Reports** — Automatically sends weather reports to subscribed clients using scheduled tasks.
* 📄 **PDF Weather Reports** — Generates weather reports in PDF format.
* 🔔 **Subscription Management** — Supports client subscription creation and subscription updates.
* 📝 **Audit Logging** — Maintains audit information for application activities.
* ⚡ **Caching** — Uses caching functionality to improve weather data retrieval performance.
* 🔄 **Event-Driven Processing** — Uses Spring Events and listeners for client and subscription-related operations.
* 🛡️ **Global Exception Handling** — Provides centralized handling of application-specific exceptions.
* 🎯 **AOP Integration** — Uses Aspect-Oriented Programming for weather-report-related cross-cutting functionality.
* 🗂️ **DTO-Based API Design** — Separates request and response data using dedicated DTOs.


## 🛠️ Tech Stack

### Backend

* **Java 17**
* **Spring Boot 3.5.7**
* **Spring Web** — Building RESTful APIs
* **Spring Data JPA** — Database interaction and persistence
* **Hibernate** — ORM for database operations
* **Spring AOP** — Aspect-oriented programming
* **Spring Validation** — Request validation
* **Spring Boot Actuator** — Application monitoring and management

### Database

* **MySQL** — Relational database
* **MySQL Connector/J** — Database connectivity

### API Documentation

* **Springdoc OpenAPI 2.8.14**
* **Swagger UI** — API documentation and testing

### Email & Reporting

* **Spring Boot Mail** — Sending email notifications and weather reports
* **Thymeleaf** — Generating HTML-based weather report templates
* **OpenPDF 1.3.39** — PDF report generation

### Development & Testing

* **Maven** — Dependency management and build automation
* **Lombok** — Reducing boilerplate Java code
* **Spring Boot DevTools** — Development-time features
* **Spring Boot Test** — Testing


## 🏗️ Architecture

The application follows a **layered architecture** to separate API handling, business logic, data persistence, and supporting application services.

```text
                         ┌──────────────────────┐
                         │       Client         │
                         │  REST API Consumer   │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │     Controller       │
                         │  REST API Layer      │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │       Service        │
                         │   Business Logic     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │     Repository       │
                         │    Data Access       │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │       MySQL          │
                         │      Database        │
                         └──────────────────────┘


              Supporting Application Components
              ─────────────────────────────────

       ┌────────────┐    ┌────────────┐    ┌─────────────┐
       │ Scheduling │    │   Events   │    │     AOP     │
       └─────┬──────┘    └─────┬──────┘    └──────┬──────┘
             │                 │                   │
             ▼                 ▼                   ▼
       Weather Report     Event Listeners     Cross-cutting
        Scheduler                              Operations


       ┌────────────┐    ┌────────────┐    ┌─────────────┐
       │    Mail    │    │    PDF     │    │   Caching   │
       │   Service  │    │ Generation │    │             │
       └────────────┘    └────────────┘    └─────────────┘
```

### Architecture Components

**Controller Layer**

Handles HTTP requests and exposes REST endpoints for weather information, client management, auditing, international weather services, and PDF generation.

**Service Layer**

Contains the application's business logic and separates business operations from the REST controllers.

**Repository Layer**

Handles persistence and database operations using Spring Data JPA.

**Entity Layer**

Contains the application's JPA entities, including client, weather report, audit, and email-log data.

**DTO Layer**

Request and response DTOs are used to control the data exchanged through the REST APIs and separate API models from database entities.

**Exception Handling**

Custom exceptions are centralized through a global exception handler to provide consistent error responses.

**Event & Listener System**

Spring Events and listeners are used for client and subscription-related application events.

**Scheduling**

Scheduled operations are used for automated weather report processing and delivery.

**AOP**

Aspect-oriented programming is used for weather-report-related cross-cutting functionality.

**Email & PDF Services**

The application integrates email functionality and PDF generation to deliver weather reports to clients.

**Caching**

Weather data caching is provided through the application's utility layer to reduce unnecessary repeated operations.

