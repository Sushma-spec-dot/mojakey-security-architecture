## Operational Data Storage

Operational platform data should be stored in a structured database that supports reliable transactions and clear relationships between users, families, children, institutions, enrollments, attendance records, roles, and payment-related records.

This storage layer should support day-to-day workflows such as account management, enrollment updates, check-in and check-out actions, institution operations, and administrative review.

## Sensitive Document and Verification Storage

Sensitive verification artifacts, such as identity-related documents or verification outputs, should be stored separately from normal operational records with tighter access controls.

Access to these records should be restricted to authorized workflows and approved administrative or verification functions only. The platform should minimize unnecessary retention of sensitive verification data and avoid exposing such data in normal user-facing workflows.

## Audit Log Storage

Audit logs should be stored in a way that preserves important history for later review. These records should capture who performed an action, what action occurred, when it happened, and in which tenant or account context it took place.

Audit log storage should support dispute handling, security investigation, administrative review, and traceability across sensitive workflows such as role changes, attendance events, enrollment changes, and payment-related updates.

## Data Integrity Considerations

The storage design should help protect important records from unauthorized change, accidental overwrite, or inconsistent updates. Attendance, enrollment, and billing-related records should remain trustworthy and tied to valid actor, time, and tenant context.

Where appropriate, the platform should preserve historical state for sensitive operational events so changes can be reviewed later through audit records and event history.

## Growth Considerations

As Mojakey grows across more institutions, families, students, programs, and attendance events, the storage design should continue to support reliable reads and writes.

The design should allow future improvements such as stronger indexing, data partitioning, service-specific access patterns, and better separation of operational records from high-volume audit or history data.
