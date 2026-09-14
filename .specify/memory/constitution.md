<!--
Sync Impact Report
Version change: unratified template -> 1.0.0
Modified principles: template placeholders -> five project principles
Added sections: Training and Technology Constraints; Development Workflow and Quality Gates
Removed sections: template examples and placeholders
Follow-up TODOs: none
-->

# ContosoDashboard Constitution

## Core Principles

### I. User Value and Bounded Scope
Every feature MUST support a documented employee workflow or training objective.
Specifications MUST define user stories, acceptance scenarios, explicit boundaries, and
measurable success criteria before implementation begins. Work outside the approved scope
requires a separate feature specification.

### II. Secure-by-Default Access
Protected pages MUST require authentication, and service operations MUST enforce
authorization at the object level rather than relying only on UI visibility. User input
MUST be validated at the service boundary. Features that expose or change another user's
data MUST define the permitted roles and ownership rules in their specification.

### III. Offline-First Simplicity
The training application MUST run locally without mandatory external services. New
infrastructure dependencies require a documented reason and a local development path.
The existing service abstractions, dependency injection, Entity Framework Core model, and
SQLite development database MUST be preferred over parallel data-access approaches.
Complexity MUST be added only when it removes a demonstrated limitation.

### IV. Verifiable Incremental Delivery
Changes MUST be traceable from specification to plan to tasks to implementation. Each user
story MUST be independently testable where practical. A change is not complete until the
application builds successfully and its relevant acceptance scenarios have been checked.
Tests, validation commands, or documented manual checks MUST be added when the change's
risk cannot be covered by compilation alone.

### V. Maintainable and Observable Code
Application code MUST preserve the separation between pages, services, models, and data
access. Public service contracts MUST remain explicit and focused. Failures MUST be logged
with enough context for local diagnosis while user-facing messages avoid leaking sensitive
details. Unused code, unrelated refactors, and speculative abstractions MUST be avoided.

## Training and Technology Constraints

ContosoDashboard is an educational application and MUST be treated as non-production code.
The supported stack is ASP.NET Core and Blazor Server on .NET 10, Entity Framework Core,
SQLite for local persistence, and the repository's existing Bootstrap-based UI. Mock
authentication is acceptable for training, but production guidance MUST call out the need
for a real identity provider, password protection, MFA, secure deployment, and audit
controls.

Database changes MUST preserve the seeded-data workflow and MUST work on supported developer
machines, including ARM64 Windows systems. The application MUST not require SQL Server
LocalDB for local development.

## Development Workflow and Quality Gates

Feature work MUST follow the Spec Kit flow: specify, clarify when needed, plan, generate
tasks, implement, and review. Plans and tasks MUST identify the files or boundaries they
affect. Before completion, contributors MUST run the narrowest relevant validation followed
by a project build. Documentation MUST be updated when setup, configuration, behavior, or
known limitations change.

## Governance

This constitution is the governing project guidance for feature specifications, plans,
tasks, and implementation reviews. A change that violates a MUST principle requires either
remediation or an explicit constitution amendment; it MUST NOT be silently ignored.

Amendments MUST update the version, last-amended date, and sync impact report. Versioning
uses semantic versioning: MAJOR for incompatible governance changes, MINOR for new or
materially expanded principles, and PATCH for clarifications or non-semantic corrections.
Feature reviews MUST check scope, authorization, offline operation, traceability, and build
validation against this document.

**Version**: 1.0.0 | **Ratified**: 2026-09-14 | **Last Amended**: 2026-09-14
