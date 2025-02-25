# CS465-Portfolio
# Full Stack Application

This repository contains a full stack web application that serves two primary audiences:  
1. **Customers**, who can interact with the app’s user-facing features.  
2. **Administrators**, who can manage data and access the administrative interface through secure login authentication.

Below, you will find an overview of the project along with answers to reflective prompts covering architecture, functionality, testing, and personal reflections on the development process.

---

## Table of Contents

1. [Project Description](#project-description)  
2. [Features](#features)  
3. [Technology Stack](#technology-stack)  
4. [Installation and Setup](#installation-and-setup)  
5. [Usage](#usage)  
6. [Architecture](#architecture)  
7. [Functionality](#functionality)  
8. [Testing](#testing)  
9. [Reflection](#reflection)  

---

## Project Description

This application allows customers to explore and interact with the front-end interface (e.g., viewing products, placing orders, or accessing services) while providing administrators a secure dashboard to manage database entries, perform CRUD operations, and monitor user activities. Security for admin access is enforced through secure login authentication using sessions and/or JWT (JSON Web Tokens).

---

## Features

- **Customer Interface**  
  - Browse and view content, products, or services  
  - Responsive and user-friendly single-page application (SPA) experience  

- **Admin Interface**  
  - Secure login with authentication  
  - Create, Read, Update, Delete (CRUD) data via an admin dashboard  
  - User management and analytics (optional or project-specific)  

- **Security**  
  - Encrypted passwords (using bcrypt or similar library)  
  - Secure session handling or JWT  

- **Database**  
  - MongoDB NoSQL database for storing product data, user information, and administrative logs  

---

## Technology Stack

- **Front End**  
  - HTML / CSS / JavaScript (Express-embedded for server-side rendered pages)  
  - Single-Page Application (SPA) Framework (e.g., React, Vue, or Angular)  

- **Back End**  
  - Node.js  
  - Express.js  

- **Database**  
  - MongoDB (NoSQL)  

- **Authentication**  
  - Passport.js (or custom middleware)  
  - bcrypt (for password hashing)  
  - JSON Web Tokens (optional approach)  

---

## Installation and Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/your-repo.git
2. **Install dependencies**:
   ```bash
   cd your-repo
   npm install
3. **Setup Environment variables**:
    ```bash
   MONGODB_URI=mongodb://localhost:27017/your-database
   JWT_SECRET=your_jwt_secret
   PORT=3000
4. **Run Application**:
    ```bash
   npm start

---

## Usage

- **Customer Usage**  
  Access the frontend UI via the root path. Interact with the SPA or server-rendered pages to browse products or services.

- **Admin Usage**  
  Navigate to the `/admin` path. Provide valid admin credentials to access the secure dashboard. Manage and update data through the admin interface.

---

## Architecture

### Frontend Development Approaches: Express HTML, JavaScript, and SPA

In this project, we used **Express** to serve initial HTML and handle routing for both the customer-facing site and the admin interface. The HTML templates include embedded JavaScript (EJS, Handlebars, or another templating engine) for simple dynamic content. However, we also integrated a **Single-Page Application (SPA)** framework for the main customer interactions to provide a more dynamic and responsive user experience without constant page reloads.

- **Express HTML + JavaScript**  
  - Pros: Simple to render server-side pages, easy to manage sessions for secure routes.  
  - Cons: Not as dynamic for user experience; page reloads are common.  

- **SPA Framework (e.g., React)**  
  - Pros: Interactive and dynamic user experience, efficient state management, partial page updates.  
  - Cons: Requires additional build and bundling steps, more complex for SEO if not using server-side rendering.  

By combining both approaches, we leveraged the simplicity of server-rendered pages (particularly for the admin login) while offering a highly interactive SPA for the customer interface.

### Why a NoSQL MongoDB Database?

MongoDB, a **NoSQL** database, is highly flexible with unstructured or semi-structured data. This project benefits from:

- **Scalability**: Horizontal scaling is straightforward.  
- **Document-Oriented Data Model**: Allows fast iteration on the schema.  
- **Ease of Use**: MongoDB integrates well with Node.js through native drivers or ODMs like Mongoose.  

This flexibility made MongoDB the optimal choice to store rapidly changing data structures and to support agile development.

---

## Functionality

### JSON vs. JavaScript and How JSON Ties the Frontend and Backend

- **JSON (JavaScript Object Notation)** is a lightweight data-interchange format. While it shares syntax similarities with JavaScript object literals, JSON is purely textual and language-independent.  
- JSON plays a key role in **API communication**: when the frontend makes an AJAX/Fetch/Axios call to the backend, data is sent in JSON format, ensuring a consistent and parseable structure on both sides.

This alignment ensures that the backend can easily send and receive data in a standardized format, while the frontend can consume it seamlessly to populate views or components.

### Refactoring for Improved Functionality and Efficiencies

During the development of this project, code refactoring occurred at multiple stages:

- **Reusable Components**: We modularized repeating UI elements (e.g., product cards, navigation bars).  
- **Service/Utility Modules**: Common helper functions (e.g., currency formatting, date parsing) were abstracted into utility files to avoid duplication.

**Benefits of Reusable UI Components**:

1. **Consistency** across the application’s look and feel.  
2. **Reduced Maintenance**: Fixing a bug in one component fixes it everywhere.  
3. **Accelerated Development**: Quicker assembly of pages by reusing tested components.

---

## Testing

### Methods, Endpoints, and Security in a Full Stack Application

- **API Methods**: Common HTTP methods used include **GET** for retrieval, **POST** for creation, **PUT/PATCH** for updates, and **DELETE** for deletions.  
- **Endpoints**: The application defines routes like `/api/products`, `/api/users`, `/admin/login`, etc., each handling specific actions. Proper status codes (e.g., 200, 404, 500) and JSON response structures are critical for predictable front-end behavior.  
- **Security Layer**: With admin authentication in place, certain routes (e.g., `/admin`, `/api/admin/*`) require valid tokens or session cookies to access. Testing becomes more complex because you must handle user authentication tokens or sessions when making requests.

**Testing Approaches**:

1. **Unit Tests**: Validate individual functions or components.  
2. **Integration Tests**: Check how various parts of the system interact, especially around API endpoints.  
3. **Security Tests**: Attempt authenticated requests with valid credentials and confirm failures with invalid or expired tokens.

By combining these methods, we ensure reliable and secure operations across the full stack.

---

## Reflection

### Professional Growth and Marketable Skills

This course and project have been instrumental in building skills crucial for a modern full stack developer, including:

- **Full Stack Architecture**: Gaining insight into how front-end frameworks and back-end APIs interact through well-defined endpoints.  
- **NoSQL Databases**: Mastering schema design and data modeling in MongoDB, as well as performing CRUD operations efficiently.  
- **Authentication & Security**: Learning techniques to secure an application with password hashing, session management, or JWT-based tokens.  
- **Reusable Components & Code Refactoring**: Boosting maintainability and scalability of applications by implementing DRY (Don’t Repeat Yourself) principles.  
- **Testing Strategies**: Understanding the importance of thorough testing (unit, integration, security) to ensure reliability.  

Overall, these skills make me a more marketable candidate by showcasing a strong grasp of end-to-end web development, modern JavaScript frameworks, and the ability to deliver secure, high-quality code.

