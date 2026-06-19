# Assignment Brief — CMMC Engagement Process Document

**To:** Gianna  **From:** Nicholas  **Re:** Turn the CMMC Engagement Workflow into an actionable PM process document

---

## 1. The assignment in one sentence

Take our existing **CMMC Engagement Workflow** (currently a 5-phase slide deck) and write it up as a clear, **step-by-step process document that any RCS project manager could follow to run a CMMC engagement end to end** — without having to ask someone what happens next.

## 2. Why this matters / who reads it

Today the workflow lives in a slide deck and in our heads. The deck shows **what** happens; it doesn't tell a PM **how** to actually do each step. As we take on more CMMC clients, we need a repeatable playbook so any PM can pick up an engagement and run it consistently. Your document becomes the internal SOP other PMs follow. This is real, used work — not busywork.

**Mental model:** the deck = the *map*; your document = the *turn-by-turn directions*.

## 3. Source materials (everything you need is here)

All in `~/repos/cmmc-projects/` (the `cmmc-projects` repo):

| Source | Path | How to use it |
|---|---|---|
| **The workflow deck** | `internal_workflow_dev/RCS-CMMC-Engagement-Workflow.pptx` | The authoritative sequence. Don't change the order or the phases — you're documenting it, not redesigning it. |
| **The deck's source data** | `internal_workflow_dev/generate_workflow_deck.py` (the `PHASES` block) | The exact 15 steps in text form — copy step names from here so wording stays consistent. (Reproduced in §5 below.) |
| **The repo README** | `cmmc-projects/README.md` | Shows the standard per-client folder layout (`00-admin` → `05-poam`) — it lines up with the 5 phases. |
| **Real client engagements** | `Southcoast-Acoustics/`, `CheckSix-Aerospace/`, `Reid_Products/`, `Floor-Tech-America/`, `Moseys-Precision-Machinists/` | Live examples at different stages. Open these to see the **real artifacts** each step produces (scoping docs, evidence folders, POA&Ms, deliverables). Best way to make a step concrete. |
| **The toolkit scripts** | `_toolkit/` (`build_remediation_workbook.py`, `build_l1_pricing_model.py`, `l1_catalog.py`) | Where some artifacts are generated. Reference what they produce, not the code internals. |
| **Pricing reference** | `internal_workflow_dev/CMMC-L1-Pricing-Benchmark.md` + `RCS_CMMC_L1_Pricing_Model.xlsx` | Context for the proposal steps (Phase 1 & 3). |

> ⚠️ **Client data caution:** the client folders contain real engagement data. Use them to understand *what an artifact looks like* — **do not copy any client names, IP addresses, or specifics into the process document.** Keep the doc generic and reusable. When you need an example, write it as "(e.g., the asset inventory)" not "(e.g., Reid's asset inventory)."

## 4. The tools referenced in the workflow (legend — use these exact names)

| Code | Full name |
|---|---|
| **URP** | Unified Reporting Platform (our reporting/deliverable platform — the "spine" of the workflow) |
| **RFT** | RapidFire Tools (Compliance Manager GRC) |
| **RMM** | Datto RMM |
| **AT** | Autotask PSA |
| **ITG** | IT Glue |
| *varied* | Mixed / engineer-led (no single tool) |

## 5. The authoritative workflow — 5 phases, 15 steps (don't change this)

**Phase 1 — Prospect & Proposal** *(qualify, scope, and win the gap-assessment engagement)* — tools: URP
1. Initial prospect / compliance guideline information
2. Compliance Proposal intake meeting *(discovery meeting)*
3. Gap Assessment Proposal generated *(proposal sent to prospect)*

**Phase 2 — Gap Assessment** *(scan, baseline, produce the POA&M in RapidFire Tools)* — tools: RFT, RMM
4. RFT discovery / scan agents from RMM
5. RFT Rapid Baseline Assessment *(optional RBA clarification meeting with client)*
6. Transfer results to Reqs & Controls assessments
7. Technical Review
8. Generate Worksheets
9. Generate POA&M

**Phase 3 — Remediation Workbook & Post-Assessment** *(turn the POA&M into the workbook, scorecard, and remediation proposal)* — tools: URP
10. Generate Remediation Workbook *(feed in RFT POA&M → output workbook → annotate pre-meeting)*
11. Gap Assessment post-meeting with client *(update roles & responsibilities in the Remediation Workbook)*
12. Feed workbook → Compliance Scorecard *(generate scorecard)*
13. Feed workbook → Remediation Proposal *(adjust proposal criteria → generate proposal)*
14. Send proposal to client for acceptance

**Phase 4 — Acceptance, Project Setup & Docs** *(on acceptance: plan the project, generate required documentation)* — tools: AT, URP
15. Set up project plan *(timeline · roles & responsibilities)*
16. Generate required docs *(policy templates → client · doc-reqs output · updated client info · upload as evidence package to ITG/RFT)*
17. Complete technical remediation tasks *(varied / engineer-led)*

