# Decision rules and trap patterns (CCAR-P)

Teaching heuristics for writing and explaining practice items. Not claims about the real exam.

## Six rules

1. **Remove, don't monitor.** Least privilege means deleting capabilities a role never
   needs. Logging and confirmations are weaker, compensating controls.
2. **Diagnose the layer first.** Wrong answers after a data refresh point to retrieval and
   indexing before models, temperature or context size.
3. **Stable first, dynamic last.** Static prefix, then variable content, then cache it.
4. **Measure before optimizing.** Define the metric and a dataset, then change one thing.
5. **Match the pattern to the problem.** Fixed steps get a workflow; open-ended exploration
   earns an agent; neither needs a multi-agent system by default.
6. **Architects answer for people too.** Compliance, human review and clear communication of
   trade-offs are design inputs, not afterthoughts.

## Trap patterns

| Trap | What it looks like | Better move |
|---|---|---|
| Detective instead of preventive | Add audit logs to a dangerous tool | Remove or restrict the tool |
| Bigger model fixes it | Upgrade the model for a retrieval or design problem | Find the failing layer |
| Truncate to save cost | Cut required policy text | Cache the stable prefix |
| Premature multi-agent | Many agents for a linear task | Simple workflow, add agents when needed |
| Vibes evaluation | "It looks better" | Metric, dataset, A/B comparison |
| Chunking by default | One chunk size for every document type | Chunk by structure and query pattern |
| Tool sprawl | Every tool loaded into every context | Progressive discovery, scoped tools |
| Compliance by promise | "Tell the model not to store PII" | Data controls, residency and access design |
| Jargon to executives | Explain with internals | Tie the decision to cost, risk, SLA and value |

## Quick cues

| If the stem says... | Think... |
|---|---|
| "same large prefix every request" | Prompt caching, static content first |
| "confident but wrong after refresh" | Retrieval or indexing |
| "role only needs read access" | Remove write and delete tools |
| "regulated data (PHI, EU residents)" | HIPAA / GDPR controls in the design |
| "many tools, slow and error-prone" | Reduce, scope, discover on demand |
| "need to prove the change helped" | A/B test with defined metrics |
| "executive asks why" | Business value, risk and cost framing |
| "uncertain high-stakes output" | Human-in-the-loop review |

## Checking an answer

Does the correct option solve the requirement with the least change and the least privilege?
Does every distractor fail for a nameable reason? Rewrite the item if one also works.
