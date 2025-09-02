# Airbnb Clone Project 🚀

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![CI/CD](https://img.shields.io/badge/CI/CD-4BC51D?style=for-the-badge)

---

## Project Overview
The backend for the Airbnb Clone project provides a robust and scalable foundation for managing user interactions, property listings, bookings, and payments. It mimics the core features of Airbnb, ensuring a smooth experience for both users and hosts. The backend is built using Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, and Docker, with automated CI/CD pipelines for testing and deployment.

---

## Team Roles

- 👨‍💻 **Backend Developer**  
  Responsible for implementing API endpoints for users, properties, bookings, payments, and reviews. Develops business logic, ensures proper authentication and authorization, and integrates with the database. Works closely with the DBA and DevOps Engineer to optimize backend performance and deployment.  

- 🗄️ **Database Administrator (DBA)**  
  Designs and manages the PostgreSQL database schema. Implements indexing and caching strategies for fast data retrieval, monitors database health, performs backups, and handles migrations. Collaborates with the Backend Developer to ensure efficient and scalable data storage.  

- ⚙️ **DevOps Engineer**  
  Sets up CI/CD pipelines for automated testing and deployment. Manages Docker containerization to ensure consistent environments across development and production. Monitors backend services for scalability and reliability. Handles server provisioning and integration with Redis and Celery for asynchronous tasks.  

- 🧪 **QA Engineer**  
  Develops and executes test plans to ensure backend functionality meets requirements. Tests API endpoints for correctness, security, and reliability. Reports bugs and collaborates with the Backend Developer and DBA to fix issues. Ensures all features meet quality standards before release.  

---

## Technology Stack

- 🐍 **Django**: High-level Python web framework for building the backend and RESTful APIs.  
- ⚡ **Django REST Framework (DRF)**: Tools for creating RESTful APIs, serialization, authentication, and request handling.  
- 🗄️ **PostgreSQL**: Relational database for storing users, properties, bookings, payments, and reviews.  
- 📊 **GraphQL**: Flexible query language for fetching exactly the data needed via a single endpoint.  
- 📝 **Celery**: Handles asynchronous and scheduled tasks like notifications and payment processing.  
- 🧩 **Redis**: In-memory data store for caching and as a message broker to support Celery.  
- 🐳 **Docker**: Containerization for consistent development, testing, and production environments.  
- 🔄 **CI/CD Pipelines**: Automates testing, building, and deployment to ensure reliable code delivery.  

---

## Database Design

### Key Entities and Relationships

**1. Users**  
- **Fields:** id (PK), name, email, password, phone_number  
- **Description:** Represents users of the platform, including guests and hosts. A user can have multiple bookings, properties (if a host), and reviews.

**2. Properties**  
- **Fields:** id (PK), title, description, price_per_night, location, host_id (FK)  
- **Description:** Represents properties listed on the platform. Each property belongs to one host and can have multiple bookings and reviews.

**3. Bookings**  
- **Fields:** id (PK), user_id (FK), property_id (FK), check_in_date, check_out_date, status  
- **Description:** Represents reservations made by users for specific properties. Each booking is linked to one user and one property.

**4. Payments**  
- **Fields:** id (PK), booking_id (FK), amount, payment_date, status  
- **Description:** Stores payment information for bookings. Each payment is associated with one booking.

**5. Reviews**  
- **Fields:** id (PK), user_id (FK), property_id (FK), rating, comment  
- **Description:** Allows users to leave feedback on properties. Each review is linked to one user and one property.

**Relationships:**  
- A **user** can have multiple **bookings**, **reviews**, and **properties** (if host).  
- A **property** can have multiple **bookings** and **reviews**.  
- A **booking** is associated with **one user** and **one property**.  
- A **payment** is linked to a **single booking**.  
- A **review** belongs to **one user** and **one property**.

---

## Feature Breakdown

- **User Management**: Allows users to register, authenticate, and manage profiles securely, providing a personalized experience.  
- **Property Management**: Hosts can create, update, and manage property listings with detailed descriptions, pricing, and location.  
- **Booking System**: Enables users to make, update, and manage bookings efficiently, preventing double-bookings.  
- **Payment Processing**: Handles secure transactions and records payment details to ensure smooth financial operations.  
- **Review System**: Allows users to post and manage reviews and ratings, building trust and transparency between hosts and guests.  
- **API Documentation**: Provides clear REST and GraphQL API documentation for easier integration and collaboration.  
- **Database Optimizations**: Indexing and caching improve performance and reduce database load, ensuring fast data retrieval.  

---

## API Security

- **Authentication**: Ensures only registered users can access protected endpoints.  
- **Authorization**: Controls access based on user roles, preventing unauthorized actions.  
- **Rate Limiting**: Prevents abuse and protects the backend from overloading.  
- **Data Encryption**: Encrypts sensitive data in transit and at rest to protect user information.  
- **Input Validation & Sanitization**: Prevents SQL injection and XSS attacks, maintaining data integrity.  
- **Logging & Monitoring**: Detects suspicious activity early and allows faster incident response.  

---

## CI/CD Pipeline

CI/CD (Continuous Integration and Continuous Deployment) pipelines automate testing, building, and deploying code changes. They ensure new features or bug fixes are delivered safely, quickly, and reliably.  

**Tools:**  
- **GitHub Actions**: Automates workflows for testing and deployment.  
- **Docker**: Ensures consistent environments across development, testing, and production.  
- **Celery & Redis**: Supports asynchronous task management.  
- **PostgreSQL**: Works with migrations and database versioning as part of the pipeline.  

Implementing CI/CD ensures higher code quality, faster delivery, and a reliable backend for users and hosts.
