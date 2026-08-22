# Beginners Guide

> [!NOTE]
> The difficulty of a particular subject is defined by 🟢 🟡 🔴 from easy to hard.
>
> The importance of a particular subject is defined by ⭐. 0 is not important, 1 is important, 2 is considerably important, 3 is very important.

> [!TIP]
> **What you're expected to *do* at this level, not just know**: ship a reviewed pull request with tests to a real repository, reproduce any bug report as a raw request with `curl`, and build and deploy a small service end to end. Employers assess beginners at that level.

## Recommended Path

If you only do ten things at this level, do these:

1. Master **Core Python** — solve small exercises every day.
2. Set up the modern toolchain: **uv**, `pyproject.toml` and **Ruff**. Commit your lockfile.
3. Learn **type hints** and run a type checker (`mypy`) on your own code.
4. Get fluent with **Git** and open pull requests other people can review.
5. Understand **HTTP semantics** (methods, status codes, headers) and debug requests with `curl -v`.
6. Write real **SQL** against PostgreSQL: joins, aggregates, CTEs.
7. Model tables with proper **constraints** and understand why they protect you.
8. Understand **transactions** and what an **index** does; read an `EXPLAIN ANALYZE` plan.
9. Validate external input with **Pydantic**, annotate internal code.
10. Build the portfolio project below and deploy it somewhere public.

**Portfolio project**: a CRUD API (FastAPI or Django) with authentication, a PostgreSQL database and a test suite, deployed publicly with a README explaining how to run it.

## General Knowledge and Best Practices

* [ ] 🟢⭐⭐ **Foundational Concepts**: Understand programming logic, algorithms, and data structures.
  * [ ] 🟢⭐⭐⭐ Programming Logic: Learn about control structures, loops, and conditional statements.
  * [ ] 🟡⭐ Algorithms: Understand basic algorithms like sorting and searching.
  * [ ] 🟢⭐⭐ Data Structures: Learn about different data structures like arrays, linked lists, stacks, queues, trees, and graphs.
* [ ] 🟢⭐⭐ **Coding Standards and Best Practices**: Familiarize yourself with clean code principles.
  * [ ] 🟢⭐⭐ Naming Conventions: Learn about the importance of meaningful and consistent naming.
  * [ ] 🟢⭐⭐ Code Formatting: Let a formatter (**Ruff**) enforce indentation and code organization instead of debating style by hand.
  * [ ] 🟢 Commenting: Learn how to write effective comments.
  * [ ] 🟢⭐⭐ Refactoring: Understand how to improve and clean up your code without changing its behavior.
* [ ] 🟡⭐⭐ **Command Line and Scripting**: Gain proficiency in using the command line and scripting with Bash.
  * [ ] 🟢⭐⭐ Basic Commands: Learn basic command line commands like `ls`, `cd`, `rm`, `cp`, `mv`, etc.
  * [ ] 🟢⭐⭐ File System Navigation: Understand how to navigate the file system using the command line.
  * [ ] 🟡 Command Line Tools: Familiarize yourself with command line tools like `grep`, `awk`, `sed`, etc.

## Database Management

> [!TIP]
> This roadmap treats **PostgreSQL as the default database** and SQLite as the local/testing companion — it reflects what most teams ship, and lets you practice concrete tooling like `EXPLAIN ANALYZE`.

* [ ] 🟢⭐⭐⭐ **Database Basics**: Databases are organized collections of data. They come in many types, including relational databases, NoSQL databases, graph databases, and time-series databases. Understanding the basics of these databases and when to use them is crucial for backend development.
  * [ ] 🟡⭐⭐ Relational Databases: Learn about relational databases and their principles.
  * [ ] 🟡⭐⭐ NoSQL Databases: Explore NoSQL databases and their principles.
* [ ] 🟢⭐⭐⭐ **Writing SQL**: The database is the main source of both bugs and latency in a backend. Install PostgreSQL and get fluent writing queries by hand before touching an ORM. ([PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html))
  * [ ] 🟢⭐⭐⭐ Queries: `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`.
  * [ ] 🟢⭐⭐⭐ Joins: all types — `INNER`, `LEFT`, `RIGHT`, `FULL`, plus self-joins.
  * [ ] 🟢⭐⭐⭐ Aggregates: `GROUP BY`, `HAVING`, and aggregate functions (`count`, `sum`, `avg`).
  * [ ] 🟡⭐⭐ Subqueries and CTEs (`WITH`): break complex queries into readable steps.
  * [ ] 🟡⭐⭐ Window Functions: at least `ROW_NUMBER`, `RANK`, and running totals.
