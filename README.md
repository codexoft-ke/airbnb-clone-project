# 🌍 AirBnB Full Stack Clone

## Project Description  
This project is a full-stack clone of the popular accommodation booking platform AirBnB. The goal is to build a functional web application that allows users to browse property listings, view detailed property information, and complete bookings. The project covers frontend development, backend APIs, database design, and deployment.

---

## 🎯 Learning Objectives  
By completing this project, you will:

- Learn to implement responsive UI/UX designs  
- Understand how to structure a complex web application  
- Practice working in a team with defined roles  
- Develop skills in component-based frontend architecture  
- Learn best practices for web application development  

---

## 🧰 Tech Stack  
- **Frontend:** HTML, CSS, JavaScript (React or similar framework)  
- **Backend:** Django, Django REST Framework, GraphQL  
- **Database:** PostgreSQL  
- **Async Processing:** Celery + Redis  
- **Containerization:** Docker  
- **CI/CD:** GitHub Actions or GitLab CI/CD  
- **Caching & Sessions:** Redis  
- **Design Tools:** Figma  
- **Version Control:** Git & GitHub  

---
## 🗄️ Database Design

The project uses a relational database structure with clearly defined entities and relationships to ensure data integrity and efficient querying.

### 🔹 Users  
Represents people using the platform (guests, hosts, or admins).  
**Important Fields:**  
- `id` (Primary Key)  
- `name`  
- `email` (unique)  
- `password` (hashed)  
- `role` (guest, host, admin)  

**Relationships:**  
- A user can list multiple properties.  
- A user can make multiple bookings.  
- A user can write multiple reviews.

---

### 🔹 Properties  
Represents accommodation listings created by hosts.  
**Important Fields:**  
- `id` (Primary Key)  
- `user_id` (Foreign Key – owner/host)  
- `title`  
- `location`  
- `price_per_night`  

**Relationships:**  
- A property belongs to one user (host).  
- A property can have multiple bookings.  
- A property can have multiple reviews.

---

### 🔹 Bookings  
Represents a reservation made by a user for a property.  
**Important Fields:**  
- `id` (Primary Key)  
- `user_id` (Foreign Key – guest)  
- `property_id` (Foreign Key)  
- `check_in_date`  
- `check_out_date`  

**Relationships:**  
- A booking is made by one user.  
- A booking belongs to one property.  
- A booking may result in one payment.

---

### 🔹 Payments  
Represents the financial transaction tied to a booking.  
**Important Fields:**  
- `id` (Primary Key)  
- `booking_id` (Foreign Key)  
- `amount`  
- `status` (pending, completed, failed)  
- `payment_method`  

**Relationships:**  
- A payment is associated with one booking.  
- A booking can have one payment record.

---

### 🔹 Reviews  
Represents feedback left by users after staying at a property.  
**Important Fields:**  
- `id` (Primary Key)  
- `user_id` (Foreign Key – guest)  
- `property_id` (Foreign Key)  
- `rating`  
- `comment`  

**Relationships:**  
- A review is written by one user.  
- A review belongs to one property.

---

### 🔗 Entity Relationships Summary  
- A **User** can have many **Properties**, **Bookings**, and **Reviews**  
- A **Property** belongs to a **User**, and can have many **Bookings** and **Reviews**  
- A **Booking** belongs to a **User** and a **Property**, and is linked to one **Payment**  
- A **Payment** is tied to one **Booking**  
- A **Review** is linked to one **User** and one **Property**

## 📦 Project Requirements  

### ✅ Project Initialization  
- Set up GitHub repository with proper documentation  
- Include a comprehensive README with project overview  

### 🎨 UI/UX Design Planning  
- Document design goals and key features  
- Create page descriptions for main views  
- Analyze Figma design specifications  
- Identify color schemes and typography  

### 🧑‍🤝‍🧑 Roles and Responsibilities  
- Define team structure and responsibilities  
- Document each role’s contribution to the project  

### 🧩 UI Component Patterns  
- Plan reusable UI components  
- Document component architecture  

---

## 💎 Best Practices  
- Maintain clean, modular code structure  
- Use feature branches and meaningful commit messages  
- Mobile-first approach for responsive design  
- Follow WCAG guidelines for accessibility  
- Keep all project documentation updated  
- Implement unit and integration tests  

---

## 🎨 UI/UX Design Planning  

### Goals  
- Create intuitive booking flow  
- Maintain visual consistency  
- Ensure fast loading times  
- Prioritize mobile responsiveness  

### Key Features  
- Property search and filtering  
- Detailed property viewing  
- Secure checkout process  
- User authentication  

### Primary Pages  
| Page | Description |
|------|-------------|
| Property Listing View | Grid display of available properties with filters |
| Listing Detailed View | Complete property details with images and booking form |
| Simple Checkout View | Streamlined payment and booking confirmation |

---

## 🌈 Figma Design Specifications  

### Color Styles  
- Primary: `#FF5A5F`  
- Secondary: `#008489`  
- Background: `#FFFFFF`  
- Text: `#222222`  
- Secondary Text: `#717171`  

### Typography  
- Primary Font: Circular, Medium (500), 16px  
- Headings: Circular, Bold (700), 24px–32px  
- Secondary Text: Circular, Book (400), 14px  

---

## 👥 Team Roles and Responsibilities  
| Role | Responsibilities |
|------|------------------|
| Project Manager | Oversees timeline, coordinates team, manages deliverables |
| Frontend Developers | Implements UI components, ensures responsive design |
| Backend Developers | Builds APIs, manages database, implements business logic |
| Designers | Creates mockups, maintains design system, ensures UX quality |
| QA/Testers | Writes test cases, performs testing, reports bugs |
| DevOps Engineers | Manages deployment, CI/CD pipeline, server infrastructure |
| Product Owner | Defines requirements, prioritizes features, represents stakeholders |
| Scrum Master | Facilitates agile processes, removes blockers, organizes meetings |

