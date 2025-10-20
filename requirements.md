# Requirement Specifications – Airbnb Clone Backend

This document outlines the technical and functional specifications for key backend features of the Airbnb Clone project.

---

## 1. User Authentication

### Description
Handles user sign-up, login, and token-based authentication using secure credentials.

### API Endpoints
- `POST /api/v1/auth/register`
- `POST /api/v1/auth/login`

### Inputs/Outputs
- **Register**
  - Input: `{ "email": "string", "password": "string", "fullName": "string" }`
  - Output: `201 Created`, `{ "message": "User created", "token": "JWT" }`
- **Login**
  - Input: `{ "email": "string", "password": "string" }`
  - Output: `200 OK`, `{ "token": "JWT" }`

### Validation Rules
- Valid email format.
- Password must be ≥ 8 characters.
- Full name must not be empty.

### Performance
- Max 200ms response time
- Rate limit: 5 login attempts/min

---

## 2. Property Management

### Description
Allows hosts to manage property listings including create, update, view, and delete.

### API Endpoints
- `POST /api/v1/properties`
- `GET /api/v1/properties/:id`
- `PUT /api/v1/properties/:id`
- `DELETE /api/v1/properties/:id`

### Inputs/Outputs
- **Create Property**
  - Input: `{ "title": "string", "location": "string", "price": "number", "images": [urls] }`
  - Output: `201 Created`, `{ "id": "uuid", "message": "Property created" }`

### Validation Rules
- Title & location required.
- Price must be > 0.

### Performance
- CRUD operations ≤ 300ms
- Pagination supported

---

## 3. Booking System

### Description
Allows users to book properties, manage reservations, and check availability.

### API Endpoints
- `POST /api/v1/bookings`
- `GET /api/v1/bookings/:id`
- `DELETE /api/v1/bookings/:id`

### Inputs/Outputs
- **Create Booking**
  - Input: `{ "propertyId": "uuid", "checkIn": "date", "checkOut": "date" }`
  - Output: `201 Created`, `{ "id": "uuid", "message": "Booking confirmed" }`

### Validation Rules
- Dates must not overlap.
- Dates must be in the future.

### Performance
- Availability check ≤ 250ms
