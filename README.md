# HHA 504 Final Project: Cloud Integration Mini-Capstone Part 1 (only) - Patient Intake and Triage System
- Name: Blanca Chimborazo-Reyes

## Assignment Overview
This submission contains the **Design-Only Track (Part 1)** deliverables for the Cloud Integration Mini-Capstone project. The designed solution is a cloud-based patient intake and triage system for small to medium-sized healthcare clinics.

## Deliverables

| File | Description |
|------|-------------|
| `use_case.md` | Problem statement, user descriptions, data sources, and workflow overview |
| `architecture_plan.md` | Service mapping, data flow narrative, security/governance considerations and cost analysis |
| `architecture_diagram.png` | Architecture diagram (visual representation of the cloud infrastructure and data flow) |
| `reflection.md` | Analysis of design confidence, alternative considered, and future enhancements |

## Architecture Summary

**Cloud Provider:** Google Cloud Platform (GCP) and MongoDB Atlas

**Key Services Used:**
- Cloud Run — Hosts the containerized Flask application. This serverless compute platform was chosen for its ability to scale to zero, ensuring cost-efficiency for a clinic environment.
- MongoDB Atlas — A fully managed NoSQL database used to store patient demographics, complex symptom questionnaires, and triage scores. It was selected for its flexible schema, which is ideal for varied healthcare data.
- Cloud Storage — Provides secure object storage for patient-uploaded documents, such as insurance card images and prior medical records.
Secret Manager — Used to manage sensitive database connection strings and API keys, ensuring credentials are never hard-coded.
- Cloud Logging & Monitoring — Provides observability into application performance and logs for debugging and audit purposes.