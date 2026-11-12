# CCDV-F blueprint (study aid)

> This file summarizes the structure of the official Claude Certified Developer – Foundations
> exam guide (v1.0, effective July 2026) so a learner can orient quickly. It is **not** a
> substitute for the guide. Weights and skills can change; always check the current guide on
> the Anthropic Partner Academy certification page.

## Exam facts (guide v1.0)

| Item | Value |
|---|---|
| Items | 53, multiple-choice and multiple-response (each states how many to select) |
| Time | 120 minutes |
| Pass mark | 720 on a 100-1,000 scale |
| Fee / validity | $125 USD / 12 months |
| Delivery | Proctored, online or test center |
| Prerequisites | None; 1-5 years of software engineering and 6+ months with Claude recommended |

## Domains and skills

| # | Domain | Weight | Skills (weight) |
|---|---|---|---|
| 1 | Agents and Workflows | 14.7% | Agent Architecture 4.5 - Agent Construction with Claude 5.3 - Agent Patterns and Frameworks 4.9 |
| 2 | Applications and Integration | 33.1% | Understanding Requirements 3.4 - Systems Life Cycle 2.8 - Claude API Mechanics 6.8 - Software Engineering Foundations 7.4 - Claude Application Design 8.6 - Configuration Management 4.1 |
| 3 | Claude Code | 3.1% | Claude Code Operation 3.1 |
| 4 | Eval, Testing, and Debugging | 2.6% | Debugging and Error Handling 2.6 |
| 5 | Model Selection and Optimization | 16.8% | LLM Fundamentals 5.2 - Technical Fundamentals 6.1 - Model Selection and Tradeoffs 2.7 - Cost and Token Management 2.8 |
| 6 | Prompt and Context Engineering | 11.0% | Context Engineering 3.8 - Prompt Engineering 4.6 - Output Handling 2.6 |
| 7 | Security and Safety | 8.1% | AI Application Security 3.2 - Guardrails and Safe Deployment 2.3 - Claude Hooks 1.0 - Identity, Secrets, and Key Management 1.6 |
| 8 | Tools and MCPs | 10.6% | Tool Implementation 4.4 - MCP Server Development 2.1 - Agentic Customization 4.1 |

Domains 2 and 5 together are about half the exam.

## Study notes by domain (verify details against current documentation)

**1. Agents and Workflows.** When a fixed workflow beats an autonomous agent. Supervisor and
subagent structures and what subagents add. Building agents with the Agent SDK or a custom
loop; hooks for deterministic actions; self-hosted versus Anthropic-hosted agents. Common
patterns: tool-use loops, memory, context management, and third-party agent frameworks.

**2. Applications and Integration.** Turning business requirements into functional and
infrastructure requirements. The Messages API: messages, tools, streaming, vision, thinking,
caching, third-party hosting, and real-time versus batch trade-offs. Engineering basics:
REST, JSON, async code, version control, code review, refactoring. Application design:
how instructions behave across Claude Code, desktop, web and API; content boundaries,
schema design, session hygiene, plugins. Configuration: CLAUDE.md, settings.json, model
version pinning, prompt versioning, plugin dependencies.

**3. Claude Code.** Rules, skills, commands, agents and memory; session management;
headless and streaming modes; the CLAUDE.md hierarchy; initialization; settings.json.

**4. Eval, Testing, and Debugging.** Telling error types apart, choosing a recovery
strategy, reading traces, and deciding whether a failure originates in the integration layer
or in the model's output.

**5. Model Selection and Optimization.** Tokens, context windows, sampling and
non-determinism; fast mode, extended and adaptive thinking, effort levels; zero-, one- and
few-shot prompting; SDKs over REST and websockets. Choosing between model tiers by quality,
latency and cost, and noting behavior changes across releases. Token budgeting, cost
modelling, prompt caching and checkpointing.

**6. Prompt and Context Engineering.** Preventing context drift and bloat (prune tool
output, compact, isolate with subagents). Clear instructions, examples, system versus user
placement, output constraints, iteration and input sanitization. Producing, validating and
parsing output defensively, with skepticism toward confident answers.

**7. Security and Safety.** Prompt injection and jailbreak defence, untrusted input, data
leakage, PII, auth and confidentiality. Content policy, guardrail layering, least privilege.
Hooks that stop destructive actions. Handling secrets, keys, identity and access approval.

**8. Tools and MCPs.** Tool definitions and descriptions, error handling, client-side versus
server-side tools, approval patterns, and building tool sets. Authoring and deploying MCP
servers: resources, tools and prompts, and transport choices. Picking among built-in tools,
custom tools, skills and MCP for a use case.

## Hands-on checklist (from the guide's preparation advice)

Build and run one small Claude application that:
- [ ] calls the API (with streaming or batch where appropriate)
- [ ] integrates at least one tool
- [ ] applies basic prompt and context engineering
- [ ] has simple security controls (untrusted input handling, least privilege)
- [ ] has a simple evaluation or test harness
