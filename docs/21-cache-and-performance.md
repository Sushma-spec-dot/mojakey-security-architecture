## Why Cache and Performance Matter

Mojakey includes parent-facing and institution-facing workflows that must feel responsive during normal daily use. Performance becomes especially important during peak periods such as student drop-off, check-in, check-out, enrollment windows, and other time-sensitive operational workflows.

The design should improve responsiveness without weakening security, tenant isolation, or event integrity.

## Where Caching Can Help

Caching can help reduce repeated reads for data that is accessed often but does not change constantly. Examples include institution settings, program metadata, schedules, class rosters, and other non-sensitive reference data used during operational workflows.

Caching may also help reduce repeated lookups for parent-facing and institution-facing views when the same data is read frequently.

## Where Caching Should Be Used Carefully

Caching should be used carefully for highly sensitive or rapidly changing data. Access-control decisions, attendance state, billing-impacting records, and security-sensitive workflows should not rely on stale cached data in a way that creates incorrect or unsafe behavior.

The platform should avoid designs where caching weakens authorization checks, tenant isolation, or trust in check-in and check-out events.

## Performance Considerations

The platform should keep parent and institution workflows responsive enough for practical daily use. Check-in and check-out flows should remain efficient during peak hours, and backend services should avoid unnecessary repeated database access where safe optimization is possible.

Security checks should be built efficiently so they protect the system without introducing avoidable delays in common workflows.

## Growth and Scale Considerations

As Mojakey grows across more institutions, families, students, programs, and operational events, performance design should continue to support reliable user experience.

Stateless application components can scale horizontally, caching can reduce repeated reads for suitable data, and service boundaries can help isolate high-volume workflows such as attendance events, reporting, and audit-related processing.
