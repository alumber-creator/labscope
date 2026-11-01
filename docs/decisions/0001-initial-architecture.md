# ADR-0001: Initial Architecture

## Status
>Accepted

## Context
LabScope requires infrastructure monitoring, network diagnostics and incident management.

The application is initially developed by a single developer.

## Decision
- Use a Modular Monolith architecture for the Backend.

- Use separate Python agents on Linux hosts.

- Use PostgreSQL for structured data.

- Use Prometheus for metrics storage.

- Use Docker Compose for central deployment.

## Consequences
- Simple initial development.
- Clear separation of responsibilities.
- Easy local deployment.
- Possibility of future modular expansion.

## Alternatives Considered
- Microservices
- Single process Monolith  