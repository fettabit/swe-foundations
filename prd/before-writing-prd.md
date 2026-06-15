---
type: resource
topic:
  - swe
  - prd
  - project-setup
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[project docs structure]]"
  - "[[notes app idea]]"
---

# Before Writing the PRD

1. Formalize the PRD
The brief becomes a Product Requirements Document. Each feature gets acceptance criteria — not “AI auto-tags notes” but “given a new note saved, the system assigns 1–5 tags within X seconds with no user action required.” Vague features get cut or deferred until they’re specifiable.
2. Architecture Decision Records (ADRs)
The complexity flags in the brief are unresolved tech decisions. Each one needs a decision document before a line of code is written:
	•	CRDT library selection (Automerge vs Yjs vs custom)
	•	Vector DB for AI graph (local on-device via SQLite-vec, or cloud — Pinecone/Supabase pgvector)
	•	AI provider strategy (OpenAI API, Anthropic, on-device via Core ML)
	•	PencilKit integration scope
	•	Sync backend infrastructure (self-hosted vs Supabase vs Cloudflare)
3. System Architecture Diagram
Map the components and their relationships — client, local storage, sync layer, AI pipeline, backend. Surfaces integration points and ownership boundaries early.
4. Milestone + Scope Definition
Cut the full feature set into vertical slices by milestone. M1 is typically the smallest possible thing that demonstrates the core loop. For this app that’s probably: create a note, save it locally, render handwriting on iPadOS. AI features are M2+.
5. Project Setup
	•	Repo structure
	•	Branch strategy (trunk-based vs Gitflow)
	•	Issue tracker seeded with M1 tasks (this is where Linear comes in)
	•	CI skeleton
	•	Environments defined (local, staging, prod)
6. Design Kickoff
Figma wireframes for the primary screens before any UI code. Highest priority: the note editor, since handwriting + AI suggestions + rich text in one surface is the hardest layout problem in the app.