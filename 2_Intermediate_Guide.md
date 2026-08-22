# Intermediate Level

> [!NOTE]
> The difficulty of a particular subject is defined by 🟢 🟡 🔴 from easy to hard.
>
> The importance of a particular subject is defined by ⭐. 0 is not important, 1 is important, 2 is considerably important, 3 is very important.

> [!TIP]
> **What you're expected to *do* at this level, not just know**: own a service in production — design its endpoints, deploy and configure it, monitor it, and be the one who fixes it when it breaks. Employers assess intermediates at that level.

## Recommended Path

If you only do ten things at this level, do these:

1. Learn **pytest** in depth: fixtures, parametrization, `monkeypatch`.
2. Build with the typed stack: **FastAPI + Pydantic + SQLAlchemy 2.0**.
3. Understand the **event loop**: `def` vs `async def` endpoints, and never block it.
4. Get **auth right once**: OAuth 2.1 / OIDC, JWT validation, object-level authorization checks.
5. Ship a **multi-stage Docker image** built with uv, running as non-root.
6. Set up **GitHub Actions CI**: lint, typecheck, test, scan dependencies.
7. Instrument a service with **OpenTelemetry**: structured logs, traces, RED metrics.
8. Add a **cache (Redis/Valkey) and background workers** with retries and a dead-letter queue.
9. Configure via **`pydantic-settings`**, deploy 12-factor style, handle SIGTERM gracefully.
10. Secure your supply chain: pinned lockfile, `pip-audit`, SBOM in CI.

**Portfolio project**: a service with a worker queue and a cache — e.g. an API that accepts uploads, enqueues processing jobs to Celery/arq backed by Redis, caches hot reads, and exposes health/readiness probes plus OpenTelemetry traces.

## General Knowledge and Best Practices

* [ ] 🟢⭐⭐⭐ **Debugging**: Learn how to follow the flow of your code with specific tools to fix errors.

## Database Management

* [ ] 🟡⭐⭐ **Database Backup and Recovery**: Learn how to back up and recover databases.
* [ ] 🟡⭐⭐ **Database Migration**: Understand database migration and its use cases.
* [ ] 🟡⭐⭐ **Database Indexing**: Beyond beginner B-trees: partial indexes, GIN/GiST for `jsonb` and full-text, when an index stops being used, and index maintenance cost on writes.
* [ ] 🟡⭐ **Time Series Databases**:
  * [ ] 🟢 InfluxDB: Understand time-series databases and their applications.
* [ ] 🟡⭐ **Search Engines**:
  * [ ] 🟢 Elasticsearch: Learn about search engines and their applications.

## Version Control and Collaboration

* [ ] 🟡⭐⭐⭐ **Version Control Systems**: Deepen your understanding of Git.
  * Explore the three states in Git: working directory, staging area, and repository.
  * Understand the Git lifecycle: working with branches, commits, and merges.
  * Grasp the importance of commit messages and writing meaningful ones.
  * Explore Git remotes and how to collaborate with others using repositories on platforms like GitHub or GitLab.
* [ ] 🔴⭐⭐⭐ **Git Flow: Familiarize yourself with Git branching strategies using Git Flow. Learn concepts like feature branches, release branches, and hotfix branches.**
  * Learn about the main branches in Git Flow: `master`, `develop`.
  * Understand the purpose of feature branches and how to create, merge, and delete them.
  * Explore release branches and how they facilitate versioning.
  * Understand hotfix branches and their role in addressing critical issues in production.
  * Familiarize yourself with advanced Git Flow concepts like supporting branches (`support`), and feature toggles.
