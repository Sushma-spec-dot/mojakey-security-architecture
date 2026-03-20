## Project Framing

This project is a design-first system design and security architecture case study for Mojakey, a multi-tenant family and institution platform for child enrollment, attendance, check-in, and check-out workflows.

I chose this problem because it is a realistic workflow with meaningful security requirements. It involves family accounts, child-related operations, institution staff actions, payment-related workflows, and trust-sensitive scenarios such as QR-based check-out and attendance disputes.

The goal of the project was to show how to think through architecture, security controls, trust boundaries, and operational risks in a practical system.

## Architecture Summary

The design centers on a family-facing application, an institution-facing admin portal, a backend API and application layer, and core services for profile management, enrollment, attendance, billing, QR validation, and audit logging.

At a high level, requests flow from the client application to authentication and verification, then to the backend API, where role and tenant checks are applied before the request is routed to the correct service. Approved changes are written to storage, and important actions are captured through audit logging.

The architecture is intentionally structured to separate user workflows, institution workflows, and cross-cutting controls such as authorization, logging, and tenant isolation.

## Security Summary

The main security concerns in Mojakey are unauthorized access, cross-tenant data exposure, unsafe check-in or check-out actions, weak QR workflows, poor traceability, and tampering with attendance or billing-related events.

To address these risks, the design includes authentication, email verification, optional higher-trust identity verification, role-based access control, tenant isolation, audit logging, QR validation, privacy protections, and event integrity controls.

The project emphasizes that security is built into the workflow, not added only at the end. Sensitive actions require checks before they are allowed, and important events are recorded so they can be investigated later if needed.

## Tradeoffs and Design Choices

One important tradeoff is between stronger verification and user friction. For example, requiring identity verification for every workflow would increase trust but also make onboarding and daily usage harder. A better design is to reserve stronger verification for higher-trust actions.

Another tradeoff is between speed and safety. Check-in and check-out flows need to be fast during peak times, but they also need strong authorization, tenant checks, and event validation. The architecture should remain responsive without weakening core protections.

A third tradeoff is around caching and consistency. Caching can improve performance for frequently accessed data such as rosters or institution settings, but sensitive workflows such as attendance and billing-impacting actions should not rely on stale data in a way that creates unsafe outcomes.

## Honest Implementation Statement

This repository is primarily a system design and security architecture project, not a full backend implementation.

I did not build the full production backend for this system. The value of the project is in the way it breaks down a realistic problem into requirements, workflows, trust boundaries, architecture components, and security controls.

I used AI tools to help speed up documentation structure and refinement, but the problem framing, workflow reasoning, security concerns, and design choices were guided by my own understanding of the real-world use case.
