# Task Tracker Orchestration

Docker Compose configuration for deploying the Task Tracker application in development and production environments.

## Repository Structure

```
├── .env.dev                      # Development environment variables
├── .env.dev.example              # Example development environment variables
├── .env.prod                     # Production environment variables
├── .env.prod.example             # Example production environment variables
├── docker-compose.dev.yml        # Docker Compose configuration for development
└── docker-compose.prod.yml       # Docker Compose configuration for production
```

## Setup Instructions

### Development Environment

1. Clone this repository:

   ```bash
   git clone https://github.com/NireekshaHuns/EVident-Battery-Orchestration-Service.git
   ```

2. Copy the example env file: (Can be skipped for now, but in production we cannot expose sensitive secrets.)

   ~~`cp .env.dev.example .env.dev`~~

3. Start development environment:

   ```bash
   docker compose -f docker-compose.dev.yml up -d
   ```

4. Access:
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:5001

## Test Instructions

### Frontend Tests

1. Start frontend tests:

   ```bash
   docker compose -f docker-compose.test.yml up --exit-code-from frontend-test --abort-on-container-exit frontend-test
   ```

### Backend Tests

1. Start backend tests:

   ```bash
   docker compose -f docker-compose.test.yml up --exit-code-from backend-test --abort-on-container-exit backend-test
   ```

## Notes

- Images are pulled directly from Docker Hub
- Backend data is stored in a Docker volume
- Configure domain and ports in the environment files as needed
