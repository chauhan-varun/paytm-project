# Paytm Project

A full-stack payment application inspired by Paytm, built with a modern tech stack in a monorepo structure.

## Project Overview

This project is a payment application with separate apps for users and merchants, featuring:

- User authentication
- Balance management
- Transaction processing
- Merchant integration

## Tech Stack

- **Frontend**: Next.js with TypeScript
- **Backend**: Node.js
- **Database**: PostgreSQL with Prisma ORM
- **Project Structure**: Turborepo monorepo
- **Styling**: Tailwind CSS

## Project Structure

```
paytm-project/
├── apps/
│   ├── user-app/       # User-facing application
│   ├── merchant-app/   # Merchant dashboard
│   └── bank-webhook/   # Bank webhook integration
├── packages/
│   ├── db/             # Database models and migrations
│   ├── ui/             # Shared UI components
│   ├── store/          # Shared state management
│   ├── eslint-config/  # Shared ESLint configuration
│   └── typescript-config/ # Shared TypeScript configuration
```

## Getting Started

### Prerequisites

- Node.js 18 or higher
- npm 10.2.4 or higher
- PostgreSQL (local or cloud)

### Setup Instructions

1. **Install dependencies**
   ```
   npm install
   ```

2. **Set up PostgreSQL**
   
   Option 1: Run locally using Docker
   ```bash
   docker run -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
   ```
   
   Option 2: Use a cloud PostgreSQL instance (e.g., neon.tech)

3. **Configure environment variables**
   - Copy all `.env.example` files to `.env` in respective directories
   - Update all `.env` files with your database connection URL

4. **Setup database**
   ```bash
   cd packages/db
   npx prisma migrate dev
   npx prisma db seed
   ```

5. **Start development server**
   ```bash
   cd apps/user-app
   npm run dev
   ```

6. **Access the application**
   - Open http://localhost:3001 in your browser
   - Log in with test credentials:
     - Phone: 1111111111
     - Password: alice 
     - (These credentials are defined in `packages/db/prisma/seed.ts`)

## Development

To run the entire monorepo in development mode:

```bash
npm run dev
```

For building all projects:

```bash
npm run build
```