* [ ] 🟢⭐⭐ **Semantic Versioning**: Learn what does each number in a version means. [SemVer](https://semver.org/)
* [ ] 🟢⭐ **Code Reviews**: Understand the importance of code reviews and how to conduct them effectively.

## Python Knowledge

* [ ] 🟡⭐⭐⭐ **Object-Oriented Programming (OOP)**: Understand OOP principles and inheritance in Python.
* [ ] 🟢⭐ **Python Standard Library**: Familiarize yourself with the Python standard library and its modules.
* [ ] **Libraries**:
  * [ ] 🟢⭐⭐ Pydantic
  * [ ] 🟡⭐⭐ HTTPX
  * [ ] 🟡⭐⭐ SQLAlchemy
  * [ ] 🟡⭐⭐ Django ORM
  * [ ] 🟡⭐ NumPy
  * [ ] 🟡⭐ Pandas
* [ ] **Frameworks**:
  * [ ] 🟡⭐⭐ Django
  * [ ] 🟡⭐⭐ FastAPI ([official docs](https://fastapi.tiangolo.com/) — one of the best-written docs in the ecosystem)
* [ ] 🟢⭐⭐ **Error Handling**: Understand how to handle and raise exceptions in Python.
* [ ] 🟢⭐⭐⭐ **Documentation**:
  * [ ] 🟢⭐⭐⭐ Docstrings: Learn how to write docstrings in Napoleon format for documenting Python code.
  * [ ] 🟢⭐⭐ Markdown: Learn how to write documentation in Markdown format.
  * [ ] 🟡⭐ Sphinx: Explore Sphinx for generating documentation from docstrings.
  * [ ] 🟢 Read the Docs: Learn how to host documentation on Read the Docs.
  * [ ] 🟡⭐ Mermaid: Explore Mermaid for generating diagrams from text.
* [ ] 🟡⭐⭐⭐ **Generators**: Explore advanced Python features for efficient and clean code.
* [ ] 🟡⭐ **Decorators**: Learn how to use decorators for advanced Python programming.
* [ ] 🟡⭐⭐ **Data Classes**: Understand data classes for solving complex structuring problems.

### Testing and Quality Assurance

> [!TIP]
> Testing is how you earn the right to deploy on Friday. The parts that make integration tests trustworthy matter more than coverage percentages.

* [ ] 🟡⭐⭐⭐ **pytest in Depth**: The backbone of Python testing. ([pytest docs](https://docs.pytest.org/))
  * Fixtures and scopes, `conftest.py`, shared test setup.
  * Parametrization and markers.
  * `pytest-asyncio`/`anyio` for async tests.
  * `monkeypatch`, `tmp_path` built-in fixtures.
  * `pytest-xdist` for parallel runs.
* [ ] 🟡⭐⭐⭐ **Real Dependencies in Tests**: Use [Testcontainers](https://testcontainers-python.readthedocs.io/) (or Docker Compose) for Postgres/Redis/Kafka instead of mocking the database; transactional rollback per test; deterministic seed data with `factory_boy`/`polyfactory`.
* [ ] 🟡⭐⭐ **Test Doubles, Used Sparingly**: `unittest.mock`, `respx`/`responses` for HTTP — and follow the "don't mock what you don't own" rule.
* [ ] 🟡⭐⭐ **API Testing**: FastAPI `TestClient`/`httpx.ASGITransport`, Django test client, and schema-driven fuzzing with [Schemathesis](https://schemathesis.readthedocs.io/) against your OpenAPI spec.
* [ ] 🟡⭐ **Property-Based Testing**: [Hypothesis](https://hypothesis.readthedocs.io/) for parsers, serializers, and money/date logic.
* [ ] 🟡⭐⭐ **Contract Testing**: consumer-driven contracts (Pact) or schema compatibility checks between services, so a producer change cannot silently break consumers.
* [ ] 🟢⭐⭐ **Coverage, Honestly**: `coverage.py`, branch coverage, why 100% is not the goal — mutation testing (`mutmut`/`cosmic-ray`) is the real quality signal.
* [ ] 🟡⭐⭐ **Test Pyramid & Flakiness**: fast unit majority, targeted integration, thin e2e; quarantine and *fix* flaky tests; freeze time (`freezegun`/`time-machine`).
* [ ] 🟡⭐ **Load and Performance Testing**: k6 or Locust, and treating a latency regression as a failing test.

## Asynchronous Programming

> [!TIP]
> Async moved here from the advanced guide: since FastAPI is an ASGI framework, you cannot write a correct FastAPI service without understanding the event loop. The most common production bug in Python backends today is a blocking call inside an `async def` handler stalling the whole worker. Threads/processes/GIL stay in the [advanced guide's Performance section](3_Advanced_Guide.md#performance-and-concurrency).

* [ ] 🟡⭐⭐⭐ **Event Loop Mental Model**: coroutines, tasks, `await`, cooperative scheduling; why CPU-bound work and `time.sleep`/`requests`/blocking DB drivers freeze the loop. ([asyncio docs](https://docs.python.org/3/library/asyncio.html))
* [ ] 🟡⭐⭐⭐ **`def` vs `async def` Endpoints in FastAPI**: threadpool offloading, `run_in_threadpool` / `asyncio.to_thread`, and how to decide per endpoint.
* [ ] 🟡⭐⭐ **Structured Concurrency**: `asyncio.TaskGroup`, `asyncio.timeout`, cancellation semantics, `ExceptionGroup` / `except*`, and `anyio` as the portable layer.
* [ ] 🟡⭐⭐ **Concurrency Primitives**: `gather` vs `TaskGroup`, semaphores for bounded fan-out, queues, graceful shutdown on SIGTERM with in-flight requests.
* [ ] 🟡⭐⭐ **Async I/O Clients**: `httpx.AsyncClient` (with connection limits and timeouts — *always* set timeouts), `asyncpg`/`psycopg3`, SQLAlchemy 2.0 async sessions, `redis.asyncio`.
* [ ] 🟡⭐⭐ **ASGI Itself**: what the spec is, the role of Uvicorn/Granian/Hypercorn, workers vs event loops, lifespan events, middleware ordering.
* [ ] 🟡⭐ **Streaming Responses**: SSE and WebSockets in FastAPI, backpressure, and why long-lived connections change your deployment (timeouts, sticky routing, scaling).
* [ ] 🔴⭐ **Debugging Async**: asyncio debug mode, detecting slow callbacks, task leaks, profiling with `py-spy`.

## Running Services in Production

> [!TIP]
> How a service is configured, started, shut down and rolled out is day-one knowledge on any team — and it is mostly framework-independent.

* [ ] 🟢⭐⭐⭐ **[12-Factor App](https://12factor.net/)**: config from the environment, stateless processes, dev/prod parity, treating logs as streams — and where the model needs adapting today.
* [ ] 🟢⭐⭐⭐ **Configuration Management**: [`pydantic-settings`](https://docs.pydantic.dev/latest/concepts/pydantic_settings/), typed settings validated at startup (fail fast on a missing var), per-environment layering, strict separation of config from secrets.
* [ ] 🟡⭐⭐⭐ **Lifecycle**: graceful startup (warm pools, run migrations *outside* the app process), SIGTERM handling, connection draining, readiness gating during rollouts, and correct restart behaviour.
* [ ] 🟡⭐⭐ **Process Model**: ASGI/WSGI servers, worker and thread counts derived from container CPU/memory limits, `--preload`/copy-on-write, request timeouts, and max-requests recycling for leak mitigation.
* [ ] 🟡⭐⭐ **Container Images for Python**: multi-stage builds with uv, layer caching, non-root user, `.dockerignore`, small bases, healthchecks, and image size vs cold-start trade-offs.
* [ ] 🟡⭐⭐ **Reverse Proxy / Ingress**: TLS termination, timeouts, body-size limits, `X-Forwarded-*` and proxy headers (getting the real client IP right matters for rate limiting and audit logs), gzip/brotli.
* [ ] 🟡⭐⭐ **Where to Run It**: managed PaaS (Cloud Run, Fly, Render, App Runner), ECS, Kubernetes, serverless — understand the trade-off table (cold starts, cost, operational burden) rather than a default answer.
* [ ] 🟢⭐⭐ **Environments**: local / preview-per-PR / staging / production, and seeding realistic non-production data safely (anonymized, never a raw prod dump).

## Web Services

* [ ] 🟡⭐⭐ **Services and Microservices**: Understand the basics of services and microservices.
  * [ ] 🟢⭐ Isolation: Learn about isolation in microservices.
  * [ ] 🟡⭐ Communication: Explore communication between microservices.
  * [ ] 🟢 Service Discovery: Understand service discovery and networking in microservices.

## Caching, Queues and Background Work

> [!TIP]
> Every non-trivial backend has an "everything that must not happen inside the request" tier. This tier shows up in almost every interview for intermediate Python roles.

### Caching

* [ ] 🟡⭐⭐⭐ **Redis / Valkey Basics**: strings, hashes, sets, sorted sets, TTLs, atomic ops, `SCAN` vs `KEYS`. ([Redis docs](https://redis.io/docs/latest/))
* [ ] 🟡⭐⭐ **Caching Patterns**: cache-aside, write-through, read-through; TTL and key-design strategy; cache invalidation as a real design problem.
* [ ] 🟡⭐⭐ **Failure Modes**: stampede/dogpile (locking, jittered TTLs), stale reads, hot keys, cache as an availability dependency.
* [ ] 🟢⭐ **HTTP-Level Caching**: `ETag`/`If-None-Match`, CDN edge caching, and `functools.lru_cache` for in-process memoization.
* [ ] 🟡⭐⭐ **Rate Limiting and Idempotency**: token bucket in Redis, distributed locks (and why `SETNX` alone is not a lock), idempotency keys for retried POSTs.

### Background Jobs

* [ ] 🟡⭐⭐⭐ **Task Queues**: Celery, and the modern async-native options (Dramatiq, ARQ, Taskiq, `procrastinate` for Postgres-backed queues).
* [ ] 🟡⭐⭐ **Brokers**: Redis vs RabbitMQ vs SQS — delivery guarantees, visibility timeouts, ack semantics.
* [ ] 🟡⭐⭐⭐ **Reliability Patterns**: at-least-once delivery, idempotent consumers, retries with exponential backoff + jitter, dead-letter queues, poison messages, task timeouts.
* [ ] 🟡⭐⭐ **Transactional Outbox**: why "write to DB then publish an event" loses messages, and how the outbox pattern fixes it (deep dive in the advanced guide's Distributed Systems section).
* [ ] 🟢⭐ **Scheduling**: periodic jobs (Celery beat, cron, Kubernetes CronJob) and preventing overlapping runs.
* [ ] 🟡⭐ **Observability of Workers**: queue depth, task latency, failure rate — and alerting on them.

## Containerization and Orchestration

* [ ] 🟢⭐⭐ **Docker Basics**: Docker is a platform that uses OS-level virtualization to deliver software in packages called containers. Containers are isolated from each other and bundle their own software, libraries and configuration files.
  * [ ] 🟡⭐ Docker Networking: Understand Docker networking and how to create Docker networks.
  * [ ] 🟡⭐ Docker Volumes: Explore Docker volumes and how to create them.
  * [ ] 🟡⭐ Docker Security: Learn about Docker security best practices.
  * [ ] 🟡⭐ Docker Performance: Learn how to optimize Docker performance.
    * [ ] 🟢⭐ Docker Order of Operations: Understand the order of operations for Docker containers and its implications.
    * [ ] 🟡⭐ Docker Stages: Understand stages for minimizing image size.
  * [ ] 🟡⭐ Export and Import Data Volumes: Learn how to export and import data volumes for Docker containers.
  * [ ] 🟡⭐ Export and Import Images: Understand how to export and import Docker images.
* [ ] 🟡⭐ **Docker Compose**: Explore multi-container applications and orchestrate them using Docker Compose.
  * [ ] 🟡⭐ Build and Deploy a Multi-Container Application: Build and deploy a multi-container application using Docker Compose.
* [ ] 🔴⭐⭐⭐ **Kubernetes Fundamentals**: Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications. It groups containers that make up an application into logical units for easy management and discovery.

## Design Knowledge

* [ ] 🟡⭐⭐ **Design Principles**: These are general, reusable solutions to commonly occurring problems in software design. They include principles like SOLID, KISS, DRY, and YAGNI.
* [ ] 🟡⭐ **Architectural Patterns**
  * [ ] 🟢⭐ MVC: Model-View-Controller is a design pattern that separates an application into three interconnected components. This separation allows for efficient code reuse and parallel development.
  * [ ] 🟢⭐ Monolithic: A monolithic architecture is a software pattern where all components of the application are interconnected and interdependent. This pattern is simple to develop, test, and deploy.
  * [ ] 🟡⭐ Microservices: Microservices is an architectural style that structures an application as a collection of small autonomous services, modeled around a business domain. The distributed-systems reasoning that makes them survivable lives in the advanced guide.
* [ ] 🟡⭐⭐ **Design Patterns**: Explore software design patterns (e.g., Singleton, Observer, Factory) and their use cases.
  * [ ] 🟢 [Refactoring Guru](https://refactoring.guru/design-patterns): A website that provides descriptions, examples, and use cases for various software design patterns.
* [ ] 🟡⭐ **Approaches**
  * [ ] 🟡⭐⭐ Domain Driven Design: An approach to software development that centers the development on programming a domain model that has a rich understanding of the processes and rules of a domain.
* [ ] 🟡⭐ **API Versioning**: Learn about different strategies for versioning APIs. Full treatment in the advanced guide's API Design and Evolution section.

## Continuous Integration and Continuous Deployment (CI/CD)

* [ ] 🟢⭐⭐ **CI/CD Pipelines**: Continuous Integration (CI) is a development practice where developers integrate code into a shared repository frequently. Continuous Deployment (CD) is a strategy for software releases wherein any code commit that passes the automated testing phase is automatically released into the production environment.
  * [ ] 🟢⭐⭐ **GitHub Actions**: The default starting point today. Automate workflows directly from your GitHub repository. ([docs](https://docs.github.com/en/actions))
    * [ ] 🟡 Workflow Files: Understand the `.github/workflows` format for defining GitHub Actions workflows.
    * [ ] 🟡 Actions: Use third-party actions — and harden them (see Supply Chain Security below).
  * [ ] 🟢⭐⭐ **GitLab CI**: Understand how to use GitLab's built-in CI/CD to automate builds, tests, and deployments.
    * [ ] 🟡 .gitlab-ci.yml: Learn about the .gitlab-ci.yml file format for defining GitLab CI/CD pipelines.
    * [ ] 🟢 Runners: Learn about GitLab runners and how they execute your CI jobs.
  * [ ] 🟡⭐ **Building Docker Images in CI/CD**: Learn how to build Docker images as part of your CI/CD pipelines.
  * [ ] 🟡⭐ **Jenkins**: Legacy you may inherit rather than a choice for new projects. Know enough to read a Jenkinsfile and migrate away.

## Observability

> [!TIP]
> Since OpenTelemetry became the vendor-neutral standard, observability is one topic — logs, metrics and traces under one SDK — not three separate tools. Distributed tracing now lives here; SLOs and incident response stay at advanced level (Reliability Engineering).

* [ ] 🟡⭐⭐⭐ **The Three Signals**: logs, metrics, traces — what each answers, and correlating them via trace/span IDs.
* [ ] 🟢⭐⭐⭐ **Structured Logging**: JSON logs (`structlog` or `logging` with a JSON formatter), context binding (request id, user id, tenant), log levels, **never logging secrets or PII**, sampling noisy logs.
* [ ] 🟡⭐⭐⭐ **OpenTelemetry in Python**: SDK + auto-instrumentation for FastAPI/Django/SQLAlchemy/httpx, spans and attributes, context propagation (W3C `traceparent`) across services and queue messages, the OTel Collector, and exporting to any backend (Grafana/Tempo, Jaeger, Datadog, Honeycomb…). ([OTel Python docs](https://opentelemetry.io/docs/languages/python/))
* [ ] 🟡⭐⭐ **Metrics That Matter**: RED (rate, errors, duration) for services, USE for resources; histograms and why averages lie; p95/p99; cardinality as a cost driver. Prometheus + Grafana as the common backend pair.
* [ ] 🟡⭐⭐ **Health and Readiness**: liveness vs readiness vs startup probes, dependency health checks, and why a health endpoint that pings the DB can cascade an outage.
* [ ] 🟢⭐⭐ **Error Tracking**: Sentry (or equivalent), grouping, release tagging, source context, alert fatigue.
* [ ] 🟡⭐⭐ **Dashboards and Alerts**: alert on symptoms (user-visible) not causes; runbook links in alerts.
* [ ] 🟡⭐ **Cost Awareness**: log volume, metric cardinality, trace sampling strategies (head vs tail sampling).

## Security Practices

* [ ] 🟢⭐⭐ **Web Security Basics**: Web security involves protecting websites or web applications by detecting, preventing and responding to attacks. Topics include Cross-Site Scripting (XSS), SQL Injection, Cross-Site Request Forgery (CSRF), and more.
* [ ] 🟢⭐⭐ **OWASP Top 10**: Familiarize yourself with the OWASP Top 10 most critical web application security risks.
* [ ] 🟢⭐⭐⭐ **OWASP API Security Top 10**: The list that matches this roadmap's audience — BOLA/IDOR, broken authentication, unrestricted resource consumption and friends live here, not just in the classic Top 10. ([owasp.org/API-Security](https://owasp.org/API-Security/))
* [ ] 🔴⭐⭐⭐ **Authentication**: This is where backend engineers ship exploitable bugs most often — be concrete about it.
  * [ ] 🟡⭐⭐⭐ Sessions vs Tokens: server-side sessions with secure cookies (`HttpOnly`, `Secure`, `SameSite`) vs stateless JWTs — and the honest trade-off (revocation).
  * [ ] 🔴⭐⭐⭐ OAuth 2.1 / OIDC: authorization code flow **with PKCE**, why implicit and password grants are dead, client credentials for service-to-service, scopes vs claims, ID token vs access token.
  * [ ] 🟡⭐⭐⭐ JWT Done Right: signature verification (never `alg: none`, never decode without verify), JWKS and key rotation, `aud`/`iss`/`exp` validation, short lifetimes, refresh token rotation and reuse detection.
  * [ ] 🟡⭐⭐ Passwords and Beyond: Argon2id/bcrypt (never plain SHA), breach-list checks, passkeys/WebAuthn and TOTP MFA.
  * [ ] 🟢⭐⭐ Using an IdP: Keycloak, Auth0, Cognito, Entra ID — when to delegate instead of building.
* [ ] 🔴⭐⭐⭐ **Authorization**:
  * [ ] 🟡⭐⭐⭐ Models: RBAC, ABAC, ReBAC (Zanzibar-style: OpenFGA, SpiceDB) and multi-tenant isolation.
  * [ ] 🟡⭐⭐⭐ Object-Level Checks: BOLA/IDOR is #1 in the OWASP API Security Top 10 — authorize the *object*, not just the route; write a test proving it.
  * [ ] 🟡⭐⭐ Enforcement Point: centralize policy (dependency/middleware/policy engine); never scatter `if user.is_admin` across handlers.
* [ ] 🟡⭐⭐⭐ **Secret Management**: env vars vs a secret manager (Vault, AWS/GCP Secrets Manager, SOPS/sealed-secrets), rotation, keeping secrets out of git and out of logs, workload identity / OIDC federation instead of long-lived keys.
* [ ] 🔴⭐⭐⭐ **Secure Communication**: Gain knowledge about secure communication protocols such as HTTPS (HTTP over SSL/TLS) and the importance of encrypting sensitive data in transit. Learn about certificate management, secure configuration of web servers, and secure transmission of data over networks.
* [ ] 🟡⭐ **Secure Data Storage**: Understand how to securely store sensitive data, including passwords, personally identifiable information (PII), and other confidential information. Learn about encryption, hashing, and salting techniques to protect data at rest.
* [ ] 🟡⭐ **Container Security**: Understand security best practices for Docker containers and Kubernetes.

## Software Supply Chain Security

> [!TIP]
> Application security covers your code; supply chain security covers everything your code depends on — where a large share of recent real-world compromises of Python systems actually happened (typosquatted PyPI packages, compromised GitHub Actions, leaked publish tokens).

* [ ] 🟡⭐⭐⭐ **Dependency Hygiene**: lockfiles with hashes, pinned transitive deps, minimal dependency count, vetting a package before adding it (maintenance activity, provenance, install scripts).
* [ ] 🟡⭐⭐⭐ **Vulnerability Scanning**: `pip-audit`/`uv audit`, OSV, Dependabot or Renovate for automated updates, Trivy/Grype for container images; triaging a CVE (is the vulnerable path even reachable?).
* [ ] 🟡⭐⭐⭐ **Hardening CI/CD**: least-privilege `permissions:` in GitHub Actions, pinning third-party actions to a commit SHA, no secrets in `pull_request_target`, ephemeral OIDC cloud credentials, protected branches and required reviews.
* [ ] 🟢⭐⭐ **Secret Scanning**: `gitleaks`/`trufflehog`, push protection, and the rotate-first incident procedure when a key leaks.
* [ ] 🟡⭐⭐ **SBOM**: CycloneDX or SPDX, generating one in CI, and what consumers do with it — regulation (EU CRA) increasingly expects this of ordinary commercial projects.
* [ ] 🟡⭐⭐ **Provenance and Signing**: Sigstore/cosign, PyPI Trusted Publishing (OIDC — no long-lived API tokens), SLSA build levels, signed container images and admission policies.
* [ ] 🟡⭐ **Container Base Images**: distroless/slim/Chainguard-style bases, non-root users, dropping build tooling from the runtime stage, rebuilding regularly for OS CVEs.
* [ ] 🟡⭐ **Code Scanning (SAST)**: CodeQL, Semgrep, `bandit` wired into PRs.

## AI-Backed Services

> [!TIP]
> In 2026 a large share of Python backend work is "put an LLM behind an API and make it reliable" — and it is *backend* work: streaming, timeouts, retries, cost control, caching, evaluation, and a new class of security problems. Treat tokens like a database bill.

### Integration Mechanics

* [ ] 🟡⭐⭐ **Calling Model APIs**: request/response shapes, streaming responses to clients (SSE), token limits, timeouts, retries with backoff, handling rate limits, structured/JSON output, tool/function calling.
* [ ] 🟡⭐⭐ **Cost and Latency Engineering**: token accounting, prompt caching, model routing (small model first), batching, semantic caching, budget alerts.
* [ ] 🟡⭐⭐ **Reliability**: LLM calls are slow, non-deterministic and occasionally down — circuit breakers, fallbacks, and never putting an uncached model call in a hot path without a timeout.

### Retrieval

* [ ] 🟡⭐⭐ **Embeddings & Vector Search**: `pgvector` in the Postgres you already run, or a dedicated store (Qdrant, Weaviate, Milvus); HNSW/IVF indexes, hybrid search (BM25 + vector), reranking.
* [ ] 🟡⭐⭐ **RAG as a Data Pipeline**: chunking, ingestion/refresh jobs, metadata filtering, per-tenant isolation of retrieved documents (a retrieval bug is a data leak).

### Agents & Protocols

* [ ] 🟡⭐ **Model Context Protocol (MCP)**: exposing your own systems as tools/resources, and the authorization boundary that implies. ([modelcontextprotocol.io](https://modelcontextprotocol.io/))
* [ ] 🟡⭐ **Agent Patterns**: tool loops, human-in-the-loop approval for side-effecting actions, idempotency for retried tool calls.

### Quality & Safety

* [ ] 🟡⭐⭐ **Evals**: golden datasets, LLM-as-judge with its caveats, regression tests on prompt changes, tracing prompts/responses (Langfuse, OTel GenAI semantic conventions), offline vs online metrics.
* [ ] 🟡⭐⭐⭐ **AI-Specific Security**: prompt injection (especially indirect, via retrieved or fetched content), the lethal-trifecta pattern (private data + untrusted content + exfiltration channel), output handling (never `eval` model output, sandbox generated code), PII in prompts/logs, and the [OWASP Top 10 for LLM Applications](https://genai.owasp.org/).

### Working with AI Tooling

* [ ] 🟢⭐⭐ **AI-Assisted Development**: use coding agents effectively while keeping review standards — you own every line you merge.

## Project Management and Documentation

* [ ] 🟡⭐⭐ **Project Management Tools**: These are tools that help manage a project and track its progress. They can be used to assign tasks, track deadlines, manage resources, and more.
  * [ ] 🟢 Jira
  * [ ] 🟢 Trello
  * [ ] 🟡 Github Projects
* [ ] 🟢⭐⭐ **Documentation**: Learn the importance of clear and concise documentation for projects.
* [ ] 🟡⭐ **Agile and Scrum**: Understand Agile principles and Scrum methodology.
* [ ] 🟢⭐ **Technical Writing**: Improve your technical writing skills for better documentation.

## Cloud Services

* [ ] 🟡⭐⭐ **Cloud Providers**: These are services that offer computing resources and storage, among other things, over the internet. The main providers are Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).
  * [ ] 🟡⭐ AWS
  * [ ] 🟢⭐ Azure
  * [ ] 🟢 Google Cloud
