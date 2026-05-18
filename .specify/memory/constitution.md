<!--
Sync Impact Report
Version change: template → 1.0.0
Modified principles: 5 principles added
Added sections: Technology & Quality Requirements, Development Workflow
Removed sections: none
Templates requiring updates: .specify/templates/plan-template.md ✅, .specify/templates/spec-template.md ✅, .specify/templates/tasks-template.md ✅
Follow-up TODOs: none
-->

# Peixes API Constitution

## Core Principles

### I. Domain-First API Design
Every service, endpoint, and data model MUST map clearly to the aquarium/fish domain. Implementation choices MUST favor explicit domain meaning over generic abstractions, so the API remains easy to understand, maintain, and evolve.
You need to follow this project structure:

## Project Structure

```text
README.md
pom.xml
src/
  main/
    kotlin/
      com/aquarium/peixes/
        PeixesApplication.java
        api/
          controller/
        domain/
          model/
          service/
            utils/
        infra/
          config/
          repository/
    resources/
      application.properties
      log4j2.xml
  test/
    java/
      com/aquarium/peixes/
        PeixesApplicationTests.java
```

### II. Kotlin and Spring Boot Idiomatic Engineering
Solutions MUST leverage Kotlin safety and Spring Boot conventions. Avoid unsafe null handling, unnecessary reflection, and custom wiring that bypasses framework semantics; prefer immutable data and standard dependency injection.

### III. Test-First Reliability
Tests MUST be written and passing before behavior is accepted. Unit tests MUST cover business rules, and integration tests MUST verify API contract and runtime wiring; regression protection is mandatory for every change.

### IV. Observability and Failure Transparency
The system MUST expose clear runtime behavior through logging, structured context, and explicit error responses. Failures SHOULD be detectable and diagnosable without guesswork, and observability MUST be part of each change.

### V. Semantic Versioning and Safe Evolution
External interfaces and runtime contracts MUST follow semantic versioning. Breaking changes MUST be documented and justified, and changes SHOULD be delivered in small, reviewable increments.

## Technology & Quality Requirements

The project MUST use Kotlin 2.2.x, Spring Boot 4.x, and Java 24 compatibility. Dependencies MUST stay current enough to avoid known security and stability issues. API contracts SHOULD be documented, configuration MUST be externalized, and deprecated APIs MUST be avoided when safer alternatives exist.

## Development Workflow

Work MUST follow the `.specify` lifecycle for planning, specification, and task execution. Every PR MUST link to the relevant spec or task artifacts, include a test summary, and state any compatibility or migration risk.

Code review MUST validate architecture, tests, and constitution compliance. Merge gates MUST include build verification, tests, and a constitution compliance check for the feature or fix.

## Governance

This constitution supersedes informal practices for the Peixes API repository. Amendments MUST be proposed through documented changes in source control, include a clear rationale, and update supporting guidance and templates as needed.

Compliance reviews MUST occur before merge, with reviewers explicitly verifying that changes follow the principles above. Non-compliant work MUST be revised rather than merged.

**Version**: 1.0.0 | **Ratified**: 2026-05-17 | **Last Amended**: 2026-05-17
