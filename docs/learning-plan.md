# 🎯 Learning Plan

This document defines my study direction and practical goals as I progress toward becoming a **Java Backend Developer**.

The focus is not only on learning technologies, but also on applying them through increasingly complex backend projects, following good software engineering practices.

---

# 🗓️ July–August 2026 — Backend Foundations

## Main Goals

* Strengthen Java fundamentals
* Learn REST API development with Spring Boot
* Understand layered backend architecture
* Work with relational databases and persistence
* Implement authentication and authorization
* Practice automated testing
* Learn Docker fundamentals
* Apply Git and GitHub workflows
* Build and publish the first portfolio project

---

## Topics Covered

### ☕ Java & Backend Fundamentals

* Object-Oriented Programming
* HTTP methods and status codes
* REST API principles
* Exception handling
* Input validation
* DTOs and data mapping

### 🌱 Spring Boot

* Controllers
* Services
* Repositories
* Dependency Injection
* Spring Data JPA
* Application configuration

### 🗄️ Persistence

* JPA & Hibernate
* PostgreSQL
* Entity modeling
* Repository pattern
* Pagination

### 🔐 Security

* Authentication and authorization
* JWT
* Password hashing with BCrypt
* Stateless authentication
* Resource ownership and access control

### 🧪 Testing

* Unit testing
* Integration testing
* JUnit
* Mockito
* Authorization scenarios

### 🐳 Delivery & Tooling

* Docker
* Maven
* Git and GitHub
* Branching workflow
* GitHub Actions
* API documentation with Swagger/OpenAPI
* Semantic versioning
* Changelog and GitHub Releases

---

## 🏁 Project Milestone — Todo List API

The first portfolio project was completed and released as **v1.0.0**.

The project provided practical experience with the complete development lifecycle of a backend API:

**design → implementation → persistence → security → testing → documentation → containerization → CI → release**

### Outcome

* REST API built with Java and Spring Boot
* PostgreSQL persistence
* JWT authentication and authorization
* Automated tests
* Swagger/OpenAPI documentation
* Docker containerization
* Continuous Integration with GitHub Actions
* Versioned release published on GitHub

---

# 🗓️ September 2026 — Intermediate Backend Development

## Main Goal

Build the **URL Shortening Service** while moving beyond basic CRUD development and focusing more on application design, data modeling, reliability, and engineering decisions.

---

## Week 1 — Project Foundation & Domain Design

* Define functional and non-functional requirements
* Design the URL shortening domain
* Define API contracts
* Model persistence entities
* Configure Spring Boot and PostgreSQL
* Establish project structure
* Prepare development environment

### Focus

> Understand the problem before implementing the solution.

---

## Week 2 — Core URL Shortening

* Create shortened URLs
* Implement short-code generation
* Store URL mappings
* Redirect short URLs
* Validate URLs
* Handle invalid and expired resources
* Improve exception handling

### Focus

> Build a clean and reliable core domain.

---

## Week 3 — Reliability & Quality

* Implement automated tests
* Add integration tests
* Review edge cases
* Handle short-code collisions
* Improve validation
* Add structured logging
* Review application configuration

### Focus

> Make the application predictable, testable, and easier to troubleshoot.

---

## Week 4 — Delivery & Release

* Containerize the application
* Configure CI with GitHub Actions
* Document the API with Swagger/OpenAPI
* Improve project documentation
* Review code and architecture
* Prepare changelog
* Publish release `v1.0.0`

### Focus

> Treat deployment and release as part of software development.

---

# 🔭 Next Phase — Advanced Backend Foundations

After completing the URL Shortening Service, the next project will be a **Scalable E-Commerce Platform**.

The goal will be to gradually introduce more advanced backend and system design concepts, including:

* Modular application design
* Advanced database modeling
* Transactions and consistency
* Caching
* Asynchronous processing
* Messaging
* Observability
* Performance
* Scalability
* Resilience
* API design at larger scale
* Deployment and operational concerns

The focus should remain on understanding **why and when** these techniques are useful rather than adding technologies only for complexity.

---

# 🧭 Learning Principles

Throughout the roadmap:

1. **Build before adding complexity**
   Start with the simplest architecture that correctly solves the problem.

2. **Understand before abstracting**
   Avoid introducing patterns or technologies without understanding the problem they solve.

3. **Test important behavior**
   Prioritize business rules, security boundaries, edge cases, and integration points.

4. **Document engineering decisions**
   Record important architectural and technical choices when they improve understanding of the project.

5. **Treat operations as part of backend development**
   Logging, configuration, containers, CI, debugging, and deployment are part of building reliable applications.

6. **Prefer depth over project count**
   A well-designed and documented project is more valuable than several superficial implementations.

---

# 🔁 Review Strategy

At the end of each week, review:

* What did I learn?
* What did I implement without guidance?
* What was difficult?
* What concepts do I understand better now?
* What still needs review?
* What technical decision did I make and why?
* What would I improve if I implemented it again?

At the end of each project, review:

* What new backend concepts did this project introduce?
* Which decisions could I explain in a technical interview?
* Which problems required debugging or investigation?
* What trade-offs did I encounter?
* What would need to change if the application had significantly more users?
* What should I carry forward into the next project?

---

# 🚀 Roadmap

| Phase        | Project                      | Main Focus                                                            | Status               |
| ------------ | ---------------------------- | --------------------------------------------------------------------- | -------------------- |
| Foundation   | Todo List API                | REST, Spring Boot, persistence, security, testing and delivery        | ✅ Completed — v1.0.0 |
| Intermediate | URL Shortening Service       | Application design, reliability and deeper backend practices          | 🚧 In Progress       |
| Advanced     | Scalable E-Commerce Platform | Scalability, distributed systems and production-oriented architecture | ⏳ Planned            |

---

> The goal is not to collect technologies.
> The goal is to progressively become capable of **designing, building, testing, debugging, and evolving reliable backend systems**.
