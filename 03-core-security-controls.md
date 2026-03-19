# Core Security Controls

## 1. Authentication
All users should authenticate through a secure login flow. Parent, staff, coach, and administrator access should require verified identity and protected sessions. Passwords must never be stored in plain text, and session handling should reduce the risk of account misuse.

## 2. Authorization and RBAC
The platform should enforce role-based access control. Parents should only view and manage their own children. Staff and coaches should only perform actions allowed by their institution role. Platform administrators may have broader visibility, but high-risk actions should be tightly restricted.

## 3. Tenant Isolation
Mojakey is a multi-tenant platform, so one institution must never access another institution’s data. Every request should be evaluated against tenant context, and data access should be scoped to the correct institution.

## 4. Audit Logging
Important actions should be recorded in tamper-resistant audit logs. This includes login activity, check-in/check-out events, role changes, billing-relevant actions, and administrative updates. Audit logs support operational review and incident investigation.

## 5. QR Security
QR-based flows should not rely on simple static codes alone. Tokens should be time-bound, hard to guess, and validated by the backend before any sensitive action is completed. Reuse protection and expiration should be considered.

## 6. Privacy Protection
The system should minimize exposure of student and parent data. Personal information should be protected in transit and at rest. User interfaces should reveal only the data required for the task being performed.

## 7. Event Integrity
Attendance and billing-related events should be trustworthy. The system should prevent duplicate check-ins, unauthorized check-outs, replayed QR scans, and manual tampering with attendance history.

## 8. Incident Investigation Readiness
The platform should be designed so suspicious activity can be investigated later. Logs, timestamps, actor identity, tenant context, and event history should make it possible to trace what happened during a dispute or security incident.
