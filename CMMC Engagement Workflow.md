# CMMC Engagement Process

## Purpose

This document converts the RCS CMMC Engagement Workflow from a high-level slide deck into an actionable, step-by-step internal process document. It is intended to help any RCS project manager run a CMMC engagement consistently from initial prospect intake through remediation, evidence assembly, and final handoff.

## Intended audience

RCS project managers

## How to use this document

Use this in sequence. Follow the phases and steps in the order shown. For each step, confirm the trigger, gather the listed inputs, complete the actions, store the artifact in the expected system or folder, and verify the handoff criteria before moving forward. 

---

## Roles glossary

- **CM (Compliance Manager)** — oversight of the end-to-end project, scoping, and all client interaction (proposals, responsibility matrix). Owns the client-facing and compliance-governance side of the engagement.
- **PM (Project Manager)** — management of client information gathering and remediation tasks.
- **Client** — provides scope inputs, documents, access, approvals, and engagement participation.

---

## Tools legend

| Code | Full name | Use in workflow |
|---|---|---|
| **URP** | Unified Reporting Platform (RCS Report Publisher) | Reporting/deliverable spine. **Compliance category** holds the CMMC-relevant reports: Compliance Guidelines · Compliance Proposal · Remediation Workbook · Compliance Scorecard · Compliance Document Pack · Requirements Matrix |
| **RFT** | RapidFire Tools (Compliance Manager GRC) | Assessment platform for baseline discovery, requirements/control assessments, worksheets, and POA&M |
| **RMM** | Datto RMM | Source of discovery / scan agents and endpoint visibility |
| **AT** | Autotask PSA | Project setup, planning, task tracking, and operational coordination |
| **ITG** | IT Glue | Long-term documentation and evidence repository |
| **varied** | Mixed / engineer-led | Manual, collaborative, or tool-specific work outside a single platform |

---

## Folder storage rules 

- **`00-admin/`** — important administrative records only 
- **`00-archive/`** — superseded or outdated versions of any document. **All archived files must follow the labeling standard stated below**
- **`01-scoping/`** — scoping artifacts
- **`02-evidence/`** — raw evidence and exports in subfolders
- **`03-assessment/`** — RFT outputs, POA&M, Remediation Workbook, Compliance Scorecard, Remediation Proposal.
- **`04-deliverables/`** — Compliance Document Pack (manifest + combined master + corpus),  final client deliverables, and the final deliverable zip. The zip is the **full package to deliver** 
- **`05-poam/`** — internal pre-assessment remediation tracking only 

### `00-archive/` labeling standard

**Format:**
YYYY.MM.DD-<TYPE>-<descriptor>[-<reason>].<ext>

- **`YYYY.MM.DD`** — date the file was **archived**
- **`<TYPE>`** — type of change or update
- **`<descriptor>`** — short, lowercase, hyphen-separated, no spaces.
- Preserve the **original extension**

---



## At-a-Glance Phase Map

- **Phase 1 — Prospect & Proposal:** qualify the prospect, gather intake data, and send the gap-assessment proposal.
- **Phase 2 — Gap Assessment:** run discovery, baseline the environment, review findings, and generate worksheets and the POA&M.
- **Phase 3 — Remediation Workbook & Post-Assessment:** turn the POA&M into the Remediation Workbook, review it with the client, and generate the scorecard and remediation proposal.
- **Phase 4 — Acceptance, Project Setup & Docs:** once accepted, stand up the project plan and generate the required document set and evidence scaffolding.
- **Phase 5 — Remediation, Evidence & Handoff:** complete remediation tracking, update assessments, assemble the evidence package, present it, and upload the final package to ITG.
---

## Phase 1 — Prospect & Proposal
**Objective:** Qualify compliance requirements, define environmental scope, and generate the Gap Assessment Proposal.

### Step 1 — Initial prospect / compliance guideline information
- **Phase:** 1
- **Owner / who does it:** CM
- **Starts when (trigger):** A prospect inquiry or internal handoff indicates a client is seeking CMMC assistance.
- **Inputs needed first:** Prospect contact information, known compliance driver, and any initial client notes.
- **Tool(s):** URP - Compliance Guidelines
- **What to do (actions):**
  1. Capture the prospect's legal entity name, primary contacts, and high-level business context.
  2. Record the stated compliance need, including any known reference to CMMC level, FCI, CUI, or contract flow-down requirements.
  3. Note any known timing drivers, scoping constraints, or immediate questions to resolve during discovery.
