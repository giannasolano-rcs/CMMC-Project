# CMMC Engagement Process

**Document type:** Internal Standard Operating Procedure (SOP)
**Owner:** RCS CMMC/Compliance Team
**Audience:** RCS Project Managers (PMs)
**Source of record:** `internal_workflow_dev/RCS-CMMC-Engagement-Workflow.pptx`
**Status:** DRAFT — pending review with Nicholas (see Open Questions)

> **Internal only.** Contains no client names, IP addresses, or PII. When an example
> is needed it is written generically, e.g., "(e.g., the asset inventory)".

---

## Purpose

This document turns the 5-phase **CMMC Engagement Workflow** deck into a step-by-step
playbook so that any RCS project manager can run a CMMC engagement end to end without
having to ask what happens next. The deck shows *what* happens; this document gives the
*turn-by-turn directions* for *how* to do each step. It is the internal SOP other PMs follow.

The workflow is documented **as it is** — phase order and step order are not changed.

## How to use this document

1. Read the **At-a-glance phase map** to orient on the five phases.
2. Work top to bottom. Each step uses the same template: who does it, what triggers it,
   inputs, tools, actions, the artifact produced, where it's stored, the handoff/gate, and
   the definition of done.
3. Where a field reads `[CONFIRM w/ Nicholas]`, that detail was not verifiable from source
   material and must be confirmed before relying on it. These are tracked in the
   **Open Questions** log at the end.
4. Use **Appendix A** as a tick-through checklist while running a live engagement.
5. Use **Appendix B** for CMMC terminology.

---

## Roles glossary

> ⚠️ The deck does not define role ownership per step. The roles below are the likely
> participants; the exact split (and whether a RACI exists) is **Open Question #1**.

| Role | Abbrev. | Likely responsibilities `[CONFIRM w/ Nicholas]` |
|---|---|---|
| Project Manager | PM | Runs the engagement end to end; owns the plan, gates, client communication. |
| Compliance Manager | CM | Compliance lead on the account; reviews assessment/remediation work product. `[CONFIRM scope vs. PM]` |
| Assigning / Lead Engineer | Engineer | Technical scanning, technical review, technical remediation tasks. |
| RCS CMMC/Compliance Team | Team | Shared pool performing scoping, artifact generation, deliverables. |
| Client | Client | Provides access/evidence, attends meetings, signs off at gates. |
| URP (automation) | URP | Platform that generates workbook, scorecard, proposals, doc package. |

## Tools legend

| Code | Full name | Role in the workflow |
|---|---|---|
| **URP** | Unified Reporting Platform | Reporting/deliverable platform — the "spine"; carries workbook, scorecard, proposals, doc package. |
| **RFT** | RapidFire Tools (Compliance Manager GRC) | Drives the assessment (scan, baseline, requirements/controls, worksheets, POA&M). |
| **RMM** | Datto RMM | Deploys discovery/scan agents for RFT. |
| **AT** | Autotask PSA | Holds the project plan and remediation tickets. |
| **ITG** | IT Glue | Holds documentation and the final evidence package. |
| *varied* | Mixed / engineer-led | No single tool; engineer-driven technical work. |

> **Source of truth principle (deck, closing slide):** RFT drives the assessment; URP
> carries the workbook, scorecard, proposals, and doc pack; AT and ITG hold the plan and
> the evidence. Every artifact traces back to the same **Remediation Workbook**.

## At-a-glance phase map

| Phase | Name | Delivers (one line) | Primary tools |
|---|---|---|---|
| 1 | Prospect & Proposal | A scoped Gap Assessment Proposal sent to the prospect. | URP |
| 2 | Gap Assessment | A baseline scan, requirements/controls assessment, worksheets, and POA&M. | RFT, RMM |
| 3 | Remediation Workbook & Post-Assessment | A Remediation Workbook, Compliance Scorecard, and Remediation Proposal sent for acceptance. | URP |
| 4 | Acceptance, Project Setup & Docs | An accepted project plan and the generated required documentation/evidence package. | AT, URP |
| 5 | Remediation, Evidence & Handoff | A completed remediation effort and full evidence package handed off to client + ITG. | varied, RFT, ITG |

### Repo folder layout (per-client)

Maps to the standard per-client structure (per the repo `README.md`):

