# Budget Tracker

Personal finance web app to track income and expenses, manage categories, and analyze trends with monthly and yearly history.

## Highlights

- Authentication with Clerk
- Dashboard with balance overview and historical charts
- Income and expense transaction tracking
- Category management with icons
- User currency preferences
- Date-range filtering for transaction history

## Tech Stack

- Next.js 15 (App Router)
- React 19
- TypeScript
- Prisma ORM
- PostgreSQL
- Tailwind CSS + Radix UI + shadcn/ui patterns
- TanStack Query and TanStack Table
- Zod validation

## Project Structure

Main directories:

- src/app: Pages, layouts, and API routes
- src/actions: Server Actions for categories, transactions, and user settings
- src/components: UI and feature components
- src/schema: Zod schemas for request and form validation
- src/lib: Shared constants, DB client, utilities
- prisma: Prisma schema and migrations

## 📋 Prerequisites

- Node.js 20+
- npm, pnpm, yarn, or Bun
- Docker (recommended for local PostgreSQL)
- Clerk account and API keys

## 🚀 Getting Started

To clone and run this application, you'll need [Git](https://git-scm.com/) and [Bun](https://bun.sh/) installed on your computer. From your command line:

```bash
# Clone this repository
$ git clone https://github.com/Alex6564/budget-tracker.git

# Navigate to the project directory
$ cd budget-tracker

# Install dependencies
$ bun install

# Set up environment variables
$ cp .env.example .env

# Start the Docker containers
$ docker-compose up -d

# Push database schema
$ bunx prisma migrate dev

# Start the development server
$ bun dev
```

## Data Model Overview

Prisma models:

- UserSettings: Per-user settings (currency)
- Category: User categories for income/expense
- Transaction: Financial entries with category and type
- MonthlyHistory: Daily aggregates per month
- YearlyHistory: Monthly aggregates per year

The app updates transaction history tables in the same transaction used to create and delete financial entries.

## App Flow

- Public routes: /sign-in and /sign-up
- Protected routes: All app pages and API routes via Clerk middleware
- First-time setup: Users are redirected to /configurations to set currency

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for discussion.
