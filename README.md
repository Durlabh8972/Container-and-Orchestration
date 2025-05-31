# Task 2 - OpenTelemetry Collector Setup with PostgreSQL Metrics

## Overview

This task adds PostgreSQL and SQL query metrics collection to the OpenTelemetry Collector setup for the project.

We use the `postgresqlreceiver` and `sqlqueryreceiver` from OpenTelemetry Collector Contrib to collect database and custom query metrics from a PostgreSQL instance.

---

## Prerequisites

- Docker installed and running.
- PostgreSQL container running with:
  - Database: `lcbo`
  - User: `lcbo`
  - Password: `Secret5555`
- OpenTelemetry Collector container configured with PostgreSQL receivers.
- Access to forwarded ports in GitHub Codespaces or local environment.

---

## PostgreSQL Container Setup

If you don't have PostgreSQL running, start it with:

```bash
docker run --name in-class-work-2-db-1 \
  -e POSTGRES_USER=lcbo \
  -e POSTGRES_PASSWORD=Secret5555 \
  -e POSTGRES_DB=lcbo \
  -p 5432:5432 \
  -d postgres
