# Backend Architecture

Production-oriented TypeScript/Node.js backend organized into domain-focused modules and infrastructure layers.

## Architecture Structure

```text
src/
├── billing/
│   ├── providers/
│   ├── types/
│   └── payment.service.ts
│
├── controllers/
├── middleware/
├── models/
│   ├── booking/
│   ├── chat/
│   ├── organization/
│   ├── service/
│   ├── user/
│   └── wallet/
│
├── modules/
├── repositories/
├── services/
├── routes/
├── jobs/
├── queues/
├── workers/
├── websocket/
└── config/
Architectural Layers
API Layer

Routes and controllers handle HTTP requests and responses.

Business Layer

Services contain application and business logic.

Data Layer

Models and repositories provide structured access to PostgreSQL data.

Infrastructure Layer

Billing providers, queues, workers, Redis, WebSocket components, and background jobs support asynchronous and real-time operations.

Main Domains
Authentication and security
Organizations and branches
Services and availability
Booking and scheduling
Billing and payments
Wallets and financial records
Payouts
Subscriptions
Social features
Communication
Design Goals
Clear separation of responsibilities
Maintainable domain boundaries
Transaction-safe financial workflows
Scalable background processing
Secure API architecture
Reliable relational data access
