---
type: resource
topic:
  - swe
  - process
  - workflow
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[swe thinking]]"
  - "[[build loop]]"
---

# Dev Workflow

1. Define the problem clearly before touching code
Write one sentence: “This app exists to let [user] do [action] so that [outcome].” If you can’t write that sentence, you don’t know what you’re building yet.
2. List features as user actions
Not “build authentication” — instead: “user can create an account,” “user can log in,” “user can reset password.” These become your tasks. This is called writing user stories.
3. Prioritize ruthlessly
Split your list into two buckets:
	•	MVP (minimum viable product) — the smallest version that actually does the core thing
	•	Later — everything else
Most solo projects die because the developer builds everything except the core thing.
4. Design before coding
Sketch the data model first. What are your entities? What fields do they have? How do they relate? A notes app has: User, Note. A note belongs to a user. That’s your schema. Draw it on paper.
Then sketch the screens/UI flow if it’s a frontend project.
5. Work ticket by ticket
Open your task tracker (you’re already using Linear). One issue = one unit of work. Branch off main, build it, test it, merge it. Don’t work on two things simultaneously.
6. Test as you go
Solo devs skip this. It compounds into bugs that take 10x longer to find later.
7. Ship early, iterate
Deploy a broken MVP before you build feature #4. Real usage reveals what matters.