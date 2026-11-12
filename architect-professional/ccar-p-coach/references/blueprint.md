# CCAR-P blueprint (study aid)

> A learner's summary of the Claude Certified Architect – Professional exam guide (v1.0,
> effective July 2026). It is **not** a substitute for the guide. Check the current guide on
> the Anthropic Partner Academy.

## Exam facts (guide v1.0)

| Item | Value |
|---|---|
| Items | 63, multiple-choice and multiple-response (each states how many to select) |
| Time | 120 minutes |
| Pass mark | 720 on a 100-1,000 scale |
| Fee / validity | $175 USD / 12 months |
| Delivery | Proctored via Pearson VUE, online or test center |
| Recommended | 3+ years architecture or platform engineering; 6+ months with Claude or similar in production (not required) |
| Retakes | 14 days after the first fail, 30 after the second, 90 after the third; up to four attempts in 12 months |

## Domains

| # | Domain | Weight |
|---|---|---|
| 1 | Solution Design and Architecture | 17% |
| 2 | Claude Models, Prompting and Context Engineering | 13% |
| 3 | Integration | 19% |
| 4 | Evaluation, Testing and Optimization | 16% |
| 5 | Governance, Safety and Risk Management | 14% |
| 6 | Stakeholder Communication and Lifecycle Management | 14% |
| 7 | Developer Productivity and Operational Enablement | 7% |

## Objectives in brief

1. **Design.** Business problem to solution; input-to-feedback architecture; workflow versus
   agentic versus augmented LLM; multi-agent orchestration; decomposition; business value
   (efficiency, cost, SLAs).
2. **Models and context.** Model trade-offs; system prompts and guardrails; zero-shot,
   few-shot, chain-of-thought; token budgeting; caching, modular prompts, Skills.
3. **Integration.** Capability bloat in tool sets; authentication and authorization gaps;
   accuracy versus latency; observability at scale; RAG chunking and indexing; retrieval matched
   to data shape; MCP versus API/CLI versus agent-to-agent; progressive discovery versus
   monolithic context.
4. **Evaluation.** Metrics (accuracy, latency, cost, safety, security); datasets and mixed
   methods; A/B tests; diagnosing prompt, hallucination and model-fit failures; cost tuning;
   logging and monitoring.
5. **Governance.** Guardrails; failure modes; human-in-the-loop; GDPR, HIPAA, FedRAMP;
   bias, fairness, transparency.
6. **Stakeholders.** Discovery; explaining trade-offs; managing expectations and SLAs;
   documentation and handoff; lifecycle phases.
7. **Productivity.** Team configuration of Claude Code; AI-assisted workflows; debugging and
   operational support.

## Hands-on checklist

- [ ] An end-to-end build with retrieval, an eval set and basic observability
- [ ] A prompt-caching change with before and after cost and latency numbers
- [ ] A least-privilege review of one agent's tools and credentials
- [ ] A one-page architecture decision record with trade-offs and a rollback plan