- **Output / artifact produced:** Initial prospect intake record and compliance context notes.
- **Where it's stored:** URP. Important records to `00-admin/`
- **Handoff / gate to next step:** Intake information is complete enough to schedule the discovery meeting.
- **Done when (definition of done):** The prospect record exists and includes enough context to run the intake meeting.


### Step 2 — Compliance Proposal intake meeting
- **Phase:** 1
- **Owner / who does it:** CM
- **Starts when (trigger):** The initial prospect intake is captured and the discovery meeting is scheduled.
- **Inputs needed first:** Initial prospect record, scoping questions, and meeting attendees from the client side.
- **Tool(s):** URP 
- **What to do (actions):**
  1. Meet with the client to identify business drivers, expected compliance target, and the high-level scope of the environment.
  2. Capture discovery notes on in-scope users, locations, systems, services, and current documentation maturity.
  3. Record open scoping questions, dependencies, and any information still needed before proposal generation.
- **Output / artifact produced:** Discovery notes and scoping inputs for proposal generation.
- **Where it's stored:** `01-scoping/`
- **Handoff / gate to next step:** Discovery details are complete enough to define the gap assessment scope and prepare pricing/proposal inputs.
- **Done when (definition of done):** Discovery notes clearly document client need, likely scope, and open issues requiring follow-up.


### Step 3 — Gap Assessment Proposal generated
- **Phase:** 1
- **Owner / who does it:** CM 
- **Starts when (trigger):** Discovery and scoping notes are complete enough to define the proposed engagement.
- **Inputs needed first:** Discovery notes, proposed scope, and pricing references. 
- **Tool(s):** URP - Compliance Proposal 
- **What to do (actions):**
  1. Translate discovery findings into the proposed gap assessment scope.
  2. Apply the approved pricing method to prepare the client proposal.
  3. Review the proposal internally before sending
  4. Send the proposal to the prospect and record the send date and follow-up plan.
- **Output / artifact produced:** Gap Assessment Proposal.
- **Where it's stored:** `04-deliverables/` 
- **Handoff / gate to next step:** Proposal has been sent; the engagement may proceed only after client acceptance
- **Done when (definition of done):** A client-ready gap assessment proposal has been issued and logged.

---

## Phase 2 — Gap Assessment

### Step 4 — RFT discovery / scan agents from RMM
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** The gap-assessment engagement is approved to begin.
- **Inputs needed first:** Client authorization to assess; target environment details; RMM access; device coverage requirements; any client scheduling constraints.
- **Tool(s):** RFT, RMM 
- **What to do (actions):**
  1. Identify the in-scope devices and systems for discovery.
  2. Use RMM to support deployment or activation of the RFT discovery/scan capability.
  3. Run or initiate the discovery/baseline scan.
  4. Confirm that scan results are collected for the intended environment.
- **Output / artifact produced:** RFT discovery/baseline scan data for the engagement.
- **Where it's stored:** Scan in `02-evidence/` and RFT assessment in `03-assessment/`
- **Handoff / gate to next step:** Scan coverage is sufficient to proceed to the baseline assessment.
- **Done when (definition of done):** RFT has collected baseline discovery data for the in-scope environment.

### Step 5 — RFT Rapid Baseline Assessment
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** Discovery/scan data is available in RFT.
- **Inputs needed first:** RFT discovery results; target compliance framework; any client clarification needed on ambiguous findings.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Run or complete the Rapid Baseline Assessment in RFT using the discovery results.
  2. Review initial findings for obvious gaps, missing data, or items needing clarification.
  3. If needed, hold the optional clarification meeting with the client to validate findings or gather missing context.
- **Output / artifact produced:** Completed or updated RFT Rapid Baseline Assessment results.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Baseline findings are ready to be transferred into the requirements and controls assessments.
- **Done when (definition of done):** The Rapid Baseline Assessment is complete enough to drive requirements/control mapping.

