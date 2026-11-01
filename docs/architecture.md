# Architecture

## General Architecture

LabScope uses a Modular Monolith architecture.

The Backend is divided into independent functional modules.

## Main Components

### Frontend
Vue 3 + TypeScript.
Provides the user interface.

### Backend 
Python + FastAPI.
Handles business logic and API requests.

### Database
PostgreSQL.
Stores infrastructure information, configuration and incidents.

### Metrics Storage
Prometheus.
Collects and storage time-series metrics.

### Agent
Independent Python application installed on monitored Linux hosts.

## Communication
- Frontend <-> Backend: HTTP REST API
- Agent -> Backend: HTTP 
- Prometheus -> Agent: HTTP/metrics
- Backend -> PostgreSQL: SQL
- Backend -> Prometheus: HTTP API