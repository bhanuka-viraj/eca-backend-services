# Backend Microservices Super-Repository

## Student Information
- **Student Name:** [Your Full Name]
- **Student Number:** [Your Student Number]
- **Slack Handle:** [@your-slack-handle]
- **GCP Project ID:** [your-gcp-project-id]

---

## Project Description
This super-repository contains all domain microservices for the enterprise system.

### Microservices (Git Submodules):
- [User & Auth Service](user-service) - Relational DB (Cloud SQL MySQL)
- [Catalog Service](catalog-service) - Non-Relational DB (MongoDB)
- [Media / Order Service](media-service) - Cloud Storage (GCS Bucket)

---

## Technology Stack
- Java 25 & Spring Boot 3.x
- Spring Data JPA (Hibernate) / Spring Data MongoDB
- Google Cloud Platform (Compute Engine MIGs, Cloud SQL, Cloud Storage)
- PM2

---

## Setup & Running
```bash
git clone --recurse-submodules https://github.com/<username>/services-repo.git
```\n