### Step 6 — Transfer results to Reqs & Controls assessments
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** Rapid Baseline Assessment findings have been reviewed.
- **Inputs needed first:** RFT baseline assessment results; target requirements/control set; any clarified client responses.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Transfer or map the baseline results into the requirements and controls assessments in RFT.
  2. Verify that the assessment reflects the intended framework and target set.
  3. Review for missing mappings, empty items, or results that need manual follow-up.
- **Output / artifact produced:** Requirements and controls assessment populated from baseline results.
- **Where it's stored:** `03-assessment/` 
- **Handoff / gate to next step:** The requirements/control assessment is populated and ready for technical review.
- **Done when (definition of done):** Results have been transferred and the controls assessment is ready for review.

### Step 7 — Technical Review
- **Phase:** 2
- **Owner / who does it:** CM
- **Starts when (trigger):** Requirements/control assessment has been populated.
- **Inputs needed first:** RFT assessment results; scan findings; any supporting environment evidence; client clarifications if already obtained.
- **Tool(s):** RFT, varied
- **What to do (actions):**
  1. Review the populated findings for technical accuracy and relevance to the engagement scope.
  2. Validate major gaps, identify false positives or unsupported assumptions, and note any items needing follow-up.
  3. Confirm what will carry forward into the worksheets and POA&M.
- **Output / artifact produced:** Reviewed assessment findings ready for worksheet generation.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Findings are validated enough to generate worksheets.
- **Done when (definition of done):** Technical review is complete and the assessment findings are approved for worksheet generation.

### Step 8 — Generate Worksheets
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** Technical review is complete.
- **Inputs needed first:** Reviewed RFT assessment results; confirmed target framework/level.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Generate the assessment worksheets from the reviewed RFT results.
  2. Confirm the worksheet output includes the expected findings and structure for the engagement.
  3. Save or export the worksheet output if needed for downstream use.
- **Output / artifact produced:** RFT worksheets.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Worksheets are available and usable for POA&M generation.
- **Done when (definition of done):** The worksheet output exists and is ready to feed the POA&M step.

### Step 9 — Generate POA&M
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** Worksheets have been generated.
- **Inputs needed first:** RFT worksheets; reviewed assessment findings.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Generate the POA&M from the assessment/worksheet results.
  2. Review the POA&M output for completeness and basic accuracy before handoff.
  3. Save or export the POA&M for use in workbook generation.
- **Output / artifact produced:** POA&M.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** POA&M is available to feed the Remediation Workbook process.
- **Done when (definition of done):** The POA&M has been generated and is ready for Phase 3 use.

---

## Phase 3 — Remediation Workbook & Post-Assessment

### Step 10 — Generate Remediation Workbook
- **Phase:** 3
- **Owner / who does it:** PM
- **Starts when (trigger):** The RFT POA&M is finalized enough to convert into a remediation planning artifact.
- **Inputs needed first:** RFT POAM; any required worksheet input; client identifier/profile details required by the generation process.
- **Tool(s):** URP - Remediation Workbook
- **What to do (actions):**
  1. Feed the RFT POA&M into the Remediation Workbook generation process.
  2. Generate the workbook output.
  3. Annotate or pre-stage the workbook for the client post-assessment meeting.
- **Output / artifact produced:** Remediation Workbook.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Workbook is ready to be reviewed with the client.
- **Done when (definition of done):** A Remediation Workbook exists and is prepared for the client post-assessment meeting.

### Step 11 — Gap Assessment post-meeting with client
- **Phase:** 3
- **Owner / who does it:** CM
- **Starts when (trigger):** The Remediation Workbook has been generated and prepared for discussion.
- **Inputs needed first:** Remediation Workbook; gap-assessment results; proposed action items; meeting agenda.
- **Tool(s):** URP
- **What to do (actions):**
  1. Conduct the post-assessment meeting with the client.
  2. Review the assessment results and proposed remediation activity.
  3. Update roles and responsibilities in the Remediation Workbook based on meeting decisions.
  4. Confirm any client-provided follow-up items or required clarifications.
