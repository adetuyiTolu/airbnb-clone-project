# airbnb-clone-project
An airbnb clone project designed to establish a robust and scalable backend system for handling user interactions, property listings, bookings, and payment processing

## 🧑‍💻 Team Roles

This section outlines the core roles involved in the development of this project and their responsibilities.

### 🛠 Backend Developer
Responsible for implementing server-side logic, building RESTful APIs, integrating with databases, and ensuring the backend system is scalable, secure, and performant.

### 🧱 Database Administrator (DBA)
Designs and manages the database structure. Ensures data integrity, performs backups, tunes performance, and maintains data security across all environments.

### 🧪 QA Engineer / Tester
Tests the application for bugs, reliability, and performance issues. Writes test plans, executes test cases (both manual and automated), and collaborates closely with the dev team to ensure quality.


### 🚀 DevOps / Deployment Engineer
Builds and maintains the infrastructure. Sets up CI/CD pipelines, manages environments, automates deployments, and monitors application health and performance.

### 👨‍💼 Product Manager
Oversees the product vision and roadmap. Collaborates with stakeholders, gathers user requirements, prioritizes features, and ensures timely delivery of project milestones.

## 🛠️ Technology Stack

Below is a list of core technologies used in this project, along with their roles:

- **Django**  
  A high-level Python web framework used for building the RESTful API. It simplifies rapid development and clean, pragmatic design.

- **Django REST Framework**  
  An extension of Django that provides powerful tools and features for building and managing RESTful APIs efficiently.

- **PostgreSQL**  
  A robust, open-source relational database used for storing and managing structured application data.

- **GraphQL**  
  A query language for APIs that enables clients to request exactly the data they need, making data fetching more efficient and flexible.

- **Celery**  
  A distributed task queue used for managing asynchronous or scheduled jobs such as email notifications, report generation, or payment processing.

- **Redis**  
  An in-memory data store used for caching and message brokering, enhancing performance and supporting task queues via Celery.

- **Docker**  
  A containerization tool that ensures consistency across development, testing, and production environments by packaging the application and its dependencies into containers.

- **CI/CD Pipelines**  
  Continuous Integration and Continuous Deployment pipelines automate testing, integration, and deployment processes, enabling faster and more reliable releases.

  ## 🗃️ Database Design

This project is built around several core entities to support the platform's functionality. Below is an overview of each entity, its key fields, and how the entities relate to one another.

### 📌 Entities and Key Fields

#### 1. **User**
Represents the individuals who interact with the platform.
- `id`: Unique identifier for each user.
- `name`: Full name of the user.
- `email`: User's email address (used for login and communication).
- `password`: Hashed password for authentication.
- `role`: Specifies if the user is a guest or host.

#### 2. **Property**
Represents a listing available for booking.
- `id`: Unique identifier for the property.
- `title`: Name or title of the property.
- `description`: Detailed information about the property.
- `location`: Address or region where the property is located.
- `price_per_night`: Cost of staying per night.

#### 3. **Booking**
Represents a reservation made by a user.
- `id`: Unique booking reference.
- `user_id`: The guest who made the booking.
- `property_id`: The property being booked.
- `start_date`: Beginning of the reservation.
- `end_date`: End of the reservation.

#### 4. **Review**
Represents feedback left by a user after a stay.
- `id`: Unique identifier for the review.
- `user_id`: Reviewer (must have booked the property).
- `property_id`: The reviewed property.
- `rating`: Numerical rating (e.g., 1-5 stars).
- `comment`: Optional text feedback.

#### 5. **Payment**
Represents the financial transaction for a booking.
- `id`: Unique transaction reference.
- `booking_id`: Booking associated with the payment.
- `amount`: Total amount paid.
- `status`: Payment status (e.g., pending, completed, failed).
- `timestamp`: Date and time the payment was made.

---

### 🔗 Entity Relationships

- A **User** can list multiple **Properties** (if they are a host).
- A **User** can make multiple **Bookings** (as a guest).
- A **Booking** is linked to one **Property** and one **User**.
- A **Review** is submitted by a **User** and linked to one **Property**.
- A **Payment** is tied to a single **Booking**.

These relationships ensure a scalable and well-structured system for managing listings, interactions, and transactions.

