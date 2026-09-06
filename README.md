# 🔥 Intel-Forge — Agentic GraphRAG for Criminal Network Analysis

**SIH 2026 prototype · single-file frontend · zero install**

Everything lives in `index.html`. Double-click it (or open it in any browser) — that's the whole setup. All data is synthetic/hardcoded; this is a demo prototype, not a connected system.

## What to show judges (60-second demo script)

1. **Hero** — point at the *live network graph*: suspects, phones, accounts, locations as glowing nodes. **Drag a node around** — it re-settles. That's the Neo4j layer of the story.
2. **Evidence Desk** — drag & drop (or click to browse):
   - a **photo** → scanning line runs, YOLOv8-style bounding boxes draw on (`person 96.4%`, `motorcycle 89.1%`…), agent feed narrates, citation gets stamped. Same file always gives the same result (seeded by filename+size — deterministic, like a real model).
   - a **PDF/TXT/CSV** → OCR + NER pulls out persons, phones, statutes with line references. (Genuine extraction on `.txt`/`.csv` — real phone numbers/names from your file.)
   - a **video** → frame scanning with a detection timeline.
   - Hit **"Add to graph ⚡"** on a result → watch the hero graph gain a new node + toast fires. **"Reject"** routes to HITL quarantine.
3. **Agent Network** — the query dot travels Orchestrator → specialists → Citation, cards flip to `✓ verified`; 15-agent roster below is "breathing".
4. **Forge Copilot** (bottom-right flame) — ask:
   - *"Who did Raj Kumar call before the robbery?"*
   - *"Find money mules in the network"*
   - *"What-if: +91 98••• 4412 is Rathi's burner"* → shows the `EPHEMERAL_BRANCH` badge (what-if never touches master graph).
   - Every answer streams with an **agent trace** and ends with **citation chips**.

## The story behind the details (viva ammo)

- **No claim without citation** — every detection/entity shows an evidence pointer (`EVD-…`, `CCTV-04 · F-1142`, `FIR L.14`), straight from the agent protocol.
- **Confidence gates** — detections can randomly come in <60% and get flagged `⚠ LOW CONF` (never auto-linked).
- **HITL quarantine** — "Reject" doesn't delete; it routes to human review, matching the operating rules.
- **What-If branches** — ephemeral overlays are explicitly read-only on the master graph.
- **15 agents** — Orchestrator, Telecom, Financial, Visual, NLP, GDS, Vector, Identity, Citation, HITL, What-If, Code Verification ("Ponytail"), Validation Gate, Audit, Dashboard.

## Files

| File | What |
|---|---|
| `index.html` | Entire prototype (HTML + CSS + JS, no build step) |
| `README.md` | This file |

Requires internet only for the Google Fonts (falls back to system fonts offline).
