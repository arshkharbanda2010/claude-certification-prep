# Decision rules and trap patterns (CCAR-F)

Teaching heuristics used to write and explain practice items. They are not claims about the
real exam's content.

## Five rules

1. **Code enforces, prompts advise.** When a rule must hold every time (a refund limit, an
   identity check), use a hook, gate or schema, not a stronger sentence.
2. **Isolate and pass context explicitly.** Subagents start clean. If they need it, hand it over;
   if they must not see it, don't.
3. **Fix the cause the stem names.** Vague tool descriptions, missing criteria or an
   over-broad tool set are the usual root cause; model swaps and bigger context rarely are.
4. **Smallest scope that works.** Narrow tool sets, path-scoped rules, one subagent, the
   cheapest API mode that meets the deadline.
5. **Make failure visible.** Structured errors, partial results flagged as partial, escalation
   when the agent cannot proceed. Never silent success.

## Trap patterns

| Trap | What it looks like | Better move |
|---|---|---|
| Prompt as enforcement | "Add instructions to always..." for a compliance rule | Programmatic gate or hook |
| Shared-context assumption | Subagent expected to know the coordinator's findings | Pass findings in its prompt |
| Tool overload | One agent with a dozen tools, wrong picks | Fewer, scoped tools with distinct descriptions |
| Swallowed error | Return empty result or generic failure | Structured error with category and retryable flag |
| Blind retry | Retry with the same input when information is missing | Retry with the validation error, or stop if the data is absent |
| Wrong API mode | Batch for a blocking job, or real-time for overnight bulk | Match mode to the deadline |
| Self-review | Same session checks its own output | Independent review instance |
| Everything in one file | Huge CLAUDE.md for unrelated areas | Hierarchy, imports, path-scoped rules |
| Summary erosion | Key facts live only in compacted history | Persistent facts block, scratchpad file |

## Quick cues

| If the stem says... | Think... |
|---|---|
| "must always", "no exceptions" | Programmatic enforcement |
| "agent picks the wrong tool" | Improve descriptions, reduce the tool set |
| "results differ between teammates" | Project-level config versus personal config |
| "pipeline runs in CI" | Headless mode, structured JSON output |
| "overnight, no one waiting" | Batch processing |
| "long session loses details" | Persistent facts, scratchpad, manifest |
| "model invents a value for a missing field" | Nullable field in the schema |
| "needs a second opinion" | Separate reviewer instance |

## Checking an answer

Does the correct option solve the stated requirement with the least change? Does every
distractor fail for a nameable reason? If a distractor would also be acceptable, rewrite the item.
