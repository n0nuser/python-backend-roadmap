# Intermediate Level

> [!NOTE]
> The difficulty of a particular subject is defined by 🟢 🟡 🔴 from easy to hard.
>
> The importance of a particular subject is defined by ⭐. 0 is not important, 1 is important, 2 is considerably important, 3 is very important.

## General Knowledge and Best Practices

* [ ] 🟢⭐⭐⭐ **Debugging**: Learn how to follow the flow of your code with specific tools to fix errors.

## Database Management

* [ ] 🟡⭐⭐ **Database Backup and Recovery**: Learn how to back up and recover databases.
* [ ] 🟡⭐⭐ **Database Migration**: Understand database migration and its use cases.
* [ ] 🟡⭐ **Database Indexing**: Learn about database indexing and how to create indexes.
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
  * [ ] 🟡⭐ NumPy
  * [ ] 🟡⭐ Pandas
  * [ ] 🟢⭐⭐ Pydantic
  * [ ] 🟡⭐⭐ HTTPX
  * [ ] 🟢⭐⭐ Requests
  * [ ] 🟡⭐⭐ SQLAlchemy
  * [ ] 🟡⭐⭐ Django ORM
* [ ] **Frameworks**:
  * [ ] 🟡⭐⭐ Django
  * [ ] 🟡⭐⭐ FastAPI
* [ ] **Deployment**:
  * [ ] 🟢⭐ Uvicorn
  * [ ] 🟢⭐ Gunicorn
  * [ ] 🟡⭐ Nginx
  * [ ] 🟡⭐⭐ [Docker](#containerization-and-orchestration)
* [ ] 🟢⭐⭐ **Error Handling**: Understand how to handle and raise exceptions in Python.
* [ ] **Testing and Quality Assurance**
  * [ ] 🟡⭐ Unit Testing: Learn the principles of unit testing in Python.
  * [ ] 🟡⭐ Integration Testing: Understand how to perform integration testing for applications.
  * [ ] Test Automation:
    * [ ] 🟡⭐ Pytest for automated testing.
    * [ ] 🟡⭐ Tox for automated testing of Python versions.
* [ ] **Documentation**:
  * [ ] 🟢⭐⭐⭐ Docstrings: Learn how to write docstrings in Napoleon format for documenting Python code.
  * [ ] 🟡⭐ Sphinx: Explore Sphinx for generating documentation from docstrings.
  * [ ] 🟢 Read the Docs: Learn how to host documentation on Read the Docs.
  * [ ] 🟢⭐⭐ Markdown: Learn how to write documentation in Markdown format.
  * [ ] 🟡⭐ Mermaid: Explore Mermaid for generating diagrams from text.
* [ ] 🟡⭐⭐⭐ **Generators**: Explore advanced Python features for efficient and clean code.
* [ ] 🟡⭐ **Decorators**: Learn how to use decorators for advanced Python programming.
* [ ] 🟡⭐⭐ **Data Classes**: Understand data classes for solving complex structuring problems.

## Web Services
  
* [ ] 🟡⭐⭐ **Services and Microservices**: Understand the basics of services and microservices.
  * [ ] 🟢⭐ Isolation: Learn about isolation in microservices.
  * [ ] 🟡⭐ Communication: Explore communication between microservices.
  * [ ] 🟢 Service Discovery: Understand service discovery and networking in microservices.

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
  * [ ] 🟡⭐ Microservices: Microservices is an architectural style that structures an application as a collection of small autonomous services, modeled around a business domain.
* [ ] 🟡⭐⭐ **Design Patterns**: Explore software design patterns (e.g., Singleton, Observer, Factory) and their use cases.
  * [ ] 🟢 [Refactoring Guru](https://refactoring.guru/design-patterns): A website that provides descriptions, examples, and use cases for various software design patterns.
* [ ] 🟡⭐ **Approaches**
  * [ ] 🟡⭐⭐ Domain Driven Design: An approach to software development that centers the development on programming a domain model that has a rich understanding of the processes and rules of a domain.
* [ ] 🟡⭐ **API Versioning**: Learn about different strategies for versioning APIs.

## Continuous Integration and Continuous Deployment (CI/CD)

* [ ] 🟢⭐⭐ **CI/CD Pipelines**: Continuous Integration (CI) is a development practice where developers integrate code into a shared repository frequently. Continuous Deployment (CD) is a strategy for software releases wherein any code commit that passes the automated testing phase is automatically released into the production environment.
  * [ ] 🟡⭐⭐ Jenkins: Learn how to set up a Jenkins server, create Jenkins pipelines, and integrate Jenkins with your version control system.
    * [ ] 🟡 Jenkinsfile: Understand the Jenkinsfile format for defining pipelines as code.
    * [ ] 🟢 Plugins: Explore the wide range of plugins available to extend Jenkins' functionality.
  * [ ] 🟢⭐⭐ **GitLab CI**: Understand how to use GitLab's built-in CI/CD to automate builds, tests, and deployments.
    * [ ] 🟡 .gitlab-ci.yml: Learn about the .gitlab-ci.yml file format for defining GitLab CI/CD pipelines.
    * [ ] 🟢 Runners: Learn about GitLab runners and how they execute your CI jobs.
  * [ ] 🟢⭐ **GitHub Actions**: Learn how to automate workflows directly from your GitHub repository with GitHub Actions.
    * [ ] 🟡 Workflow Files: Understand the .github/workflows format for defining GitHub Actions workflows.
    * [ ] 🟡 Actions: Explore the marketplace of actions available to use in your workflows.
  * [ ] 🟡⭐ **Building Docker Images in CI/CD**: Learn how to build Docker images as part of your CI/CD pipelines.

## Monitoring and Logging

* [ ] 🟢⭐⭐ **Logging Strategies**: Logging is the act of keeping a log, or a record of activities or events within a system. It's crucial for debugging and monitoring system health.
  * [ ] 🟡 Log Levels: Understand the different log levels (e.g., INFO, DEBUG, ERROR) and when to use each.
  * [ ] 🟡 Structured Logging: Learn about structured logging and how it can make searching and analyzing logs easier.
  * [ ] 🟢 Log Rotation: Understand the concept of log rotation to manage disk space.

## Security Practices

* [ ] 🟢⭐⭐ **Web Security Basics**: Web security involves protecting websites or web applications by detecting, preventing and responding to attacks. Topics include Cross-Site Scripting (XSS), SQL Injection, Cross-Site Request Forgery (CSRF), and more.
* [ ] 🟢⭐⭐ **OWASP Top 10**: Familiarize yourself with the OWASP Top 10 most critical web application security risks.
* [ ] 🔴⭐⭐⭐ **Secure Authentication and Authorization**: Learn about secure authentication and authorization mechanisms. Understand the importance of strong password policies, multi-factor authentication (MFA), and secure session management. Implement proper access control to ensure that only authorized users can perform specific actions and access sensitive information.
* [ ] 🔴⭐⭐⭐ **Secure Communication**: Gain knowledge about secure communication protocols such as HTTPS (HTTP over SSL/TLS) and the importance of encrypting sensitive data in transit. Learn about certificate management, secure configuration of web servers, and secure transmission of data over networks.
* [ ] 🟡⭐ **Secure Data Storage**: Understand how to securely store sensitive data, including passwords, personally identifiable information (PII), and other confidential information. Learn about encryption, hashing, and salting techniques to protect data at rest. Implement secure data storage practices to prevent unauthorized access and data breaches.
* [ ] 🟡⭐ **Container Security**: Understand security best practices for Docker containers and Kubernetes.

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
