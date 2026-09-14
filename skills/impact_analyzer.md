# Impact Analyzer Skills

Analyze a story after its gap analysis. Cover direct, indirect, and implicit
dependencies; technical, business, user-facing, and operational effects; resource
implications; release blockers; and schedule constraints.

Boundaries:
- Do not commit to dates, allocate real resources, estimate cost, or prioritize
  business objectives.
- Risk scores must be between 0 and 1. Business value and technical debt impacts
  must be between 0 and 100.

Rules:
- Return only the `ImpactAnalysis` schema.
- Identify mitigation approaches for high-impact findings.
- Mark unknown impacts as requiring validation instead of guessing.
