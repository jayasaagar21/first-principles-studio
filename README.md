# First Principles Studio

*Working name. This repository holds the product blueprint and the first working version of the app.*

An offline, voice-first assistant for first-principles research. You talk to a specialist expert bot out loud. A second, silent agent (the Scribe) listens to the whole conversation and turns it into a block diagram, research, a score, a verdict and a document. Everything runs on your own PC, with an optional Online switch.

**Open [`index.html`](index.html) in a browser for the interactive blueprint.**

## What is here

| File | What it is |
|---|---|
| [`index.html`](index.html) | The interactive blueprint: five figures that explain the whole product. Opens in any browser. |
| [`app.html`](app.html) | The first working version of the app, in one file. |

### The working app

`app.html` does what the blueprint describes: you talk to an expert by voice or text, it answers aloud, and the Scribe keeps structured notes, draws the block diagram or knowledge graph, runs the three fits, scores ideas with RICE, gives a verdict and writes the report. Sessions are saved and can be reopened.

It runs in two ways:

- **Inside Claude, as a page.** The brain, ears and voice come from Claude. Nothing to set up.
- **On its own.** Download `app.html`, open it in Chrome or Edge, then open Settings and pick a brain: a local model through Ollama (free and offline), or Claude through your own API key (online, paid per use). You can switch at any time. Voice uses the browser's speech features, and sessions are saved in the browser.

Notes for running it on its own:

- Ollama only answers pages it trusts. Set its `OLLAMA_ORIGINS` setting to allow the page, then restart Ollama.
- An API key typed into Settings is stored in that browser only and sent straight to the Claude API. Use a key with a spending limit.
- In Chrome, voice input is an online service even when the brain is local. Typing works fully offline.

Three things in it are deliberately different from the original description:

- Offline needs the Ollama brain. Inside Claude, or with an API key, it is online.
- The three fits come from the model's general knowledge, not a live web search. Each one lists what to verify.
- Wikipedia and YouTube links are search links, so a link can never be invented.

### Next

1. An Android APK.
2. A browser extension.
3. Offline speech recognition and offline Wikipedia, as in the blueprint.

## The loop

```
You ask out loud → speech to text → expert bot → text to speech → you listen
                         │
                         └─ the Scribe hears every word and builds as you talk
```

## Two rooms

**Build room** takes a product idea from a hunch to a clear yes or no.

1. **Talk.** You and an expert sort every statement into facts, assumptions and open questions.
2. **Map.** The Scribe draws a block diagram and flags links that rest on assumptions.
3. **Three fits.**
   - Market fit: direct and indirect competitors, the market today, blue ocean room, cost to enter, viability.
   - Product fit: problem match, resource appetite, complexity, known unknowns, step-by-step path to launch the ideation phase.
   - Customer fit: personas, segments, TAM / SAM / SOM, channels.
4. **Score.** Ideas are ranked with RICE (Reach × Impact × Confidence ÷ Effort). ICE, Kano or MoSCoW can replace it.
5. **Verdict.** Pursue, park or drop. The Scribe lays out the evidence and you make the call.
6. **Document.** One report, saved as Markdown and PDF.

**Learn room** is for understanding any subject from the ground up. Each idea becomes a node on a knowledge graph, linked to the ideas it rests on, with checked sources attached. Graphs from different sessions join where they share a node.

## The experts

Each bot is one narrow specialist with its own starting principles and questioning style: Physicist, Engineer, Economist, Market analyst, Customer researcher, Finance lead, Regulator, Skeptic, Historian, Philosopher, Geographer, Mathematician. You can write your own. An expert is a small text file with a name and domain, starting principles, questioning style, depth, allowed sources and a voice.

## Offline first

| Part | Offline, always | Online, when switched on |
|---|---|---|
| Ears (speech to text) | Whisper or Parakeet, local | No change |
| Brain (the expert) | Open model run by Ollama | Optional stronger cloud model |
| Voice (text to speech) | Kokoro or Piper, local | No change |
| Library | Offline Wikipedia via Kiwix, saved sessions | Live web search, YouTube search |
| Links | Wikipedia articles from the local library | Wikipedia and YouTube links, each from a search result and checked |
| Research | Structure, questions, what to look up | Named competitors, prices, market size, with sources |
| Updates | Fixed at what you installed | Newer models and library on demand |

### Limits to design around

- A local model stops learning on its training date. Anything recent needs Online.
- Models invent links. No link may come from the model's memory, only from the local library or a search result.
- Video does not play offline. Video links are saved and open when you connect.
- Depth depends on hardware. 16 GB of memory is a comfortable floor for a mid-size model.

## Session folder

```
FirstPrinciples/
├─ ideas/
│  └─ 2026-11-15 solar-cold-box/
│     ├─ session.json     resume point
│     ├─ transcript.md    every word, by speaker
│     ├─ principles.md    facts, assumptions, questions
│     ├─ diagram.mmd      block diagram
│     ├─ market-fit.md
│     ├─ product-fit.md
│     ├─ customer-fit.md
│     ├─ score.json       RICE inputs and result
│     └─ report.md        final document, also .pdf
├─ learn/
│  └─ monsoon/
│     ├─ session.json
│     ├─ transcript.md
│     ├─ graph.json       nodes and links
│     └─ sources.md       checked links only
├─ experts/
│  ├─ physicist.yaml
│  └─ skeptic.yaml
└─ library/               offline Wikipedia, model files
```

Every session is a folder of plain files. Reopening one loads its summary and the last few turns, then searches the rest for whatever the next question needs.

## Build order

1. **The voice loop.** Speak to one expert offline and hear the answer. The transcript saves to a folder.
2. **The expert shelf.** Pick, edit and create experts. Saved sessions reopen with their context.
3. **The Scribe.** Live sorting into facts, assumptions and questions. Block diagram. The final document.
4. **Three fits and the Online switch.** Sourced research, scoring, the verdict page.
5. **The Learn room.** Knowledge graph, offline Wikipedia, checked links.

Stages 4 and 5 can swap.

## Notes

- The sample idea (a solar cold box for vegetable vendors), the sample topic (the monsoon) and the RICE numbers in the blueprint are illustrative.
- Model and tool names are examples as of November 2026 and should stay swappable.
- Licences to check before selling a product built on this: Kokoro is Apache-2.0; Piper's engine is GPL-3.0 and each voice has its own terms.
