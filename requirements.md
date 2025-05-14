# 📑 Airbnb Clone - Backend Requirement Specifications

This document defines the technical and functional requirements for key backend features of the Airbnb Clone project.

## 1. 👤 User Authentication
- **Endpoint**: `/api/users/`
- **Methods**: `POST` (register), `POST /login`, `GET/PUT/DELETE` for profile
- **Fields**: `username`, `email`, `password`, `role`
- **Validation**: Email must be unique, password minimum 8 characters
- **Performance**: Must support 10+ auth requests per second

## 2. 🏠 Property Management
- **Endpoint**: `/api/properties/`
- **Methods**: `GET`, `POST`, `PUT`, `DELETE`
- **Fields**: `name`, `description`, `price`, `location`, `host_id`
- **Validation**: Host must exist, price must be non-negative
- **Performance**: Property listing retrieval must complete in < 200ms

## 3. 📅 Booking System
- **Endpoint**: `/api/bookings/`
- **Methods**: `POST`, `GET`, `DELETE`, `PUT`
- **Fields**: `user_id`, `property_id`, `start_date`, `end_date`, `status`
- **Validation**: Dates must not overlap, only guest role can book
- **Performance**: Booking creation must complete under 500ms

## 🔐 Security
- Token-based authentication (JWT)
- Permissions enforced by user role
- Input sanitization on all API fields

## 📦 API Format
- REST (with OpenAPI docs)
- GraphQL supported for frontend queries
