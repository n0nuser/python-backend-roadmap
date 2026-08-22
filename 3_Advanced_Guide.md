# Advanced Level

> [!NOTE]
> The difficulty of a particular subject is defined by 🟢 🟡 🔴 from easy to hard.
>
> The importance of a particular subject is defined by ⭐. 0 is not important, 1 is important, 2 is considerably important, 3 is very important.

> [!TIP]
> **What you're expected to *do* at this level, not just know**: design a system and defend its trade-offs, ship schema changes and rollouts with zero downtime, and lead an incident at 03:00. Employers assess seniors at that level — this is the gap between "I can build a service" and "I can be trusted with a system".

## Recommended Path

If you only do ten things at this level, do these:

1. **Profile before optimizing**: `py-spy`, `cProfile`, `memray` on a real service.
2. Understand the **GIL**, executors, and evaluate free-threaded CPython for your stack.
3. **Load test** with k6/Locust and find the knee of the latency curve before your users do.
4. Internalize distributed failure: timeouts, retry amplification, circuit breakers, backpressure.
5. Get delivery semantics right: idempotent consumers, dedup keys, transactional outbox.
6. Ship a **zero-downtime migration** using expand/migrate/contract.
7. Define **SLIs/SLOs** with burn-rate alerting and use the error budget to decide priorities.
8. Run a **blameless postmortem** with tracked action items after a real incident.
9. Evolve an API safely: contract-first OpenAPI, breaking-change detection in CI, deprecation policy.
10. Adopt progressive delivery: canary releases with automated rollback.

**Portfolio project**: a small multi-service system (2–3 services plus a worker) communicating over events with a broker, sharing context via OpenTelemetry traces across services, deployed with GitOps, fronted by SLO-based dashboards and alerts.

## Database Management

* [ ] 🟡⭐ **Database Sharding**: Explore database sharding and its use cases.
* [ ] 🟡⭐ **Database Replication**: Understand database replication and its use cases.
* [ ] 🟡⭐ **Database Partitioning**: Learn about database partitioning and its use cases.
* [ ] 🟡⭐ **Database Scaling**: Learn about database scaling and its use cases.
* [ ] 🟡⭐ **Graph Databases**:
  * [ ] 🟢 Neo4j: Learn about graph databases and their applications.

## Python Knowledge

* [ ] 🟡⭐ **Metaclasses**: Understand metaclasses for advanced class customization. Genuinely rare in application code — most custom behaviour is achievable with `__init_subclass__`, decorators or descriptors; reach for metaclasses last.
* [ ] 🟡⭐ **Context Managers**: Learn to work with context managers for resource management.

