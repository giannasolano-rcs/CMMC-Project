# CMMC Engagement Process

## Purpose

This document converts the RCS CMMC Engagement Workflow from a high-level slide deck into an actionable, step-by-step internal process document. It is intended to help any RCS project manager run a CMMC engagement consistently from initial prospect intake through remediation, evidence assembly, and final handoff.

## Intended audience

RCS project managers, compliance managers, assigning engineers, and other internal staff supporting CMMC engagements.

## How to use this document

Use this SOP in sequence. Follow the phases and steps in the order shown; do not reorder them. For each step, confirm the trigger, gather the listed inputs, complete the actions, store the artifact in the expected system or folder, and verify the handoff criteria before moving forward. If a field is marked `[CONFIRM w/ Nicholas]`, treat it as an open item requiring clarification before standardizing the process.

---

## Roles glossary

> These role definitions are working placeholders based on the workflow materials and must be validated before final approval.

- **PM** — Project Manager. Owns coordination, scheduling, client communication, task tracking, status updates, and handoffs. `[CONFIRM w/ Nicholas]`
- **CM** — Compliance Manager / Compliance Lead. Supports scoping, assessment review, control interpretation, remediation planning, and client-facing assessment discussions. `[CONFIRM w/ Nicholas]`
- **Assigning Engineer** — Technical lead or assigned remediation engineer responsible for scans, technical review, remediation execution, and evidence collection. `[CONFIRM w/ Nicholas]`
- **Automation / URP process owner** — Internal role or function responsible for running or validating URP-generated outputs where applicable. `[CONFIRM w/ Nicholas]`
- **Client stakeholder** — Client-side decision-maker, compliance contact, or operational lead who provides scope, confirms business context, reviews findings, and approves proposals.
- **Client technical contact** — Client-side IT or operational resource who provides access, supports scans, answers technical questions, and supplies evidence.
- **RCS leadership / approver** — Internal approver for proposals, delivery quality, or exceptions as needed. `[CONFIRM w/ Nicholas]`

---

## Tools legend

| Code | Full name | Use in workflow |
|---|---|---|
| **URP** | Unified Reporting Platform | Reporting and deliverable platform; workflow spine for workbook, scorecard, proposal, and document package generation |
| **RFT** | RapidFire Tools (Compliance Manager GRC) | Assessment platform for baseline discovery, requirements/control assessments, worksheets, and POA&M |
| **RMM** | Datto RMM | Source of discovery / scan agents and endpoint visibility |
| **AT** | Autotask PSA | Project setup, planning, task tracking, and operational coordination |
| **ITG** | IT Glue | Long-term documentation and evidence repository |
| **varied** | Mixed / engineer-led | Manual, collaborative, or tool-specific work outside a single platform |

---

## At-a-glance phase map

| Phase | Name | Primary outcome |
|---|---|---|
| **Phase 1** | Prospect & Proposal | Qualified opportunity, scoped engagement, and gap assessment proposal sent |
| **Phase 2** | Gap Assessment | Baseline assessment completed and POA&M generated in RFT |
| **Phase 3** | Remediation Workbook & Post-Assessment | Remediation workbook, scorecard, and remediation proposal produced and reviewed with client |
| **Phase 4** | Acceptance, Project Setup & Docs | Accepted project converted into an active plan with required documentation generated |
| **Phase 5** | Remediation, Evidence & Handoff | Remediation tracked, evidence package completed, presented, and archived in ITG |

---

## Standard engagement storage model

Based on the repo layout provided in `cmmc-projects`, the standard client engagement folder structure is:

- `00-admin`
- `00-archive`
- `01-scoping`
- `02-evidence`
- `03-assessment`
- `04-deliverables`
- `05-poam`

### Working storage guidance

Until a canonical system of record is confirmed, use the following working assumptions:

- `00-admin` — engagement admin, meeting notes, scheduling, internal coordination, intake artifacts
- `01-scoping` — scope definition, environment understanding, client context, boundary/scoping material
- `02-evidence` — evidence collected from client and RCS during assessment and remediation
- `03-assessment` — RFT exports, baseline assessment outputs, worksheets, draft/final POA&M, remediation workbook drafts
- `04-deliverables` — scorecards, proposals, executive/client-ready outputs, final package copies
- `05-poam` — active remediation tracking artifacts and updated remediation workbooks

> Canonical source of truth across repo / URP / AT / ITG is `[CONFIRM w/ Nicholas]`.

---

# Phase 1 — Prospect & Proposal

## Phase objective

Qualify the client need, establish the engagement scope, and generate the gap assessment proposal without changing the authoritative sequence.

## Phase deliverables

