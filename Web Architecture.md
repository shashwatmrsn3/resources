

## 1. API Design & Architecture

### RESTful APIs
- Resource modeling
- HTTP methods & status codes
- Versioning (URI, headers, query params)
- Pagination (offset vs cursor)
- HATEOAS

### GraphQL
- Schema definition
- Resolvers
- N+1 query problem
- Query complexity limits

### gRPC
- Protocol Buffers
- Unary vs streaming RPCs
- Strong typing and contract enforcement
- Authentication via metadata

### API Documentation
- OpenAPI / Swagger
- Postman Collections
- API-first development

### API Gateway
- Request routing
- Rate limiting & throttling
- Authentication and Authorization
- Caching and compression
- Tools: Kong, Apigee, AWS API Gateway

---

## 2. Authentication

### OAuth 2.0
- Roles: Resource owner, client, auth server, resource server
- Grant types: Authorization code, Client credentials, Implicit, PKCE

### OpenID Connect (OIDC)
- Identity layer on top of OAuth 2.0
- ID token vs access token

### JWT (JSON Web Tokens)
- Structure: Header, Payload, Signature
- Expiry, audience, issuer validation
- Risks: token leakage, replay

### Session-based Auth
- Cookies & session stores
- CSRF protection

### Single Sign-On (SSO)
- SAML, OIDC
- Enterprise integrations (Okta, Azure AD)

### Multi-Factor Authentication (MFA)
- TOTP, SMS, Email codes
- WebAuthn / FIDO2

---

## 3. Microservices

### Architecture
- Bounded Contexts
- Domain-Driven Design (DDD)
- Shared nothing architecture

### API Gateway
- Centralized ingress point
- Protocol translation (REST ⇄ gRPC)
- Authentication, metrics, and routing

### Service Discovery
- Client-side vs server-side discovery
- Tools: Consul, Eureka, Kubernetes DNS

### Inter-service Communication
- Synchronous: REST, gRPC
- Asynchronous: Kafka, RabbitMQ
- Event-driven design

### Data Ownership
- Database per service
- Eventual consistency
- Saga pattern (orchestration vs choreography)
- Outbox pattern, Change Data Capture

### Fault Tolerance
- Circuit breakers (Resilience4j, Hystrix)
- Retries, timeouts, bulkheads
- Load shedding

### Observability
- Centralized logging (ELK, Loki)
- Tracing (OpenTelemetry, Jaeger)
- Metrics (Prometheus, Grafana)

---

## 4. Caching

### Caching Layers
- Client-side (e.g., HTTP caching, browser)
- CDN (e.g., Cloudflare, Akamai)
- Server-side (application, database)

### Cache Strategies
- Write-through
- Write-behind
- Cache-aside
- Read-through

### Eviction Policies
- LRU, LFU, FIFO
- TTL / Expiry

### Tools & Systems
- In-memory: Redis, Memcached
- HTTP caching headers: ETag, Cache-Control
- Distributed caching considerations (consistency, invalidation)

---

## 5. Security

### Web Security (OWASP Top 10)
- SQL Injection, XSS, CSRF
- Insecure deserialization
- Security misconfigurations

### API Security
- Input validation
- Rate limiting
- Authentication & Authorization
- API keys vs OAuth tokens

### Token Management
- Secure storage
- Token expiry & refresh mechanisms
- Blacklisting and revocation

### Encryption
- TLS for data in transit
- AES for data at rest
- Hashing passwords (bcrypt, Argon2)

### Secrets Management
- Vault, AWS Secrets Manager
- Avoiding secrets in code
- Rotation policies

---

## 6. Testing

### Types of Tests
- Unit testing (fast, isolated)
- Integration testing (e.g., DB, services)
- End-to-end testing
- Smoke and sanity tests

### Microservice Testing
- Consumer-driven contract tests (Pact)
- API testing (Postman, REST Assured)
- Test containers for ephemeral dependencies

### Test Automation
- CI-integrated test suites
- Test coverage tools (Jacoco, Istanbul)
- Mocking frameworks (Mockito, WireMock)

### Load & Performance Testing
- JMeter, k6, Gatling
- Performance baselines & SLAs
- Chaos engineering (Gremlin, Litmus)

---

## 7. CI/CD (Continuous Integration / Delivery / Deployment)

### CI Concepts
- Automated builds and test runs
- Linting and static code analysis
- Artifact creation (e.g., Docker image, binary)

### CD Concepts
- Deployment pipelines
- Manual approvals, gates
- Progressive delivery: canary, blue-green, rolling

### Tools
- GitHub Actions, GitLab CI, Jenkins
- ArgoCD (GitOps)
- Spinnaker, CircleCI

### Deployment Strategies
- Rolling updates
- Blue-Green
- Canary deployments
- Feature flags

---

## 8. Scaling Databases

### Vertical vs Horizontal Scaling
- Read replicas
- Master-slave, master-master
- Sharding

### Partitioning
- Range vs Hash partitioning
- Rebalancing strategies
- Handling hot partitions

### Caching Layers
- Query caching
- Materialized views
- Redis as side cache

### Consistency & Availability
- Eventual vs strong consistency
- CAP Theorem
- Write concerns and read preferences (MongoDB, Cassandra)

### Tools and Techniques
- PostgreSQL: logical replication, partitioning
- MySQL: read replicas, Galera Cluster
- NoSQL: Cassandra, DynamoDB scaling patterns

---

## 9. Software Architecture Styles

### Monolith
- Single deployable unit
- Tight coupling of modules
- Easier to develop and test early on
- Hard to scale or modify over time

### Microservices
- Services are independent and loosely coupled
- Technology agnostic
- Requires CI/CD, service discovery, observability
- Higher operational complexity

### Serverless
- Function-as-a-Service (e.g., AWS Lambda)
- Event-driven
- No infrastructure management
- Cold start latency, observability limits

### Event-Driven Architecture
- Publish-subscribe pattern
- Asynchronous processing
- Scalability & decoupling
- Challenges in consistency & ordering

### Modular Monolith
- Clear module boundaries
- Internal service abstraction without network calls
- Easier transition path to microservices

### Service Mesh
- Infrastructure layer for service communication
- Features: observability, retries, circuit breaking, mTLS
- Tools: Istio, Linkerd

