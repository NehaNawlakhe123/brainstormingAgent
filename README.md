# Jira Epic Brainstorming Agent

This example demonstrates a sequential multi-agent workflow with Pydantic AI:

1. The story analyzer evaluates each story's narrative and completeness.
2. The gap analyzer checks requirements and cross-story context.
3. The impact analyzer assesses dependencies, risks, resources, and timelines.
4. The parent orchestrator synthesizes the analyses into a validated
   `OrchestratedOutput`.

Agent boundaries and quality rules live in the versioned files under
[`skills/`](skills/):

- [`story_analyzer.md`](skills/story_analyzer.md)
- [`gap_analyzer.md`](skills/gap_analyzer.md)
- [`impact_analyzer.md`](skills/impact_analyzer.md)
- [`orchestrator.md`](skills/orchestrator.md)

The Python wrappers validate required story fields before model calls, preserve
the sequential workflow, validate structured outputs through Pydantic AI, and
retry bounded transient failures up to three times. The workflow does not modify
the source Jira models.

## Run it

From this directory, install the example's dependency and set an OpenAI key:

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=your-key
python brainstorming_agent.py
```

On Windows PowerShell:

```powershell
pip install -r requirements.txt
$env:OPENAI_API_KEY = "your-key"
python brainstorming_agent.py
```

Set `BRAINSTORMING_MODEL` to use a different Pydantic AI model, for example
`openai:gpt-4.1-mini`.