- Intake and discovery information
- Initial scope/context notes
- Gap assessment proposal

---

### Step 1 — Initial prospect / compliance guideline information
- **Phase:** 1
- **Owner / who does it:** PM with CM support `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** A prospect inquiry or internal sales handoff indicates a client is seeking CMMC assistance.
- **Inputs needed first:** Prospect contact information, known compliance driver, known contract/regulatory context, any initial client notes.
- **Tool(s):** URP `[exact feature name CONFIRM w/ Nicholas]`; varied for intake notes
- **What to do (actions):**
  1. Capture the initial prospect details, including legal entity name, primary contacts, industry context, and why the client is pursuing CMMC.
  2. Record known compliance guideline information, including whether the client believes the engagement is tied to FCI, CUI, customer contract flow-downs, or another compliance requirement.
  3. Note any known target level, desired timeline, and urgency drivers.
  4. Create or prepare the internal engagement record so later artifacts have a consistent naming and storage location.
- **Output / artifact produced:** Initial prospect intake record and compliance context notes
- **Where it's stored:** `00-admin/` and/or URP intake record `[CONFIRM canonical home w/ Nicholas]`
- **Handoff / gate to next step:** Prospect information is complete enough to schedule and run the compliance proposal intake meeting.
- **Done when (definition of done):** The PM can explain who the prospect is, why they are seeking CMMC support, and what needs to be clarified in discovery.
- **Notes / common pitfalls:** Do not assume the client knows whether they are in scope for Level 1 or Level 2; capture what they say and validate later.

---

### Step 2 — Compliance Proposal intake meeting
- **Phase:** 1
- **Owner / who does it:** PM and CM `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Initial prospect information has been captured and a discovery meeting is scheduled.
- **Inputs needed first:** Initial intake notes, meeting invite, prospect stakeholder list, preliminary scoping questions.
- **Tool(s):** URP `[exact intake/discovery feature name CONFIRM w/ Nicholas]`; varied for meeting notes
- **What to do (actions):**
  1. Run the discovery meeting with the client to identify business drivers, expected compliance target, in-scope operations, known systems, and current documentation maturity.
  2. Complete the intake form or equivalent structured notes during or immediately after the meeting.
  3. Identify what the client already has available, such as inventories, policies, diagrams, MSP documentation, or prior assessments.
  4. Clarify whether the requested engagement is limited to a gap assessment or expected to continue into remediation and evidence packaging.
  5. Document unresolved scoping questions that must be answered before final proposal generation.
- **Output / artifact produced:** Completed discovery/intake notes and scoping inputs for proposal generation
- **Where it's stored:** `00-admin/` and `01-scoping/`; URP intake/discovery record `[CONFIRM]`
- **Handoff / gate to next step:** Intake data is complete enough to define the proposed scope and prepare a gap assessment proposal.
- **Done when (definition of done):** Discovery notes clearly document client need, likely scope, expected deliverables, and open questions.
- **Notes / common pitfalls:** Missing stakeholders at this stage can cause scope rework later; note decision-makers and technical contacts separately.

---

### Step 3 — Gap Assessment Proposal generated
- **Phase:** 1
- **Owner / who does it:** PM with CM and internal approver support `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Discovery and intake information is complete enough to define the proposed gap assessment scope.
- **Inputs needed first:** Discovery notes, client context, pricing assumptions, proposed scope, proposal criteria, pricing references.
- **Tool(s):** URP `[exact proposal feature name CONFIRM w/ Nicholas]`
- **What to do (actions):**
  1. Translate discovery findings into a proposed gap assessment scope, including target framework, likely boundary, expected client participation, and anticipated outputs.
  2. Apply the relevant pricing and proposal criteria to generate the gap assessment proposal.
  3. Review the proposal internally for scope alignment, commercial accuracy, and delivery feasibility.
  4. Send the proposal to the prospect and record the send date, version, and next follow-up action.
- **Output / artifact produced:** Gap assessment proposal
- **Where it's stored:** `04-deliverables/` and URP `[CONFIRM]`
- **Handoff / gate to next step:** Proposal has been sent to the prospect; engagement moves forward when the proposal is accepted or otherwise authorized to begin.
- **Done when (definition of done):** A client-ready gap assessment proposal has been issued and logged.
- **Notes / common pitfalls:** Keep proposal scope aligned to the actual gap assessment phase; do not imply remediation is included unless explicitly scoped.

---

# Phase 2 — Gap Assessment

## Phase objective

Perform baseline discovery and assessment activities in RFT, review the results, and produce worksheets and a POA&M.

## Phase deliverables

- RFT discovery/baseline data
- Requirements and controls assessment entries
- Technical review notes
- Worksheets
- POA&M

---

### Step 4 — RFT discovery / scan agents from RMM
- **Phase:** 2
- **Owner / who does it:** Assigning Engineer with PM coordination `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** The gap assessment proposal is accepted and the engagement is authorized to begin.
- **Inputs needed first:** Client authorization, target tenant/site/account in RFT, access to RMM, identified in-scope endpoints/systems, client technical contact.
- **Tool(s):** RFT; RMM
- **What to do (actions):**
  1. Confirm the client assessment instance or organization exists in RFT and matches the engagement naming convention.
  2. Use RMM as the source for discovery / scan agent deployment or data collection as applicable to the engagement.
  3. Validate that the expected assets are reporting and that the discovery data reflects the intended environment scope.
  4. Record any obvious coverage gaps, inaccessible systems, or excluded assets that could affect the baseline.
