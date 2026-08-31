# 🚀 Project Ideas & Status

This document tracks the main projects in my **Java Backend Roadmap**, from foundational REST APIs to more complex and scalable backend systems.

Each project introduces new concepts while reinforcing practices learned in previous projects.

The goal is to prioritize **depth, engineering decisions, and progressive complexity** rather than simply increasing the number of completed projects.

---

# 🟢 Foundation Level

## Todo List API

**Status:** ✅ Completed — `v1.0.0`
**Tech:** Java + Spring Boot + PostgreSQL

### Main Features

* User registration and authentication
* JWT-based authentication
* Todo CRUD operations
* Todo status management
* User-specific resource access
* Input validation
* Pagination
* Global exception handling
* API documentation with Swagger/OpenAPI

### Engineering Practices

* Layered architecture
* DTOs
* Spring Data JPA
* BCrypt password hashing
* Unit tests
* Integration tests
* Docker containerization
* Continuous Integration with GitHub Actions
* Git branching workflow
* Semantic versioning
* Changelog and GitHub Releases

### Main Learning Outcome

Build and release a complete REST API while understanding the fundamental components of a modern Spring Boot backend application.

---

# 🟡 Intermediate Level

## URL Shortening Service

**Status:** 🚧 In Progress
**Tech:** Java + Spring Boot + PostgreSQL

### Planned Core Features

* Create shortened URLs
* Generate unique short codes
* Redirect short URLs to original URLs
* Persist URL mappings
* Validate URLs
* Handle invalid or unavailable short codes
* Track basic URL metadata

### Engineering Focus

* API contract design
* Domain modeling
* Short-code generation strategies
* Collision handling
* Database constraints
* Error handling
* Structured logging
* Automated testing
* Integration testing
* Configuration management
* Docker
* Continuous Integration
* API documentation

### Main Learning Outcome

Move beyond basic CRUD development by working with domain-specific logic, edge cases, reliability, and technical design decisions.

---

# 🔵 Advanced Level

## Scalable E-Commerce Platform

**Status:** ⏳ Planned
**Tech:** Java + Spring Boot ecosystem

### Planned Domains

* Users
* Products
* Inventory
* Shopping carts
* Orders
* Payments
* Order lifecycle

### Engineering Focus

The exact architecture and technologies will be defined as the project evolves, based on the problems that need to be solved.

Topics expected to be explored include:

* Modular architecture
* Advanced relational data modeling
* Transactions
* Data consistency
* Caching
* Asynchronous processing
* Messaging
* Observability
* Resilience
* Performance
* Scalability
* Security
* Containerization
* Deployment strategies

### Main Learning Outcome

Learn how backend architecture evolves when an application has multiple business domains, larger workloads, integration points, and stronger reliability requirements.

The project should begin with the simplest architecture that satisfies its requirements and evolve only when additional complexity is justified.

---

# 🗺️ Project Progression

| Level           | Project                      | Primary Focus                                                       | Status         |
| --------------- | ---------------------------- | ------------------------------------------------------------------- | -------------- |
| 🟢 Foundation   | Todo List API                | REST APIs, Spring Boot fundamentals, security, testing and delivery | ✅ Completed    |
| 🟡 Intermediate | URL Shortening Service       | Domain logic, reliability and engineering decisions                 | 🚧 In Progress |
| 🔵 Advanced     | Scalable E-Commerce Platform | Architecture, scalability and production-oriented backend design    | ⏳ Planned      |

---

# 🔄 Project Evolution

Projects do not necessarily end when their first stable version is released.

When justified, completed projects may receive improvements such as:

* Refactoring
* Additional automated tests
* Dependency updates
* Documentation improvements
* Performance improvements
* Security improvements
* Observability
* Architectural improvements

New features or technologies should be introduced when they solve a meaningful problem rather than only to increase the project's technical stack.

---

# 📌 Status Legend

* ⏳ **Planned** — Not started
* 🚧 **In Progress** — Currently under development
* ✅ **Completed** — Stable version released
* 🔄 **Evolving** — Completed project receiving meaningful improvements

---

# 🧠 Guiding Principle

> Each project should answer a new engineering question.

**Todo List API:**
Can I build, test, secure, document, containerize, and release a complete REST API?

**URL Shortening Service:**
Can I design and implement reliable backend behavior beyond conventional CRUD operations?

**Scalable E-Commerce Platform:**
Can I design a backend that remains maintainable and reliable as business rules, integrations, and scale increase?

The objective is to demonstrate **progressive backend engineering capability**, not simply a collection of frameworks and technologies.
