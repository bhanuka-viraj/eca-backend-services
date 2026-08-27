# Enterprise Cloud Architecture - Domain Microservices Super-Repository

## 👨‍🎓 Student & Project Information
- **Student Name:** J P Bhanuka Viraj Madhuranga
- **Student ID:** 241711105
- **GitHub Username:** bhanuka-viraj
- **GCP Project ID:** enterprise-cloud-module-503705
- **GCP Region:** `us-central1` (Multi-zone: `us-central1-a`, `us-central1-b`)

---

## 🌐 Live Production Endpoints

| Component | Architecture Role | Live Public URL | Protocol / Health |
| :--- | :--- | :--- | :--- |
| **API Gateway (Courses)** | Global Load Balancer $\to$ Port 8080 | [http://34.160.86.95/api/v1/courses](http://34.160.86.95/api/v1/courses) | HTTP 200 OK (MongoDB) |
| **API Gateway (Users)** | Global Load Balancer $\to$ Port 8080 | [http://34.160.86.95/api/v1/users](http://34.160.86.95/api/v1/users) | HTTP 200 OK (Cloud SQL) |
| **Frontend Web App** | Global Load Balancer $\to$ Cloud Run | [http://34.111.29.195](http://34.111.29.195) | HTTP 200 OK |
| **Config Server** | Global Load Balancer $\to$ Port 8888 | [http://34.160.42.139/actuator/health](http://34.160.42.139/actuator/health) | HTTP 200 OK |
| **Eureka Registry** | Platform VM Instance Direct | [http://34.44.99.62:8761](http://34.44.99.62:8761) | HTTP 200 OK |

---

## 🏛️ Domain Microservices Overview

This super-repository contains all domain microservices for the EduCloud enterprise course portal using Git submodules:

### Microservices (Git Submodules)
- **[User Service](https://github.com/bhanuka-viraj/user-service):** User, instructor, and student directory management backed by **GCP Cloud SQL MySQL** (`34.29.246.228:3306`, Port 8081).
- **[Course Service](https://github.com/bhanuka-viraj/course-service):** Rich course catalog, curriculum authoring, category filtering, and syllabus management backed by **MongoDB** (`35.254.57.189:27017`, Port 8082).
- **[Media Service](https://github.com/bhanuka-viraj/media-service):** File attachment, image streaming, and course thumbnail upload integrated with **Google Cloud Storage** (`gs://educloud-media-bucket-535026634701`, Port 8083).

---

## 🖥️ Compute Engine Multi-Zone Deployment

- **Managed Instance Group:** `educloud-services-mig`
- **Zones:** `us-central1-a`, `us-central1-b`
- **Instance Template:** `educloud-public-template-v1`
- **Named Ports:** `user:8081`, `course:8082`, `media:8083`
- **Service Discovery:** Automatic registration with Netflix Eureka Server on startup.
- **Process Manager:** PM2 daemon configured for automated startup, fault tolerance, and restart policies.

---

## 🛠️ Technology Stack
- Java 25 & Spring Boot 4.1.1
- Spring Cloud 2025.1.3 (Eureka Client, Actuator)
- Spring Data JPA / Hibernate / MySQL Connector
- Spring Data MongoDB
- Google Cloud Storage Client SDK
- PM2 Process Manager
- Google Cloud Platform (Compute Engine Multi-Zone MIGs, Cloud SQL, Cloud Storage)

---

## 💻 Local Development & Setup

```bash
# Clone super-repository with all submodules
git clone --recurse-submodules https://github.com/bhanuka-viraj/eca-backend-services.git
cd eca-backend-services

# Build all microservices
cd user-service && ./mvnw clean package && cd ..
cd course-service && ./mvnw clean package && cd ..
cd media-service && ./mvnw clean package && cd ..
```