- **Output / artifact produced:** Populated discovery/baseline data set in RFT; scan coverage notes
- **Where it's stored:** RFT as system of work; supporting notes in `01-scoping/` or `03-assessment/`
- **Handoff / gate to next step:** Sufficient discovery data is available to run the Rapid Baseline Assessment.
- **Done when (definition of done):** RFT contains usable discovery data for the in-scope environment, and known scan limitations are documented.
- **Notes / common pitfalls:** An incomplete scan can create false gaps; document exclusions and missing agents before interpreting results.

---

### Step 5 — RFT Rapid Baseline Assessment
- **Phase:** 2
- **Owner / who does it:** CM and/or Assigning Engineer `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Discovery data has populated in RFT.
- **Inputs needed first:** RFT discovery data, engagement scope, framework selection, client clarification items, baseline assessment template/settings `[CONFIRM]`
- **Tool(s):** RFT
- **What to do (actions):**
  1. Run or complete the Rapid Baseline Assessment in RFT using the agreed engagement scope.
  2. Review the initial findings for obvious mismatches, missing context, or items requiring clarification.
  3. If needed, hold an optional clarification meeting with the client to resolve ambiguities in ownership, implementation status, or environment design.
  4. Document assumptions or exceptions that will affect downstream control interpretation.
- **Output / artifact produced:** Completed or substantially completed RFT Rapid Baseline Assessment
- **Where it's stored:** RFT; supporting notes in `03-assessment/`
- **Handoff / gate to next step:** Baseline findings are stable enough to transfer into requirements and controls assessments.
- **Done when (definition of done):** The baseline assessment accurately reflects the environment to the extent possible and unresolved issues are documented.
- **Notes / common pitfalls:** Do not treat auto-discovered data as complete evidence on its own; client clarification is often required.

---

### Step 6 — Transfer results to Reqs & Controls assessments
- **Phase:** 2
- **Owner / who does it:** CM / Assigning Engineer `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** The Rapid Baseline Assessment is complete enough to map findings into the formal assessment structure.
- **Inputs needed first:** Completed RFT baseline results, selected compliance framework, client clarifications, scope assumptions.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Transfer or map the baseline assessment results into the requirements and controls assessment area in RFT.
  2. Review the mapped results for alignment to the intended framework and engagement scope.
  3. Flag controls or requirements that need manual adjustment, narrative context, or evidence supplementation.
- **Output / artifact produced:** Updated requirements and controls assessment records in RFT
- **Where it's stored:** RFT
- **Handoff / gate to next step:** Requirements and controls results are ready for technical review.
- **Done when (definition of done):** RFT reflects baseline findings in the requirements/control structure that will drive worksheets and POA&M generation.
- **Notes / common pitfalls:** Incorrect scope mapping here will carry into every downstream artifact.

---

### Step 7 — Technical Review
- **Phase:** 2
- **Owner / who does it:** Assigning Engineer with CM review `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Requirements and controls assessment entries are populated in RFT.
- **Inputs needed first:** RFT control assessment results, scan coverage notes, client technical clarifications, any known compensating context.
- **Tool(s):** RFT; varied
- **What to do (actions):**
  1. Review findings for technical accuracy, duplicates, false positives, and scope issues.
  2. Confirm that technical gaps reflect actual remediation needs versus missing evidence or incomplete discovery.
  3. Add reviewer notes where technical interpretation or sequencing will matter later in remediation planning.
  4. Escalate uncertain findings for internal review before generating client-facing artifacts.
- **Output / artifact produced:** Reviewed assessment findings with technical notes and corrected issues
- **Where it's stored:** RFT and supporting notes in `03-assessment/`
- **Handoff / gate to next step:** Findings are accurate enough to generate worksheets.
- **Done when (definition of done):** Technical review has been completed and any material inaccuracies have been corrected or flagged.
- **Notes / common pitfalls:** If false positives are not cleaned up here, the workbook and proposal will be inflated.

---

### Step 8 — Generate Worksheets
- **Phase:** 2
- **Owner / who does it:** CM / PM / Automation `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Technical review is complete.
- **Inputs needed first:** Finalized RFT assessment results after review.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Generate the worksheet output from the reviewed RFT assessment.
  2. Validate that the worksheet content aligns with the reviewed findings and includes the expected requirement/control detail.
  3. Save the exported artifact using the standard client naming convention and versioning practice.
