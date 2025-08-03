# 🏗️ System Architecture - Centralized Contract Management Portal (CMP)

## 1. High-Level Overview

The CMP backend service provides RESTful API endpoints for user authentication, organization management, and PDF contract storage. The architecture is designed to be modular, scalable, and secure.

---

## 2. Architecture Illustration

Client (Web UI)
|
| HTTP Requests
v
Express.js Backend
├── Auth Service (JWT login)
├── Organization Service (CRUD)
├── Document Service (Upload/Download)
|
Database (MongoDB)
├── Users Collection
├── Organizations Collection
├── Documents Collection (metadata + file path)
|
File Storage
└── Local storage or GridFS for PDF files.

## 3. Backend Modules

- **Routes:** Define endpoints for authentication, organizations, and documents.
- **Controllers:** Handle incoming requests and responses.
- **Services:** Business logic for file uploads, downloads, and database interaction.
- **Models:** Mongoose schemas for users, organizations, and documents.
- **Middlewares:** Authentication checks, file validation.
- **Utils:** Helper functions (e.g., error handling, input sanitization).

---

## 4. Data Model

### Users

| Field    | Type   | Description     |
| -------- | ------ | --------------- |
| id       | String | Unique user ID  |
| email    | String | Login email     |
| password | String | Hashed password |

### Organizations

| Field     | Type   | Description            |
| --------- | ------ | ---------------------- |
| id        | String | Unique organization ID |
| name      | String | Organization name      |
| createdAt | Date   | Timestamp              |

### Documents

| Field      | Type   | Description                |
| ---------- | ------ | -------------------------- |
| id         | String | Unique document ID         |
| orgId      | String | Linked organization ID     |
| name       | String | Document display name      |
| type       | String | SLA, SOW, Co-location, NDA |
| filePath   | String | Path or URL to stored file |
| uploadedAt | Date   | Upload timestamp           |

---

## 5. Security

- JWT-based authentication for API requests.
- Role-based access (Admin users only for this version).
- File type validation (PDF only).
