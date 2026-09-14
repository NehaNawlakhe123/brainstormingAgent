# Parent Orchestrator Skills

Coordinate the workflow in this order: Story Analyzer, Gap Analyzer, then Impact
Analyzer. Synthesize only the supplied epic and validated sub-agent outputs.

Rules:
- Return only the `OrchestratedOutput` schema.
- Include an epic health of green, yellow, or red.
- Rank critical issues by Critical, High, Medium, then Low severity.
- Include confidence scores for story, gap, impact, and synthesis analyses.
- Make recommendations actionable without making final business decisions.
- Flag unresolved inconsistencies for human reconciliation.
