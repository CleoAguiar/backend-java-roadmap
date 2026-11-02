# 🎯 Learning Plan

This document defines my progression from **Java Backend Development** toward **System Architecture and Platform Engineering**.

The learning strategy is project-driven: each stage introduces a new class of engineering problems while reusing skills developed earlier.

## 🧭 Long-term progression

1. **Backend foundations** — build, test, secure, document, containerize, and release APIs.
2. **Microservices** — understand service boundaries, distributed communication, data consistency, and operational complexity.
3. **System Architecture** — reason about system-wide requirements, quality attributes, trade-offs, and scalability.
4. **Platform Engineering** — build reliable, automated platforms and improve developer experience.

---

# ✅ July–August 2026 — Backend Foundations

## Project milestone — Todo List API

**Status:** Completed — `v1.0.0`, published August 18, 2026.

Topics practiced:
- Java, object-oriented programming, HTTP, REST, and API contracts
- Spring Boot, dependency injection, and layered architecture
- JPA, Hibernate, PostgreSQL, and pagination
- JWT authentication, authorization, and resource ownership
- Validation and exception handling
- JUnit, Mockito, and integration tests
- Docker, GitHub Actions, OpenAPI, versioning, and releases

**Lifecycle:** design → implementation → persistence → security → testing → documentation → containerization → CI → release.

---

# ✅ September–October 2026 — Intermediate Backend Development

## Project milestone — URL Shortening Service

**Status:** Completed — `v1.0.0`, published October 30, 2026.

Topics practiced:
- Domain modeling and API contract design
- Short-code generation and URL mapping
- PostgreSQL and Flyway migrations
- Validation and global exception handling
- Automated tests
- Docker image and container workflow
- GitHub Actions CI workflow
- Documentation and release management

**Key progression:** moving beyond conventional CRUD endpoints and completing a second end-to-end backend delivery cycle.

---

# 🚧 November 2026 onward — Microservices with E-Commerce

## Main objective

Build the **Scalable E-Commerce Platform** to understand the architectural and operational challenges of microservices through practical business workflows.

The project is not a race to use many frameworks. First understand the business workflows and decide where independent services provide a meaningful benefit.

## Suggested learning sequence

### Stage 1 — Understand the domain and define boundaries
- Identify core business capabilities: catalog, inventory, cart, order, payment, and identity.
- Map the main user journeys, especially checkout.
- Define service responsibilities and ownership.
- Identify the data each service owns.
- Document boundaries and assumptions before implementation.

**Deliverable:** context diagram, service responsibility map, and initial API/event contracts.

### Stage 2 — Build the first services
- Create a small number of Spring Boot services.
- Give each service a clear responsibility.
- Define independent persistence ownership.
- Configure local development with Docker Compose.
- Add health checks, configuration, and service-level tests.

**Deliverable:** a working end-to-end flow across a deliberately small set of services.

### Stage 3 — Communication and integration
- Compare synchronous HTTP with asynchronous messaging.
- Define event schemas and message ownership.
- Implement a broker only when an asynchronous workflow requires it.
- Handle duplicate messages and idempotent consumers.
- Understand delivery guarantees and eventual consistency.

**Deliverable:** at least one business workflow that uses an asynchronous event safely.

### Stage 4 — Distributed data and reliability
- Understand why an ACID transaction cannot simply span independent databases.
- Explore Saga orchestration or choreography for a business workflow.
- Handle timeouts, retries, backoff, and circuit breakers.
- Design compensation and failure paths.
- Avoid retry storms and duplicate side effects.

**Deliverable:** documented failure scenarios and tested recovery behavior for order/checkout processing.

### Stage 5 — Observability and delivery
- Use structured logs with correlation identifiers.
- Collect service metrics and health information.
- Introduce distributed tracing.
- Build CI pipelines for the services.
- Run the system locally with repeatable container configuration.
- Document deployment and operational procedures.

**Deliverable:** a reproducible environment and enough telemetry to investigate a request across services.