- **Output / artifact produced:** RFT worksheet export
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Worksheet export is available and validated for POA&M generation.
- **Done when (definition of done):** A usable worksheet file has been generated and saved to the engagement folder.
- **Notes / common pitfalls:** Keep draft and final versions clearly labeled to avoid feeding outdated files into the next phase.

---

### Step 9 — Generate POA&M
- **Phase:** 2
- **Owner / who does it:** CM / PM / Automation `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Worksheet generation is complete and reviewed.
- **Inputs needed first:** Reviewed RFT findings, generated worksheet, assessment context, any internal notes needed for remediation planning.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Generate the POA&M from the reviewed assessment results.
  2. Review the POA&M for completeness, item quality, and consistency with the technical review.
  3. Confirm that remediation items are specific enough to be converted into a remediation workbook in the next phase.
- **Output / artifact produced:** POA&M export
- **Where it's stored:** `03-assessment/` and/or `05-poam/` depending on working state `[CONFIRM standard w/ Nicholas]`
- **Handoff / gate to next step:** A validated POA&M is available for workbook generation.
- **Done when (definition of done):** The POA&M accurately represents the gap assessment findings and is ready for post-assessment planning.
- **Notes / common pitfalls:** Do not proceed with a POA&M that still contains unresolved scope errors or duplicate items.

---

# Phase 3 — Remediation Workbook & Post-Assessment

## Phase objective

Convert the assessment outputs into the working remediation workbook, review it with the client, and generate the scorecard and remediation proposal.

## Phase deliverables

- Remediation workbook
- Updated workbook with responsibilities
- Compliance scorecard
- Remediation proposal
- Proposal sent for acceptance

---

### Step 10 — Generate Remediation Workbook
- **Phase:** 3
- **Owner / who does it:** PM / CM / URP automation `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** The POA&M from Phase 2 is finalized for planning use.
- **Inputs needed first:** RFT POA&M, worksheet output, any workbook generation template or process, client naming convention.
- **Tool(s):** URP `[exact workbook generation feature name CONFIRM w/ Nicholas]`
- **What to do (actions):**
  1. Feed the RFT POA&M into the workbook generation process in URP.
  2. Generate the initial remediation workbook and validate that all expected items were carried over.
  3. Pre-annotate the workbook for the client meeting, including preliminary notes on likely responsibility splits, sequencing, and discussion items.
  4. Save a draft version for internal review before sharing with the client.
- **Output / artifact produced:** Draft Remediation Workbook
- **Where it's stored:** `03-assessment/` for draft working copy; URP `[CONFIRM]`
- **Handoff / gate to next step:** Workbook is ready for the post-assessment client meeting.
- **Done when (definition of done):** A draft remediation workbook exists, is internally reviewed, and is annotated for discussion.
- **Notes / common pitfalls:** Verify item counts and workbook structure before meeting with the client to avoid discussing incomplete outputs.

---

### Step 11 — Gap Assessment post-meeting with client
- **Phase:** 3
- **Owner / who does it:** PM and CM, with client stakeholders
- **Starts when (trigger):** The draft remediation workbook is ready for review.
- **Inputs needed first:** Draft remediation workbook, POA&M context, reviewed assessment findings, client attendee list.
- **Tool(s):** URP output; varied for meeting delivery
- **What to do (actions):**
  1. Walk the client through the assessment findings, major gaps, and expected remediation themes.
  2. Review workbook items with the client and update roles and responsibilities for each action item where possible.
  3. Clarify which items are RCS-led, client-led, or joint responsibility.
  4. Capture client constraints, timing considerations, and any disagreements or follow-up items.
- **Output / artifact produced:** Updated remediation workbook with role/responsibility assignments and meeting notes
- **Where it's stored:** `03-assessment/` and/or `05-poam/`; meeting notes in `00-admin/`
- **Handoff / gate to next step:** Workbook responsibilities are sufficiently updated to drive scorecard and proposal generation.
- **Done when (definition of done):** The workbook reflects the latest client discussion and includes responsibility assignments or documented follow-up items.
- **Notes / common pitfalls:** If ownership is not clarified here, remediation planning and proposal generation will be less accurate.

