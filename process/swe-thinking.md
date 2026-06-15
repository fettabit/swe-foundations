---
type: resource
topic:
  - swe
  - process
  - lifecycle
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[dev workflow]]"
  - "[[project initiation process]]"
---

# SWE Thinking

1. Requirements Gathering
Before a single line of code is written, engineers define what the software needs to do. This comes from a client, a product manager, or your own vision if you’re building solo.
Output: a list of functional requirements (what it does) and non-functional requirements (how fast, how secure, how many users).
2. System Design
Now you answer: how will you build it? This breaks into two levels:
	•	High-level design — what components exist, how they communicate (databases, APIs, frontend, backend)
	•	Low-level design — how individual components work internally (data models, class structures, algorithms)
This is where you make technology choices: language, framework, database type.
3. Breaking Work Into Tasks
Engineers convert design into discrete, executable units of work — tickets, issues, stories. Each one should be small enough to complete in hours or a few days, with a clear definition of done.
This is what tools like Linear, Jira, or GitHub Issues are for.
4. Implementation
Writing code against those defined tasks. Engineers work feature by feature, not by writing everything at once.
5. Testing
Unit tests, integration tests, manual QA. Does it do what the requirements said?
6. Deployment
Shipping to production. CI/CD pipelines automate this.
7. Maintenance
Bug fixes, performance improvements, new feature iterations. Most of a working engineer’s time is here, not greenfield development.