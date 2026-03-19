# Users, Assets, and Trust Boundaries

## Main Users
- Parents
- Students
- Institution staff
- Coaches
- Institution administrators
- Platform super admins

## Sensitive Assets
- Parent and student profile data
- Attendance records
- Check-in and check-out timestamps
- QR-based access or verification tokens
- Billing-related records
- Institution-level operational data
- Audit logs
- Staff role assignments

## Key Trust Boundaries
- Parent device to Mojakey application
- Staff/admin device to Mojakey admin portal
- Application backend to database
- Application backend to authentication provider
- Institution tenant data boundary
- QR scan flow between user/device and backend validation service

## Main Security Questions
- Who is allowed to check in or check out a child?
- How do we prevent one institution from seeing another institution’s data?
- How do we verify QR codes securely?
- How do we make sure attendance events are not tampered with?
- How do we log sensitive actions for later review?
