# PostgreSQL Dockerized Environment with Schema and Triggers

This repository provides a complete Dockerized PostgreSQL setup with the following features:
- A **Docker Compose** configuration to run a PostgreSQL database.
- Automatic creation of the `auth` schema and a `users` table during initialization.
- A **trigger function** that updates the `updated_at` column whenever a row in the `users` table is updated.
- Data persistence via Docker volumes, ensuring durability across container restarts.

## Key Highlights

1. **Schema Management**:
   - `auth` schema is created automatically if it doesn't exist.
   - `users` table includes fields for `name`, `email`, `password_hash`, and timestamps (`created_at` and `updated_at`).

2. **Trigger Automation**:
   - The `update_updated_at_column` function ensures that the `updated_at` field reflects the last modification time of each row.

3. **Containerized Setup**:
   - PostgreSQL runs in an isolated Docker container, making it easy to set up and maintain.

4. **Environment Configuration**:
   - Configurable database credentials via `.env` variables:
     - `POSTGRES_USER`
     - `POSTGRES_PASSWORD`
     - `POSTGRES_DB`

5. **Compatibility**:
   - Easily connect to the database using tools like `psql`, **pgAdmin**, or **DBeaver**.

## Usage

- Clone the repository, configure environment variables, and start the PostgreSQL container using Docker Compose.
- The initialization scripts will set up the database schema, table, and triggers automatically.
