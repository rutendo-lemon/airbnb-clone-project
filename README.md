# Airbnb Clone Project

## Project Overview
The backend for the Airbnb Clone project provides a robust and scalable foundation for managing user interactions, property listings, bookings, and payments. It mimics the core features of Airbnb, ensuring a smooth experience for both users and hosts. The backend is built using Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, and Docker, with automated CI/CD pipelines for testing and deployment.

---

## Team Roles

- 👨‍💻 **Backend Developer**:  
  Responsible for implementing API endpoints for users, properties, bookings, payments, and reviews. Develops business logic, ensures proper authentication and authorization, and integrates with the database. Works closely with the DBA and DevOps Engineer to optimize backend performance and deployment.  

- 🗄️ **Database Administrator (DBA)**:  
  Designs and manages the PostgreSQL database schema. Implements indexing and caching strategies for fast data retrieval, monitors database health, performs backups, and handles migrations. Collaborates with the Backend Developer to ensure efficient and scalable data storage.  

- ⚙️ **DevOps Engineer**:  
  Sets up CI/CD pipelines for automated testing and deployment. Manages Docker containerization to ensure consistent environments across development and production. Monitors backend services for scalability and reliability. Handles server provisioning and integration with Redis and Celery for asynchronous tasks.  

- 🧪 **QA Engineer**:  
  Develops and executes test plans to ensure backend functionality meets requirements. Tests API endpoints for correctness, security, and reliability. Reports bugs and collaborates with the Backend Developer and DBA to fix issues. Ensures all features meet quality standards before release.  

---

## Technology Stack

- 🐍 **Django**: A high-level Python web framework used to build the backend of the Airbnb Clone. Handles server-side logic, routing, and integration with the database, providing a solid foundation for building RESTful APIs.  

- ⚡ **Django REST Framework (DRF)**: An extension of Django that simplifies building RESTful APIs. Provides tools for serialization, authentication, permissions, and request handling, making backend development faster and more secure.  

- 🗄️ **PostgreSQL**: A powerful open-source relational database used to store and manage data such as user profiles, property listings, bookings, payments, and reviews. Supports complex queries, indexing, and ensures data integrity.  

- 📊 **GraphQL**: A flexible query language and runtime that allows clients to request exactly the data they need. Improves efficiency by reducing over-fetching and provides a single endpoint for accessing multiple resources.  

- 📝 **Celery**: A distributed task queue for handling asynchronous and scheduled tasks. Used to process background jobs such as sending email notifications and handling payment processing.  

- 🧩 **Redis**: An in-memory data structure store used as a cache and message broker. Improves performance by storing frequently accessed data and supports Celery task queues.  

- 🐳 **Docker**: A containerization platform that packages the application and its dependencies into a container. Ensures consistency across development, testing, and production environments.  

- 🔄 **CI/CD Pipelines**: Continuous Integration and Continuous Deployment pipelines automate testing, building, and deploying code. Ensures that new features or bug fixes are delivered safely, quickly, and reliably.  

---

## Database Design

### Key Entities

- **Users**  
  Fields: `id`, `name`, `email`, `password`, `phone_number`  
  Relationships: A user can have multiple bookings, reviews, and properties (if a host).  

- **Properties**  
  Fields: `id`, `title`, `description`, `price_per_night`, `location`, `host_id`  
  Relationships: A property belongs to a user (host), can have multiple bookings and reviews.  

- **Bookings**  
  Fields: `id`, `user_id`, `property_id`, `check_in_date`, `check_out_date`, `status`  
  Relationships: A booking belongs to one user and one property.  

- **Reviews**  
  Fields: `id`, `user_id`, `property_id`, `rating`, `comment`  
  Relationships: A review belongs to one user and one property; a property can have many reviews.  

- **Payments**  
  Fields: `id`, `booking_id`, `amount`, `payment_date`, `payment_status`  
  Relationships: A payment is associated with a single booking; a booking can have one or multiple payments.  

### ERD (Text-Based)
```Users
+------------+ +------------+
| id (PK) | 1 * | Properties |
| name |---------| id (PK) |
| email | | title |
| password | | description|
| phone | | price |
+------------+ | location |
| host_id(FK)|
+------------+

Users
1
|
*
Bookings
+------------+ +------------+
| id (PK) | 1 1 | Properties |
| user_id(FK)|---------| id (PK) |
| property_id(FK)| +------------+
| check_in |
| check_out |
| status |
+------------+

Bookings
1
|
*
Payments
+------------+
| id (PK) |
| booking_id(FK)|
| amount |
| payment_date|
| status |
+------------+

Users
1
|
*
Reviews
+------------+
| id (PK) |
| user_id(FK)|
| property_id(FK)|
| rating |
| comment |
+------------+```


---

## Feature Breakdown

- **User Management**  
  Allows users to register, authenticate, and manage profiles securely, providing a personalized experience.  

- **Property Management**  
  Hosts can create, update, and manage property listings with detailed descriptions, pricing, and location.  

- **Booking System**  
  Enables users to make, update, and manage bookings efficiently, preventing double-bookings.  

- **Payment Processing**  
  Handles secure transactions and records payment details to ensure smooth financial operations.  

- **Review System**  
  Allows users to post and manage reviews and ratings, building trust and transparency between hosts and guests.  

- **API Documentation**  
  Provides clear REST and GraphQL API documentation for easier integration and collaboration.  

- **Database Optimizations**  
  Indexing and caching improve performance and reduce database load, ensuring fast data retrieval.  

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
