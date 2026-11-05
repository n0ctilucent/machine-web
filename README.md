# Machine-Readable Content & LLM Evaluation

**Researcher:** Nathan Wintroub  
**Email:** nathan.wintroub@ucdenver.edu  
**Faculty Sponsor:** Franklin Diaz, Adjunct Faculty — Information Systems, CU Denver Business School (BUS 6204)  
**Course:** ISMG Applied AI / Information Systems (BUS 6204)  

---

## Overview

This project investigates the **human-machine interface gap**: how commercial LLMs consume, interpret, and extract value from enterprise research documentation — and whether structured discovery artifacts (`llms.txt`, machine-readable manifests, agent instruction patterns) measurably improve comprehension efficiency.

The broader theoretical motivation stems from ideas around **pasigraphy** and **semiotic efficiency** — using compact symbolic representations to trade information between humans and machines more rapidly than natural-language HTML parsing allows. This work is the practical bridge: building machine-friendly scaffolding for a real-world site and measuring whether LLMs actually benefit.

---

## Research Questions

1. **Information Efficiency:** How much does structured metadata (summary, key facts, content type, boundaries) reduce token waste and hallucination compared to raw HTML parsing?
2. **Document-Type Sensitivity:** Do dense technical documents benefit more from scaffolding than high-level index pages — or vice versa?
3. **Model Variance:** Are some LLMs more amenable to structured inputs than others?
4. **Enterprise Applicability:** What concrete steps should an organization take to make its internal knowledge base agent-ready?

---

## Testbed

**Site:** [bitsmasher.net](https://www.bitsmasher.net) — a live research archive with ~60 blog posts spanning infrastructure, security, networking, cryptography, agent protocols, and lab operations (Aug 2026–Oct 2026).

### Reference Artifacts

| # | Artifact | Live URL |
|---|----------|----------|
| 1 | Machine Catalog — `index.json` structured manifest | https://www.bitsmasher.net/research/index.json |
| 2 | Human-Facing Surface — rendered research index | https://www.bitsmasher.net/research/ |
| 3 | Agent Instruction Pattern — SKILL.md boundary rules | https://www.bitsmasher.net/skills/agent-discovery/SKILL.md |

### Key Blog Posts Evaluated

- [Infrastructure Patching & Network Reconvergence](https://www.bitsmasher.net/research/blog/2026-09-21-infrastructure-patching-and-network-reconvergence.html)
- [Cold Storage Replication & KDC Trust Path](https://www.bitsmasher.net/research/blog/2026-09-25-cold-storage-replication-and-kdc-trust-path.html)

---

## Evaluation Models

| # | Provider | Model / Version | API Endpoint Type |
|---|----------|-----------------|--------------------|
| 1 | OpenAI | gpt-4o | REST API |
| 2 | Google | Gemini Pro | REST API |
| 3 | Anthropic | Claude 3.5 Sonnet | REST API |

### Test Conditions (per page × model)

| Condition | Input | Purpose |
|-----------|-------|---------|
| **Baseline** | URL only (or raw HTML text) | Measure unassisted comprehension |
| **Structured** | `llms.txt` entry + same prompt | Measure scaffolding benefit |

---

## Directory Structure

```
machine-web/
├── README.md                              # This file — project overview
├── HONORS_RESEARCH_TEMPLATE.md            # Submission template (methodology, metrics, semantic analysis)
└── images/                                # Screenshots, diagrams, evaluation visuals
```

### Artifact Sources (external to this repo)

| Artifact | Path / URL |
|----------|------------|
| Research Work Plan | `/mnt/snowy/home/franklin/Documents/scratch/research/work-plan-comprehensive.md` |
| Applied Research Brief | `Applied Research Brief_ Enterprise Machine-Readable Content & LLM Evaluation (Nathan Wintroub).pdf` |
| Shared Project Doc | [Google Docs link](https://docs.google.com/document/d/1lfYRAgsBpioojagVj68x8oDXxkwFCYtIpVKgzhn9vSE/edit?usp=sharing) |

---

## Phases

### Phase 1 — Discovery Orientation (~2h)
Observe and document what each reference artifact reveals (and hides): machine catalog, human-facing surface, agent instruction pattern. Compare noise levels and extractability across formats.

### Phase 2 — Author `llms.txt` Entries (~4h)
Create 3 structured discovery entries using the schema: canonical URL, summary, content type, key facts, relevant/not-relevant roles. One high-level page + two dense technical pages for contrast.

### Phase 3 — Multi-Model Evaluation (~5h)
Run 9 evaluations (3 models × 3 pages), each with baseline and structured conditions. Score on a 1–5 scale across accuracy, reasoning depth, and hallucination rate.

### Phase 4 — Synthesis & Brief (~2h)
Produce a 1-page executive brief answering: information efficiency takeaways, document-type impact analysis, and enterprise recommendations for agent-ready knowledge bases.

---

## Timeline

~13–14 hours total over approximately 2–3 weeks.

## Contact

franklin@bitsmasher.net / franklin.diaz@ucdenver.edu