- **Output / artifact produced:** Updated Remediation Workbook with reviewed roles and responsibilities.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Workbook assignments and remediation assumptions are updated enough to generate downstream outputs.
- **Done when (definition of done):** The post-assessment meeting is complete and the workbook reflects the meeting outcomes.

### Step 12 — Feed workbook → Compliance Scorecard
- **Phase:** 3
- **Owner / who does it:** PM
- **Starts when (trigger):** The Remediation Workbook has been updated after the client meeting.
- **Inputs needed first:** Updated Remediation Workbook; client profile details required by scorecard generation.
- **Tool(s):** URP - Compliance Scorecard 
- **What to do (actions):**
  1. Feed the updated workbook into the Compliance Scorecard generation process.
  2. Generate the scorecard output.
  3. Review the scorecard for alignment with the workbook and engagement status.
- **Output / artifact produced:** Compliance Scorecard.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Scorecard is available and the same workbook is ready to feed the remediation proposal.
- **Done when (definition of done):** The Compliance Scorecard is generated and reviewed.

### Step 13 — Feed workbook → Remediation Proposal
- **Phase:** 3
- **Owner / who does it:** CM
- **Starts when (trigger):** The updated workbook is approved for proposal generation.
- **Inputs needed first:** Updated Remediation Workbook; proposal criteria; pricing inputs; approved remediation scope.
- **Tool(s):** URP - Compliance Proposal
- **What to do (actions):**
  1. Feed the updated workbook into the Remediation Proposal generation process.
  2. Adjust proposal criteria as needed for the remediation scope.
  3. Generate the remediation proposal.
  4. Review the proposal for scope, pricing, and consistency with the workbook.
- **Output / artifact produced:** Remediation Proposal.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Remediation proposal is approved internally for delivery to the client.
- **Done when (definition of done):** The remediation proposal is generated and ready to send.

### Step 14 — Send proposal to client for acceptance
- **Phase:** 3
- **Owner / who does it:** CM
- **Starts when (trigger):** The remediation proposal has been generated and internally reviewed.
- **Inputs needed first:** Final remediation proposal; client delivery contact; any approval requirements.
- **Tool(s):** URP
- **What to do (actions):**
  1. Deliver the remediation proposal to the client.
  2. Track proposal status and any client questions or requested revisions.
  3. Record acceptance, rejection, or revision feedback.
- **Output / artifact produced:** Proposal delivery record and client acceptance status.
- **Where it's stored:** `00-admin/`
- **Handoff / gate to next step:** Client accepts the remediation proposal before project setup and remediation delivery begin.
- **Done when (definition of done):** The proposal has been sent and client acceptance status is recorded.

---

## Phase 4 — Acceptance, Project Setup & Docs

### Step 15 — Set up project plan
- **Phase:** 4
- **Owner / who does it:** PM
- **Starts when (trigger):** The client accepts the remediation proposal.
- **Inputs needed first:** Accepted proposal; approved scope; workbook action items; agreed roles and responsibilities; timeline inputs.
- **Tool(s):** AT, URP
- **What to do (actions):**
  1. Create the remediation project in AT.
  2. Build the project plan and timeline from the approved remediation scope and workbook.
  3. Assign roles, responsibilities, and target dates.
  4. Align the project plan with the engagement record and workbook.
- **Output / artifact produced:** Active project plan with timeline and assigned responsibilities.
- **Where it's stored:** AT; `00-admin/`
- **Handoff / gate to next step:** Project plan is active and can support document generation and remediation execution.
- **Done when (definition of done):** The project exists, tasks are defined, and responsibilities/timeline are assigned.

### Step 16 — Generate required docs
- **Phase:** 4
- **Owner / who does it:** CM
- **Starts when (trigger):** The project plan is in place and the engagement can move into document generation.
- **Inputs needed first:** Client profile information; workbook; scope details; required-docs criteria; any available client policies, standards, procedures, or forms.
- **Tool(s):** URP - Compliance Document Pack and Requirements Matrix, ITG, RFT
- **What to do (actions):**
  1. Generate the required document set from URP using the client’s profile and engagement scope.
  2. Update the generated documents with current client information as required.
  3. Produce the document requirements output or tracking artifact.
  4. Upload the generated documentation/evidence package components to the required repository or platforms.