---

### Step 12 — Feed workbook → Compliance Scorecard
- **Phase:** 3
- **Owner / who does it:** PM / CM / URP automation `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** The remediation workbook has been updated following the client post-meeting.
- **Inputs needed first:** Updated remediation workbook, any required client profile/context data, scorecard criteria.
- **Tool(s):** URP `[exact scorecard feature name CONFIRM w/ Nicholas]`
- **What to do (actions):**
  1. Input the updated workbook into the scorecard generation process.
  2. Validate that the scorecard reflects the current assessment state and any documented strategic context collected during the engagement.
  3. Review the scorecard for presentation quality and internal consistency before release or proposal packaging.
- **Output / artifact produced:** Compliance Scorecard
- **Where it's stored:** `04-deliverables/` and URP
- **Handoff / gate to next step:** Scorecard is complete and available to support remediation proposal generation and client communication.
- **Done when (definition of done):** A client-ready or near-client-ready scorecard has been generated and validated.
- **Notes / common pitfalls:** Do not generate the final scorecard from an outdated workbook version.

---

### Step 13 — Feed workbook → Remediation Proposal
- **Phase:** 3
- **Owner / who does it:** PM with CM support `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Updated workbook and scorecard inputs are available.
- **Inputs needed first:** Updated remediation workbook, proposal criteria, pricing assumptions, scope assumptions, internal review requirements.
- **Tool(s):** URP `[exact remediation proposal feature name CONFIRM w/ Nicholas]`
- **What to do (actions):**
  1. Adjust the proposal criteria to reflect the current workbook scope, ownership split, and expected remediation effort.
  2. Generate the remediation proposal using the workbook as the primary driver.
  3. Review the proposal internally for scope accuracy, commercial accuracy, and consistency with the scorecard and workbook.
- **Output / artifact produced:** Remediation proposal
- **Where it's stored:** `04-deliverables/` and URP
- **Handoff / gate to next step:** Proposal is approved internally and ready to send to the client.
- **Done when (definition of done):** The remediation proposal is finalized for client delivery.
- **Notes / common pitfalls:** Ensure the proposal scope matches the agreed ownership split from the post-meeting.

---

### Step 14 — Send proposal to client for acceptance
- **Phase:** 3
- **Owner / who does it:** PM
- **Starts when (trigger):** Remediation proposal has passed internal review.
- **Inputs needed first:** Final remediation proposal, client decision-maker contact(s), any transmittal notes, internal follow-up plan.
- **Tool(s):** URP and/or standard client communication method `[CONFIRM]`
- **What to do (actions):**
  1. Send the remediation proposal to the client for review and acceptance.
  2. Clearly communicate what is included, what assumptions were used, and what acceptance triggers next.
  3. Record the send date, expected response date, and follow-up cadence.
  4. Track questions, redlines, or requested scope changes through to resolution.
- **Output / artifact produced:** Client-issued remediation proposal and acceptance tracking record
- **Where it's stored:** `04-deliverables/`; acceptance tracking in `00-admin/` and/or AT `[CONFIRM]`
- **Handoff / gate to next step:** Client accepts the remediation proposal or otherwise authorizes project setup.
- **Done when (definition of done):** The proposal has been delivered and is actively tracked to acceptance or revision.
- **Notes / common pitfalls:** Proposal acceptance is a formal gate; do not start project setup without explicit authorization.

---

# Phase 4 — Acceptance, Project Setup & Docs

## Phase objective

Convert an accepted remediation proposal into an active project, generate the required documentation package, and begin technical remediation execution.

## Phase deliverables

- Project plan in AT
- Timeline and responsibilities
- Required documentation package
- Active remediation workstream

---

### Step 15 — Set up project plan
- **Phase:** 4
- **Owner / who does it:** PM
- **Starts when (trigger):** The remediation proposal is accepted.
- **Inputs needed first:** Accepted proposal, updated remediation workbook, known timeline constraints, client contacts, delivery assumptions.
- **Tool(s):** AT; URP for reference
- **What to do (actions):**
  1. Create the engagement project in AT using the accepted scope and standard project structure.
  2. Build the timeline, milestones, task groups, and dependencies based on the workbook and expected documentation requirements.
  3. Assign internal roles and document client responsibilities where known.
  4. Schedule kickoff and working sessions needed for remediation and evidence collection.
- **Output / artifact produced:** Active project plan with timeline and role assignments
- **Where it's stored:** AT; supporting exports or notes in `00-admin/`
- **Handoff / gate to next step:** Project plan is active and the team has enough structure to begin document generation and remediation coordination.
- **Done when (definition of done):** The project is created, scheduled, assigned, and ready for execution.
- **Notes / common pitfalls:** If workbook tasks are not translated into the plan, remediation progress will be difficult to manage.

