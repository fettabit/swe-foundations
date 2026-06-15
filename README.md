# swe-foundations

Personal SWE reference notes, organized by topic. Curated by Jafet (`fettabit`).

These originated as Obsidian notes (2026-04-12 batch). The frontmatter `related:` fields still use Obsidian wikilinks (`[[note]]`) that will not resolve on GitHub — they are preserved for round-tripping back into the vault. If cross-linking on GitHub matters, convert them to relative paths.

## Contents

```
swe-foundations/
├── README.md
├── principles/
│   ├── foundational-swe-principles.md        separation of concerns, DRY, YAGNI, KISS, fail fast, etc.
│   └── building-large-software-projects.md   dependability, modularization, risk profiling
├── process/
│   ├── swe-thinking.md                        the engineering lifecycle, requirements to maintenance
│   ├── project-initiation-process.md         problem statement, design, env, structure, build loop, test, deploy
│   ├── dev-workflow.md                        MVP-first, ticket-driven, ship-early-iterate
│   └── build-loop.md                          vertical-slice execution order, per-feature breakdown
├── prd/
│   ├── before-writing-prd.md                  formalizing the brief, ADRs, architecture diagram, milestones
│   └── project-docs-structure.md             /docs layout: PRD, ADR, ARCHITECTURE, MILESTONES, STACK, DESIGN
└── tips/
    └── tips-n-tricks.md                       git discipline, debugging protocol, environment hygiene, API gotchas
```

## How to use

- Treat these as **fet's own reference**, not external authority. They are notes to himself, formatted for quick recall.
- For a new project, the natural reading order is: `principles/` → `process/project-initiation-process.md` → `process/dev-workflow.md` → `prd/before-writing-prd.md`.
- For ongoing work on an existing project, the working layer is `process/build-loop.md` and `tips/tips-n-tricks.md`.