- **Output / artifact produced:** Required document set; document requirements output; initial evidence package components.
- **Where it's stored:** - Document Pack in `04-deliverables/`.
  - Scoping artifacts in `01-scoping/`.
  - Supporting evidence in `02-evidence/`
  - Uploaded copies in ITG/RFT. 
  - Superseded doc versions to `00-archive/`.
- **Handoff / gate to next step:** Required documents are generated and available to support remediation completion.
- **Done when (definition of done):** The required document set is generated, updated for the client, and stored/uploaded where the team expects to use it.

### Step 17 — Complete technical remediation tasks
- **Phase:** 4
- **Owner / who does it:** PM
- **Starts when (trigger):** Project tasks are assigned and required documentation has been generated or identified.
- **Inputs needed first:** Project plan; Remediation Workbook action items; technical findings; client coordination; access needed to implement changes.
- **Tool(s):** varied
- **What to do (actions):**
  1. Execute the approved technical remediation tasks identified in the workbook and project plan.
  2. Track progress against the assigned remediation items.
  3. Collect implementation evidence as remediation tasks are completed.
  4. Prepare completed work for evidence packaging and workbook updates.
- **Output / artifact produced:** Completed technical remediation work and supporting evidence.
- **Where it's stored:** task tracking in AT
  - Implementation evidence in `02-evidence/` 
  - remediation status reflected in the Remediation Workbook in `03-assessment/`
- **Handoff / gate to next step:** Remediation work is complete enough to update the workbook and reassessment artifacts.
- **Done when (definition of done):** Assigned remediation tasks are completed or statused clearly enough to proceed into evidence and reassessment updates.

---

## Phase 5 — Remediation, Evidence & Handoff

### Step 18 — Update Remediation Workbook
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** Technical remediation work has progressed enough to update action-item status.
- **Inputs needed first:** Current Remediation Workbook; completed-task status; implementation evidence; client responses where applicable.
- **Tool(s):** varied
- **What to do (actions):**
  1. Update the workbook to reflect the current status of remediation actions.
  2. Record completed, deferred, or outstanding items as appropriate.
  3. Verify that workbook status aligns with actual remediation progress and collected evidence.
- **Output / artifact produced:** Updated Remediation Workbook.
- **Where it's stored:** `03-assessment/`
- **Handoff / gate to next step:** Workbook status is current enough to support the RFT assessment update.
- **Done when (definition of done):** The workbook reflects the current remediation state and is ready to support reassessment.

### Step 19 — Update RFT Baseline Assessment
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** The Remediation Workbook has been updated with current remediation status.
- **Inputs needed first:** Updated workbook; updated evidence; original RFT assessment; remediation outcomes requiring reassessment.
- **Tool(s):** RFT
- **What to do (actions):**
  1. Update the baseline assessment in RFT based on completed remediation and new evidence.
  2. Transfer updated results to the requirements and controls assessment as needed.
  3. Verify that the updated assessment reflects the current engagement state.
- **Output / artifact produced:** Updated RFT baseline and/or requirements/controls assessment.
- **Where it's stored:** `02-evidence/` and `03-assessment/`
- **Handoff / gate to next step:** Assessment updates are complete enough to assemble the final evidence package.
- **Done when (definition of done):** RFT reflects the latest remediation-supported assessment status.

### Step 20 — Gather full evidence package
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** Remediation status and assessment updates are current.
- **Inputs needed first:** Updated workbook; updated RFT assessment; generated documents; technical control evidence; client-supplied documentation.
- **Tool(s):** RFT, ITG
- **What to do (actions):**
  1. Collect the full set of policy, technical control evidence, and supporting documentation for the engagement.
  2. Verify that evidence aligns to the current assessment state and required deliverables.
  3. Organize the evidence package into the expected folder structure and/or platform locations.
- **Output / artifact produced:** Full evidence package.
- **Where it's stored:** `02-evidence/` and `04-deliverables/`
- **Handoff / gate to next step:** Evidence package is complete enough for client presentation.
- **Done when (definition of done):** The evidence package is assembled and ready for presentation.