---

### Step 16 — Generate required docs
- **Phase:** 4
- **Owner / who does it:** PM / CM / URP automation `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Project plan is established and required document generation can begin.
- **Inputs needed first:** Accepted scope, client intake details, updated client info, required-docs manifest, policy template set, workbook/document register inputs.
- **Tool(s):** URP `[exact required-docs / policy-template feature names CONFIRM w/ Nicholas]`; ITG; RFT
- **What to do (actions):**
  1. Generate the required documentation set using the available policy templates and document-generation process.
  2. Populate generated documents with updated client information and scope-specific details.
  3. Review the generated documents for completeness, naming consistency, and suitability for client review.
  4. Upload or stage the initial documentation/evidence package in the appropriate working repositories for use during remediation.
- **Output / artifact produced:** Required documentation package, including policy templates and document-request outputs
- **Where it's stored:** `02-evidence/`, `04-deliverables/`, and uploaded evidence working locations in ITG/RFT `[CONFIRM exact standard]`
- **Handoff / gate to next step:** Required documents are generated and available for remediation execution and evidence collection.
- **Done when (definition of done):** The initial required document package has been generated, reviewed, and stored in the engagement workspaces.
- **Notes / common pitfalls:** Generated templates still require review; do not assume auto-filled content is client-ready without validation.

---

### Step 17 — Complete technical remediation tasks
- **Phase:** 4
- **Owner / who does it:** Assigning Engineer; PM tracks progress
- **Starts when (trigger):** Project plan is active and remediation tasks are assigned.
- **Inputs needed first:** Updated remediation workbook, project plan, technical access, client scheduling, required documentation package.
- **Tool(s):** varied
- **What to do (actions):**
  1. Execute the assigned technical remediation tasks in the order needed to close or reduce the identified gaps.
  2. Capture implementation details, screenshots, configuration exports, and related evidence as remediation is completed.
  3. Coordinate with the client for any client-owned tasks or approvals required to implement changes.
  4. Report progress and blockers back to the PM for plan updates and escalation as needed.
- **Output / artifact produced:** Completed remediation work items and associated technical evidence
- **Where it's stored:** Evidence in `02-evidence/`; tracking in `05-poam/` and AT
- **Handoff / gate to next step:** Enough remediation progress exists to update the workbook and reassess status in Phase 5.
- **Done when (definition of done):** Assigned remediation tasks are completed or statused with evidence and next actions.
- **Notes / common pitfalls:** Changes may affect production systems; schedule maintenance windows and preserve rollback information where appropriate.

---

# Phase 5 — Remediation, Evidence & Handoff

## Phase objective

Update the remediation record, refresh assessment status, assemble the complete evidence package, present the package, and archive the final set in ITG.

## Phase deliverables

- Updated remediation workbook
- Updated RFT assessment state
- Full evidence package
- Client presentation package
- ITG upload / final handoff

---

### Step 18 — Update Remediation Workbook
- **Phase:** 5
- **Owner / who does it:** PM with Assigning Engineer and CM input `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Technical remediation work has progressed and status updates are available.
- **Inputs needed first:** Current workbook, remediation status notes, collected evidence, task completion updates.
- **Tool(s):** URP output workbook; varied
- **What to do (actions):**
  1. Update each workbook item to reflect current remediation status, evidence availability, and outstanding tasks.
  2. Revise owners, dates, or notes where implementation reality differs from the original plan.
  3. Mark items that are ready for reassessment or evidence packaging.
- **Output / artifact produced:** Updated remediation workbook
- **Where it's stored:** `05-poam/` as working remediation tracker; copy in `03-assessment/` if needed for continuity
- **Handoff / gate to next step:** Workbook status accurately reflects current remediation progress and can be used to update RFT.
- **Done when (definition of done):** The workbook is current enough to serve as the single working reference for remaining gaps and completed actions.
- **Notes / common pitfalls:** If evidence is completed but workbook status is stale, final packaging will be inconsistent.

---

