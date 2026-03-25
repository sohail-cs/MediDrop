MediDrop

#Overview
Medidrop is an on-demand medicine delivery platform that enables users to order prescription-based medication online. The system connects customers with pharmacies that verify and fulfill prescriptions, and drivers who handle delivery.

This project is designed to simulate a real-world, scalable backend system similar to modern delivery platforms, with a strong focus on system design, reliability, and backend engineering principles.

# Problem Statement
Accessing medication can be slow and inconvenient, especially for elderly individuals, people with mobility challenges, or those requiring urgent prescriptions.

Medidrop solves this by digitizing the process of prescription verification, order management, and delivery coordination.

# Key Features
- User authentication (JWT-based)
- Prescription upload
- Order placement and tracking
- Pharmacy order acceptance/rejection
- Driver assignment and delivery tracking
- Payment simulation (success/failure handling)
- Order lifecycle management

# System Architecture

Medidrop follows a modular backend architecture with clearly separated responsibilities:

- **User Service** – handles authentication and user management  
- **Order Service** – manages order creation and lifecycle  
- **Pharmacy Service** – handles order acceptance and preparation  
- **Delivery Service** – manages driver assignment and delivery tracking  
- **Payment Service** – simulates payment processing  

## Flow:
User → Order Service → Pharmacy → Delivery → Payment

## Database Design

## Core Tables:
- `users`
- `orders`
- `prescriptions`
- `pharmacies`
- `drivers`
- `payments`

## Relationships:
- A user can have multiple orders  
- Each order is linked to one prescription  
- Each order is fulfilled by one pharmacy  
- Each order is delivered by one driver  
- Each order has one payment record  

## API Endpoints

## Authentication
- `POST /auth/register`
- `POST /auth/login`

## Users
- `GET /users/profile`

## Prescriptions
- `POST /prescriptions`
- `GET /prescriptions/{id}`

## Orders
- `POST /orders`
- `GET /orders/{id}`
- `GET /orders`
- `POST /orders/{id}/cancel`

## Pharmacy
- `GET /pharmacy/orders`
- `POST /pharmacy/orders/{id}/accept`
- `POST /pharmacy/orders/{id}/reject`

## Driver
- `GET /driver/orders`
- `POST /driver/orders/{id}/accept`
- `POST /driver/orders/{id}/complete`

## Payments
- `POST /payments`
- `GET /payments/{orderId}`

# Order Lifecycle

Orders move through the following states:

- CREATED  
- PENDING_VERIFICATION  
- ACCEPTED  
- REJECTED  
- DISPATCHED  
- DELIVERED  
- CANCELLED  


## Project Goal
This project is built to demonstrate backend engineering skills including system design, API development, database modeling, and handling real-world edge cases in a scalable system.
