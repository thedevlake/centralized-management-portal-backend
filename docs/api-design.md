# API Design - CMP Backend

Base URL: `/api/v1`

## Authentication

- **POST** `/auth/login` – Authenticate user, return JWT token.

## Organizations

- **GET** `/organizations` – Fetch all organizations.
- **POST** `/organizations` – Add a new organization.

## Documents

- **GET** `/organizations/:id/documents` – List all documents under an organization.
- **POST** `/organizations/:id/documents` – Upload a PDF document (fields: `name`, `type`, `file`).
- **GET** `/documents/:docId/download` – Download a document by ID.