### Step 19 — Update RFT Baseline Assessment
- **Phase:** 5
- **Owner / who does it:** CM / Assigning Engineer `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Workbook updates indicate remediation items have changed assessment status.
- **Inputs needed first:** Updated remediation workbook, supporting evidence, original RFT assessment records.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Revisit the affected baseline and requirements/control assessment items in RFT.
  2. Transfer updated remediation outcomes into the RFT assessment so the platform reflects the current state.
  3. Verify that the updated statuses align with available evidence and internal review conclusions.
- **Output / artifact produced:** Updated RFT baseline / requirements-control assessment state
- **Where it's stored:** RFT
- **Handoff / gate to next step:** RFT and the workbook are aligned closely enough to support final evidence packaging and presentation.
- **Done when (definition of done):** RFT reflects the current post-remediation state for the relevant items.
- **Notes / common pitfalls:** Do not mark items improved in RFT without supporting evidence or documented rationale.

---

### Step 20 — Gather full evidence package
- **Phase:** 5
- **Owner / who does it:** PM coordinates; Assigning Engineer and client provide inputs `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Remediation status and RFT updates are sufficiently mature for final packaging.
- **Inputs needed first:** Updated workbook, updated RFT status, policies, technical evidence, documentation artifacts, client-provided materials.
- **Tool(s):** varied; RFT; ITG
- **What to do (actions):**
  1. Collect the full package of policy evidence, technical control evidence, and supporting documentation required for the engagement deliverables.
  2. Organize the evidence according to the engagement structure so each item can be traced to the relevant workbook or assessment line item.
  3. Review the package for completeness, readability, naming consistency, and missing artifacts.
  4. Record any remaining evidence gaps and assign follow-up actions before client presentation.
- **Output / artifact produced:** Full evidence package
- **Where it's stored:** `02-evidence/` as working evidence repository; final outputs may also be staged in `04-deliverables/`
- **Handoff / gate to next step:** Evidence package is complete enough for client presentation.
- **Done when (definition of done):** The engagement team can present a coherent evidence package tied back to the assessment and remediation record.
- **Notes / common pitfalls:** Evidence should be organized and attributable; unstructured file dumps make final handoff difficult.

---

### Step 21 — Present package to client
- **Phase:** 5
- **Owner / who does it:** PM and CM `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Full evidence package and presentation materials are ready.
- **Inputs needed first:** Evidence package, executive summary or findings summary, scorecard, technical report or operational feasibility output `[CONFIRM exact deliverables]`
- **Tool(s):** URP outputs; varied for presentation delivery
- **What to do (actions):**
  1. Present the completed package to the client, including findings, remediation status, and the supporting evidence set.
  2. Review any executive summary, engagement findings, and technical report outputs included in the final deliverable package.
  3. Capture client questions, requested revisions, or acceptance comments.
  4. Document any agreed follow-up items, including optional support such as SPRS filing or vendor submission if applicable.
- **Output / artifact produced:** Client presentation of final package; client feedback and acceptance notes
- **Where it's stored:** `04-deliverables/` and `00-admin/` for meeting notes
- **Handoff / gate to next step:** Client presentation is complete and final package contents are ready for archival upload to ITG.
- **Done when (definition of done):** The client has been walked through the package and any final revisions or handoff expectations are documented.
- **Notes / common pitfalls:** Confirm whether client sign-off is required here before final archival. `[CONFIRM w/ Nicholas]`

---

### Step 22 — Upload full package to ITG
- **Phase:** 5
- **Owner / who does it:** PM or documentation owner `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Final package has been presented and any immediate revisions are complete.
- **Inputs needed first:** Final evidence package, final deliverables, client naming/location standard in ITG.
- **Tool(s):** ITG
- **What to do (actions):**
  1. Upload the finalized package to ITG using the agreed documentation structure and naming standard.
  2. Confirm that the uploaded package includes the final deliverables, evidence set, and any key remediation tracking artifacts that should persist in the client record.
  3. Verify access and readability for internal users who will need the package later.
  4. Close or transition the engagement record according to internal process.
- **Output / artifact produced:** Final engagement package archived in ITG
- **Where it's stored:** ITG; supporting repo copies remain in `02-evidence/`, `04-deliverables/`, and `05-poam/` as applicable
- **Handoff / gate to next step:** Engagement handoff is complete; any ongoing managed remediation or annual review work is transitioned separately.
- **Done when (definition of done):** The final package is uploaded to ITG, accessible, and tied to the completed engagement.
- **Notes / common pitfalls:** Ensure the final package version uploaded to ITG matches the version presented to the client.

---

# Appendix A — PM checklist version

## Phase 1 — Prospect & Proposal
- [ ] Step 1 — Initial prospect / compliance guideline information
- [ ] Step 2 — Compliance Proposal intake meeting
- [ ] Step 3 — Gap Assessment Proposal generated

## Phase 2 — Gap Assessment
- [ ] Step 4 — RFT discovery / scan agents from RMM
- [ ] Step 5 — RFT Rapid Baseline Assessment
- [ ] Step 6 — Transfer results to Reqs & Controls assessments
- [ ] Step 7 — Technical Review
- [ ] Step 8 — Generate Worksheets
- [ ] Step 9 — Generate POA&M