* [ ] 🟢⭐⭐⭐ **DDL & Constraints**: primary/foreign keys, `UNIQUE`, `NOT NULL`, `CHECK`, and `ON DELETE` behaviour. Constraints are the last line of defence for data integrity — enforce rules in the schema, not only in application code.
* [ ] 🟡⭐⭐⭐ **Transactions**: `BEGIN`/`COMMIT`/`ROLLBACK`; isolation levels (read committed vs repeatable read vs serializable); what a deadlock looks like; why "one transaction per request" is a design decision, not an accident.
* [ ] 🟡⭐⭐ **Indexes, early**: B-tree basics, composite index column order, covering indexes, and reading `EXPLAIN ANALYZE` on PostgreSQL. ([Use The Index, Luke](https://use-the-index-luke.com))
* [ ] 🟡⭐⭐ **PostgreSQL Types Worth Knowing**: `jsonb`, arrays, `uuid`, `timestamptz` (and always storing UTC), `numeric` vs `float` for money.
* [ ] 🟡⭐⭐ **The ORM Boundary**: know what SQLAlchemy/Django ORM actually generates, the N+1 query problem, lazy vs eager loading, and when to drop down to raw SQL.
* [ ] 🟢⭐ **Connections**: connection pools, why they are finite, and what "too many connections" means once every container needs its own pool.
* [ ] 🟡⭐⭐ **Database Design**: Learn about database design and normalization.
  * [ ] 🟢⭐ Entity Relationship Diagrams (ERDs): Learn how to create ERDs for database design.
  * [ ] 🟡⭐⭐ Database Normalization: Understand the importance of database normalization and how to normalize databases.
  * [ ] 🟡⭐ **Database Denormalization**: Understand database denormalization and its use cases.
  * [ ] 🟡⭐⭐ SQL and NoSQL: Understand the difference between SQL and NoSQL databases and when to use each.
  * [ ] 🟡⭐ ACID and CAP Theorem: Learn about the ACID properties of transactions and the CAP theorem.
* [ ] 🟡⭐⭐ **Relational Databases**:
  * [ ] 🟢⭐ SQLite: Great as a local and testing companion.
  * [ ] 🟢⭐⭐ PostgreSQL: The default choice for new backend services.
  * [ ] ...
* [ ] 🟡⭐ **NoSQL Databases**:
  * [ ] 🟢⭐ MongoDB: Explore the basics of document-oriented databases.
  * [ ] 🟢⭐ Apache Cassandra: Learn about distributed NoSQL databases and their principles.

## Version Control and Collaboration

* [ ] 🟢⭐⭐⭐ **Version Control**: Version control systems allow you to track changes to your code, collaborate with other developers, and revert back to previous versions of your code if necessary. Git is the most widely used version control system.
  * Understand the basic concepts of version control.
  * Install Git on your local machine.
  * Set up your first Git repository.
  * Learn the basic Git commands: `init`, `add`, `commit`, `status`, `log`.

## Python Knowledge

* [ ] 🟢⭐⭐⭐ **Core Python**: Master the basics of Python programming. This includes understanding variables, data types, operators, control flow, functions, and error handling.
* [ ] 🟢⭐⭐⭐ **Type Hints and Static Typing**: In 2026 a typed codebase is the norm — FastAPI, Pydantic and SQLAlchemy 2.0 are designed around annotations, so learn them now rather than re-learning the libraries later. ([Static typing docs](https://typing.readthedocs.io/))
  * [ ] 🟢⭐⭐⭐ Basic Annotations: parameters, return types, variables; built-in generics (`list[int]`, `dict[str, int]`); `X | None` instead of the legacy `typing.List` / `Optional`.
  * [ ] 🟢⭐⭐ Type Checkers: run `mypy` (or `pyright`/`ty`) locally and in CI. Understand that Python does *not* enforce annotations at runtime. ([mypy](https://mypy.readthedocs.io/))
  * [ ] 🟡⭐⭐ Useful Constructs: `TypedDict`, `Protocol` (structural typing), `Literal`, `Enum`, `NewType`, generics with the PEP 695 syntax (`class Box[T]`).
  * [ ] 🟡⭐ Gradual Typing: adopting types in an untyped codebase, per-module strictness, `# type: ignore` hygiene.
  * [ ] 🟢⭐⭐ Runtime Validation vs Static Typing: why Pydantic exists and where the boundary sits — external input is validated, internal code is annotated.
* [ ] 🟢⭐⭐⭐ **Environment Setup**: Set up your Python development environment with the modern toolchain. Dependency resolution, reproducible environments, and a consistent formatter are the first things a team expects from a new hire — before any framework knowledge.
  * [ ] 🟢⭐ Venv: Python's built-in virtual environment mechanism that tools like uv manage for you.
  * [ ] 🟢⭐⭐⭐ [`pyproject.toml`](https://packaging.python.org/en/latest/guides/writing-pyproject-toml/): the single project manifest — metadata, dependencies, tool config. Understand PEP 621 fields and why a bare `requirements.txt` is no longer enough.
  * [ ] 🟢⭐⭐⭐ [uv](https://docs.astral.sh/uv/): the de-facto fast installer/resolver/venv manager (`uv venv`, `uv add`, `uv sync`, `uv run`, `uv lock`, `uv python install`). Understand what a **lockfile** is and why it must be committed.
  * [ ] 🟢⭐⭐ Poetry / PDM / pip-tools: know they exist and what problem they all solve, so you can work in an existing repo that uses them.
  * [ ] 🟢⭐⭐⭐ [Ruff](https://docs.astral.sh/ruff/): linting *and* formatting in one tool (replaces flake8 + isort + black in most new projects). Learn to read and configure rule selections.
  * [ ] 🟢⭐⭐ pre-commit: run format/lint/secret checks before code ever reaches CI.
  * [ ] 🟢⭐⭐ Python Versions: what changed from 3.11 → 3.14 (performance, error messages, `tomllib`, `ExceptionGroup`, free-threaded builds), how to pick a version for a new service, and how to read the [CPython release/EOL calendar](https://devguide.python.org/versions/).
  * [ ] 🟢⭐ Editable Installs & Project Layout: `src/` layout, why imports break, `__init__.py`, packages vs modules.

## Web Fundamentals

> [!TIP]
> Containers and PaaS hide the machine until something breaks. Most production incidents a junior backend dev meets are HTTP/TLS/DNS-shaped, not framework-shaped. An engineer who can read a `curl -v` trace and a TLS error resolves incidents without escalating.

* [ ] 🟢⭐⭐⭐ **HTTP**: The protocol you will debug every single day. ([MDN HTTP docs](https://developer.mozilla.org/en-US/docs/Web/HTTP))
  * Methods and their semantics (safe / idempotent).
  * Status codes and when to use which class.
  * Headers, content negotiation, cookies.
  * Caching headers (`Cache-Control`, `ETag`) and CORS.
* [ ] 🟢⭐⭐⭐ **REST in Practice**: resource modelling, status code choice, pagination, error payload shape ([RFC 9457 problem details](https://www.rfc-editor.org/rfc/rfc9457)), idempotency keys.
* [ ] 🟢⭐⭐ **Client Tooling**: `curl`, HTTPie, `httpx`, browser dev tools — reproduce any bug report as a raw request.
* [ ] 🟡⭐⭐ **HTTP/1.1 vs HTTP/2 vs HTTP/3**: connection reuse, multiplexing, head-of-line blocking — enough to know why a proxy config matters.
* [ ] 🟡⭐⭐ **TLS/HTTPS Basics**: certificates, chains, SNI, expiry, `openssl s_client`; why "certificate verify failed" happens.
* [ ] 🟢⭐⭐ **DNS Basics**: A/AAAA/CNAME records, TTL, resolution order, `dig`.
* [ ] 🟡⭐⭐ **Ports, Sockets and Process Basics on Linux**: `ss`/`netstat`, `lsof`, environment variables, signals (SIGTERM and graceful shutdown), exit codes, file permissions, `systemd`/journald at a glance.
* [ ] 🟢⭐ **Serialization Formats**: JSON (and its footguns: floats, big ints, datetimes), plus awareness of Protobuf/MessagePack.

## Web Services

* [ ] 🟡⭐⭐⭐ **APIs and Web Services**: APIs, or Application Programming Interfaces, allow different software applications to communicate with each other. Web services are a type of API that operate over the web.
  * [ ] 🟢⭐ OpenAPI: The OpenAPI Specification (formerly Swagger) is a specification for building APIs. It provides a way to describe and document a RESTful API.
  * [ ] 🟡 GraphQL: An alternative to REST, GraphQL allows clients to define the structure of the data required, and the same structure of the data is returned from the server. Trade-offs are covered at advanced level.
