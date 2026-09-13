# Agentic Automation: AI-Driven Multi-Agent Workflow Engineering — Drops

Session owner: **Eshmith Saideep** · Series: Be10x · Daily Drop

Subject taught: **n8n and how to engineer a multi-agent system inside it.**
Stock analysis (Infosys) is the worked example only — the lesson is nodes, ports, sub-nodes,
agent-as-tool wiring, items/expressions, and the Code → Gmail last mile.

## The five drops

| Day | Drop type | File | Suggested Vercel name |
|---|---|---|---|
| Monday | PDF | `n8n-multiagent-carousel.html` | `n8n-carousel` |
| Tuesday | Handson | `n8n-multiagent-lab.html` | `n8n-lab-1` |
| Wednesday | HTML | `n8n-multiagent-playground.html` | `n8n-playground` |
| Thursday | Flash Cards | `n8n-multiagent-flashcards.html` | `n8n-flashcards` |
| Friday | Quiz | `n8n-multiagent-quiz.html` | `n8n-quiz` |

Naming follows the existing scheme (`llm-*`, `langgraph-*`, `datacleaning-*`, `dashboards-*`).

## Deploying

Each file is a self-contained static page — no build step, no dependencies.
The only external resource is the Google Fonts stylesheet.

```
mkdir n8n-playground && cp n8n-multiagent-playground.html n8n-playground/index.html
cd n8n-playground && vercel --prod
```

Repeat per drop. Or drag each folder onto the Vercel/Netlify dashboard.

## Producing the PDF (Monday's drop)

Open `n8n-multiagent-carousel.html`, click **Save as PDF** (or Cmd-P) and choose
"Save as PDF". The print stylesheet lays the deck out one square slide per page —
12 pages, backgrounds preserved, navigation chrome hidden.

## Design systems used

These match the existing drop family exactly — do not re-theme them.

- **Carousel, Playground, Quiz** — warm cream: `--bg:#F7EFE2` `--card:#FFFBF3` `--line:#E7D8C4`
  `--ink:#4A3830` `--clay:#B4785B` `--sage:#7FA37A` `--rose:#C97B7B`.
  Fonts: Fraunces + Nunito + JetBrains Mono (+ Permanent Marker).
- **Flash Cards** — sky blue: `--bg:#E9F4FB` `--card:#FDFEFF` `--line:#CFE4F2` `--ink:#24425C`
  `--sky:#3E97D1` `--ok:#5FAF97` `--bad:#E08A8A`. Same font set.
- **Lab** — technical slate: `--bg:#F7F8FA` `--surface:#FFFFFF` `--border:#E3E7ED` `--ink:#101828`
  `--accent:#2563EB` `--ok:#059669` `--err:#DC2626`. Fonts: Inter + JetBrains Mono.

## Optional hero images

The carousel, flashcards and quiz each expose a `HERO_IMAGE` constant near the top of
their `<script>`. Paste an image URL between the quotes and the hero slot unhides itself.

## The canonical workflow taught (12 nodes)

Main line: **When chat message received** → **Orchestrator Agent** → **Code in JavaScript** → **Send a message** (Gmail)

Under the Orchestrator: OpenAI Chat Model (gpt-4o-mini), Simple Memory,
and the two specialists attached to its **Tool** port —
**Fundamental Analysis Agent** (what to buy) and **Technical Analysis Agent** (when).
Each specialist carries its own OpenAI Chat Model and its own SerpAPI tool.

## The through-line

The idea threaded across all five drops, because it is the thing learners get wrong and it is
genuinely n8n-specific: **the AI Agent node has a row of ports underneath it** — Chat Model
(required), Memory (optional), Tool (zero or many) — drawn as dotted downward connections,
unlike the solid left-to-right main line. And a tool's **description** is what decides whether
the orchestrator ever calls it.

All five files carry the educational-use / not-financial-advice note.