## Phase 3 — Remediation Workbook & Post-Assessment
- [ ] Step 10 — Generate Remediation Workbook
- [ ] Step 11 — Gap Assessment post-meeting with client
- [ ] Step 12 — Feed workbook → Compliance Scorecard
- [ ] Step 13 — Feed workbook → Remediation Proposal
- [ ] Step 14 — Send proposal to client for acceptance

## Phase 4 — Acceptance, Project Setup & Docs
- [ ] Step 15 — Set up project plan
- [ ] Step 16 — Generate required docs
- [ ] Step 17 — Complete technical remediation tasks

## Phase 5 — Remediation, Evidence & Handoff
- [ ] Step 18 — Update Remediation Workbook
- [ ] Step 19 — Update RFT Baseline Assessment
- [ ] Step 20 — Gather full evidence package
- [ ] Step 21 — Present package to client
- [ ] Step 22 — Upload full package to ITG

---

# Appendix B — CMMC glossary

- **CMMC** — Cybersecurity Maturity Model Certification.
- **FCI** — Federal Contract Information.
- **CUI** — Controlled Unclassified Information.
- **POA&M** — Plan of Action and Milestones; a tracked list of gaps, remediation items, owners, and target actions.
- **RBA** — Rapid Baseline Assessment in RFT; used to establish an initial posture view. `[term usage based on workflow materials; exact expansion CONFIRM if needed]`
- **SSP** — System Security Plan.
- **Control family** — Grouping of related security practices or requirements.
- **Evidence package** — The organized set of policy, technical, and procedural artifacts used to support the engagement findings and client handoff.
- **Compliance Scorecard** — RCS/URP-generated summary artifact showing client posture and remediation context. `[CONFIRM official output name]`
- **Remediation Workbook** — The central working artifact that converts assessment gaps into tracked remediation actions, responsibilities, and downstream deliverables.

---

# Open Questions

## Seed questions from assignment brief
1. **Who owns each step?** Is there a formal role split between PM, CM, assigning engineer, automation, and client? Is there a RACI to apply?
2. **What are the exact URP feature names** for:
   - Remediation Workbook generation
   - Compliance Scorecard
   - Remediation Proposal
   - required-docs / policy-template generation
3. **Which steps require client sign-off** before proceeding, besides proposal acceptance?
4. **Are there target timelines or SLAs** by phase or step that should be added for PM expectation-setting?
5. **What is the canonical system of record** for an active engagement: repo folder, URP, Autotask, IT Glue, or a defined mix?

## Additional questions identified during drafting
6. Should **Step 3** require internal approval before sending the gap assessment proposal? If so, who approves it?
7. In **Step 4**, what is the exact expected method for using RMM as the source for RFT discovery / scan agent deployment?
8. In **Step 5**, is the optional clarification meeting with the client a standard checkpoint or only used by exception?
9. In **Step 8** and **Step 9**, should worksheets and POA&M be stored primarily in `03-assessment/`, or is POA&M expected to move immediately to `05-poam/`?
10. For **Step 10**, what is the exact URP process or automation path used to generate the Remediation Workbook from RFT outputs?
11. For **Step 11**, is there a required agenda or standard client-facing deck/format for the post-assessment meeting?
12. For **Step 12**, what data beyond the workbook feeds the Compliance Scorecard, if any?
13. For **Step 13**, what proposal criteria are typically adjusted before generating the remediation proposal?
14. For **Step 15**, is there a standard Autotask project template for CMMC engagements?
15. For **Step 16**, what is the authoritative required-docs manifest, and where is it maintained?
16. For **Step 16**, should generated documentation first be reviewed internally before being shared with the client every time?
17. For **Step 17**, how should PMs distinguish between remediation complete, evidence complete, and validation complete?
18. For **Step 19**, is there a required internal review before statuses are updated in RFT post-remediation?
19. For **Step 21**, what are the standard final deliverables included in the client presentation package?
20. For **Step 21**, is formal client acceptance/sign-off required before upload to ITG?
21. Are the **optional activities** from the workflow deck — SPRS filing support and vendor submission support — part of the standard SOP, or should they be documented as separate optional procedures?
22. The deck references **“one source of truth”** anchored on the Remediation Workbook. Should this SOP explicitly define the workbook as the operational source of truth during active remediation?

---

## Revision notes

- Drafted from assignment brief, parsed workflow deck text, and provided folder structure.
- No client-specific names, IP addresses, or engagement details included.
- Any uncertain ownership, feature names, or gating is marked `[CONFIRM w/ Nicholas]`.
