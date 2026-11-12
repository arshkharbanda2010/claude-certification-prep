# Decision rules and trap patterns

Used by the coach to write practice items and to explain answers. These are teaching
heuristics distilled from the CCDV-F skill areas and the guide's sample-question reasoning.
They are not claims about the real exam's content.

## Four rules

1. **Find the layer that is failing.** Is the problem in the integration (request, parsing,
   config, session, secrets) or in the model's output? Fix that layer first.
2. **Enforce, don't ask.** For security and safety, use isolation of untrusted input, least
   privilege, hooks and guardrails. A sentence in a prompt is a request, not a control.
3. **Smallest sufficient change.** Prefer the cheapest fix that satisfies the stated
   requirement. New infrastructure, classifiers and routers are rarely the first step.
4. **Match the lever to the requirement.** Pick the API mode, model tier, tool type and
   deployment shape that the requirement names: cost, latency, reuse, safety, scale.

## Trap patterns

| Trap | What it looks like | Better move |
|---|---|---|
| Prose as a control | "Add a line telling the model not to..." or "tell users not to..." | Isolate untrusted content, limit tools, gate sensitive actions with hooks or approval |
| Wrong lever | Lower temperature, change `max_tokens`, or use a bigger model to fix a non-model problem | Diagnose first; fix config, design or data flow |
| Over-engineering | Add a router, classifier, vector store or extra service as the first step | Try the simple change that addresses the root cause |
| Wrong API mode | Parallel real-time calls for a non-urgent bulk job; or batch for a blocking, interactive path | Batch for latency-tolerant bulk work; synchronous for interactive or blocking work |
| Context stuffing | Paste live or large data into every request | Provide access through a tool or resource; cache stable prefixes |
| Hard-coded integration | Duplicate the same integration logic in each app's prompt | Build a reusable component (for example an MCP server) |
| Wrong tool type | Assume a built-in tool reaches any internal system; or build a custom tool where a built-in one fits | Choose among built-in, custom, skill and MCP by reuse and reach |
| Secrets in the wrong place | Keys in code, prompts or shared config | Use managed secrets and least-privilege access |

## Quick cues

| If the stem says... | Think... |
|---|---|
| "overnight", "not urgent", "cost is the priority" | Batch processing |
| "users see nothing until it finishes" | Streaming |
| "same large prefix on every request" | Prompt caching |
| "output format changed after an upgrade" | Pin the model version, test before upgrading |
| "reuse across several applications" | MCP server |
| "page, email or document contains hidden instructions" | Untrusted input, least privilege, hooks |
| "can't tell whether the bug is in our code or the model" | Trace both layers; isolate the origin |
| "agent steps are fixed and known in advance" | A workflow, not an autonomous agent |
| "context keeps growing and quality drops" | Prune tool output, compact, isolate with subagents |
| "need guaranteed structure from the model" | Structured output via a schema, plus validation |

## Checking an answer

Before finalizing any item, ask: does the correct option solve the stated requirement with
the least change? Does each distractor fail for a specific, nameable reason? If a distractor
would also be acceptable, rewrite the item.