---

## 🧱 UI Component Patterns  

### Navbar  
- Logo  
- Search bar  
- User navigation  
- Responsive menu  

### Property Card  
- Property image  
- Basic details (price, location, rating)  
- Favorite button  
- Responsive layout  

### Footer  
- Site links  
- Company information  
- Social media links  
- Copyright  

---

## 🏆 Project Goals  
- **User Management:** Secure registration, authentication, and profile management  
- **Property Management:** Property listing creation, updates, retrieval  
- **Booking System:** Users can reserve properties and manage bookings  
- **Payment Processing:** Securely handle payment transactions  
- **Review System:** Allow users to leave reviews and ratings  
- **Data Optimization:** Indexing, caching for performance  

---

## 🛠️ Features Overview  

### 1. API Documentation  
- **OpenAPI Standard** for RESTful API docs  
- **Django REST Framework** for CRUD operations  
- **GraphQL** for flexible querying  

### 2. User Authentication  
**Endpoints:** `/users/`, `/users/{user_id}/`  
- Register new users  
- User login/authentication  
- Profile management  

### 3. Property Management  
**Endpoints:** `/properties/`, `/properties/{property_id}/`  
- Create, update, retrieve, delete property listings  

### 4. Booking System  
**Endpoints:** `/bookings/`, `/bookings/{booking_id}/`  
- Make and manage bookings  
- Check-in/check-out flow  

### 5. Payment Processing  
**Endpoints:** `/payments/`  
- Handle transactions related to bookings  

### 6. Review System  
**Endpoints:** `/reviews/`, `/reviews/{review_id}/`  
- Post and manage property reviews  

### 7. Database Optimizations  
- **Indexing** for common queries  
- **Caching** using Redis  

---
## 🧩 Feature Breakdown

### 1. User Management  
This feature allows users to register, log in, and manage their profiles securely. It ensures authentication through JWT tokens and supports role-based access for different types of users like guests, hosts, and admins.

### 2. Property Management  
Hosts can list properties by providing essential details like pricing, location, and images. They can also update or delete listings, making the platform dynamic and easy to manage for content creators.

### 3. Booking System  
Users can book available properties by selecting check-in and check-out dates. This feature includes booking validation, availability checks, and reservation storage to streamline the travel planning experience.

### 4. Payment Processing  
Secure payments are handled via a dedicated API that captures transaction details during booking. This feature simulates real-world checkout experiences and prepares the project for payment gateway integrations.

### 5. Review System  
Users can leave reviews and rate properties they’ve stayed in. This fosters trust and helps future users make informed booking decisions based on past guest experiences.

### 6. Search and Filtering  
Users can search properties by location, availability, and price range. This enhances usability by making it easy to discover relevant listings quickly.

### 7. API Security  
The project includes JWT-based authentication, rate limiting, role-based access control, and input sanitization. These measures ensure the safety of user data and protect the platform from malicious attacks.

## 🔐 API Security

### 1. Authentication & Authorization  
- **JWT Authentication** secures all protected endpoints  
- **Role-Based Access Control (RBAC)** ensures access rights per user role (Admin, Host, User)  

### 2. Input Validation & Sanitization  
- All inputs validated on both frontend and backend  
- Prevents common attacks: SQL Injection, XSS, Object Injection  
- Handled through Django serializers and GraphQL schema  

### 3. Rate Limiting & Throttling  
- DRF's throttling system limits request rates  
- Prevents brute-force and spam requests  

### 4. CSRF Protection  
- Enabled for session-based routes  
- JWT-protected routes bypass CSRF (stateless)  

### 5. HTTPS Enforcement  
- All requests over HTTPS in production  
- HTTP automatically redirected to HTTPS  

### 6. CORS Policy  
- Strict origin control  
- Only approved frontend domains can call the API  

### 7. Secrets & Secure Configs  
- All secrets handled via environment variables  
- Production secrets stored securely (e.g., via Vault or Docker secrets)  
- `.env` file never committed to version control  

---

## 📈 API Documentation Overview  
- REST API available via Swagger/OpenAPI UI  
- GraphQL schema introspection enabled  
- Postman collection available for testing  

---

## 📌 Endpoints Overview  

### Users  
- `GET /users/` – List all users  
- `POST /users/` – Create a new user  
- `GET /users/{user_id}/` – Get specific user  
- `PUT /users/{user_id}/` – Update user  
- `DELETE /users/{user_id}/` – Delete user  

### Properties  
- `GET /properties/` – List all properties  
- `POST /properties/` – Create property  
- `GET /properties/{property_id}/` – Get property  
- `PUT /properties/{property_id}/` – Update property  
- `DELETE /properties/{property_id}/` – Delete property  

### Bookings  
- `GET /bookings/` – List bookings  
- `POST /bookings/` – Create booking  
- `GET /bookings/{booking_id}/` – Get booking  
- `PUT /bookings/{booking_id}/` – Update booking  
- `DELETE /bookings/{booking_id}/` – Delete booking  

### Payments  
- `POST /payments/` – Process a payment  

### Reviews  
- `GET /reviews/` – List reviews  
- `POST /reviews/` – Create review  
- `GET /reviews/{review_id}/` – Get review  
- `PUT /reviews/{review_id}/` – Update review  
- `DELETE /reviews/{review_id}/` – Delete review  
