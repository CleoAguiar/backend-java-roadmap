# 📚 Study Notes

This document contains notes, concepts, commands, and lessons learned throughout my **Java Backend Roadmap**.

The goal is to build a personal knowledge base that helps me:

* consolidate what I learn
* review important backend concepts
* document practical lessons from projects
* remember useful commands and patterns
* prepare for technical discussions and interviews

> This is a living document. Topics should evolve as I encounter them in real projects.

---

# ☕ Java

## Object-Oriented Programming

### Encapsulation

Keep an object's internal state protected and expose behavior through controlled interfaces.

### Inheritance

Allows a class to reuse and extend behavior from another class.

Use inheritance when there is a meaningful **is-a** relationship rather than only for code reuse.

### Polymorphism

Allows different implementations to be accessed through a common abstraction.

### Abstraction

Expose relevant behavior while hiding unnecessary implementation details.

---

## Collections

Important interfaces:

* `List` — ordered collection that allows duplicates
* `Set` — collection of unique elements
* `Map` — key-value associations

Common implementations:

* `ArrayList`
* `HashSet`
* `HashMap`

### Review

* Choosing the appropriate collection
* `equals()` and `hashCode()`
* Immutable collections
* Iteration and Stream API

---

# 🌐 HTTP & REST

## HTTP Methods

| Method   | Typical Use                               |
| -------- | ----------------------------------------- |
| `GET`    | Retrieve a resource                       |
| `POST`   | Create a resource or trigger an operation |
| `PUT`    | Replace or update a resource              |
| `PATCH`  | Partially update a resource               |
| `DELETE` | Remove a resource                         |

---

## Common HTTP Status Codes

| Status                      | Meaning                                         |
| --------------------------- | ----------------------------------------------- |
| `200 OK`                    | Request succeeded                               |
| `201 Created`               | Resource created                                |
| `204 No Content`            | Request succeeded without response body         |
| `400 Bad Request`           | Invalid request                                 |
| `401 Unauthorized`          | Authentication required or invalid              |
| `403 Forbidden`             | Authenticated client cannot access the resource |
| `404 Not Found`             | Resource does not exist                         |
| `409 Conflict`              | Request conflicts with current resource state   |
| `500 Internal Server Error` | Unexpected server error                         |

### Important Distinction

`401` and `403` represent different situations:

* **401** → authentication is missing or invalid
* **403** → authentication succeeded, but access is not allowed

---

## REST Principles

A REST API should model resources and use HTTP semantics consistently.

Example:

```text
POST   /todos
GET    /todos
GET    /todos/{id}
PUT    /todos/{id}
DELETE /todos/{id}
```

Prefer resource-oriented URLs instead of action-oriented URLs when possible.

```text
GET /todos/10
```

instead of:

```text
GET /getTodo/10
```

---

## JSON

JSON is commonly used to represent request and response bodies in REST APIs.

Example:

```json
{
  "title": "Study Spring Boot",
  "description": "Review dependency injection",
  "status": "IN_PROGRESS"
}
```

---

# 🌱 Spring Boot

## Layered Architecture

A common structure:

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
Database
```

### Controller

Responsible for the HTTP layer:

* receiving requests
* validating request data
* delegating business operations
* returning appropriate responses

### Service

Contains application and business logic.

It should coordinate operations without depending on HTTP-specific concerns.

### Repository

Responsible for persistence operations.

Spring Data JPA can generate common repository implementations automatically.

---

## Dependency Injection

Instead of creating dependencies manually:

```java
TodoService service = new TodoService();
```

dependencies are provided by the Spring container.

Constructor injection makes dependencies explicit and improves testability.

```java
public TodoController(TodoService todoService) {
    this.todoService = todoService;
}
```

---

## DTOs

DTOs separate the external API contract from internal persistence models.

Typical examples:

```text
TodoRequest
TodoResponse
UserRegisterRequest
UserResponse
```

Benefits:

* control exposed fields
* separate API and database models
* apply request validation
* avoid exposing entities directly
* make API contracts clearer

---

# 🗄️ Persistence

## JPA

JPA defines APIs and rules for object-relational persistence in Java.

## Hibernate

Hibernate is an ORM framework and a commonly used JPA implementation.

A useful distinction:

```text
JPA → specification/API
Hibernate → implementation
```

---

## Repository

Spring Data JPA repositories reduce repetitive persistence code.

Example:

```java
public interface TodoRepository extends JpaRepository<Todo, Long> {
}
```

---

## PostgreSQL

PostgreSQL is the relational database used for persistent application data in the portfolio projects.

### Topics to Review

* Primary keys
* Foreign keys
* Unique constraints
* Indexes
* Transactions
* Relationships
* Query performance

---

# 🔐 Authentication & Authorization

## Authentication

Answers:

> Who is making this request?

Example:

```text
username + password
        ↓
