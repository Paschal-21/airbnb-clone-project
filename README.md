# AirBnB Clone Project

## 🏡 Overview
The **AirBnB Clone Project** is a full-stack web application that replicates the core functionality of the AirBnB platform — allowing users to create, browse, and book accommodations.  
This project focuses on mastering backend development, RESTful API design, and front-end integration.

## 🎯 Project Goals
- Build a scalable backend using modern frameworks.
- Implement user authentication and authorization.
- Manage database models for users, listings, and bookings.
- Create RESTful API endpoints for CRUD operations.
- Develop a responsive front-end interface.
- Deploy the project for public access.

## 🧰 Tech Stack
**Backend:** Python, Django, Django REST Framework  
**Frontend:** HTML, CSS, JavaScript (React or Vanilla JS)  
**Database:** PostgreSQL / SQLite (development)  
**Version Control:** Git & GitHub  
**Deployment:** Render / Vercel / AWS (optional)

## 👨‍💻 Author
**Paschal Ebitse**  
Software Engineer | Backend Developer | ALX Graduate  
GitHub: [@Paschal-21](https://github.com/Paschal-21)


## 👥 Team Roles

A successful software project relies on a diverse team of specialists, each contributing their unique expertise.  
Below are the key roles and their responsibilities in the **AirBnB Clone Project** (adapted from ITRexGroup’s software development team structure).

### 🧑‍💻 Backend Developer
Responsible for building and maintaining the server-side logic, APIs, and integrations.  
- Develop RESTful API endpoints using Django REST Framework.  
- Implement business logic, authentication, and data handling.  
- Ensure scalability and performance of backend services.

### 🗃️ Database Administrator (DBA)
Manages the database systems ensuring data integrity, security, and optimization.  
- Design and maintain the database schema.  
- Handle migrations and query optimization.  
- Manage data backups and recovery processes.

### 🎨 Frontend Developer
Responsible for creating the user interface and ensuring a seamless user experience.  
- Develop responsive pages using HTML, CSS, and JavaScript (or React).  
- Connect frontend components to backend APIs.  
- Optimize the UI for speed and accessibility.

### 🧩 Project Manager (PM)
Oversees project planning, coordination, and delivery.  
- Define timelines, milestones, and deliverables.  
- Facilitate communication among team members.  
- Ensure project objectives are met on schedule.

### 🧪 QA Engineer (Quality Assurance)
Ensures the application meets quality standards through testing and validation.  
- Develop and execute manual and automated test cases.  
- Identify, report, and track bugs.  
- Verify fixes and ensure system reliability.

### 🧠 UI/UX Designer
Focuses on designing intuitive and engaging user experiences.  
- Create wireframes, prototypes, and user flows.  
- Work closely with frontend developers for design consistency.  
- Conduct usability tests and iterate based on feedback.

### ☁️ DevOps Engineer
Manages infrastructure, deployment pipelines, and continuous integration/delivery.  
- Set up CI/CD

## 🧰 Technology Stack

The **AirBnB Clone Project** is built using a modern, scalable, and efficient technology stack that enables seamless backend and frontend development, database management, and deployment.

Below are the key technologies and their purposes:

### 🐍 Django
A high-level Python web framework that simplifies backend development.  
- Provides tools for handling routing, ORM, authentication, and security.  
- Powers the RESTful API and business logic for the application.

### ⚙️ Django REST Framework (DRF)
An extension of Django used to build RESTful APIs efficiently.  
- Handles serialization, authentication, and API responses.  
- Facilitates smooth communication between the backend and frontend.

### 🗃️ PostgreSQL
A robust and reliable relational database system.  
- Stores structured data such as user information, property listings, and bookings.  
- Supports advanced queries and relationships using Django’s ORM.

### 💬 GraphQL *(Optional Enhancement)*
A query language for APIs that enables clients to request only the data they need.  
- Improves data fetching efficiency and flexibility.  
- Can be used alongside REST for optimized client-server communication.

### 🧑‍🎨 HTML, CSS, JavaScript
Core web technologies used for building and styling the frontend interface.  
- HTML defines structure, CSS handles design, and JavaScript adds interactivity.  
- Provides users with a responsive and engaging experience.

### ⚛️ React *(Optional Frontend Framework)*
A JavaScript library for building dynamic and reusable user interfaces.  
- Enables component-based frontend development.  
- Enhances performance and scalability of the client-side experience.

### 🧪 Git & GitHub
Version control and collaboration tools for tracking changes and managing codebase.  
- Enables branching, merging, and issue tracking.  
- Supports continuous integration and teamwork.

### ☁️ Render / Vercel / AWS (Deployment)
Cloud platforms used for deploying and hosting the project.  
- Provides scalability, uptime, and secure access for users.  
- Simplifies CI/CD pipelines and environment configuration.

---

Each technology plays a crucial role in ensuring the AirBnB Clone Project is robust, maintainable, and user-friendly.

## 🗄️ Database Design

The **AirBnB Clone Project** uses a relational database structure designed to store and manage user, property, and booking data efficiently.  
The key entities and their relationships are outlined below:

---

### 🧑‍🤝‍🧑 Users
Stores information about all registered users on the platform.

**Key Fields:**
- `id`: Unique identifier for each user (Primary Key).  
- `username`: The user’s unique login name.  
- `email`: Contact email address.  
- `password`: Encrypted user password.  
- `role`: Defines user type (e.g., Host or Guest).

**Relationships:**
- A **User** can list multiple **Properties**.  
- A **User** (as a Guest) can make multiple **Bookings** and **Payments**.  
- A **User** can leave multiple **Reviews**.

---

### 🏠 Properties
Represents accommodation listings created by hosts.

**Key Fields:**
- `id`: Unique identifier for each property.  
- `owner`: Foreign key linking to the **User** who owns the property.  
- `title`: Name or title of the property.  
- `location`: City or region where the property is located.  
- `price_per_night`: Cost to rent the property per night.

**Relationships:**
- A **Property** belongs to one **User** (host).  
- A **Property** can have multiple **Bookings** and **Reviews**.

---

### 📅 Bookings
Stores reservation details for users who book properties.

**Key Fields:**
- `id`: Unique identifier for each booking.  
- `guest`: Foreign key linking to the **User** making the booking.  
- `property`: Foreign key linking to the **Property** being booked.  
- `check_in`: Date when the booking starts.  
- `check_out`: Date when the booking ends.

**Relationships:**
- A **Booking** belongs to one **User** (guest).  
- A **Booking** belongs to one **Property**.  
- A **Booking** can have one **Payment**.

---

### 💬 Reviews
Captures user feedback and ratings for properties.

**Key Fields:**
- `id`: Unique identifier for each review.  
- `user`: Foreign key linking to the **User** who wrote the review.  
- `property`: Foreign key linking to the **Property** being reviewed.  
- `rating`: Numerical rating (1–5).  
- `comment`: Text feedback from the user.

**Relationships:**
- A **Review** belongs to one **User** and one **Property**.  
- A **Property** can have multiple **Reviews**.

---

### 💳 Payments
Tracks payment transactions for bookings.

**Key Fields:**
- `id`: Unique identifier for each payment.  
- `booking`: Foreign key linking to the **Booking** it corresponds to.  
- `amount`: Total payment amount.  
- `payment_method`: Type of payment (e.g., Card, Bank Transfer).  
- `status`: Payment status (e.g., Completed, Pending, Failed).

**Relationships:**
- A **Payment** belongs to one **Booking**.  
- A **User** can have multiple **Payments** through their bookings.

---

### 🔗 Entity Relationships Summary
- **User ↔ Property**: One-to-Many (a host can have many properties).  
- **Property ↔ Booking**: One-to-Many (a property can be booked multiple times).  
- **User ↔ Booking**: One-to-Many (a guest can make multiple bookings).  
- **Booking ↔ Payment**: One-to-One (each booking has one payment).  
- **Property ↔ Review**: One-to-Many (a property can have many reviews).

---

This schema ensures clean data relationships and efficient queries, supporting both host and guest interactions within the AirBnB Clone ecosystem.