> Asynchronous programming now lives at [intermediate level](2_Intermediate_Guide.md#asynchronous-programming); threads/processes/GIL are covered below in Performance and Concurrency.

## Performance and Concurrency

> [!TIP]
> The Python runtime landscape changed materially: free-threaded (no-GIL) builds became officially supported and are moving from experimental to production-viable, which changes the standard "threads are useless for CPU work in Python" advice.

### Measure First

* [ ] 🔴⭐⭐⭐ **Profiling**: `py-spy` (sampling, works on a live production process), `cProfile`/`pyinstrument`, `memray`/`tracemalloc` for memory, reading flamegraphs, benchmarking with `pytest-benchmark`/`hyperfine`.
* [ ] 🟡⭐⭐⭐ **Finding the Real Bottleneck**: it is usually the database or a serial network call, not Python — measure before optimizing; latency budgets and Amdahl's law.

### Concurrency Model

* [ ] 🔴⭐⭐⭐ **GIL, Threads, Processes**: what the GIL does and doesn't block, `ThreadPoolExecutor` vs `ProcessPoolExecutor`, `multiprocessing` costs (pickling, fork vs spawn).
* [ ] 🔴⭐⭐ **Free-Threaded CPython (3.13+/3.14)**: what changes ([PEP 703](https://peps.python.org/pep-0703/)), the single-thread overhead trade-off, C-extension compatibility, and how to test whether your stack supports it.
* [ ] 🟡⭐ **Subinterpreters (PEP 734)**: where they fit between threads and processes.
* [ ] 🟡⭐⭐ **Worker Topology in Production**: Gunicorn/Uvicorn worker counts vs CPU limits, threads per worker, and why the container CPU limit — not the host core count — is the number that matters.

### Making Python Fast

* [ ] 🟡⭐⭐ **Data-Layer Wins**: N+1 elimination, batching, `COPY`/bulk inserts, prepared statements, pool sizing, read replicas, keyset pagination instead of `OFFSET`.
* [ ] 🟡⭐⭐ **Serialization and Hot Paths**: `orjson`/`msgspec`, avoiding needless model re-validation, streaming large responses.
* [ ] 🟡⭐ **Native Acceleration**: PyO3/Rust, Cython, or C extensions for genuinely CPU-bound cores; NumPy/Polars/DuckDB for data-shaped work.
* [ ] 🟡⭐ **Runtime Choices**: JIT progress in CPython, alternative runtimes — and how to evaluate the claim honestly with your own benchmark.

### Prove It

* [ ] 🟡⭐⭐ **Load Testing and Capacity Planning**: k6/Locust, closed vs open workload models, Little's law, soak tests, and finding the knee of the latency curve before your users do.

## Distributed Systems

> [!TIP]
> Recommended background reading: [*Designing Data-Intensive Applications*](https://dataintensive.net/) (Kleppmann) and the ["Fallacies of Distributed Computing"](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing).

* [ ] 🔴⭐⭐⭐ **Failure Is the Normal Case**: partial failure, timeouts, retries and the amplification they cause, jitter, circuit breakers, bulkheads, load shedding, backpressure.
* [ ] 🔴⭐⭐⭐ **Delivery Semantics**: at-most-once / at-least-once / "exactly-once" — and why it is really *effectively-once* via idempotency + dedup keys.
* [ ] 🔴⭐⭐ **Consistency Models**: strong vs eventual, read-your-writes, CAP and its more useful sibling PACELC, quorum reads/writes.
* [ ] 🔴⭐⭐ **Distributed Transactions**: why 2PC is usually the wrong answer, sagas (choreography vs orchestration), compensating actions, the transactional outbox and CDC (Debezium).
* [ ] 🟡⭐⭐ **Event Streaming**: Kafka/Redpanda (or Pulsar/Kinesis) — partitions and ordering guarantees, consumer groups, offsets, rebalancing, compaction, replay.
* [ ] 🟡⭐⭐ **Schemas and Evolution**: Avro/Protobuf/JSON Schema, a schema registry, backward/forward compatibility, versioning events as a public API.
* [ ] 🟡⭐⭐ **Patterns**: event sourcing and CQRS (and when *not* to use them), materialized views, eventual consistency in the UI.
* [ ] 🟡⭐ **Coordination**: leader election, distributed locks and their fencing tokens, clock skew and why timestamps are not ordering.
* [ ] 🟡⭐ **Service Topology**: API gateways, service mesh, gRPC for internal RPC, service discovery, multi-region and data residency.
* [ ] 🟡⭐⭐ **Judgement**: the modular monolith as the correct default, and what actually forces a split (team boundaries, scaling asymmetry, compliance).

## Design Knowledge

* [ ] 🟡⭐ **Architectural Patterns**
  * [ ] 🟡⭐ Event-Driven Architecture: Understand the event-driven architecture pattern and its use cases. The full distributed-systems treatment lives in the section above.
  * [ ] 🟡 Functional Programming: Learn about functional programming concepts and how to apply them in Python.
* [ ] 🟡⭐ **Approaches**
  * [ ] 🟡⭐⭐ Test Driven Development: A software development process that relies on the repetition of a very short development cycle: first the developer writes a failing automated test case that defines a desired improvement or new function, then produces code to pass that test and finally refactors the new code to acceptable standards.
  * [ ] 🟡⭐ Behavior Driven Development: A software development methodology in which an application is specified and designed by describing how its behavior should appear to an outside observer.

## API Design and Evolution

> [!TIP]
> For an advanced backend engineer the API *is* the product surface and the hardest thing to change. Design accordingly.

* [ ] 🟡⭐⭐⭐ **Contract-First Development**: OpenAPI 3.1 as the source of truth, generated clients/servers, spec linting (Spectral), breaking-change detection in CI (oasdiff).
* [ ] 🟡⭐⭐⭐ **Versioning Strategies**: URL vs header vs media-type versioning, additive-only evolution, deprecation policy (`Deprecation`/`Sunset` headers), sunset timelines and consumer migration — and the honest answer that not versioning at all, by never breaking, is often best.
* [ ] 🟡⭐⭐ **Designing for Scale**: cursor/keyset pagination, filtering and sparse fieldsets, bulk endpoints, async/long-running operations (202 + status resource), webhooks (signing, retries, replay protection), idempotency keys.
* [ ] 🟡⭐⭐ **Error Contracts**: RFC 9457 problem details, machine-readable error codes, never leaking internals in messages.
* [ ] 🟡⭐⭐ **Protocol Choice**: REST vs gRPC (internal, low-latency, streaming) vs GraphQL (client-driven aggregation) vs WebSockets/SSE — with the operational cost of each: GraphQL needs depth/complexity limits and persisted queries; gRPC needs schema governance and proxy support.
* [ ] 🟡⭐ **Multi-Tenancy in the API**: tenant scoping, quotas, per-tenant rate limits, noisy-neighbour isolation.
* [ ] 🟡⭐ **Developer Experience**: docs that stay true (generated from the spec), sandbox environments, SDK generation, changelogs.
* [ ] 🟡⭐⭐ **API Security**: Design against the [OWASP API Security Top 10](https://owasp.org/API-Security/) — object-level authorization, resource consumption limits, injection through every input channel.

## Containerization and Orchestration

* [ ] 🔴⭐⭐ **Kubernetes Deployment**: Understand how to deploy and manage applications on a Kubernetes cluster.
* [ ] 🔴⭐ **Kubernetes Services**: Learn about Kubernetes services like LoadBalancer, NodePort, and ClusterIP.
* [ ] 🔴⭐⭐ **Helm**: Understand how to package and deploy applications on Kubernetes using Helm charts.

## Reliability Engineering

> [!TIP]
> Deployment tooling is not operational discipline: how you decide a service is healthy enough, how you ship a schema change without downtime, and what you do at 03:00 when it goes wrong separate a senior backend engineer from a fast one.

### Defining "Good Enough"

* [ ] 🟡⭐⭐⭐ **SLIs, SLOs and Error Budgets**: choosing user-visible indicators, availability vs latency objectives, burn-rate alerting, and using the error budget to decide between shipping features and fixing reliability. ([Google SRE book](https://sre.google/books/))
* [ ] 🟡⭐⭐ **Graceful Degradation**: feature flags and kill switches, fallbacks, read-only mode, timeouts and retry budgets end to end.

### Shipping Safely

* [ ] 🔴⭐⭐⭐ **Zero-Downtime Schema Migrations**: the expand/migrate/contract pattern, backward-compatible deploys, avoiding long-held locks (`ALTER TABLE` on a hot table), backfills in batches, online index creation, always having a rollback plan; Alembic/Django migrations run in CI, tested against production-sized data.
* [ ] 🟡⭐⭐ **Progressive Delivery**: blue/green, canary, feature flags for decoupling deploy from release, automated rollback on SLO burn (Argo Rollouts/Flagger).
* [ ] 🟡⭐⭐ **GitOps**: Argo CD or Flux, declarative environments, drift detection, pull-based deploys vs pushing from CI.
* [ ] 🟡⭐ **Data Safety**: backup *restore* drills (an untested backup is not a backup), PITR, RPO/RTO targets, disaster recovery runbooks.

### When It Breaks

* [ ] 🟡⭐⭐⭐ **Incident Response**: on-call, severity levels, incident commander role, comms, blameless postmortems with tracked action items.
* [ ] 🟡⭐⭐ **Debugging Production**: correlating traces/logs/metrics, `py-spy` on a live process, request replay, safe read access to production data.
* [ ] 🟡⭐ **Chaos and Game Days**: fault injection, dependency-failure drills, load shedding under overload.

### Measuring the Team

* [ ] 🟢⭐ **DORA Metrics**: deployment frequency, lead time, change failure rate, MTTR — as feedback, not as a scoreboard.
* [ ] 🟡⭐ **Cost/FinOps**: cost per request, right-sizing, autoscaling policies, knowing what your service costs to run.

## Security Practices

* [ ] 🔴⭐ **Security Testing and Vulnerability Assessments**: Learn about various security testing techniques, including penetration testing, vulnerability scanning, and code reviews. Understand the importance of regularly testing applications and infrastructure for vulnerabilities. Familiarize yourself with tools and methodologies used in security testing to identify and address potential weaknesses.
* [ ] 🟡⭐⭐⭐ **Secure Software Development Lifecycle (SDLC)**: Incorporate security into the software development lifecycle. Understand secure coding practices, such as input validation, output encoding, proper error handling, and secure use of libraries and frameworks. Implement security checks and code reviews throughout the development process to identify and fix security issues early on.
* [ ] 🔴⭐⭐ **Security Incident Response**: Learn how to respond to security incidents effectively. Understand the importance of incident response plans, incident detection and analysis, containment, eradication, and recovery. Complements the general incident response practice in Reliability Engineering above.
* [ ] 🟡⭐⭐ **Cloud Security**: Gain knowledge of security best practices for cloud environments, such as Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform (GCP). Understand the shared responsibility model, secure configuration of cloud services, identity and access management, and monitoring and logging in the cloud.
* [ ] 🟡⭐⭐ **Secure APIs**: Covered where the design decisions are made — see [API Security](#api-design-and-evolution) above (object-level authorization, resource consumption limits, injection through every input channel), with the authentication and authorization mechanics in the [intermediate guide](2_Intermediate_Guide.md#security-practices).

## Cloud Services

> [!TIP]
> The Reliability Engineering section above assumes declarative, reviewable infrastructure — GitOps and progressive delivery only work if the environment itself is code.

* [ ] 🟡⭐⭐ **Infrastructure as Code (IaC)**: Terraform/OpenTofu, Pulumi or CDK — and the practices that make IaC safe rather than just declarative.
  * [ ] 🟡⭐⭐ State: remote state, locking, and why a state file is as sensitive as a credential.
  * [ ] 🟡⭐⭐ Modules and Environments: composition, per-environment variables, avoiding copy-pasted stacks.
  * [ ] 🟡⭐⭐ Plan Review: reading a plan diff in a pull request, and never applying an unreviewed destroy.
  * [ ] 🟡⭐ Drift: detecting manual console changes and reconciling them.
  * [ ] 🟡⭐ Policy as Code: OPA/Conftest, Checkov or `tfsec` to block insecure resources before apply.
* [ ] 🟡⭐ **Serverless Computing**: Understand serverless concepts and frameworks — cold starts, execution limits, per-request pricing, and connection pooling against a database that was not designed for a thousand ephemeral clients.
* [ ] 🟡⭐ **Managed Services**: Understand the concept of managed services and when to use them — the build-vs-buy trade-off, lock-in, and the operational burden you are actually paying to avoid.
