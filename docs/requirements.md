# Project Requirements - Centralized Contract Management Portal (CMP)

## 1. Introduction

The Centralized Contract Management Portal (CMP) is a backend system designed for the company to serve as a secure and organized repository for all official documents such as Service Level Agreements (SLAs), Statements of Work (SOWs), Co-location Agreements, NDAs, and other contracts. The system provides controlled access for authorized staff to log in, manage organizations, and upload/download contract files.

---

## 2. Objectives

- **Centralize contract storage:** Provide a single, secure location for storing all company-related contracts and agreements.
- **Simplify document access:** Allow authorized users to find, download, or upload documents by organization easily.
- **Enable basic metadata tagging:** Allow users to assign clear names and optional types to uploaded documents for easy identification.
- **Support multiple document types:** Handle common contract formats (SLA, SOW, Co-location, NDA) in PDF format.
- **Lay groundwork for future improvements:** Build scalable backend services to enable features like version control, expiry reminders, and advanced search later.

---

## 3. Intended Users

- **Internal Admin Staff:** Employees who will manage organizations and related documents.
- **System Administrator:** Technical user responsible for maintaining the system.

---

## 4. Functional Requirements

1. **User Authentication**

   - Staff users must log in before accessing any portal feature.
   - Secure token-based authentication (JWT).

2. **Organization Management**

   - View a list of organizations.
   - Add a new organization with a required name field.

3. **Document Management**

   - Upload PDF contracts under an organization.
   - Metadata fields:
     - Document Name (required)
     - Document Type (optional: SLA, SOW, Co-location, NDA)
   - Download stored PDF files.
   - View a list of uploaded files per organization (with name and upload date).

4. **Validation**
   - Only PDF files accepted.
   - Required fields must be filled before submission.
   - Display proper error messages for invalid uploads or empty fields.

---

## 5. Non-Functional Requirements

- **Security:** Only authenticated users can access or manage documents.
- **Storage:** Files are securely stored on the server or a cloud service.
- **Scalability:** Design API endpoints and database to support future enhancements.
- **Performance:** Fast file upload and retrieval.
- **Reliability:** Persistent data storage to prevent loss on server restart.

---

## 6. Technology Stack

- **Backend:** Node.js with Express.js
- **Database:** MongoDB
- **Authentication:** JWT
- **File Handling:** Multer (for uploads)
- **Storage:** Local server or cloud storage for PDF files
