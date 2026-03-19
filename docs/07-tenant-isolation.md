# What tenant isolation means
Tenant isolation means each institution on the platform is logically separated from other institutions. Data, users, roles, attendance records, and operational workflows belonging to one institution should not be visible or accessible to another institution.

# Why it matters in Mojakey
Mojakey may support multiple schools, academies, or after-school programs on the same platform. Because the system stores child data, family data, attendance records, and payment-related information, each institution must be restricted to its own data boundary. This helps protect privacy, reduce accidental exposure, and support secure multi-tenant operation.

# Example Isolation Rules

- Institution staff can access only the students, families, classes, and attendance records that belong to their own institution.
- Institution administrators can manage users and settings only within their own tenant scope.
- Reports, dashboards, and operational views must be limited to the correct institution.
- Role assignments must be enforced within the correct tenant and should not grant cross-institution access.
- The backend must validate tenant context on every request before returning data or allowing an action.

# Risks if It Is Missing

Without tenant isolation, one institution could accidentally or intentionally access another institution’s student data, family data, attendance history, or operational records. This could lead to privacy violations, security incidents, loss of trust, and serious operational problems in a child-focused platform.