**Phase 5 — Remediation, Evidence & Handoff** *(remediate, assemble the evidence package, hand off to client + ITG)* — tools: varied, RFT, ITG
18. Update Remediation Workbook
19. Update RFT Baseline Assessment *(transfer to Req & Control assessment)*
20. Gather full evidence package *(policy · technical control evidence · documentation)*
21. Present package to client
22. Upload full package to ITG

> *(The deck groups these as "15 steps" at the phase level; the numbered list above is the fully expanded set — document every line.)*

## 6. What to produce — required structure

Write **one Markdown document**. Use this structure:

**Front matter**
- Title, purpose (1 short paragraph), intended audience (RCS PMs), and "how to use this document."
- **Roles glossary** — who's involved (PM, assigning engineer, client, etc.). *(Ask Nicholas to confirm the exact roles — see Open Questions.)*
- **Tools legend** (from §4).
- **At-a-glance phase map** — the 5 phases and what each delivers (one line each).

**Body — one section per phase, then the step template (below) for every step in that phase.**

**Appendices (optional but nice)**
- A simple checklist version (every step as a checkbox) a PM can tick through.
- A glossary of CMMC terms a new PM might not know (POA&M, RBA, SSP, control family, FCI/CUI).

## 7. The per-step template (this is the core — fill it in for every step)

For **each** of the ~22 steps, fill this in:

```
### Step X — <step name, copied from §5>
- **Phase:** <1–5>
- **Owner / who does it:** <role — e.g., PM, engineer, client>   [CONFIRM if unsure]
- **Starts when (trigger):** <what kicks this step off / the prior handoff>
- **Inputs needed first:** <docs/data/access you must have before starting>
- **Tool(s):** <URP / RFT / RMM / AT / ITG — and *where* in the tool, if you know it>
- **What to do (actions):**
  1. <concrete step>
  2. <concrete step>
- **Output / artifact produced:** <the file or result this step creates>
- **Where it's stored:** <repo folder / URP / ITG / AT — map to the 00-admin…05-poam layout where it fits>
- **Handoff / gate to next step:** <what must be true before moving on; any client approval>
- **Done when (definition of done):** <a one-line test for "this step is complete">
- **Notes / common pitfalls:** <anything a first-timer would trip on>   [optional]
```

Keep each step tight — a PM should be able to read one step and act. If you don't know a field, **write `[CONFIRM w/ Nicholas]` — do not guess or make it up** (see §8).

## 8. How to work it (suggested approach)

1. **Read first:** open the deck, skim the five client folders to see what real artifacts look like, and read the repo README's folder layout.
2. **Draft phase by phase.** Do Phase 1 completely, show Nicholas, get feedback, then continue — better to course-correct early than redo all five.
3. **Map each step to where its artifact lives** (the `00-admin → 05-poam` folders are your friend).
4. **Flag, don't fabricate.** This is the most important rule: if you're not sure who owns a step, what a tool screen is called, or what the exact gate is, write `[CONFIRM w/ Nicholas]` and add it to the Open Questions log (§11). A document that's honest about its gaps is far more useful than one that sounds confident and is wrong.
5. **Keep it reusable and generic** — no client specifics, no PII.

## 9. Rules & constraints (quick reference)
- ✅ Document the workflow **as it is** — don't reorder or redesign it.
- ✅ Use the **exact tool names and step names** from §4 and §5 (consistency matters).
- ✅ **Internal-only** document. **No client names, IPs, or PII.**
- ✅ Plain, direct, professional voice — written for a busy PM.
- ❌ Don't invent procedure you don't know — flag it instead.

## 10. Deliverable — format & location
- **Format:** Markdown (`.md`).
- **Save as:** `internal_workflow_dev/CMMC-Engagement-Process.md` (right next to the deck).
- Keep your **Open Questions** at the bottom of the same file (or a separate `…-QUESTIONS.md`) so Nicholas can answer them in one pass.

## 11. Open questions to seed (start your log with these — Nicholas to answer)
These are the gaps the deck *doesn't* settle; you'll hit them as you write:
1. **Who owns each step?** Is there a role split (PM vs. engineer vs. URP/automation vs. client)? Is there a RACI we should reflect?
2. **Exact URP feature names** for: Remediation Workbook generation, Compliance Scorecard, Remediation Proposal, required-docs/policy templates. (Reference them by the real menu/feature names.)
3. **The client-facing gates** — which steps require client sign-off before proceeding (proposal acceptance is obvious; are there others)?
4. **Timeline / SLA per phase** — rough durations so a PM can set expectations? (Optional, but useful.)
5. **Where is the canonical home** for a running engagement — this repo's client folder, URP, Autotask, or a mix? (Affects the "Where it's stored" field.)

## 12. Definition of done (for this assignment)
- Every step in §5 documented with the §7 template, no blank fields except where marked `[CONFIRM]`.
- Front matter (purpose, roles, tools legend, phase map) complete.
- A PM who has never run a CMMC engagement could read it and know what to do next at every step.
- Open Questions log filled in for anything you couldn't confirm.
- Reviewed with Nicholas after Phase 1 draft, then again at full draft.

---

*You've got the right instincts for this — read the real engagements, document what you see, and flag what you don't. When in doubt, ask. — N.*