### Stage 6 — Review architecture and trade-offs
- Compare the result with a modular monolith alternative.
- Identify operational overhead and duplicated concerns.
- Explain why each service boundary exists.
- Record important decisions as ADRs.
- Identify what should be simplified.

**Deliverable:** architecture overview, ADRs, and project retrospective.

## Concepts to understand—not just implement

- Bounded contexts and service boundaries
- Database per service and data ownership
- Synchronous vs. asynchronous communication
- Messaging, events, and eventual consistency
- Idempotency and duplicate delivery
- Saga pattern and compensating actions
- Timeouts, retries, circuit breakers, and bulkheads
- API Gateway and service discovery
- Centralized logging, metrics, and distributed tracing
- Deployment independence and operational complexity

## Scope guardrails

- Start with a small number of services; do not create one service per database table.
- Do not introduce Kubernetes before Docker Compose and service operation are understood.
- Choose RabbitMQ or Kafka based on the messaging requirements; do not adopt both by default.
- Avoid distributed transactions where eventual consistency is sufficient.
- Keep security, tests, documentation, and CI in scope from the beginning.
- Record trade-offs and alternatives, including when a modular monolith would be simpler.

---

# ⏳ Later stage — System Architecture

After the microservices project, shift from implementing individual services to reasoning about whole systems.

Study:
- Functional and non-functional requirements
- Quality attributes and architectural trade-offs
- Capacity estimation and bottleneck analysis
- Availability, scalability, and fault tolerance
- Caching, data partitioning, replication, and consistency
- Architecture styles and integration patterns
- Architecture Decision Records
- System design diagrams and technical communication

**Expected outcome:** explain and defend architecture decisions based on requirements and trade-offs, not technology preference.

---

# ⏳ Later stage — Platform Engineering

Build on backend and distributed-systems knowledge to understand how teams build, deploy, and operate software at scale.

Study:
- Linux, networking, and troubleshooting
- Containers and Kubernetes
- Infrastructure as Code
- GitOps
- CI/CD platform design
- Observability and SRE practices
- Secrets and configuration management
- Developer experience and Internal Developer Platforms
- Security, governance, and automation

**Expected outcome:** understand how to provide reusable, secure, observable paths for development teams to deliver software.

---

# 🧭 Learning Principles

1. **Build before adding complexity.** Start with the simplest architecture that meets the requirements.
2. **Understand before abstracting.** Introduce patterns and technologies to solve observed problems.
3. **Test important behavior.** Prioritize business rules, security boundaries, integration points, and failure paths.
4. **Document engineering decisions.** Record alternatives, trade-offs, and reasons.
5. **Treat operations as part of development.** Logging, configuration, containers, CI, debugging, and deployment matter.
6. **Prefer depth over project count.** A well-designed and explained project is more valuable than superficial technology coverage.
7. **Compare alternatives.** Be able to explain why a modular monolith, synchronous call, or simpler deployment might be preferable.

## 🔁 Weekly review

- What did I learn and implement without guidance?
- What was difficult, and how did I investigate it?
- Which concepts can I explain without looking at code?
- What trade-off did I make, and what alternative did I reject?
- What should I review or simplify?

## 🏁 Project retrospective

- What new engineering problems did this project introduce?
- Which decisions could I explain in an interview?
- What failure scenarios did I test?
- What operational complexity did I add?
- Would a simpler architecture have worked?
- What should I carry into the next stage?

## 📊 Roadmap Status

| Stage | Project / Focus | Status |
| --- | --- | --- |
| Foundation | Todo List API | ✅ Completed — `v1.0.0` |
| Intermediate | URL Shortening Service | ✅ Completed — `v1.0.0` |
| Advanced | Scalable E-Commerce Platform / Microservices | 🚧 Next |
| Future | System Architecture | ⏳ Planned |
| Future | Platform Engineering | ⏳ Planned |

> The goal is not to collect technologies. The goal is to become capable of **designing, building, testing, debugging, and evolving reliable systems—and understanding the platforms that deliver them**.
