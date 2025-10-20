# Features and Functionalities – Airbnb Clone Backend

This document lists the main backend features and functionalities planned for the Airbnb Clone system.

---

## 🧩 Core Features

### 1. User Authentication & Authorization
- Register a new user account.
- Secure login using JWT tokens.
- Password hashing using bcrypt.
- Role-based access (User, Admin).

### 2. Property Management
- Admin can add, edit, and delete property listings.
- Users can browse all approved properties.
- Properties include details: title, description, price per night, location, and availability.

### 3. Booking System
- Users can book available properties for specific dates.
- Check-in and check-out validation.
- Admin can view all bookings.

### 4. Payment Processing
- Users can make online payments (e.g., via Stripe).
- Generate booking confirmations after successful payment.
- Store payment status in database.

### 5. User Dashboard
- Users can view their bookings and payment history.
- Cancel upcoming bookings before check-in date.

### 6. Admin Management
- Admin can approve or reject newly added properties.
- Admin can manage users and view all transactions.

---

## 🗄️ Database Entities
- **Users:** id, name, email, passwordHash, role  
- **Properties:** id, title, description, price, location, status  
- **Bookings:** id, userId, propertyId, startDate, endDate, status  
- **Payments:** id, bookingId, amount, method, paymentStatus

---

## 📘 Summary
These features define the main backend scope of the Airbnb Clone proje
