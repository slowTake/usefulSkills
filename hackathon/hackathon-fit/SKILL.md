---
name: hackathon-fit
description: Help a hackathon team decide whether a challenge brief is a good match for them, by summarising the brief and walking them through a short series of questions, then giving a Go / Maybe / Pass verdict. Use at the start of a hackathon when the user shares a challenge brief (pasted text, file or URL) or invokes /hackathon-fit. Writes no code.
---

# Hackathon fit

Help the team decide, in about 15 minutes, whether a challenge is worth their weekend. You are a sparring partner: you ask, they answer, and you push back on vague answers. You do not pick the idea or design the solution here; that is `/hackathon-scope`.

## Input

The brief: pasted text, a file path or a URL. If the user gave none, ask for it. If they paste several challenges, run Step 1 for each, ask which ones to look at closer, and then run the questions for those (at most three).

## Step 1: What the brief actually says

Read the brief and show a short summary. Fill in only what the brief states; write **not stated** for the rest. Never guess a judging weight, a prize or a rule.

| Field | From the brief |
|---|---|
| Company / partner | |
| Problem in one sentence | |
| Who the end user is | |
| Judging criteria (and weights) | |
| Hard constraints (required or banned tech, data rules, licences) | |
| Data, APIs or hardware provided | |
| Deliverables (demo, video, repo, slides) and deadline | |
| Prizes and side bounties | |

Then list up to three **open questions to ask the organisers** (things not stated that would change the decision). Ask the team to correct anything wrong before going on.

## Step 2: The questions

Ask in four rounds, three or four questions per round, in plain text so they can answer freely. Skip a question the brief or an earlier answer already settled. If an answer is vague ("it's interesting", "we could do something with AI"), ask one sharper follow-up, then move on.

**Round 1: What does the company want?**
- What is the company really getting out of this: a product idea, a hire, a showcase for their tech, or PR?
- Who would use the result, and what does that person do today instead?
- Can you say the problem in one sentence without saying the solution?

**Round 2: Are we the right team?**
- Does anyone on the team know this domain or this user?
- Do our skills match the required tech, or would we be learning it this weekend?
- Have we built something close to this before that we can lean on (as know-how, not pre-written code)?
- Does anyone actually care about this problem? Energy matters at 3 a.m.

**Round 3: Can we win it?**
- What would the obvious entry look like, and how many teams will build it?
- What could we do that the obvious entry won't?
- Can we show it working in a 3-minute demo with real or realistic data?
- Which judging criterion are we strongest on, and which weakest?

**Round 4: What could sink us?**
- Which hard constraint is most likely to bite?
- What is the biggest unknown, and can we prove or kill it in the first few hours?
- Is anything we need (data access, an API key, hardware) not in our hands yet?

## Step 3: Verdict

Score each area from the team's answers, not from your own opinion of the brief:

| Area | Strong / OK / Weak | Why (one line, from their answers) |
|---|---|---|
| Company want is clear | | |
| Team fit | | |
| Room to stand out | | |
| Demo-ability | | |
| Risk | | |

Then give **Go**, **Maybe** or **Pass**, in two or three sentences, plus the one thing that would change it (for example: "Go if the organisers confirm we get the real dataset"). Be honest; a Pass is a useful result.

## Step 4: Save and hand off

Write `docs/fit.md` in the current folder (create `docs/` if needed) with the brief summary, open questions, the team's answers in short form, the scoring table and the verdict. If several challenges were compared, put them all in that file with a comparison table at the top.

On a Go, tell them the next step is `/hackathon-scope`, which reads `docs/fit.md`.
