# Be10x Daily Drops

Interactive learning drops on applied AI engineering. Three series, five drops each —
a deck, a hands-on lab, an interactive playground, flash cards and a quiz.

**Live:** https://drops-n8n-multi-agent-system.vercel.app

Every drop is a single self-contained HTML file. No build step, no dependencies,
no bundler — Vercel serves this repository exactly as it is.

---

## Series 01 — n8n · Agentic Automation

Multi-agent workflow engineering in n8n: one orchestrator agent, two specialists on its
Tool port, and a report that writes and sends itself. Twelve nodes.

| Drop | Path | What it is |
|---|---|---|
| Mon | [`n8n/carousel/`](n8n/carousel/)     | 12-slide deck, cover to close |
| Tue | [`n8n/lab/`](n8n/lab/)               | Wire all twelve nodes, then diagnose six real failures |
| Wed | [`n8n/playground/`](n8n/playground/) | Six live widgets — pull the brain out of an agent, watch it break |
| Thu | [`n8n/flashcards/`](n8n/flashcards/) | Twelve ideas that make n8n agents click |
| Fri | [`n8n/quiz/`](n8n/quiz/)             | Ten questions on mechanics and design judgement |

## Series 02 — LangChain · Agentic AI

Building intelligent agents with LangChain: one question, three tool calls, and a model
that chose how many times to go round — in about twenty lines of Python.

| Drop | Path | What it is |
|---|---|---|
| Mon | [`langchain/carousel/`](langchain/carousel/)     | One question, three tool calls |
| Tue | [`langchain/lab/`](langchain/lab/)               | Assemble the agent |
| Wed | [`langchain/playground/`](langchain/playground/) | Stop scripting it. Let it decide. |
| Thu | [`langchain/flashcards/`](langchain/flashcards/) | Twelve ideas behind a LangChain agent |
| Fri | [`langchain/quiz/`](langchain/quiz/)             | Ten questions on agents in LangChain |

## Series 03 — RAG · Retrieval Engineering

RAG foundations and optimisation in one week: chunking, retrieval design, hybrid search,
reranking and evaluation — why yours returns the wrong paragraph, and the five stages that fix it.

| Drop | Path | What it is |
|---|---|---|
| Mon | [`rag/carousel/`](rag/carousel/)     | Closest is not correct |
| Tue | [`rag/lab/`](rag/lab/)               | The retrieval bench |
| Wed | [`rag/playground/`](rag/playground/) | Why yours returns the wrong paragraph |
| Thu | [`rag/flashcards/`](rag/flashcards/) | Twelve ideas between question and answer |
| Fri | [`rag/quiz/`](rag/quiz/)             | Ten questions on making retrieval work |

---

## Repository layout

```
index.html              hub — links to the three series
vercel.json             clean URLs + redirects from the old flat filenames
n8n/index.html          series landing page
n8n/<drop>/index.html   one folder per drop
langchain/…             same shape
rag/…                   same shape
```

Each drop lives in its own folder as `index.html`, so its URL is the folder path —
`/rag/quiz/` rather than a long filename. A folder without an `index.html` has no
URL of its own, which is why the structure looks like this.

## Adding a new series

1. Create `<topic>/` with an `index.html` landing page.
2. Add one folder per drop, each containing `index.html`.
3. Link the topic from the root `index.html`.
4. Commit and push — Vercel deploys `main` automatically.

## Credits

Built by **Eshmith Saideep** for Be10x.

Educational material. The stock analysis, order-support agent and company handbook used
across these series are worked examples for teaching the engineering — not financial,
operational or legal advice.
