# ADR-0001: Initial Architecture

## Status
>Accepted

## Context
LabScope requires infrastructure monitoring, network diagnostic and incident management.

The application is initially developed by a single developer.

## Decision
- Use Modular Monolith architecture for the Backend.

- Use separate Python Agents on Linux hosts.

- Use PostgreSQL for structured data.

- Use Prometheus for metrics storage.

- Use Docker Compose for central deployment

## Consequences
- Simple initial development.
- Clear separation of responsibilities.
- Easy local deployment.
- Possibility of future modular expansion.

## Alternatives Considered
- Microservice
- Single-process Monolith  