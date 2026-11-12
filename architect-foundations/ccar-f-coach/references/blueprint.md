# CCAR-F blueprint (study aid)

> A learner's summary of the structure of the official Claude Certified Architect –
> Foundations exam guide. It is **not** a substitute for the guide. Weights and scenarios can
> change; always check the current guide on the Anthropic Partner Academy.

## Exam facts

| Item | Value |
|---|---|
| Items | 60, multiple-choice and multiple-response |
| Format | Scenario-based: 4 of 6 scenarios are presented |
| Time | 120 minutes |
| Pass mark | 720 on a 100-1,000 scale |
| Fee / validity | $125 USD / 12 months |

## Domains

| # | Domain | Weight |
|---|---|---|
| 1 | Agentic Architecture and Orchestration | 27% |
| 2 | Tool Design and MCP Integration | 18% |
| 3 | Claude Code Configuration and Workflows | 20% |
| 4 | Prompt Engineering and Structured Output | 20% |
| 5 | Context Management and Reliability | 15% |

Scenarios (verify against the guide): customer support resolution agent, code generation with
Claude Code, multi-agent research system, developer productivity, Claude Code in CI,
structured data extraction.

## Study notes by domain

**1. Agentic architecture.** Loops driven by `stop_reason`; coordinator with subagents;
subagents get context passed explicitly, not inherited; restricting subagent tools;
hooks and prerequisite gates for rules that must always hold; decomposition, session resume
and fork.

**2. Tools and MCP.** Tool descriptions that disambiguate similar tools; structured errors
(category, retryable flag); scoping tool sets per agent; `tool_choice` modes; project versus
user MCP configuration and secret expansion; resources versus tools.

**3. Claude Code.** CLAUDE.md hierarchy and imports; path-scoped rules; commands and skills
(including forked context); plan mode versus direct execution; headless runs with structured
JSON output in CI; independent review passes.

**4. Prompts and structured output.** Explicit criteria over vague instructions; few-shot
examples; schema design (nullable fields, enums with an "other"); validate, then retry with
the error; Batch API trade-offs (cheaper, up to 24 h, no multi-turn tools).

**5. Context and reliability.** Keep key facts outside the summarized history; trim tool
output; escalation rules; error propagation with partial results; scratchpad and manifests for
long tasks; provenance for claims; calibration and sampling to measure quality.

## Hands-on checklist

- [ ] An agent loop that ends on `stop_reason`, with one tool that can return a structured error
- [ ] A coordinator that delegates to a subagent with explicit context
- [ ] A hook or gate that enforces one business rule in code
- [ ] A project CLAUDE.md, one scoped rule file and one MCP server entry
- [ ] An extraction schema with a validation-and-retry loop
