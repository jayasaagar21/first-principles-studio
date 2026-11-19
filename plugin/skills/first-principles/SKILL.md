---
name: first-principles
description: Break a product idea, plan or topic down to first principles. Sorts statements into facts, assumptions and open questions, draws a block diagram, runs market, product and customer checks marked for verification, scores ideas with RICE, gives a pursue, park or drop verdict, and writes a Markdown report. Use when the user wants to test, research or learn something from the ground up.
---

# First principles

Work through the idea in this order. Keep each step short. Ask one sharp question at a time, and wait for the answer before moving on.

## 1. Sort the statements

Keep three lists and update them as the user talks:

- **Facts**: things that can be checked today (physics, arithmetic, a stated price, a known law).
- **Assumptions**: things believed but not proven (demand, willingness to pay, a supplier existing). Mark each one to test.
- **Open questions**: things nobody knows yet. Name who could answer each one.

Never move an assumption into facts without evidence the user has given.

## 2. Draw the block diagram

Show the idea as blocks and arrows (for example: solar panel → refrigeration unit → ice storage). Put a dashed outline on any block or link that rests on an assumption. Use Mermaid so it renders:

```mermaid
flowchart LR
  a[solar panel] --> b[refrigeration unit]
  b --> c[ice storage]
```

## 3. Run the three fits

For market, product and customer fit, give a short answer and a "To verify" list:

- **Market fit** — is there room? Direct and indirect competitors, the market today, cost to enter.
- **Product fit** — can it be built sensibly? Problem it solves, resources, complexity, steps to start.
- **Customer fit** — are these the right people? Personas, segments, market size (TAM / SAM / SOM), channels.

Name competitors only if the user knows them or they are well known. Otherwise write "unknown" and add it to "To verify". Do not invent numbers. Give market size as a range only when the user supplies the inputs.

## 4. Score with RICE

For each idea: Reach (people per quarter), Impact (0.25 to 3), Confidence (percent), Effort (person-months). Score = Reach × Impact × Confidence ÷ Effort. Show the inputs with the score so the user can change them.

## 5. Verdict

Give one of three: **pursue**, **park** or **drop**. State the evidence for it, and which assumption would change it. The user makes the final call.

## 6. Links

Link to sources only from a real search, never from memory. For Wikipedia use `https://en.wikipedia.org/w/index.php?search=<topic>`. For YouTube use `https://www.youtube.com/results?search_query=<topic>`. Say so when a link is a search link.

## 7. Report

Save one file, `first-principles/<YYYY-MM-DD>-<short-slug>/report.md`, with sections in this order: Facts, Assumptions to test, Open questions, Diagram, Market fit, Product fit, Customer fit, Score, Verdict, To verify. Also keep `transcript.md` with the conversation so the session can be resumed later.

If a `first-principles/` folder already holds this idea, read its `report.md` and `transcript.md` and carry on from there.
