# Vrix Concierge — Build Story

**How a production product was shipped by directing coding agents**

> Vrix Concierge is an embeddable website concierge: AI chat that answers from the site's own content, seamless handoff to a human, and audio/video calls — added to any website with one script tag. It was built by one person, in a few weeks, by directing AI coding agents. This document describes the method, because the method is the interesting part.

---

## The operating model

### 1. Specs, not code

Every feature started as a written specification: what it does, what it must never do, and how it would be verified. The agent (Claude Code) implemented against the spec.

The quality of the output tracked the quality of the spec almost one-to-one. Vague spec → vague code. The discipline of writing precise intent did more for quality than any review that came after.

### 2. The agent built; a human gated

Nothing reached the main branch without human review — the same standard applied to a 30-engineer team, not a skim. Coding agents are fast and tireless; they are also confidently wrong at times. The gate is not optional.

### 3. Architecture stayed human

Structural decisions — how the widget isolates from the host page, how calls are routed, when the AI hands off to a human — were made by a human and written down. The agent executed within those boundaries.

### 4. Verification was engineered, not hoped for

Every feature carried tests and manual verification before merge, under the same auditable-governance rules used across the company's engineering teams: approved tooling, logged usage, mandatory human verification of agent output.

Agent output that isn't verified isn't an asset — it's risk with good grammar.

---

## What shipped

- Embeddable widget, single `<script>` tag integration
- AI chat grounded in the host site's own content
- Seamless escalation from AI to a human operator
- In-widget audio and video calls
- Production deployment across real client sites

## Why this is published

This build is a working demonstration of the governance-driven adoption framework described in:

- **"A Governance-Driven Framework for Adopting Agentic AI in Software Engineering Organisations"** — submitted to IEEE AIEI 2027
- **[Agentic AI Benchmark](https://github.com/ksanusha84/agentic-ai-benchmark)** — an MIT-licensed, open-source benchmark for evaluating AI coding assistants (10 production-context task specifications, 5-dimension rubric)

The claim both make: agents can build real products **if** the governance around them is engineered as carefully as the code. This product is the existence proof.

## The shift for engineering teams

The leverage is real, but it is not free. It moves the work:

| From | To |
|---|---|
| Writing code | Writing intent (specs) |
| Reviewing diffs | Engineering verification |
| Managing people only | Managing people **and** agent workflows |

Teams whose leaders understand that shift will ship multiples of what they ship today. Teams that just "add an assistant" won't.

---

*Anusha K S — CTO, Vriksha Techno Solutions · [LinkedIn](https://www.linkedin.com/in/ksanusha/) · [Google Scholar](https://scholar.google.com/citations?user=NAkCyPQAAAAJ)*

*The production Vrix Concierge codebase is proprietary; this repository documents the build method.*
