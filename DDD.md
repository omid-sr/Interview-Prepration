# Domain-Driven Design (DDD) Concepts

## 1. **Problem Domain vs. Solution Domain**

### Problem Domain  
Refers to the **real-world challenges** and **business rules** that an application addresses. Requires collaboration with domain experts to understand requirements, constraints, and core business logic.

### Solution Domain  
Focuses on **technical implementation** and design patterns (architecture, frameworks, technologies) used to solve problem domain challenges.

---

## 2. **Strategic Design**  
High-level architectural decisions aligning software with business needs.

### 2.1 Ubiquitous Language  
A **shared domain-specific vocabulary** used by developers and domain experts to eliminate misunderstandings.

### 2.2 Bounded Context  
A **clear boundary** where a domain model is defined and consistent. Prevents conflicts between different parts of the system.

### 2.3 Sub-domains  
A domain is divided into:  
- **Core Domain**: Critical part driving competitive advantage.  
- **Supporting Sub-domain**: Important but not a differentiator.  
- **Generic Sub-domain**: Common functionality handled by off-the-shelf solutions.

---

## 3. **Tactical Design**  
Implementation patterns within a bounded context.

### 3.1 Aggregate Root & Aggregate  
- **Aggregate**: A cluster of domain objects treated as a single unit.  
- **Aggregate Root**: The main entity controlling access and enforcing business rules.

### 3.2 Value Object  
An **immutable object** without a unique identity (e.g., `Money`, `Address`, `DateRange`).

### 3.3 Domain Services  
Logic that doesn’t fit in entities or value objects (e.g., operations spanning multiple aggregates).

### 3.4 Application Services  
Orchestrates workflows, delegates tasks to domain objects, and exposes functionality to clients.

### 3.5 Domain Events  
Captures domain changes (e.g., `OrderPlaced`, `UserRegistered`) for asynchronous system notifications.

### 3.6 Context Mapping  
Relationships between bounded contexts:  
- **Partnership**: Teams collaborate closely.  
- **Shared Kernel**: Shared subset of the model.  
- **Customer-Supplier**: Dependency between contexts.  
- **Conformist**: One context conforms to another’s model.

### 3.7 Integration Between Bounded Contexts  
- **Messaging (Event-Driven)**: Kafka, RabbitMQ.  
- **RPC**: gRPC, REST APIs.  
- **Data Sharing**: Shared databases (use cautiously).

### 3.8 Entity Persistence  
Using ORMs (e.g., Entity Framework, Hibernate) while preserving domain rules.

---

## 4. **Common DDD Patterns**

### 4.1 Factory  
Encapsulates complex object creation logic.

### 4.2 Repository  
Abstracts data access for domain-focused business logic.

### 4.3 Unit of Work  
Ensures atomic transactions for multiple changes.

### 4.4 Event Sourcing  
Stores domain events (not state) for auditability and state reconstruction.

### 4.5 CQRS (Command Query Responsibility Segregation)  
Separates read/write operations for performance/scalability.

---

## 5. **Additional Patterns & Concepts**

### 5.1 Anti-Corruption Layer  
Translates between bounded contexts to prevent model contamination.

### 5.2 Saga Pattern  
Manages long-running transactions with compensating actions.

### 5.3 Hexagonal Architecture (Ports & Adapters)  
Decouples core logic from infrastructure for maintainability.

### 5.4 Specification Pattern  
Encapsulates business rules into reusable objects (e.g., `CustomerEligibilitySpecification`).

### 5.5 Domain Event Handlers  
React to domain events and trigger further actions (e.g., sending emails on `OrderPlaced`).

### 5.6 Event Storming  
A workshop technique to explore and model complex domains.

### 5.7 Layered Architecture  
Separates concerns into layers: Presentation, Application, Domain, and Infrastructure.

### 5.8 Domain-Driven Security  
Integrates security concerns into the domain model.

### 5.9 Eventual Consistency  
Asynchronous propagation of updates in distributed systems.

### 5.10 Domain-Driven Microservices  
Applying DDD principles to microservices architecture.

### 5.11 Domain-Driven Testing  
Writing tests that reflect the domain model.

### 5.12 Domain-Driven Refactoring  
Refactoring code to better align with the domain model.

### 5.13 Domain-Driven Documentation  
Creating documentation that reflects the ubiquitous language and domain model.
