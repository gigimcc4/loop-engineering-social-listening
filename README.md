# Loop Engineering, by Hand — a Weekly Competitor-Listening Agent

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gigimcc4/loop-engineering-social-listening/blob/main/Loop_Engineering_Weekly_Competitor_Agent.ipynb)

> Built for the **AI Tinkerers** community.
> **Created by Dr. Jeanne McClure · [Ars Innovate](https://arsinnovate.com).**

Point it at your product and its rivals. Every week it listens across the open web, measures the mood, models the topics, and emails you where you're winning, losing, and the gaps to attack — running on **open models, no API keys**.

This is a hands-on look at **loop engineering**: instead of "calling an LLM in a loop," you decide *step by step* which engine each job deserves — and reserve the (paid) LLM for the one thing only it can do.

---

## What it does

A market-research agent that runs itself. Each step uses the right tool for the job:

| Step | Tool | Token cost |
|---|---|---|
| **Listen** — Bluesky + Hacker News (+ Reddit, optional) | open APIs | 0 |
| **Sentiment** | [VADER](https://github.com/cjhutto/vaderSentiment) (NLTK) — validated for social text | 0 |
| **Topics** | [BERTopic](https://maartengr.github.io/BERTopic/) — BERT embeddings + c-TF-IDF | 0 |
| **Interpret · find gaps · propose new signals** | [IBM Granite](https://www.ibm.com/granite) (open LLM via [Ollama](https://ollama.com)) | a little — *only here* |
| **Deliver · ask what to watch next** | a Monday-morning email you can reply to | 0 |

The loop even **improves itself**: Granite proposes competitors it wasn't asked to track, the Monday email asks if you want them, and your reply widens next week's listening — self-improvement with a human gate.

It also shows the two sides of loop engineering side by side: **Part A** — *you* engineer the loop (the [Ralph loop](https://ghuntley.com/), coined by Geoffrey Huntley); **Part B** — the *agent* engineers its own loop (IBM [BeeAI](https://github.com/i-am-bee)).

## Run it

1. Open in Colab (badge above) → **File → Save a copy in Drive**.
2. **Runtime → Change runtime type → T4 GPU → Save**.
3. **Runtime → Run all**. First setup takes ~3 minutes.
4. Edit `PLAN` (Step 1) to your own product + competitors, then Run all again.

No code required, no API keys. Reddit is optional and needs free credentials.

## Prompt vs. Context vs. Loop engineering

| Approach | What you shape | Reach for it when |
|---|---|---|
| **Prompt engineering** | the wording of one request | you want one good answer |
| **Context engineering** | what the model can see — docs, data, tools | it needs the right facts/tools in front of it |
| **Loop engineering** | the *steps* the model repeats — gather, reason, check, adjust | the work repeats or runs itself (this agent) |

---

## Credit & License

**© 2026 Dr. Jeanne McClure · Ars Innovate.** Licensed under **[Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/)**.

You are free to **share and adapt** this material for **non-commercial** purposes, **with attribution** to Dr. Jeanne McClure / Ars Innovate. Please keep the credit and pass it on — a lot of work goes into sharing these resources. For commercial use, please get in touch.

Standing on the shoulders of: the **Ralph loop** (Geoffrey Huntley); Goal → Action → Observation → Adjustment framing (IBM); **VADER** (Hutto & Gilbert, 2014); **BERTopic** (Grootendorst, 2022); **Granite** & **BeeAI** (IBM, open-source). The **ICI** (Instruction · Context · Input) prompting framework and the **From Vibes to Evidence** evaluation framework are © Dr. Jeanne McClure / Ars Innovate.
