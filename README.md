# Backend Developer Learning Roadmap

This repository serves as a comprehensive learning roadmap for aspiring backend developers. It includes checklists covering general knowledge, best practices, Python proficiency, collaborative tools, and design principles. Use this roadmap to guide your learning journey, track your progress, and enhance your skills in backend development.

The repository is going to be updated as my knowledge about backend world improves.

Feel free to fork and customize this roadmap based on your preferences and career goals by forking this repository and editing the `README.md` file.

>[!IMPORTANT]
>The repository contains:
>
> * A beginner guide to foundational concepts and basic backend development skills.
> * An intermediate guide focusing on more advanced backend topics and specialized areas.
> * An advanced guide covering expert-level concepts, performance optimization, and architectural design considerations.
>
> Each guide opens with a **Recommended Path** ("if you only do ten things, do these") and a **portfolio project**, so the checklists translate into an actionable plan. A "what you're expected to *do*, not just know" note per level helps you self-place.

## Contents

### 🌱 Beginner Level

Located [here!](1_Beginner_Guide.md).

* **General Knowledge and Best Practices**: Foundational Concepts, Coding Standards and Best Practices, Command Line and Scripting.
* **Database Management**: Database Basics, Writing SQL, DDL & Constraints, Transactions, Indexes, PostgreSQL Types, The ORM Boundary, Connections, Database Design.
* **Version Control and Collaboration**: Basic concepts of version control, Git commands.
* **Python Knowledge**: Core Python, Type Hints and Static Typing, Environment Setup (`pyproject.toml`, uv, Ruff, pre-commit, Python versions).
* **Web Fundamentals**: HTTP, REST in Practice, Client Tooling, TLS/HTTPS, DNS, Ports/Sockets/Linux Basics, Serialization Formats.
* **Web Services**: APIs and Web Services.

**Portfolio project**: a CRUD API with authentication, a PostgreSQL database and a test suite, deployed publicly.

### 🚀 Intermediate Level

Located [here!](2_Intermediate_Guide.md).

* **General Knowledge and Best Practices**: Debugging.
* **Database Management**: Database Backup and Recovery, Database Migration, Database Indexing, Time Series Databases, Search Engines.
* **Version Control and Collaboration**: Deepen understanding of Git, Git Flow, Semantic Versioning, Code Reviews.
* **Python Knowledge**: Object-Oriented Programming (OOP), Python Standard Library, Libraries, Error Handling, Frameworks, Documentation, Generators, Decorators, Data Classes.
* **Testing and Quality Assurance**: pytest in Depth, Real Dependencies with Testcontainers, Test Doubles, API Testing, Property-Based Testing, Contract Testing, Coverage, Test Pyramid & Flakiness, Load Testing.
* **Asynchronous Programming**: Event Loop Mental Model, `def` vs `async def` in FastAPI, Structured Concurrency, Concurrency Primitives, Async I/O Clients, ASGI, Streaming Responses, Debugging Async.
* **Running Services in Production**: 12-Factor App, Configuration Management, Lifecycle, Process Model, Container Images, Reverse Proxy/Ingress, Where to Run It, Environments.
* **Web Services**: Services and Microservices.
* **Caching, Queues and Background Work**: Redis/Valkey, Caching Patterns, Failure Modes, Rate Limiting & Idempotency, Task Queues, Brokers, Reliability Patterns, Transactional Outbox, Scheduling, Worker Observability.
* **Containerization and Orchestration**: Docker Basics, Docker Compose, Kubernetes Fundamentals.
* **Design Knowledge**: Design Principles, MVC, Monolithic, Microservices, Design Patterns, Domain Driven Design, API Versioning.
* **CI/CD Pipelines**: GitHub Actions, GitLab CI, Building Docker Images in CI/CD, Jenkins (legacy).
* **Observability**: The Three Signals, Structured Logging, OpenTelemetry in Python, Metrics That Matter, Health and Readiness, Error Tracking, Dashboards and Alerts, Cost Awareness.
* **Security Practices**: Web Security Basics, OWASP Top 10, OWASP API Security Top 10, Authentication (OAuth 2.1/OIDC, JWT), Authorization (RBAC/ABAC/ReBAC), Secret Management, Secure Communication, Secure Data Storage, Container Security.
* **Software Supply Chain Security**: Dependency Hygiene, Vulnerability Scanning, Hardening CI/CD, Secret Scanning, SBOM, Provenance and Signing, Base Images, SAST.
* **AI-Backed Services**: Calling Model APIs, Cost and Latency Engineering, Embeddings & Vector Search, RAG, Model Context Protocol, Agent Patterns, Evals, AI-Specific Security, AI-Assisted Development.
* **Project Management and Documentation**: Project Management Tools, Agile and Scrum, Documentation and Technical Writing.
* **Cloud Services**: Cloud Providers.

**Portfolio project**: a service with a worker queue and a cache, instrumented with OpenTelemetry.

### 🔥 Advanced Level

Located [here!](3_Advanced_Guide.md).

* **Database Management**: Database Sharding, Database Replication, Database Partitioning, Database Scaling, Graph Databases.
* **Python Knowledge**: Metaclasses, Context Managers.
* **Performance and Concurrency**: Profiling, Finding the Real Bottleneck, GIL/Threads/Processes, Free-Threaded CPython, Subinterpreters, Worker Topology, Data-Layer Wins, Serialization and Hot Paths, Native Acceleration, Load Testing and Capacity Planning.
* **Distributed Systems**: Failure Is the Normal Case, Delivery Semantics, Consistency Models, Distributed Transactions (Sagas, Outbox, CDC), Event Streaming, Schemas and Evolution, Event Sourcing/CQRS, Coordination, Service Topology, Judgement (Modular Monolith).
* **Design Knowledge**: Event-Driven Architecture, Functional Programming, Test Driven Development, Behavior Driven Development.
* **API Design and Evolution**: Contract-First Development, Versioning Strategies, Designing for Scale, Error Contracts, Protocol Choice, Multi-Tenancy, Developer Experience, API Security.
* **Containerization and Orchestration**: Kubernetes Deployment, Kubernetes Services, Helm.
* **Reliability Engineering**: SLIs/SLOs/Error Budgets, Graceful Degradation, Zero-Downtime Schema Migrations, Progressive Delivery, GitOps, Data Safety, Incident Response, Debugging Production, Chaos Engineering, DORA Metrics, Cost/FinOps.
* **Security Practices**: Security Testing and Vulnerability Assessments, Secure Software Development Lifecycle (SDLC), Security Incident Response, Cloud Security, Secure APIs.
* **Cloud Services**: Serverless Computing, Infrastructure as Code (IaC), Managed Services.

**Portfolio project**: a small multi-service system communicating over events, traced end to end, deployed with GitOps and guarded by SLO-based alerts.
