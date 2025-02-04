1. Problem Domain vs. Solution Domain

Problem Domain

The problem domain refers to the real-world challenges and business rules that an application is intended to address. Understanding the problem domain requires collaboration with domain experts to grasp requirements, constraints, and core business logic.

Solution Domain

The solution domain consists of the technical implementation and design patterns used to solve the problems identified in the problem domain. This includes architecture, frameworks, and technologies used to create the software solution.

2. Strategic Design

Strategic Design focuses on defining high-level architectural decisions, ensuring that the software reflects the business domain.

2.1 Ubiquitous Language

A shared, domain-specific language used by both developers and domain experts. It eliminates misunderstandings by ensuring that everyone involved in the project uses the same terminology.

2.2 Bounded Context

A Bounded Context is a clear boundary within which a particular domain model is defined and consistent. It ensures that different parts of the system do not conflict due to differences in definitions or rules.

2.3 Sub-domains

A domain can be divided into three types of sub-domains:

Core Domain: The most critical part of the system, where the company derives its competitive advantage.

Supporting Sub-domain: Important for the core domain but not a differentiator.

Generic Sub-domain: Common functionalities that can be handled using off-the-shelf solutions.

3. Tactical Design

Tactical design focuses on implementation patterns within a bounded context.

3.1 Aggregate Root & Aggregate

Aggregate: A cluster of domain objects that should be treated as a single unit.

Aggregate Root: The main entity that controls access to the aggregate and enforces business rules.

3.2 Value Object

A small, immutable object without a unique identity, used to represent domain concepts such as Money, Address, or DateRange.

3.3 Domain Services

Domain logic that doesn’t naturally belong to an entity or value object, often used for operations involving multiple aggregates.

3.4 Application Services

Orchestrates workflows by delegating work to domain objects, enforcing application logic, and exposing domain functionality to clients.

3.5 Domain Events

A mechanism to capture domain-relevant changes (e.g., OrderPlaced, UserRegistered) and notify other parts of the system asynchronously.

3.6 Context Mapping

Defines the relationships between bounded contexts. Some common mapping patterns:

Partnership: Two teams collaborate closely.

Shared Kernel: A shared subset of the model is maintained together.

Customer-Supplier: One context depends on another.

Conformist: One context must conform to another’s model.

3.7 Integration between Bounded Contexts

Different bounded contexts can communicate via:

Messaging (Event-Driven Architecture): Using message queues like Kafka or RabbitMQ.

Remote Procedure Calls (RPC): Direct synchronous calls, often via gRPC or REST APIs.

Data Sharing: Sharing databases cautiously when necessary.

3.8 Entity Persistence

Persisting domain entities using an ORM (like Entity Framework, Hibernate) while ensuring domain rules are not violated.

4. Common DDD Patterns

4.1 Factory

Encapsulates complex object creation logic, ensuring valid domain objects are instantiated.

4.2 Repository

Provides an abstraction for data access, allowing the domain model to focus on business logic.

4.3 Unit of Work

Ensures multiple changes are committed as a single transaction, reducing data inconsistency.

4.4 Event Sourcing

Stores a sequence of domain events instead of the current state, allowing full auditability and state reconstruction.

4.5 Command Query Responsibility Segregation (CQRS)

Separates read and write operations to optimize performance and scalability.

5.1 Anti-Corruption Layer

A layer that translates between two bounded contexts to prevent model contamination.

5.2 Saga Pattern

Manages long-running business transactions across multiple services using compensating actions.

5.3 Hexagonal Architecture (Ports & Adapters)

Separates the core domain logic from infrastructure concerns, making the system more maintainable.