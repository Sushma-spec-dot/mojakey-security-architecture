## High-Level Diagram

Parent / Guardian App
        |
        v
Authentication and Verification Layer
        |
        v
Backend API and Application Logic
        |
        +------------------------------+
        |              |               |
        v              v               v
Profile Service   Enrollment Service   Attendance Service
                                        |
                                        v
                                  QR Validation Service

Backend API and Application Logic
        |
        +------------------------------+
        |              |               |
        v              v               v
Billing Service   Audit Logging Service   Database / Secure Storage

## Security Checkpoints

- Authentication before protected access
- Email or identity verification where required
- Role-based access control before sensitive actions
- Tenant isolation before data access
- QR validation before QR-triggered workflows
- Audit logging after sensitive operational or administrative events
- Event validation before attendance, enrollment, or billing-impacting writes

