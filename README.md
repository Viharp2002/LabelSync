# LabelSync

**Real-Time Collaborative Data-Annotation Platform with Role-Based Workflows**

LabelSync is a full-stack platform that lets teams collaboratively annotate datasets (images and text) in real time, with role-based access control, conflict-resolved version history, and an AI-assisted annotation microservice.

## Architecture

- **Backend:** Node.js + Express, handling core business logic, authentication, and REST endpoints
- **Frontend:** React, providing the real-time collaborative annotation interface
- **AI/ML Microservice:** Python-based service for model-assisted annotation suggestions, called by the Node backend
- **Database:** MongoDB, with aggregation pipelines powering analytics on annotator throughput and inter-annotator agreement
- **Real-Time Sync:** Socket.io, propagating annotation changes to all connected users instantly
- **API Layer:** Hybrid REST + GraphQL, REST for high-frequency operations, GraphQL for complex nested queries around annotation history and roles
- **Auth:** JWT-based role authentication (admin / annotator / reviewer)
- **Deployment:** Docker Compose, with CI/CD via GitHub Actions for zero-downtime releases

## Key Features

- **Real-time collaboration:** Multiple users can annotate the same dataset simultaneously, with changes synced live via WebSockets
- **Conflict-resolved version history:** Concurrent edits are tracked and reconciled rather than silently overwritten
- **Role-based workflows:** Admins, annotators, and reviewers have distinct permissions and views
- **AI-assisted annotation:** A Python microservice provides model-assisted suggestions to speed up annotation
- **Analytics:** MongoDB aggregation pipelines surface annotator throughput and inter-annotator agreement metrics
- **Scalable deployment:** Fully containerized with Docker Compose and automated CI/CD

## Tech Stack

Node.js, Express, React, Python, MongoDB, Socket.io, GraphQL, REST, JWT, Docker, GitHub Actions

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Viharp2002/LabelSync.git
cd LabelSync

# Start all services (Node backend, React frontend, Python microservice, MongoDB)
docker-compose up --build
```