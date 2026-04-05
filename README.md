# Finance Data Processing \& Access Control Backend

A RESTful API backend for a finance dashboard system featuring **JWT authentication**, **role-based access control (RBAC)**, **financial record management**, and **dashboard analytics**.

\---

## Tech Stack

|Layer|Technology|
|-|-|
|Language|TypeScript|
|Framework|Express.js|
|Database|SQLite (via Prisma ORM)|
|Authentication|JWT (jsonwebtoken)|
|Validation|Zod|
|Password Hashing|bcryptjs|
|API Docs|Swagger UI (OpenAPI 3.0)|

\---

## Project Structure

```
src/
├── app.ts                     # Express app entry point
├── config/
│   └── swagger.ts             # OpenAPI/Swagger configuration
├── database/
│   ├── client.ts              # Prisma client singleton
│   └── seed.ts                # Database seeder
├── middleware/
│   ├── authenticate.ts        # JWT verification middleware
│   ├── authorize.ts           # RBAC middleware (role enforcement)
│   ├── validate.ts            # Zod-based request validation
│   └── errorHandler.ts        # Global error handler + 404 handler
├── routes/
│   ├── auth.routes.ts         # /api/auth
│   ├── user.routes.ts         # /api/users
│   ├── transaction.routes.ts  # /api/transactions
│   └── dashboard.routes.ts    # /api/dashboard
├── schemas/
│   └── index.ts               # Zod validation schemas
├── services/
│   ├── auth.service.ts        # Auth business logic
│   ├── user.service.ts        # User management logic
│   ├── transaction.service.ts # Transaction CRUD logic
│   └── dashboard.service.ts   # Analytics/aggregation logic
└── types/
    └── index.ts               # Shared TypeScript types \& enums
prisma/
└── schema.prisma              # Database schema
```

\---

## Getting Started

### Prerequisites

* Node.js v18+
* npm

### 1\. Install dependencies

```bash
npm install
```

### 2\. Configure environment

```bash
# .env is pre-configured for development. Key values:
PORT=3000
DATABASE\_URL="file:./finance.db"
JWT\_SECRET=finance\_system\_super\_secret\_key\_2024\_change\_in\_production
JWT\_EXPIRES\_IN=7d
```

### 3\. Initialize the database

```bash
npx prisma db push
```

### 4\. Seed initial data

```bash
npm run seed
```

This creates three users and 10 sample transactions.

### 5\. Start the server

```bash
npm run dev        # Development (with hot reload)
npm run build \&\& npm start   # Production
```

### API is live at:

* **Base URL:** `http://localhost:3000`

