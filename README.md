## Dishlist - Development Environment

Local development dependencies for the Dishlist app (Docker Compose).

## Local Development Setup

Follow these steps to set up your local Dishlist development environment:

1. **Make sure colima is running**

   ```bash
   colima start
   ```

2. **Navigate to dev-environment directory (this service)**

   ```bash
   cd dev-environment
   ```

3. **Start the development dependencies**

   ```bash
   docker-compose up
   ```

4. **Navigate to your Dishlist service directory**

   ```bash
   cd ../your-dishlist-service
   ```

5. **Start your service**

   ```bash
   pnpm run start
   ```

6. **Everything should work!**

The Docker Compose setup provides shared development dependencies (like Postgres) that Dishlist services can connect to.

### Start Postgres

From this folder:

```bash
# Docker Compose v2 (Docker Desktop)
docker compose up

# Docker Compose v1
docker-compose up
```

Or in the background:

```bash
# Docker Compose v2 (Docker Desktop)
docker compose up -d

# Docker Compose v1
docker-compose up -d
```

### Connection details (defaults)

- Host: `localhost`
- Port: `5432`
- User: `postgres`
- Password: `postgres`

**Note:** This is a shared Postgres server. Each Dishlist service should connect to this server and create its own database (e.g., `dishlist_api_development`, `dishlist_auth_development`).

Connection string template:

`postgres://postgres:postgres@localhost:5432/<your_dishlist_service_database>`

### Stop / reset

```bash
# Docker Compose v2 (Docker Desktop)
docker compose down

# Docker Compose v1
docker-compose down
```

Delete data volume too:

```bash
# Docker Compose v2 (Docker Desktop)
docker compose down -v

# Docker Compose v1
docker-compose down -v
```
