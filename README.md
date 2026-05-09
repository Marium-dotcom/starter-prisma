# Prisma Starter

A minimal Prisma ORM starter with PostgreSQL, TypeScript, and `pg`.

## Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment variables

Copy the example env file and fill in your database credentials:

```bash
cp .env.example .env
```

Then edit `.env`:

```env
DATABASE_URL="postgresql://USER:PASSWORD@HOST:PORT/DATABASE"
```

| Variable       | Description                                      | Example                                          |
| -------------- | ------------------------------------------------ | ------------------------------------------------ |
| `DATABASE_URL` | Full PostgreSQL connection string (required)     | `postgresql://postgres:123@localhost:5432/mydb`  |

> `.env` is gitignored and never committed. Only `.env.example` is tracked.

### 3. Run database migrations

```bash
npx prisma migrate dev
```

### 4. Generate Prisma Client

```bash
npx prisma generate
```

### 5. Run the script

```bash
npx tsx script.ts
```

## Schema

The schema defines two models:

- **User** — `id`, `email` (unique), `name`, and a relation to `Post[]`
- **Post** — `id`, `title`, `content`, `published`, and a `authorId` foreign key to `User`

Schema file: [prisma/schema.prisma](prisma/schema.prisma)
# starter-prisma
