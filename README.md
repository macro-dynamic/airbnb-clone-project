# airbnb-clone-project

## 👥 Team Roles

The following roles contribute to the success of the AirBnB Clone project. Each team member may be responsible for one or more of these roles, ensuring clean, scalable development.

| Role                    | Responsibilities |
|-------------------------|------------------|
| **Backend Developer**   | Implements core logic and APIs using Django and DRF. Handles serializers, views, URL routing, and integrations. |
| **Database Administrator (DBA)** | Designs PostgreSQL schema, manages indexes, relationships, migrations, and performance tuning. |
| **DevOps Engineer**     | Builds and manages Docker containers, configures CI/CD pipelines, and oversees deployment environments. |
| **QA Engineer**         | Writes and runs tests (unit/integration), ensures API reliability, and manages testing tools and coverage. |
| **Security Engineer**   | Enforces secure authentication, handles permissions, guards against vulnerabilities like SQL injection, XSS, CSRF. |
| **Project Manager**     | Manages planning, tasks, timelines, and coordination using GitHub issues or project boards. |


## 🧱 Technology Stack

This project uses a modern backend development stack to ensure performance, scalability, and maintainability.

| Technology            | Purpose |
|------------------------|---------|
| **Python**             | The core programming language used to build the backend logic. |
| **Django**             | A high-level Python web framework used for rapid development and clean, pragmatic design. Powers the main web server and handles routing, views, and templates. |
| **Django REST Framework (DRF)** | An extension of Django for building RESTful APIs. Provides tools for serialization, authentication, and API views. |
| **PostgreSQL**         | A powerful open-source relational database used to store all application data including users, properties, bookings, and payments. |
| **GraphQL**            | An optional query language used to provide flexible data fetching alternatives to REST, enabling clients to request only the data they need. |
| **Docker**             | Used to containerize the application and its services for consistent development and production environments. |
| **Redis**              | An in-memory data store used for caching and background task queuing via Celery. |
| **Celery**             | A distributed task queue used to handle asynchronous tasks like sending confirmation emails or processing payments. |
| **GitHub Actions**     | Provides CI/CD automation for testing and deploying the project on every code push or pull request. |


## 🗄️ Database Design

The AirBnB Clone backend relies on a relational database schema implemented in **PostgreSQL**. Below are the core entities and their relationships, aligned with the project’s REST API endpoints and features.

### 🔑 Key Entities

#### 1. Users
Stores information for both guests and hosts.

**Important Fields:**
- `id` (Primary Key)
- `username`
- `email`
- `password` (hashed)
- `is_host` (Boolean: true if user can list properties)
- `created_at` (timestamp)

#### 2. Properties
Represents listings created by hosts.

**Important Fields:**
- `id`
- `title`
- `description`
- `location` (city, country, address)
- `price_per_night`
- `host_id` (Foreign Key to Users)
- `created_at`

#### 3. Bookings
Tracks property reservations made by users.

**Important Fields:**
- `id`
- `user_id` (FK to Users)
- `property_id` (FK to Properties)
- `start_date`
- `end_date`
- `status` (pending, confirmed, cancelled)
- `created_at`

#### 4. Payments
Handles transactions for bookings.

**Important Fields:**
- `id`
- `booking_id` (FK to Bookings)
- `amount`
- `status` (e.g., success, failed)
- `payment_method`
- `paid_at`

#### 5. Reviews
Stores user feedback for properties.

**Important Fields:**
- `id`
- `user_id` (FK to Users)
- `property_id` (FK to Properties)
- `rating` (e.g., 1–5)
- `comment`
- `created_at`

---

### 🔗 Entity Relationships

- A **User** can act as a **guest** or a **host**.
- A **Host (User)** can create multiple **Properties**.
- A **User** can make multiple **Bookings**, each linked to a specific **Property**.
- A **Booking** has exactly one **Payment**.
- A **User** can write multiple **Reviews** about **Properties** they’ve booked.
- A **Property** can have many **Reviews** and **Bookings**.

This structure ensures clear referential integrity and aligns with the provided API endpoints.


## ✨ Feature Breakdown

This project implements core functionalities of a property rental platform, replicating key workflows of Airbnb from both user and host perspectives.

### 🧑‍💼 1. User Management
Allows users to register, log in, and manage their profiles. Authentication ensures secure access, and profile features support both guests and hosts depending on user roles.

### 🏠 2. Property Management
Hosts can create, update, and manage property listings with details like title, description, price, and location. These listings form the core inventory available to users for booking.

### 📅 3. Booking System
Users can browse listings and book properties for specific dates. The system manages availability, check-in/check-out dates, and booking status (pending, confirmed, canceled).

### 💳 4. Payment Processing
Secure payment handling is implemented to process transactions related to bookings. Each booking is tied to a single payment record, and transaction status is tracked for success or failure.

### ⭐ 5. Review System
After their stay, users can leave reviews and star ratings for properties. This builds trust in the platform and provides valuable feedback for both hosts and future guests.

### 🚀 6. API Design (REST + GraphQL)
RESTful endpoints are provided for all core resources using Django REST Framework. Optional GraphQL support allows flexible, client-driven querying for performance and precision.

### ⚙️ 7. Optimization & Performance
Includes database indexing and Redis-based caching to optimize query performance. Celery is used for background tasks like sending notifications or handling asynchronous payments.


