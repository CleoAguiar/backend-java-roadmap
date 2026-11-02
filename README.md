# Backend Java Roadmap

![Java](https://img.shields.io/badge/Java-25-orange)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-Portfolio-brightgreen)
![Roadmap](https://img.shields.io/badge/Roadmap-In_Progress-blue)
![Portfolio](https://img.shields.io/badge/Portfolio-2%20Projects%20Released-success)

This repository documents my journey in **Java Backend Development**, combining structured learning with practical projects of increasing complexity.

The progression is intentional: **Backend Foundations → Microservices → System Architecture → Platform Engineering**.

## 🎯 Goals

- Build production-oriented backend applications with Java and Spring Boot
- Design RESTful APIs and maintainable application architectures
- Practice testing, security, relational databases, caching, and messaging
- Containerize applications and automate delivery with CI/CD
- Understand distributed systems, reliability, and observability
- Progress toward System Architecture and Platform Engineering

## 🛠 Tech Stack

- Java 25, Spring Boot, Maven
- Spring Data JPA / Hibernate, Spring Security
- PostgreSQL, Redis
- JUnit, Mockito, Testcontainers
- Docker and Docker Compose
- Git and GitHub Actions
- OpenAPI / Swagger
- Future topics: RabbitMQ or Kafka, OpenTelemetry, Kubernetes, IaC, and GitOps

---

## 🗺️ Roadmap

### 1. Foundation — [Todo List API](https://github.com/CleoAguiar/todo-list-api) — **Completed**

A REST API that allows authenticated users to manage their own tasks.

**Implemented:**
- CRUD operations and REST API design
- JWT authentication and authorization
- User resource isolation
- Validation, global error handling, and pagination
- PostgreSQL persistence
- Unit and integration tests
- OpenAPI / Swagger documentation
- Docker containerization
- CI with GitHub Actions
- Versioning and release management

**Release:** `v1.0.0` — published August 18, 2026.

**Additional links:** [roadmap.sh solution](https://roadmap.sh/projects/todo-list-api/solutions?u=6a3b28a65d8dee437edeeda3) · [LinkedIn project post](https://lnkd.in/p/dzAn5YMJ)

### 2. Intermediate — [URL Shortening Service](https://roadmap.sh/projects/url-shortening-service) — **Completed**

A service that generates short URLs, redirects users to original addresses, and manages URL mappings.

**Implemented and practiced:**
- Java and Spring Boot REST API
- PostgreSQL persistence and Flyway migrations
- Domain modeling and short-code generation
- URL validation and global exception handling
- Automated tests
- Docker
- CI with GitHub Actions
- API documentation and release workflow

**Release:** `v1.0.0` — published October 29, 2026.

**Additional links:** [roadmap.sh solution](https://roadmap.sh/projects/url-shortening-service/solutions?u=6a3b28a65d8dee437edeeda3) · [LinkedIn project post](https://lnkd.in/p/d5b7sfvv)

### 3. Advanced — [Scalable E-Commerce Platform](https://roadmap.sh/projects/scalable-ecommerce-platform) — **Next project**

Build an e-commerce platform to understand **microservices architecture** through practical business workflows.

**Candidate domains:** catalog, inventory, cart, orders, payments, and users/identity.

**Learning focus:**
- Service boundaries and domain decomposition
- Independent data ownership
- Synchronous communication and API contracts
- Asynchronous communication and event-driven architecture
- Messaging and eventual consistency
- Distributed transactions and the Saga pattern
- Idempotency, retries, timeouts, and resilience
- API Gateway and service discovery, when justified
- Centralized logs, metrics, and distributed tracing
- Docker Compose, CI/CD, and deployment

The goal is to understand the trade-offs of microservices—not to split an application into services just to use more technologies. Start small and introduce infrastructure only when it solves a concrete problem.

### 4. Future — System Architecture

After practical experience with distributed applications, deepen knowledge of:
- Requirements and quality attributes
- Architecture styles and trade-offs
- Capacity estimation and bottleneck analysis
- Scalability, availability, and fault tolerance
- Data architecture and consistency
- Architecture Decision Records (ADRs)
- System design communication and technical documentation

### 5. Future — Platform Engineering

Build on backend and distributed-systems knowledge:
- Linux and networking foundations
- Containers and Kubernetes
- Infrastructure as Code
- GitOps and deployment automation
- CI/CD platform design
- Observability and reliability practices
- Developer experience and Internal Developer Platforms
- Security, governance, and operational standards

---

## 📦 Portfolio Status

| Stage | Project / Focus | Status |
| --- | --- | --- |
| Foundation | Todo List API | ✅ Completed — `v1.0.0` |
| Intermediate | URL Shortening Service | ✅ Completed — `v1.0.0` |
| Advanced | Scalable E-Commerce Platform | 🚧 Next project |
| Future | System Architecture | ⏳ Planned |
| Future | Platform Engineering | ⏳ Planned |

## 📁 Repository Purpose

This repository is the central hub for the learning roadmap. Each practical project has its own GitHub repository containing source code, technical documentation, architecture decisions, setup instructions, tests, CI/CD workflows, and releases.

## 📈 Progress

**Started:** July 2026

**Completed**
- Todo List API — `v1.0.0` (August 18, 2026)
- URL Shortening Service — `v1.0.0` (October 29, 2026)

**Current focus**
- Consolidate lessons from the first two backend projects
- Design and implement the Scalable E-Commerce Platform
- Learn microservices through real business workflows and explicit trade-offs

**Later**
- System Architecture
- Platform Engineering

## 🔗 Connect

- [GitHub](https://github.com/CleoAguiar)
- [LinkedIn](https://www.linkedin.com/in/cleoaguiar/)
- [roadmap.sh Backend](https://roadmap.sh/backend)