authentication
        ↓
authenticated user
```

---

## Authorization

Answers:

> Is this user allowed to perform this operation?

Authentication does not automatically imply authorization.

A user can be correctly authenticated but still be forbidden from accessing another user's resource.

---

## JWT

JWT stands for **JSON Web Token**.

A token is composed of three encoded parts:

```text
header.payload.signature
```

### Important

A signed JWT provides integrity and authenticity when its signature is correctly verified.

Its payload is encoded, **not encrypted by default**.

Sensitive information should therefore not be placed in the token simply because JWT is being used.

---

## Stateless Authentication

With stateless authentication, the server does not need to maintain a traditional login session for each authenticated client.

The client sends its token with requests:

```text
Authorization: Bearer <token>
```

The backend validates the token before allowing access to protected resources.

---

## BCrypt

Passwords should not be stored as plaintext.

BCrypt produces password hashes and incorporates a salt as part of the hashing process.

Typical flow:

```text
Password
   ↓
BCrypt
   ↓
Password Hash
   ↓
Database
```

Authentication compares the submitted password against the stored hash.

---

# ✅ Validation & Error Handling

## Validation

Validate incoming data before executing business operations.

Common Bean Validation annotations:

```java
@NotNull
@NotBlank
@Size
@Email
@Min
@Max
```

Example:

```java
@NotBlank
@Size(max = 100)
private String title;
```

---

## Global Exception Handling

Centralized exception handling helps maintain consistent API error responses.

Spring provides:

```java
@RestControllerAdvice
```

and:

```java
@ExceptionHandler
```

This avoids duplicating error-handling logic across controllers.

---

# 🧪 Testing

## Unit Tests

Test a small unit of behavior in isolation.

Dependencies are commonly mocked.

Typical tools:

* JUnit
* Mockito

Example structure:

```text
Given → initial conditions
When  → operation
Then  → expected result
```

---

## Integration Tests

Verify that multiple application components work together.

Examples:

* HTTP request → controller → service → repository
* authentication flow
* authorization rules
* persistence behavior

---

## What Should Be Tested?

Prioritize:

* business rules
* validation
* authentication
* authorization
* ownership rules
* error scenarios
* important edge cases

The objective is not simply to maximize test count or coverage.

---

# 🐳 Docker

Docker packages an application and its runtime dependencies into a container image.

Basic concepts:

```text
Dockerfile
    ↓
Image
    ↓
Container
```

### Build Image

```bash
docker build -t application-name .
```

### Run Container

```bash
docker run -p 8080:8080 application-name
```

### List Running Containers

```bash
docker ps
```

### Stop Container

```bash
docker stop <container-id>
```

---

# ⚙️ Continuous Integration

CI automatically validates changes pushed to the repository.

Typical pipeline:

```text
Push / Pull Request
        ↓
GitHub Actions
        ↓
Checkout
        ↓
Setup Java
        ↓
Maven
        ↓
Tests
        ↓
Build verification
```

A successful pipeline provides confidence that the project can be built and its automated checks pass in a clean environment.

---

# 🌿 Git & GitHub

## Branching Workflow

Current workflow:

```text
main
  ↑
develop
  ↑
