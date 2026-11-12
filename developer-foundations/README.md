# Claude Certified Developer – Foundations (CCDV-F) prep

A practice coach for the CCDV-F exam, packaged as a Claude skill.

## What you get

`ccdv-f-coach/` is a skill that, from **your own copy of the official exam guide**, can:

- run a 30-question baseline weighted by the real domain weights
- build a study plan around your exam date and daily hours
- drill a single domain or skill, with the reasoning behind every answer
- run timed mocks (15, 30 or full length) with no feedback until you submit
- turn your misses into a ranked weak-spot list

It does not contain exam questions. The real exam is confidential and this repo does not try
to reproduce it.

## Get the exam guide

Download the CCDV-F Exam Guide from the Claude Certified Developer – Foundations page on
the Anthropic Partner Academy. The guide is Anthropic's document and is not included here.

## Install

**Claude (web or desktop):** add the `ccdv-f-coach` folder as a skill in your skills settings.

**Claude Code:** copy the folder to `~/.claude/skills/ccdv-f-coach/` (personal) or
`<your-project>/.claude/skills/ccdv-f-coach/` (one project), then start a new session.

## Use it

1. Attach the exam guide PDF to the conversation.
2. Say: *"Start CCDV-F prep"* and answer the intake questions.
3. Then ask for `baseline`, `plan`, `drill <domain>`, `mock short`, or `review`.

Progress lives in the conversation. For longer prep, use it inside a Claude Project with the
guide attached, or ask the coach for a summary block to paste into your notes.

## Layout

```
ccdv-f-coach/
  SKILL.md                    how the coach behaves
  references/
    blueprint.md              domain/skill map and study notes (verify against the guide)
    decision-rules.md         the reasoning rules and trap patterns behind the practice items
```

## Disclaimer

Unofficial community material. Not affiliated with or endorsed by Anthropic. Exam facts can
change; the official guide is the authority.