### Step 21 — Present package to client
- **Phase:** 5
- **Owner / who does it:** CM
- **Starts when (trigger):** The evidence package and engagement outputs are complete enough for review.
- **Inputs needed first:** Full evidence package; engagement findings; executive summary; technical report or equivalent outputs; meeting participants.
- **Tool(s):** varied
- **What to do (actions):**
  1. Present the final package and engagement outputs to the client.
  2. Review findings, evidence, and any remaining open items with the client.
  3. Capture any requested edits, follow-ups, or acceptance outcomes.
- **Output / artifact produced:** Client presentation of the final package and any resulting action list or acceptance record.
- **Where it's stored:** `04-deliverables/` 
- **Handoff / gate to next step:** Client presentation is complete and the package is approved or finalized for archival/upload.
- **Done when (definition of done):** The package has been presented and the outcome is documented.

### Step 22 — Upload full package to ITG
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** Final package is approved for handoff or archival upload.
- **Inputs needed first:** Finalized evidence package; final client-facing deliverables; confirmed ITG destination/organization structure.
- **Tool(s):** ITG
- **What to do (actions):**
  1. Upload the finalized package to ITG.
  2. Confirm all expected deliverables and evidence components are present.
  3. Record that the handoff repository has been updated.
- **Output / artifact produced:** Final package stored in ITG.
- **Where it's stored:** ITG
- **Handoff / gate to next step:** Engagement package is fully uploaded and available as the final handoff repository.
- **Done when (definition of done):** The full package is uploaded to ITG and confirmed present.

---

## Appendix A — PM AND CM checklist

- [ ] Step 1 — Initial prospect / compliance guideline information
- [ ] Step 2 — Compliance Proposal intake meeting
- [ ] Step 3 — Gap Assessment Proposal generated
- [ ] Step 4 — RFT discovery / scan agents from RMM
- [ ] Step 5 — RFT Rapid Baseline Assessment
- [ ] Step 6 — Transfer results to Reqs & Controls assessments
- [ ] Step 7 — Technical Review
- [ ] Step 8 — Generate Worksheets
- [ ] Step 9 — Generate POA&M
- [ ] Step 10 — Generate Remediation Workbook
- [ ] Step 11 — Gap Assessment post-meeting with client
- [ ] Step 12 — Feed workbook → Compliance Scorecard
- [ ] Step 13 — Feed workbook → Remediation Proposal
- [ ] Step 14 — Send proposal to client for acceptance
- [ ] Step 15 — Set up project plan
- [ ] Step 16 — Generate required docs
- [ ] Step 17 — Complete technical remediation tasks
- [ ] Step 18 — Update Remediation Workbook
- [ ] Step 19 — Update RFT Baseline Assessment
- [ ] Step 20 — Gather full evidence package
- [ ] Step 21 — Present package to client
- [ ] Step 22 — Upload full package to ITG

## Appendix B — Glossary
- **CMMC** — Cybersecurity Maturity Model Certification
- **POA&M** — Plan of Action and Milestones
- **RBA** — Rapid Baseline Assessment
- **SSP** — System Security Plan
- **Control family** — A grouped set of related security requirements or practices
- **FCI** — Federal Contract Information
- **CUI** — Controlled Unclassified Information
- **SPRS** — Supplier Performance Risk System

---

## Open Questions Log
These are the gaps the deck *doesn't* settle; you'll hit them as you write:
1. **Who owns each step?** Is there a role split (PM vs. engineer vs. URP/automation vs. client)? Is there a RACI we should reflect?
2. **Exact URP feature names** for: Remediation Workbook generation, Compliance Scorecard, Remediation Proposal, required-docs/policy templates. (Reference them by the real menu/feature names.)
3. **The client-facing gates** — which steps require client sign-off before proceeding (proposal acceptance is obvious; are there others)?
4. **Timeline / SLA per phase** — rough durations so a PM can set expectations? (Optional, but useful.)
5. **Where is the canonical home** for a running engagement — this repo's client folder, URP, Autotask, or a mix? (Affects the "Where it's stored" field.)

confirm all roles/owners and tools
1. what is the split of work between CM and PM?
2. confirming file location
3. client proposal acceptance?
4. archive labeling standard
5. mention zip folder
6. urp workflowOv


