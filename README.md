# Enterprise Cloud Architecture - Domain Microservices Super-Repository

## Student Information
- **Student Name:** J P Bhanuka Viraj Madhuranga
- **Student Number:** 241711105
- **GCP Project ID:** enterprise-cloud-module-503705

---

## Project Overview
This super-repository contains all domain microservices for the EduCloud enterprise course portal using Git submodules.

### Microservices (Git Submodules)
- [User Service](https://github.com/bhanuka-viraj/user-service) — User & instructor management backed by GCP Cloud SQL MySQL.
- [Course Service](https://github.com/bhanuka-viraj/course-service) — Course catalog & curriculum management backed by MongoDB.
- [Media Service](https://github.com/bhanuka-viraj/media-service) — File attachment and thumbnail storage integrated with Google Cloud Storage.

---

## Technology Stack
- Java 25 & Spring Boot 4.1.1
- Spring Cloud 2025.1.3 (Eureka Client, Actuator)
- Spring Data JPA / Hibernate / MySQL Connector
- Spring Data MongoDB
- Google Cloud Storage Client SDK
- PM2 Process Manager
- Google Cloud Platform (Compute Engine Multi-Zone MIGs)

---

## Local Development & Setup
`ash
# Clone super-repository with all submodules
git clone --recurse-submodules https://github.com/bhanuka-viraj/eca-backend-services.git
cd eca-backend-services

# Build all microservices
cd user-service && ./mvnw clean package && cd ..
cd course-service && ./mvnw clean package && cd ..
cd media-service && ./mvnw clean package && cd ..
`