| Folder | Typical contents | Aligns to |
|---|---|---|
| `00-admin/` | Admin, kickoff, role assignment. | Phase 1 / setup |
| `00-archive/` | Superseded/archived material. | All phases |
| `01-scoping/` | Scope of engagement, asset inventory, boundary, intake. | Phases 1–2 |
| `02-evidence/` | Collected evidence artifacts. | Phases 3, 5 |
| `03-assessment/` | POA&M, worksheets, remediation workbook (draft). | Phases 2–3 |
| `04-deliverables/` | Scorecard, proposals, executive summary, final package. | Phases 3–5 |
| `05-poam/` | POA&M / pre-assessment remediation tracking. | Phases 2, 5 |

---

# Phase 1 — Prospect & Proposal

*Qualify, scope, and win the gap-assessment engagement. Tools: URP.*

### Step 1 — Initial prospect / compliance guideline information
- **Phase:** 1
- **Owner / who does it:** PM `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** New prospect identified or inbound compliance inquiry received.
- **Inputs needed first:** Prospect contact details; the compliance driver (e.g., contract requirement, target framework/level).
- **Tool(s):** URP — intake `[CONFIRM exact URP location/feature name]`
- **What to do (actions):**
  1. Capture the prospect's compliance guideline/driver (framework, level, deadline, contract context).
  2. Record initial scope indicators (org size, environment overview, FCI/CUI involvement).
  3. Create/open the engagement record. `[CONFIRM where: URP / AT / repo client folder]`
- **Output / artifact produced:** Initial prospect/compliance-guideline record.
- **Where it's stored:** `00-admin/` and/or URP `[CONFIRM canonical home — Open Q #5]`
- **Handoff / gate to next step:** Enough qualifying info captured to schedule the intake meeting.
- **Done when (definition of done):** Prospect record exists with the compliance driver documented and the intake meeting scheduled.
- **Notes / common pitfalls:** Confirm the target framework **and level** early (e.g., CMMC L1 vs L2) — it drives the entire scope. `[CONFIRM]`

### Step 2 — Compliance Proposal intake meeting *(discovery meeting)*
- **Phase:** 1
- **Owner / who does it:** PM `[CONFIRM]` (CM may attend `[CONFIRM]`)
- **Starts when (trigger):** Intake meeting scheduled from Step 1.
- **Inputs needed first:** Prospect record; intake form template; target framework/level.
- **Tool(s):** URP — intake form `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Hold the discovery meeting/interview; identify client needs.
  2. Complete the intake form (environment, services in scope, FCI/CUI flow, constraints).
  3. Note observations relevant to scoping.
- **Output / artifact produced:** Completed intake form / discovery notes.
- **Where it's stored:** `01-scoping/` and/or URP `[CONFIRM]`
- **Handoff / gate to next step:** Intake form complete enough to define scope and generate a proposal.
- **Done when (definition of done):** Intake form completed and scope basis agreed internally.
- **Notes / common pitfalls:** Pin down the assessment boundary and information types (FCI/CUI) during this meeting — vague scope here inflates the proposal later.

### Step 3 — Gap Assessment Proposal generated *(proposal sent to prospect)*
- **Phase:** 1
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Intake form complete (Step 2).
- **Inputs needed first:** Completed intake form; pricing reference (`CMMC-L1-Pricing-Benchmark.md` / `RCS_CMMC_L1_Pricing_Model.xlsx`); L1 pricing model output. `[CONFIRM how pricing feeds the proposal — Open Q #2]`
- **Tool(s):** URP — proposal generation `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Apply the appropriate pricing model for the scoped gap assessment.
  2. Generate the Gap Assessment Proposal in URP.
  3. Review for accuracy, then send to the prospect.
- **Output / artifact produced:** Gap Assessment Proposal.
- **Where it's stored:** `04-deliverables/` and/or URP `[CONFIRM]`
- **Handoff / gate to next step:** **Client gate** — proposal sent; proceed on prospect acceptance of the gap-assessment engagement. `[CONFIRM if signature required — Open Q #3]`
- **Done when (definition of done):** Proposal generated, reviewed, and delivered to the prospect.
- **Notes / common pitfalls:** Ensure the proposal scope matches the intake form exactly; mismatches surface during the assessment.

---

# Phase 2 — Gap Assessment

*Scan, baseline, and produce the POA&M in RapidFire Tools. Tools: RFT, RMM.*

### Step 4 — RFT discovery / scan agents from RMM
- **Phase:** 2
- **Owner / who does it:** Engineer `[CONFIRM]`
- **Starts when (trigger):** Gap-assessment engagement accepted; client access confirmed.
- **Inputs needed first:** Client environment access; RMM deployment access; confirmed scope/boundary.
- **Tool(s):** RMM (Datto) to deploy agents → RFT to receive scan data. `[CONFIRM exact deployment path]`
- **What to do (actions):**
  1. Deploy RFT discovery/scan agents via RMM to in-scope systems.
  2. Verify agents check in and scan data populates RFT.
  3. Validate coverage against the scoped asset list.
- **Output / artifact produced:** RFT discovery/scan dataset.
- **Where it's stored:** RFT `[CONFIRM]`
- **Handoff / gate to next step:** Scan data is complete and covers the agreed scope.
- **Done when (definition of done):** All in-scope assets scanned and results visible in RFT.
- **Notes / common pitfalls:** Confirm scan coverage matches the boundary defined in scoping — missed assets create gaps in the assessment.

### Step 5 — RFT Rapid Baseline Assessment *(optional RBA clarification meeting with client)*
- **Phase:** 2
- **Owner / who does it:** Engineer / CM `[CONFIRM]`
- **Starts when (trigger):** RFT scan data available (Step 4).
- **Inputs needed first:** RFT scan dataset; scope/boundary.
- **Tool(s):** RFT — Rapid Baseline Assessment `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Run the Rapid Baseline Assessment (RBA) in RFT.
  2. *(Optional)* Hold an RBA clarification meeting with the client to resolve ambiguities.
  3. Record clarifications back into RFT.
- **Output / artifact produced:** RFT baseline assessment results.
- **Where it's stored:** RFT `[CONFIRM]`
- **Handoff / gate to next step:** Baseline established and clarifications resolved.
- **Done when (definition of done):** RBA complete; open questions from the client resolved or logged.
- **Notes / common pitfalls:** The clarification meeting is optional — use it when scan data is ambiguous rather than guessing.

### Step 6 — Transfer results to Reqs & Controls assessments
- **Phase:** 2
- **Owner / who does it:** Engineer / CM `[CONFIRM]`
- **Starts when (trigger):** Baseline assessment complete (Step 5).
- **Inputs needed first:** RFT baseline results.
- **Tool(s):** RFT — Requirements & Controls assessment `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Transfer baseline results into the Requirements & Controls assessment in RFT.
  2. Confirm each requirement/control maps correctly.
- **Output / artifact produced:** Populated Requirements & Controls assessment.
- **Where it's stored:** RFT `[CONFIRM]`
- **Handoff / gate to next step:** Results transferred and ready for technical review.
- **Done when (definition of done):** Requirements & Controls assessment is populated from baseline data.
- **Notes / common pitfalls:** Verify the transfer completed for every control — partial transfers skew the technical review.

### Step 7 — Technical Review
- **Phase:** 2
- **Owner / who does it:** Engineer `[CONFIRM]`
- **Starts when (trigger):** Requirements & Controls assessment populated (Step 6).
- **Inputs needed first:** Populated assessment; technician observations.
- **Tool(s):** RFT `[CONFIRM]`
- **What to do (actions):**
  1. Review assessment results for technical accuracy.
  2. Correct misclassifications; add engineer notes/observations.
  3. Confirm met/not-met determinations are technically defensible.
- **Output / artifact produced:** Reviewed/validated assessment results.
- **Where it's stored:** RFT `[CONFIRM]`
- **Handoff / gate to next step:** Technical review signed off `[CONFIRM who signs off]`.
- **Done when (definition of done):** All control determinations reviewed and corrected as needed.
- **Notes / common pitfalls:** Automated scan results need human validation — don't pass them straight to worksheets.

### Step 8 — Generate Worksheets
- **Phase:** 2
- **Owner / who does it:** Engineer / Team `[CONFIRM]`
- **Starts when (trigger):** Technical review complete (Step 7).
- **Inputs needed first:** Reviewed assessment results.
- **Tool(s):** RFT — worksheet generation `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Generate the assessment worksheets in RFT.
  2. Verify worksheets reflect the reviewed determinations.
- **Output / artifact produced:** RFT worksheets.
- **Where it's stored:** `03-assessment/` and/or RFT `[CONFIRM]`
- **Handoff / gate to next step:** Worksheets generated and validated.
- **Done when (definition of done):** Worksheets exist and match the reviewed assessment.
- **Notes / common pitfalls:** Worksheets feed the workbook later — confirm they're final before generating the POA&M.

### Step 9 — Generate POA&M
- **Phase:** 2
- **Owner / who does it:** Engineer / CM `[CONFIRM]`
- **Starts when (trigger):** Worksheets generated (Step 8).
- **Inputs needed first:** RFT worksheets.
- **Tool(s):** RFT — POA&M generation (RapidFire 4-sheet format) `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Generate the POA&M in RFT.
  2. Confirm it captures all not-met items.
- **Output / artifact produced:** Plan of Action & Milestones (POA&M).
- **Where it's stored:** `03-assessment/` and/or `05-poam/` `[CONFIRM canonical location]`
- **Handoff / gate to next step:** POA&M finalized; it becomes the input to Phase 3.
- **Done when (definition of done):** POA&M generated and reviewed.
- **Notes / common pitfalls:** For **CMMC L1**, no POA&M is permitted at assessment — all practices must be MET. Any `05-poam/` use at L1 is internal pre-assessment remediation tracking only. `[CONFIRM how L1 vs L2 changes this step]`

---

# Phase 3 — Remediation Workbook & Post-Assessment

*Turn the POA&M into the workbook, scorecard, and remediation proposal. Tools: URP.*

### Step 10 — Generate Remediation Workbook *(feed in RFT POA&M → output workbook → annotate pre-meeting)*
- **Phase:** 3
- **Owner / who does it:** PM / CM `[CONFIRM]`
- **Starts when (trigger):** POA&M finalized (Step 9).
- **Inputs needed first:** RFT POA&M; RFT worksheets.
- **Tool(s):** URP — Remediation Workbook generation `[CONFIRM exact feature name]`. Reference: `_toolkit/build_remediation_workbook.py` produces the workbook (action items + Documents Register). `[CONFIRM relationship between toolkit script and URP feature]`
- **What to do (actions):**
  1. Feed the RFT POA&M (and worksheets) into URP to output the Remediation Workbook.
  2. Annotate the workbook pre-meeting (e.g., pre-split owners across RCS / Joint / Client).
  3. Submit for CM review. `[CONFIRM review step]`
- **Output / artifact produced:** Remediation Workbook (DRAFT) — action items + Documents Register.
- **Where it's stored:** `03-assessment/` `[CONFIRM]`
- **Handoff / gate to next step:** Workbook drafted and annotated, ready for the post-meeting.
- **Done when (definition of done):** Remediation Workbook generated, pre-annotated, and CM-reviewed.
- **Notes / common pitfalls:** The Remediation Workbook is the single source of truth — every later artifact traces back to it. Keep it authoritative.

### Step 11 — Gap Assessment post-meeting with client *(update roles & responsibilities in the Remediation Workbook)*
- **Phase:** 3
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Draft Remediation Workbook ready (Step 10).
- **Inputs needed first:** Draft Remediation Workbook.
- **Tool(s):** URP (workbook) `[CONFIRM]`
- **What to do (actions):**
  1. Hold the post-assessment meeting; review and discuss the gap assessment and proposed activity.
  2. Update roles & responsibilities (RCS / Joint / Client) in the workbook based on the discussion.
- **Output / artifact produced:** Updated Remediation Workbook (roles & responsibilities confirmed).
- **Where it's stored:** `03-assessment/` `[CONFIRM]`
- **Handoff / gate to next step:** **Client gate** — roles & responsibilities agreed with the client. `[CONFIRM sign-off requirement — Open Q #3]`
- **Done when (definition of done):** Workbook reflects agreed ownership for each action item.
- **Notes / common pitfalls:** Lock down who owns what here; ambiguous ownership stalls remediation in Phase 5.

### Step 12 — Feed workbook → Compliance Scorecard *(generate scorecard)*
- **Phase:** 3
- **Owner / who does it:** PM / Team `[CONFIRM]`
- **Starts when (trigger):** Workbook updated post-meeting (Step 11).
- **Inputs needed first:** Updated Remediation Workbook.
- **Tool(s):** URP — Compliance Scorecard generation `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Feed the workbook into URP to generate the Compliance Scorecard.
  2. Review the scorecard for accuracy.
- **Output / artifact produced:** Compliance Scorecard.
- **Where it's stored:** `04-deliverables/` `[CONFIRM]`
- **Handoff / gate to next step:** Scorecard generated and reviewed.
- **Done when (definition of done):** Scorecard reflects current workbook data.
- **Notes / common pitfalls:** Regenerate the scorecard if the workbook changes — keep them in sync.

### Step 13 — Feed workbook → Remediation Proposal *(adjust proposal criteria → generate proposal)*
- **Phase:** 3
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Workbook updated post-meeting (Step 11).
- **Inputs needed first:** Updated Remediation Workbook; pricing reference/model.
- **Tool(s):** URP — Remediation Proposal generation `[CONFIRM exact feature name]`. Reference: `_toolkit/build_l1_pricing_model.py` / `l1_catalog.py` for pricing inputs. `[CONFIRM]`
- **What to do (actions):**
  1. Adjust the proposal criteria (scope, pricing, owner split) in URP.
  2. Generate the Remediation Proposal.
  3. Review for accuracy.
- **Output / artifact produced:** Remediation Proposal.
- **Where it's stored:** `04-deliverables/` `[CONFIRM]`
- **Handoff / gate to next step:** Proposal ready to send to the client.
- **Done when (definition of done):** Remediation Proposal generated and internally reviewed.
- **Notes / common pitfalls:** Confirm the proposal's owner split matches the workbook's roles & responsibilities (Step 11).

### Step 14 — Send proposal to client for acceptance
- **Phase:** 3
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Remediation Proposal reviewed (Step 13).
- **Inputs needed first:** Final Remediation Proposal.
- **Tool(s):** URP / standard delivery channel `[CONFIRM]`
- **What to do (actions):**
  1. Send the Remediation Proposal to the client.
  2. Track for acceptance; answer client questions.
- **Output / artifact produced:** Sent proposal; client acceptance record.
- **Where it's stored:** `04-deliverables/` and/or URP `[CONFIRM]`
- **Handoff / gate to next step:** **Client gate** — client accepts the Remediation Proposal before Phase 4 begins. `[CONFIRM acceptance mechanism — Open Q #3]`
- **Done when (definition of done):** Client acceptance received and recorded.
- **Notes / common pitfalls:** Do not begin project setup (Phase 4) before written acceptance.

---

# Phase 4 — Acceptance, Project Setup & Docs

*On acceptance: plan the project and generate required documentation. Tools: AT, URP.*

### Step 15 — Set up project plan *(timeline · roles & responsibilities)*
- **Phase:** 4
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Client accepts the Remediation Proposal (Step 14).
- **Inputs needed first:** Accepted proposal; Remediation Workbook (roles & responsibilities).
- **Tool(s):** AT (Autotask PSA) — project/plan `[CONFIRM exact location]`
- **What to do (actions):**
  1. Create the project in Autotask with timeline and milestones.
  2. Assign roles & responsibilities per the workbook.
  3. Generate remediation tickets. `[CONFIRM if tickets are created here or in Phase 5]`
- **Output / artifact produced:** Project plan (timeline, roles, tickets).
- **Where it's stored:** AT (Autotask) `[CONFIRM]`
- **Handoff / gate to next step:** Project plan published and resources assigned.
- **Done when (definition of done):** Project exists in AT with timeline, roles, and tasks defined.
- **Notes / common pitfalls:** Mirror the workbook owner split exactly so the plan and workbook don't diverge.

### Step 16 — Generate required docs *(policy templates → client · doc-reqs output · updated client info · upload as evidence package to ITG/RFT)*
- **Phase:** 4
- **Owner / who does it:** PM / Team `[CONFIRM]`
- **Starts when (trigger):** Project plan set up (Step 15).
- **Inputs needed first:** Workbook Documents Register; doc-gen manifest; updated client info.
- **Tool(s):** URP — required-docs/policy template generation `[CONFIRM exact feature name]`; ITG and RFT for upload.
- **What to do (actions):**
  1. Generate required policy templates and documentation from the doc-reqs output / doc-gen manifest.
  2. Provide policy templates to the client.
  3. Update client information.
  4. Upload the generated documentation as an evidence package to ITG/RFT.
- **Output / artifact produced:** Generated policy/documentation package.
- **Where it's stored:** `02-evidence/` and ITG/RFT `[CONFIRM]`
- **Handoff / gate to next step:** Required docs generated and made available to the client.
- **Done when (definition of done):** Doc package generated, delivered to client, and uploaded to ITG/RFT.
- **Notes / common pitfalls:** Use the doc-gen manifest to autofill — don't hand-build documents that the manifest already covers. `[CONFIRM manifest workflow]`

### Step 17 — Complete technical remediation tasks *(varied / engineer-led)*
- **Phase:** 4
- **Owner / who does it:** Engineer (engineer-led) `[CONFIRM PM coordination role]`
- **Starts when (trigger):** Project plan and tickets in place (Steps 15–16).
- **Inputs needed first:** Remediation Workbook; assigned tickets; client access.
- **Tool(s):** *varied* / engineer-led (no single tool).
- **What to do (actions):**
  1. Work the assigned technical remediation tickets.
  2. Capture evidence as each control is remediated.
  3. Update ticket/workbook status as work completes.
- **Output / artifact produced:** Remediated controls + supporting technical evidence.
- **Where it's stored:** `02-evidence/` (evidence); AT (ticket status) `[CONFIRM]`
- **Handoff / gate to next step:** Technical remediation substantially complete, feeding Phase 5.
- **Done when (definition of done):** Assigned remediation tasks completed and evidence captured.
- **Notes / common pitfalls:** Capture evidence at the moment of remediation — reconstructing it later wastes time.

> **Note on phase boundary:** The brief places Step 17 in Phase 4 (§5); the deck depicts
> technical remediation as flowing into the Phase 5 (deck "Phase 4 of 4") handoff. Documented
> per the brief's §5 placement. `[CONFIRM phase boundary]`

---

# Phase 5 — Remediation, Evidence & Handoff

*Remediate, assemble the evidence package, and hand off to client + ITG. Tools: varied, RFT, ITG.*

### Step 18 — Update Remediation Workbook
- **Phase:** 5
- **Owner / who does it:** PM / Engineer `[CONFIRM]`
- **Starts when (trigger):** Technical remediation progresses (Step 17).
- **Inputs needed first:** Current remediation status; captured evidence.
- **Tool(s):** URP (workbook) `[CONFIRM]`
- **What to do (actions):**
  1. Update the Remediation Workbook to reflect completed/remaining items.
  2. Confirm status against tickets and evidence.
- **Output / artifact produced:** Updated Remediation Workbook.
- **Where it's stored:** `03-assessment/` `[CONFIRM]`
- **Handoff / gate to next step:** Workbook reflects current remediation state.
- **Done when (definition of done):** Workbook status matches actual remediation progress.
- **Notes / common pitfalls:** Keep this current — the scorecard and final package derive from it.

### Step 19 — Update RFT Baseline Assessment *(transfer to Req & Control assessment)*
- **Phase:** 5
- **Owner / who does it:** Engineer / CM `[CONFIRM]`
- **Starts when (trigger):** Remediation items completed (Step 18).
- **Inputs needed first:** Updated workbook; remediation evidence.
- **Tool(s):** RFT — Baseline Assessment → Requirements & Controls assessment `[CONFIRM exact feature name]`
- **What to do (actions):**
  1. Update the RFT Baseline Assessment to reflect remediated controls.
  2. Transfer updated results to the Requirements & Controls assessment.
- **Output / artifact produced:** Updated RFT baseline / Req & Control assessment.
- **Where it's stored:** RFT `[CONFIRM]`
- **Handoff / gate to next step:** RFT reflects post-remediation control state.
- **Done when (definition of done):** Baseline updated and transferred to Req & Control assessment.
- **Notes / common pitfalls:** Ensure RFT and the workbook agree before assembling the package.

### Step 20 — Gather full evidence package *(policy · technical control evidence · documentation)*
- **Phase:** 5
- **Owner / who does it:** PM / Team `[CONFIRM]`
- **Starts when (trigger):** RFT updated post-remediation (Step 19).
- **Inputs needed first:** Policy docs; technical control evidence; documentation.
- **Tool(s):** ITG / RFT / repo `02-evidence/` `[CONFIRM]`
- **What to do (actions):**
  1. Collect policy evidence, technical control evidence, and documentation.
  2. Assemble into the full evidence package.
  3. Verify completeness against the Documents Register / control set.
- **Output / artifact produced:** Full evidence package.
- **Where it's stored:** `02-evidence/` and/or ITG `[CONFIRM]`
- **Handoff / gate to next step:** Evidence package complete and verified.
- **Done when (definition of done):** Every required control has corresponding evidence assembled.
- **Notes / common pitfalls:** Cross-check the package against the Documents Register so nothing is missing before client presentation.

### Step 21 — Present package to client
- **Phase:** 5
- **Owner / who does it:** PM `[CONFIRM]`
- **Starts when (trigger):** Full evidence package assembled (Step 20).
- **Inputs needed first:** Evidence package; Compliance Scorecard; Engagement Findings / Executive Summary / Operational Feasibility report.
- **Tool(s):** URP (deliverables) `[CONFIRM]`
- **What to do (actions):**
  1. Present Engagement Findings, Executive Summary, and the Operational Feasibility report.
  2. Walk the client through the scorecard and evidence package.
  3. Address questions and confirm client acknowledgement.
- **Output / artifact produced:** Presented deliverables; client acknowledgement.
- **Where it's stored:** `04-deliverables/` `[CONFIRM]`
- **Handoff / gate to next step:** **Client gate** — client receives and acknowledges the package. `[CONFIRM sign-off requirement]`
- **Done when (definition of done):** Package presented and client acknowledgement recorded.
- **Notes / common pitfalls:** Confirm whether SPRS filing / vendor submission support is in scope (see optional items below) before closing.

### Step 22 — Upload full package to ITG
- **Phase:** 5
- **Owner / who does it:** PM / Team `[CONFIRM]`
- **Starts when (trigger):** Package presented and accepted (Step 21).
- **Inputs needed first:** Final evidence package; final deliverables.
- **Tool(s):** ITG (and RFT updated with client details) `[CONFIRM]`
- **What to do (actions):**
  1. Upload the full package to ITG.
  2. Confirm ITG and RFT are updated with current client details.
  3. Close out the engagement record. `[CONFIRM closeout steps]`
- **Output / artifact produced:** Archived full package in ITG; updated ITG/RFT records.
- **Where it's stored:** ITG (canonical) + `04-deliverables/` `[CONFIRM]`
- **Handoff / gate to next step:** Engagement closed; knowledge management updated.
- **Done when (definition of done):** Full package uploaded to ITG and engagement closed.
- **Notes / common pitfalls:** Verify the uploaded package is complete and matches what was presented to the client.

### Optional Phase 5 items (from deck — not in §5 numbered list) `[CONFIRM placement]`
- **(Optional) Facilitate SPRS Filing** — include SPRS-required documentation; facilitate providing selective information on submission.
- **(Optional) Facilitate Vendor Submission.**

> These appear on the deck (Phase 4 of 4) but are not in the brief's §5 numbered list, so they
> are documented as optional add-ons rather than standalone steps. Confirm whether they should
> become numbered steps and who owns them.

---

# Appendix A — PM Checklist (tick-through)

**Phase 1 — Prospect & Proposal**
- [ ] Step 1 — Initial prospect / compliance guideline information
- [ ] Step 2 — Compliance Proposal intake meeting (discovery)
- [ ] Step 3 — Gap Assessment Proposal generated & sent  ⟵ *client gate*

**Phase 2 — Gap Assessment**
- [ ] Step 4 — RFT discovery / scan agents from RMM
- [ ] Step 5 — RFT Rapid Baseline Assessment (optional RBA meeting)
- [ ] Step 6 — Transfer results to Reqs & Controls assessments
- [ ] Step 7 — Technical Review
- [ ] Step 8 — Generate Worksheets
- [ ] Step 9 — Generate POA&M

**Phase 3 — Remediation Workbook & Post-Assessment**
- [ ] Step 10 — Generate Remediation Workbook
- [ ] Step 11 — Gap Assessment post-meeting (update roles & responsibilities)  ⟵ *client gate*
- [ ] Step 12 — Feed workbook → Compliance Scorecard
- [ ] Step 13 — Feed workbook → Remediation Proposal
- [ ] Step 14 — Send proposal to client for acceptance  ⟵ *client gate*

**Phase 4 — Acceptance, Project Setup & Docs**
- [ ] Step 15 — Set up project plan
- [ ] Step 16 — Generate required docs
- [ ] Step 17 — Complete technical remediation tasks

**Phase 5 — Remediation, Evidence & Handoff**
- [ ] Step 18 — Update Remediation Workbook
- [ ] Step 19 — Update RFT Baseline Assessment
- [ ] Step 20 — Gather full evidence package
- [ ] Step 21 — Present package to client  ⟵ *client gate*
- [ ] Step 22 — Upload full package to ITG
- [ ] (Optional) Facilitate SPRS Filing
- [ ] (Optional) Facilitate Vendor Submission

---

# Appendix B — Glossary of CMMC terms

| Term | Meaning |
|---|---|
| **CMMC** | Cybersecurity Maturity Model Certification — DoD program for assessing contractor cybersecurity. |
| **FCI** | Federal Contract Information — information provided by/generated for the government under a contract, not intended for public release. |
| **CUI** | Controlled Unclassified Information — information requiring safeguarding/dissemination controls per law, regulation, or government-wide policy. |
| **POA&M** | Plan of Action & Milestones — documents control gaps and the plan/timeline to remediate them. *(Not permitted at CMMC L1 — all practices must be MET.)* |
| **RBA** | Rapid Baseline Assessment — RFT baseline scan/assessment used to establish the environment's compliance baseline. |
| **SSP** | System Security Plan — documents how a system meets each applicable requirement (system boundary, controls, responsibilities). `[CONFIRM where SSP is produced in this workflow]` |
| **Control family** | A grouping of related security requirements (e.g., Access Control, Identification & Authentication). |
| **SPRS** | Supplier Performance Risk System — DoD system where self-assessment scores/affirmations are submitted. |
| **CMMC L1** | Level 1 — 17 practices across 6 families (FAR 52.204-21 / NIST SP 800-171 subset); all practices must be MET; annual self-assessment + senior-official affirmation. |
| **CMMC L2** | Level 2 — expanded requirement set (NIST SP 800-171 based); broader scope than L1. `[CONFIRM workflow deltas for L2]` |

---

# Open Questions log (Nicholas to answer)

> Documented per §11 plus gaps found while writing. These block fields marked `[CONFIRM]`.

1. **Step ownership / RACI.** Who owns each step — PM vs. CM vs. Engineer vs. URP automation vs. Client? Is there an existing RACI to mirror? (Affects every "Owner" field.)
2. **Exact URP feature/menu names** for: Remediation Workbook generation, Compliance Scorecard, Remediation Proposal, required-docs/policy templates, and proposal generation (Steps 3, 10, 12, 13, 16). Also: relationship between the `_toolkit/` scripts and the URP features (do the scripts back the URP buttons, or are they separate?).
3. **Client-facing gates.** Confirmed gates appear at Steps 3, 11, 14, 21. Which require formal written sign-off vs. acknowledgement? Any others?
4. **Timeline / SLA per phase.** Rough durations per phase so PMs can set client expectations? (Optional.)
5. **Canonical home for a running engagement.** Repo client folder, URP, Autotask, or a mix? This determines every "Where it's stored" field (currently dual-listed with `[CONFIRM]`).
6. **L1 vs L2 differences.** How do Steps 9 (POA&M) and 16 (doc package) change between CMMC L1 and L2? (Deck notes an L2 expansion is planned.)
7. **Phase boundary for Step 17 (technical remediation).** Brief §5 places it in Phase 4; the deck flows it into the handoff phase. Confirm.
8. **Optional SPRS / Vendor Submission.** Should these become numbered steps? Who owns them, and when are they in scope?
9. **SSP.** Where (if anywhere) is the System Security Plan produced in this workflow? It's a common CMMC artifact but is not named in §5.
10. **Engineer vs. CM split in Phase 2.** Steps 5–9 mix engineer and CM work — confirm who does technical review and POA&M generation.