feature / fix / chore / docs / test branches
```

### Commit Convention

Examples:

```text
feat: add URL creation endpoint
fix: handle invalid short codes
test: add redirect integration tests
docs: update API documentation
refactor: simplify URL mapping logic
chore: configure development environment
```

---

## Semantic Versioning

Version format:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
v1.0.0
```

General meaning:

* `MAJOR` → incompatible changes
* `MINOR` → backward-compatible functionality
* `PATCH` → backward-compatible fixes

---

# 📦 Release Process

A stable project release may include:

```text
Complete milestone
      ↓
Review code
      ↓
Run tests
      ↓
Review documentation
      ↓
Update changelog
      ↓
Merge into main
      ↓
Create version tag
      ↓
Publish GitHub Release
```

---

# 🛠️ Useful Commands

## Maven

Run tests:

```bash
mvn test
```

Run full project verification:

```bash
mvn verify
```

Clean and build:

```bash
mvn clean install
```

Run Spring Boot:

```bash
mvn spring-boot:run
```

---

## Git

Check repository status:

```bash
git status
```

Create and switch to a branch:

```bash
git switch -c <branch-name>
```

Switch branches:

```bash
git switch <branch-name>
```

Update local branch:

```bash
git pull
```

View commit history:

```bash
git log --oneline
```

---

# 🧩 Lessons From Projects

## Todo List API

### What I Practiced

* Building a complete REST API
* Separating responsibilities between application layers
* Persisting data with PostgreSQL
* Implementing JWT authentication
* Protecting user-specific resources
* Writing unit and integration tests
* Documenting an API
* Containerizing an application
* Creating a CI pipeline
* Publishing a stable release

### Important Lessons

**Security is more than authentication.**
Authenticating a user does not guarantee that the user should have access to every resource.

**Testing should verify behavior, not only successful requests.**
Authorization failures, validation errors, and resource ownership are important scenarios.

**Delivery is part of development.**
Docker, CI, documentation, versioning, and releases are part of producing a usable backend application.

**Finishing a project exposes different problems from starting one.**
Documentation, configuration, testing, packaging, and release preparation require attention beyond feature implementation.

---

## URL Shortening Service

### Current Focus

* Domain modeling
* API design
* URL mapping
* Short-code generation
* Persistence design

### Lessons Learned

*To be updated as the project evolves.*

---

# 🔍 Troubleshooting Notes

Use this section to record meaningful problems encountered during development.

For each problem, document:

```text
Problem:
Symptoms:
Initial hypothesis:
Investigation:
Root cause:
Solution:
What I learned:
```

The goal is to improve systematic debugging instead of only recording the final fix.

---

# 🔁 Things to Review

## Java

* [ ] Collections and their trade-offs
* [ ] `equals()` and `hashCode()`
* [ ] Streams
* [ ] Exceptions

## Spring

* [ ] Spring dependency injection lifecycle
* [ ] Spring Security request flow
* [ ] Transaction management
* [ ] Application configuration and profiles

## Database

* [ ] Transactions
* [ ] Indexes
* [ ] Constraints
* [ ] Entity relationships
* [ ] Query performance

## Testing

* [ ] Mockito fundamentals
* [ ] Test isolation
* [ ] Integration testing strategies
* [ ] Testcontainers

## Backend Engineering

* [ ] Logging strategies
* [ ] Configuration management
* [ ] API idempotency
* [ ] Caching fundamentals
* [ ] Observability fundamentals

---

# 🧠 Review Questions

I should be able to explain, without relying only on code:

* What happens when an HTTP request reaches my Spring Boot application?
* What is the difference between authentication and authorization?
* Why use DTOs instead of exposing entities directly?
* What is the difference between JPA and Hibernate?
* What is the difference between `401` and `403`?
* Why should passwords be hashed?
* What information does a JWT signature protect?
* What is the difference between unit and integration tests?
* Why use database constraints in addition to application validation?
* What problem does Docker solve?
* What does the CI pipeline protect against?
* How would I investigate an API that suddenly started returning errors?
* What would I change if the application needed to handle significantly more traffic?
