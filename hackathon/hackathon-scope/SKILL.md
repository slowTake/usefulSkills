---
name: hackathon-scope
description: "Interview a hackathon team to turn a chosen challenge into a scoped solution: the pitch, the core feature, what to build, fake or cut, the stack, who does what, and how each judging criterion is covered. Use after /hackathon-fit gives a Go, or when the user invokes /hackathon-scope. Produces docs/plan.md and docs/decisions.md; writes no code."
---

# Hackathon scope

Help the team shape a challenge they have chosen into a plan they can build in the time they have. You ask, they decide. Offer an idea when they are stuck, but label it as a suggestion and let them choose.

## Input

Read `docs/fit.md` if it exists (from `/hackathon-fit`) and use its brief summary and answers; don't re-ask what it settles. If it doesn't exist, ask for the brief and do a short version of the fit summary first (company, problem, judging criteria, hard constraints, deliverables, deadline).

Also ask, once: how many people, how many hours until submission, and how many of those they expect to actually build.

## The questions

Ask in five rounds, three or four questions per round, in plain text. Skip what is already answered. After each round, play back a one-line summary of what they decided before moving on.

**Round 1: Problem and pitch**
- Who exactly is the user, and what moment in their day does this change?
- Finish the sentence: "Today they ___; with our thing they ___."
- What should a judge understand in the first 30 seconds of the demo?

**Round 2: The solution**
- What is the one thing it must do for the demo to work? (The core loop.)
- What is the moment that makes the judges sit up?
- What can be faked for the demo (mock data, hard-coded steps, a scripted path) and what must be real to be believable?

**Round 3: Scope**
- List everything you'd like it to do. Then sort it: **MVP** (the demo fails without it), **nice to have**, **cut**.
- Push back if the MVP needs more than about half of the build hours: the rest goes to integration, bugs, the demo and the pitch.
- What gets cut first if you're behind at the halfway point?

**Round 4: Build**
- Which stack does the team already know best, and is anything in the brief forcing a different one?
- Where does the data come from, and when will you have it?
- Who owns which part? What is the first thing that must work end to end, and by which hour?

**Round 5: Judging and demo**
- For each judging criterion, which feature or deliverable earns its points? Flag any criterion with nothing behind it.
- What are the four or five beats of the demo, in order?
- Which deliverables are due (video, repo, slides, README) and who makes each?

## Output

Write two files in the current folder (create `docs/` if needed):

**`docs/plan.md`**
- Pitch: one sentence, and the "today / with us" line
- User and problem
- Core loop and the wow moment
- Scope table: MVP / nice to have / cut, with an owner for each MVP item
- Real vs faked for the demo
- Stack and data sources
- Timeline: milestones by hour, including a feature freeze and time for the demo and pitch
- Judging criteria → what covers each one
- Demo beats
- Deliverables checklist with owners
- Open risks and the first thing to prove

**`docs/decisions.md`**, a decision log in this format, with one entry per real decision made in the interview (stack, scope cuts, what is faked, data source):

```markdown
# Decision log

Decisions numbered `D-NNN`. Add the next number, an index row and an entry. Never rewrite an entry; supersede it with a new one.

| ID    | Date       | Decision | Status   |
| ----- | ---------- | -------- | -------- |
| D-001 | YYYY-MM-DD | ...      | Accepted |

## D-001: <decision>
<Why, and what was considered instead, in two or three sentences.>
```

If `docs/decisions.md` already exists, append with the next numbers instead of overwriting.

Finish by showing the scope table and the timeline in chat, and ask whether anything should change before they start building.
