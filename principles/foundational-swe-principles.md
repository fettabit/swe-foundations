---
type: resource
topic:
  - swe
  - principles
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[tips n' tricks]]"
  - "[[swe thinking]]"
---

# Foundational SWE Principles

**Separation of Concerns** — each module does one thing; mixing responsibilities creates debt that compounds

**Single Responsibility Principle** — a function, class, or module should have one reason to change

**DRY (Don't Repeat Yourself)** — duplication is a maintenance liability; abstract when you see the second instance of a pattern

**YAGNI (You Aren't Gonna Need It)** — don't build for hypothetical future requirements; build for what exists now

**KISS (Keep It Simple, Stupid)** — complexity is a cost; simplicity is a feature

**Fail Fast** — surface errors early and loudly; silent failures are the hardest bugs to find

**Defensive Programming** — validate inputs, assert assumptions, never trust external data

**Version Control Everything** — code, configs, migrations, infrastructure definitions

**Secrets Never in Code** — environment variables, secret managers; this is non-negotiable

**Readable Code Over Clever Code** — you will read code far more than you write it; optimize for comprehension

**Premature Optimization is the Root of All Evil** — make it correct first, then fast if measurement proves it's needed

**Incremental Delivery** — working software in small steps beats a big-bang release every time

**Observability** — logging, metrics, and tracing are not optional in production systems; you cannot debug what you cannot see

**Documentation as Code** — treat docs with the same discipline as code; stale docs are worse than no docs