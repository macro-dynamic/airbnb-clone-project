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
