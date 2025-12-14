# HHA 504 Final Project: Cloud Integration Mini-Capstone Part 1 (only) - Patient Intake and Triage System
- Name: Blanca Chimborazo-Reyes

## Assignment Overview
This submission contains the **Design-Only Track (Part 1)** deliverables for the Cloud Integration Mini-Capstone project. The designed solution is a cloud-based patient intake and triage system for small to medium-sized healthcare clinics.

## Deliverables

| File | Description |
|------|-------------|
| `use_case.md` | Problem statement, user descriptions, data sources, and workflow overview |
| `architecture_plan.md` | Service mapping, data flow narrative, security considerations, cost analysis, and diagram description |
| `architecture_diagram.png` | Architecture diagram |
| `reflection.md` | Analysis of design confidence, alternative considered, and future enhancements |

## Architecture Summary

**Cloud Provider:** Google Cloud Platform (GCP)

**Key Services Used:**
- **Cloud Run** — Hosts containerized Flask application (serverless compute)
- **Cloud SQL (PostgreSQL)** — Stores patient data, triage scores, visit records
- **Cloud Storage** — Stores uploaded documents (insurance cards, medical records)
- **GitHub Actions** — CI/CD pipeline for automated testing and deployment
- **Cloud Logging & Monitoring** — Observability and alerting