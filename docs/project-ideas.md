# 🚀 Project Ideas & Status

This document tracks the practical projects in my roadmap and the engineering questions each one should answer.

The progression is intentional: **complete backend applications → distributed applications → system-wide architecture → platforms for software delivery**.

---

# 🟢 Foundation Level

## Todo List API

**Status:** ✅ Completed — `v1.0.0` (August 18, 2026)  
**Tech:** Java + Spring Boot + PostgreSQL

### Main Features
- User registration and authentication
- JWT-based authentication
- Todo CRUD operations and status management
- User-specific resource access
- Input validation, pagination, and global exception handling
- API documentation with Swagger/OpenAPI

### Engineering Practices
- Layered architecture and DTOs
- Spring Data JPA
- BCrypt password hashing
- Unit and integration tests
- Docker containerization
- CI with GitHub Actions
- Git workflow, semantic versioning, changelog, and GitHub Releases

### Main Learning Outcome
Build, test, secure, document, containerize, and release a complete REST API.

---

# 🟡 Intermediate Level

## URL Shortening Service

**Status:** ✅ Completed — `v1.0.0` (October 30, 2026)  
**Tech:** Java + Spring Boot + PostgreSQL

### Implemented / Practiced
- REST API and URL mapping
- Short-code generation
- PostgreSQL persistence and Flyway migrations
- Domain modeling
- URL validation and global exception handling
- Automated tests
- Docker
- GitHub Actions CI
- API documentation and release workflow

### Main Learning Outcome
Move beyond basic CRUD by implementing domain-specific behavior, handling edge cases, and completing a reliable delivery workflow.

---

# 🔵 Advanced Level — Next Project

## Scalable E-Commerce Platform

**Status:** 🚧 Next project  
**Architecture focus:** Microservices  
**Tech direction:** Java + Spring Boot ecosystem

### Learning Objective

Understand when and why a system may be decomposed into independently deployable services, and learn the trade-offs this creates in communication, data consistency, testing, deployment, and operations.

### Candidate Business Domains
- Product catalog
- Inventory
- Shopping cart
- Orders
- Payments
- Users / identity

These are candidate boundaries, not a requirement to create six services immediately. Boundaries should emerge from business capabilities, data ownership, and workflow requirements.

### Suggested Implementation Progression

#### 1. Domain and boundaries
- Map the main business workflows.
- Define service responsibilities and data ownership.
- Identify invariants and consistency requirements.
- Draw a context diagram and service interaction map.

#### 2. Service implementation
- Implement a small initial set of Spring Boot services.
- Define explicit API contracts.
- Give each service ownership of its data.
- Use Docker Compose for local orchestration.
- Add health checks and service-level tests.

#### 3. Communication
- Use synchronous HTTP where an immediate response is required.
- Introduce asynchronous messaging for decoupled workflows.
- Select RabbitMQ or Kafka based on the problem and learning goals.
- Handle duplicate events and make consumers idempotent.

#### 4. Distributed workflows
- Understand eventual consistency.
- Explore Saga orchestration or choreography.
- Implement compensating actions for failed workflows.
- Apply timeouts, retries with backoff, and circuit breakers.

#### 5. Observability and delivery
- Structured logs and correlation IDs
- Metrics and health checks
- Distributed tracing
- CI workflows for each service
- Repeatable local environment and deployment documentation

### Constraints and Non-Goals
- Do not split every entity or table into a service.
- Do not use microservices merely to make the project look advanced.
- Do not introduce Kubernetes before understanding containers and local orchestration.
- Do not adopt multiple brokers without a concrete reason.
- Keep the architecture small enough to explain and operate.

### Main Learning Outcome
Explain the benefits and costs of microservices, design service boundaries, implement communication and failure handling, and observe a distributed workflow end to end.

---

# 🧭 Future Learning Stages

## System Architecture

**Status:** ⏳ Planned — after the E-Commerce project

Focus:
- Functional and non-functional requirements
- Quality attributes and trade-offs
- Scalability, availability, and fault tolerance
- Capacity estimation and bottleneck analysis
- Data replication, partitioning, caching, and consistency
- Architecture styles and integration patterns
- Architecture Decision Records (ADRs)
- System design documentation and communication

**Learning outcome:** design and defend system-level architecture based on requirements, constraints, and trade-offs.

## Platform Engineering

**Status:** ⏳ Planned — after strengthening architecture foundations

Focus:
- Linux and networking
- Containers and Kubernetes
- Infrastructure as Code
- GitOps and CI/CD platform design
- Observability and reliability
- Secrets and configuration management
- Developer experience
- Internal Developer Platforms
- Automation, security, and governance

**Learning outcome:** understand how to build and operate reusable platforms that help development teams deliver software safely and efficiently.

---

# 🗺️ Project Progression

| Stage | Project / Focus | Primary question | Status |
| --- | --- | --- | --- |
| Foundation | Todo List API | Can I deliver a complete, secure REST API? | ✅ Completed |
| Intermediate | URL Shortening Service | Can I implement reliable domain behavior and delivery? | ✅ Completed |
| Advanced | Scalable E-Commerce Platform | Can I build and operate workflows across services? | 🚧 Next |
| Future | System Architecture | Can I reason about and defend system-wide trade-offs? | ⏳ Planned |
| Future | Platform Engineering | Can I create reliable paths for teams to build and deliver software? | ⏳ Planned |

---

# 🔄 Project Evolution

A project may evolve after its first stable release when there is a meaningful reason:
- Refactoring and maintainability
- Additional automated tests
- Dependency and security updates
- Documentation improvements
- Performance improvements
- Observability
- Architectural improvements

New features and technologies should solve a real problem or reinforce a learning objective.

---

# 📌 Status Legend

- ⏳ **Planned** — Not started
- 🚧 **In Progress / Next** — Current focus or next project
- ✅ **Completed** — Stable version released
- 🔄 **Evolving** — Completed project receiving meaningful improvements

---

# 🧠 Guiding Principle

> Each project should answer a new engineering question.

**Todo List API:** Can I build, test, secure, document, containerize, and release a complete REST API?

**URL Shortening Service:** Can I design and implement reliable backend behavior beyond conventional CRUD operations?

**Scalable E-Commerce Platform:** Can I design service boundaries and operate business workflows across independently deployable services?

**System Architecture:** Can I choose and defend system-wide design decisions based on requirements and trade-offs?

**Platform Engineering:** Can I make software delivery more reliable, repeatable, and efficient for development teams?

The objective is to demonstrate **progressive engineering capability**, not simply a collection of frameworks.
