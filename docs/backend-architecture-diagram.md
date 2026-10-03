# Backend Architecture Diagram

```mermaid
flowchart LR

    C[Clients<br/>Web / Mobile / API Consumers]

    A[API Layer<br/>Routes · Controllers · Middleware]

    B[Business Layer<br/>Services · Modules · Validation]

    D[Data Layer<br/>Models · Repositories]

    DB[(PostgreSQL<br/>Relational Data Layer)]

    C --> A
    A --> B
    B --> D
    D --> DB

    subgraph CORE["Core Application Domains"]
        U[Users & Security]
        O[Organizations & Branches]
        S[Services & Availability]
        BK[Bookings & Scheduling]
        SUB[Subscriptions]
        SOC[Reviews & Social]
        COM[Communication]
        LIVE[WebSocket & Presence]
    end

    subgraph FIN["Financial Domain"]
        PAY[Payments]
        BP[Billing Providers]
        WAL[Wallets & Ledger]
        PO[Payouts]
        FX[Currencies]
        REC[Reconciliation]
    end

    subgraph INFRA["Infrastructure & Async Processing"]
        R[Redis]
        Q[Queues]
        W[Workers]
        J[Scheduled Jobs]
        WS[WebSocket]
        K[Kafka / Async Events]
    end

    B --> CORE
    B --> FIN
    B --> INFRA

    PAY --> BP
    PAY --> WAL
    WAL --> PO
    FX --> PAY
    PO --> REC

    Q --> W
    R --> Q
    J --> W
    K --> W
    WS --> COM

    CORE --> DB
    FIN --> DB
```

## Architecture Layers

- **API Layer:** Routes, controllers, and middleware.
- **Business Layer:** Services, modules, and validation.
- **Data Layer:** Domain models and repositories.
- **PostgreSQL:** Relational persistence and data integrity.

## Main Domains

- Users and security
- Organizations and branches
- Services and availability
- Bookings and scheduling
- Subscriptions
- Reviews and social features
- Communication
- Payments and billing
- Wallets and financial ledger
- Payouts
- Currency management
- Reconciliation

## Infrastructure

- Redis
- Queues
- Background workers
- Scheduled jobs
- WebSocket communication
- Kafka / asynchronous event processing

> This is a sanitized architecture diagram modeled from the documented backend structure. Production source code, credentials, private schemas, customer data, and sensitive business logic are excluded.
