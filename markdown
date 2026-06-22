# CMMC Engagement Process Guide
**Standard Operating Procedure (SOP) for End-to-End Client Compliance Engagements**

---

## Front Matter

### Purpose
This document provides an actionable, step-by-step project management playbook derived from the RCS CMMC Engagement Workflow. It establishes a repeatable, standardized process for RCS Project Managers (PMs) to execute CMMC client engagements from initial prospect qualification through final remediation handoff, ensuring compliance data and deliverables are maintained systematically across all client folders.

### Intended Audience
RCS Project Managers (PMs), Account Managers, and Assigning/Technical Engineers.

### How to Use This Document
This playbook serves as a tactical "turn-by-turn" guide. PMs must follow the steps chronologically. Do not proceed to a subsequent phase until all entry criteria and "Definitions of Done" for the current phase are satisfied. When executing steps, maintain directory mapping consistency with the standard local client folders (`00-admin` through `05-poam`).

### Roles Glossary
*   **Project Manager (PM):** Tracks milestones, schedules key checkpoint meetings, manages customer communications, compiles deliverables, and updates project tasks in Autotask.
*   **Assigning / Technical Engineer:** Executes technical scans, performs GPO/infrastructure review, implements technical configuration controls, and validates remediation.
*   **Sales / Account Manager:** Drafts initial contracts, provides financial proposals, and handles initial commercial escalation points. `[CONFIRM w/ Nicholas]`
*   **Client Point of Contact (POC):** The client's designated internal representative (usually an IT manager, executive, or compliance officer) responsible for providing internal system context, policies, and operational access.

### Tools Legend
*   **URP:** Unified Reporting Platform (RCS's core reporting, deliverable, and assessment engine).
*   **RFT:** RapidFire Tools (Compliance Manager GRC platform).
*   **RMM:** Datto RMM (remote monitoring and management platform used for technical scan deployments).
*   **AT:** Autotask PSA (the core ticketing, project management, and time-tracking system).
*   **ITG:** IT Glue (secure centralized documentation repository).
*   **Varied:** Engineer-led manual configuration or verification processes utilizing toolsets specific to the target environment (e.g., Active Directory, Azure AD/Entra ID, local firewall interfaces).

### At-a-Glance Phase Map

| Phase | Description | Key Deliverable | Target Storage Folder |
| :--- | :--- | :--- | :--- |
| **Phase 1: Prospect & Proposal** | Qualify, scope, and win the assessment engagement. | Signed Gap Assessment SOW | `00-admin/` |
| **Phase 2: Gap Assessment** | Scan, baseline, and establish initial gaps. | Baseline Assessment & RFT POA&M | `01-scoping/` & `02-assessment/` |
| **Phase 3: Workbook & Post-Assessment** | Establish remediation roadmap and commercial proposal. | Remediation Workbook & Proposal | `03-remediation/` |
| **Phase 4: Setup & Implementation** | Schedule resources and execute technical tasks. | Hardened Infrastructure & Policies | `04-evidence/` |
| **Phase 5: Remediation & Handoff** | Package evidence, update metrics, and close engagement. | Completed Evidence Package & SSP | `04-evidence/` & IT Glue |

---

## Phase 1 — Prospect & Proposal
**Objective:** Capture scoping requirements, assess engineering complexity, and secure a signed Gap Assessment SOW.

### Step 1 — Initial prospect / compliance guideline information
- **Phase:** 1
- **Owner / who does it:** Sales / Account Manager `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** A warm lead expresses interest in CMMC Level 1 or Level 2 certification, or a contractual requirement requires compliance verification.
- **Inputs needed first:** Basic prospect details (corporate structure, location, primary point of contact, targeted compliance level).
- **Tool(s):** URP (Intake and Scoping Module `[CONFIRM w/ Nicholas on exact module path]`)
- **What to do (actions):**
  1. Input prospect corporate metrics (number of users, physical locations, external contractors) into the URP Profile form.
  2. Document target CMMC level. According to the Office of the Under Secretary of Defense for Acquisition & Sustainment (OUSD(A&S)) CMMC Guidelines, Level 1 covers 17 basic safeguarding practices; Level 2 aligns directly with the 110 security requirements of NIST SP 800-171.
  3. Generate the preliminary target profile within URP.
- **Output / artifact produced:** Client compliance target profile record.
- **Where it's stored:** URP database and synced to Autotask CRM.
- **Handoff / gate to next step:** Complete baseline customer profile is established; proceed to scheduling the technical discovery session.
- **Done when (definition of done):** Preliminary customer profile is complete with identified target CMMC compliance level.
- **Notes / common pitfalls:** Ensure the user count includes all active contractors and external users, not just internal FTEs.

### Step 2 — Compliance Proposal intake meeting (discovery meeting)
- **Phase:** 1
- **Owner / who does it:** PM / Technical Engineer `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Scheduling of discovery session confirmed by prospect.
- **Inputs needed first:** Preliminary target profile from Step 1.
- **Tool(s):** URP / Autotask (Meeting ticket)
- **What to do (actions):**
  1. Interview client regarding Federal Contract Information (FCI) and Controlled Unclassified Information (CUI) flow. Per CMMC Scoping Guidance v2.0, determine what assets process, store, or transmit FCI or CUI.
  2. Determine boundary limits (e.g., identifying segmented VLANs, air-gapped environments, cloud services).
  3. Verify network topology, endpoints count, server count, and directory service infrastructure (Active Directory vs. Entra ID).
- **Output / artifact produced:** Scoping questionnaire answers and environment architecture notes.
- **Where it's stored:** Local repo folder: `01-scoping/`
- **Handoff / gate to next step:** Boundary limits verified; scoping notes ready for pricing calculations.
- **Done when (definition of done):** Technical boundary scope is fully documented and confirmed by the engineering representative.
- **Notes / common pitfalls:** Clients often underreport where CUI resides. Ensure you ask specifically about shared file systems (SharePoint/OneDrive), local workstations, and personal email.

### Step 3 — Gap Assessment Proposal generated (proposal sent to prospect)
- **Phase:** 1
- **Owner / who does it:** Sales / PM `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Technical boundary and scope notes finalized in Step 2.
- **Inputs needed first:** Endpoint count, location counts, CMMC level target, and pricing reference files (`CMMC-L1-Pricing-Benchmark.md` and `RCS_CMMC_L1_Pricing_Model.xlsx`).
- **Tool(s):** URP (Proposal Generator Module `[CONFIRM w/ Nicholas on exact module name]`) / Excel (`RCS_CMMC_L1_Pricing_Model.xlsx`)
- **What to do (actions):**
  1. Open `RCS_CMMC_L1_Pricing_Model.xlsx` and input endpoint and site quantities to generate the pricing schedule.
  2. Input pricing output into URP to compile the formal SOW (Statement of Work).
  3. Export the finished PDF Proposal.
  4. Deliver the proposal to the prospect and secure formal signature.
- **Output / artifact produced:** Gap Assessment Proposal PDF.
- **Where it's stored:** Local repo folder: `00-admin/` (and linked in Autotask Opportunity).
- **Handoff / gate to next step:** SOW is fully signed and executed by the customer.
- **Done when (definition of done):** Executed signature copy of the Gap Assessment SOW is uploaded to `00-admin/`.

---

## Phase 2 — Gap Assessment
**Objective:** Deploy technical agents, analyze configuration data, identify compliance gaps, and generate the baseline POA&M.

### Step 4 — RFT discovery / scan agents from RMM
- **Phase:** 2
- **Owner / who does it:** Technical Engineer
- **Starts when (trigger):** SOW signed; onboarding process initiated.
- **Inputs needed first:** Technical contact approval, administrator access credentials.
- **Tool(s):** RMM (Datto RMM), RFT (RapidFire Tools Compliance Manager).
- **What to do (actions):**
  1. Log into Datto RMM and target the client site/endpoints.
  2. Deploy the RFT collector agents across all discovered endpoints and servers.
  3. Initiate an external and internal vulnerability scan along with local Active Directory configuration audits.
  4. Verify that data collections complete and push data to RFT's management portal.
- **Output / artifact produced:** Raw RFT scan file (`.edf` or equivalent format) containing local asset configurations and AD data.
- **Where it's stored:** RFT portal (and staging copy in local folder `01-scoping/`).
- **Handoff / gate to next step:** Scans finish running on all in-scope systems.
- **Done when (definition of done):** 100% of discovered in-scope endpoints have a recorded scan result within the RFT portal.
- **Notes / common pitfalls:** Ensure that remote or offline users connect to the VPN so that local scans are fully completed.

### Step 5 — RFT Rapid Baseline Assessment
- **Phase:** 2
- **Owner / who does it:** Technical Engineer / PM
- **Starts when (trigger):** Scan agent collection completes in Step 4.
- **Inputs needed first:** Raw asset data and domain profiles in the RFT portal.
- **Tool(s):** RFT (Compliance Manager Interface)
- **What to do (actions):**
  1. Run the "Rapid Baseline Assessment" automated script in RFT.
  2. Identify and flag unmapped, offline, or newly discovered assets.
  3. (Optional but recommended) Schedule an internal/client RBA clarification call if discrepancies in network structure or assets occur.
- **Output / artifact produced:** Draft Rapid Baseline Report PDF.
- **Where it's stored:** Local repo folder: `01-scoping/`
- **Handoff / gate to next step:** Initial network/asset list is clean and validated with client boundaries.
- **Done when (definition of done):** Discrepancies are resolved and the baseline asset configuration report is successfully exported to local storage.

### Step 6 — Transfer results to Reqs & Controls assessments
- **Phase:** 2
- **Owner / who does it:** Technical Engineer
- **Starts when (trigger):** Baseline asset configuration report finalized in Step 5.
- **Inputs needed first:** Rapid Baseline Report data.
- **Tool(s):** RFT (Compliance Manager GRC Assessment module).
- **What to do (actions):**
  1. Open the specific compliance assessment template within RFT (CMMC Level 1 or Level 2).
  2. Initiate the automated "Merge Scan Results" function to transfer asset configuration data, user lists, and patching states directly into the controls engine.
  3. Review initial auto-mapped controls for consistency.
- **Output / artifact produced:** Populated Requirements & Controls assessment project in RFT.
- **Where it's stored:** RFT portal environment.
- **Handoff / gate to next step:** Automated data transfer successfully aligns with standard CMMC domains.
- **Done when (definition of done):** The GRC portal lists populated control fields for all active system-level controls.

### Step 7 — Technical Review
- **Phase:** 2
- **Owner / who does it:** Technical Engineer
- **Starts when (trigger):** Automated integration of scan data finishes in Step 6.
- **Inputs needed first:** Requirements & Controls assessment dataset.
- **Tool(s):** Varied (engineer-led verification using GPOs, active firewall reviews, M365 admin dashboards).
- **What to do (actions):**
  1. Manually evaluate and verify compliance items that automated tools cannot scan (e.g., physical access policies, visitor logs, written user awareness programs).
  2. Cross-reference firewall logging, backup policies, and internal patch governance settings against requirements.
  3. Document compliance notes for every objective, noting gaps where settings do not match standard CMMC practices.
- **Output / artifact produced:** Verified technical analysis and findings logs.
- **Where it's stored:** Local repo folder: `02-assessment/`
- **Handoff / gate to next step:** QA check complete; technical reviews on all target controls are compiled.
- **Done when (definition of done):** Technical analysis notes are complete for all required practice controls (17 for L1; 110 for L2).

### Step 8 — Generate Worksheets
- **Phase:** 2
- **Owner / who does it:** PM
- **Starts when (trigger):** Technical Review marked complete in Step 7.
- **Inputs needed first:** Technical analysis reviews and control data within the RFT project.
- **Tool(s):** RFT (Reporting/Exporting Module)
- **What to do (actions):**
  1. Navigate to the Reports section of the RFT portal.
  2. Select and generate the detailed "Requirements Worksheet" or "Control Assessment Workbook".
  3. Save the exported worksheets directly to the client's local project workspace.
- **Output / artifact produced:** Completed Assessment Worksheets (PDF or Excel format).
- **Where it's stored:** Local repo folder: `02-assessment/`
- **Handoff / gate to next step:** Worksheets are validated for completeness, ready to extract non-compliant items.
- **Done when (definition of done):** Complete set of CMMC compliance status worksheets is exported to local storage.

### Step 9 — Generate POA&M
- **Phase:** 2
- **Owner / who does it:** PM / Technical Engineer
- **Starts when (trigger):** Worksheets are finalized in Step 8.
- **Inputs needed first:** Assessment Worksheets, identified gaps.
- **Tool(s):** RFT (POA&M Engine)
- **What to do (actions):**
  1. Extract all controls flagged as "Non-Compliant" or "Incomplete".
  2. Use the RFT POA&M wizard to structure and compile these open gaps into a standardized Plan of Action and Milestones report. According to NIST SP 800-171, a POA&M must specify the associated costs, scheduled completion dates, and milestones for each deficiency.
  3. Assign baseline estimates for remediation phases.
- **Output / artifact produced:** CMMC-compliant POA&M report.
- **Where it's stored:** Local repo folder: `05-poam/`
- **Handoff / gate to next step:** Final baseline POA&M is established; ready to migrate to the URP toolkit.
- **Done when (definition of done):** POA&M PDF and spreadsheet containing all identified deficiencies are safely stored in `05-poam/`.

---

## Phase 3 — Remediation Workbook & Post-Assessment
**Objective:** Transform raw gaps into a prioritizable client-facing remediation strategy, score the business, and present pricing for the implementation phase.

### Step 10 — Generate Remediation Workbook
- **Phase:** 3
- **Owner / who does it:** PM `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** POA&M is archived in Step 9.
- **Inputs needed first:** Baseline POA&M spreadsheet.
- **Tool(s):** URP / Local toolkit script (`build_remediation_workbook.py`).
- **What to do (actions):**
  1. Copy the POA&M spreadsheet file to the workspace.
  2. Run the `build_remediation_workbook.py` command-line script in the toolkit environment to compile the POA&M into the official Remediation Workbook layout:
     ```bash
     python3 _toolkit/build_remediation_workbook.py --input ../05-poam/poam_export.xlsx --output ../03-remediation/Remediation_Workbook.xlsx
     ```
  3. Annotate the file with preliminary RCS standard remediation notes for identified gaps before reviewing with the client.
- **Output / artifact produced:** Configured Remediation Workbook (`Remediation_Workbook.xlsx`).
- **Where it's stored:** Local repo folder: `03-remediation/`
- **Handoff / gate to next step:** Script executes without errors and fields are fully formatted.
- **Done when (definition of done):** The client's annotated Remediation Workbook is generated and stored in `03-remediation/`.

### Step 11 — Gap Assessment post-meeting with client
- **Phase:** 3
- **Owner / who does it:** PM / Technical Engineer
- **Starts when (trigger):** Workbook generated and pre-annotated in Step 10.
- **Inputs needed first:** Draft Remediation Workbook.
- **Tool(s):** Varied (Meeting software / URP review screen)
- **What to do (actions):**
  1. Conduct a deep-dive review meeting with the client's stakeholders.
  2. Walk through each gap on the POA&M.
  3. Determine and allocate technical Roles & Responsibilities (RCS vs. Client Internals vs. 3rd Party) for each task.
  4. Update task owners in the workbook in real-time.
- **Output / artifact produced:** Updated Remediation Workbook with assigned ownership and target milestones.
- **Where it's stored:** Local repo folder: `03-remediation/`
- **Handoff / gate to next step:** Client reaches agreement on operational ownership for every listed gap.
- **Done when (definition of done):** Client-assigned workbook is complete and stored in `03-remediation/`.

### Step 12 — Feed workbook → Compliance Scorecard
- **Phase:** 3
- **Owner / who does it:** PM
- **Starts when (trigger):** Signed-off roles and responsibilities saved in Step 11.
- **Inputs needed first:** Updated Remediation Workbook.
- **Tool(s):** URP (Scorecard Portal module `[CONFIRM w/ Nicholas on exact module name]`)
- **What to do (actions):**
  1. Log into URP and navigate to the Compliance Scorecard Generator module.
  2. Import the finalized Remediation Workbook file.
  3. Execute the scorecard engine to calculate the Supplier Performance Risk System (SPRS) compliance rating. Under the NIST SP 800-171 Assessment Methodology, scores begin at 110 and are decremented (down to a potential -203) based on the severity and weight of missed security requirements.
- **Output / artifact produced:** Executive Compliance Scorecard (SPRS baseline score report).
- **Where it's stored:** Local repo folder: `03-remediation/` (and URP cloud storage).
- **Handoff / gate to next step:** Baseline score is generated and verified for accurate weighting.
- **Done when (definition of done):** Accurate baseline SPRS scorecard output is archived in local storage.

### Step 13 — Feed workbook → Remediation Proposal
- **Phase:** 3
- **Owner / who does it:** PM / Sales
- **Starts when (trigger):** Scorecard verified in Step 12.
- **Inputs needed first:** Updated Remediation Workbook and SPRS score.
- **Tool(s):** URP (Proposal Generator Module `[CONFIRM w/ Nicholas on exact module name]`)
- **What to do (actions):**
  1. Isolate all tasks assigned to "RCS" as primary owner in the Remediation Workbook.
  2. Import these technical tasks into the URP Proposal Generator.
  3. Apply standard technical implementation pricing logic to compile a scope-specific SOW for technical remediation.
- **Output / artifact produced:** Technical Remediation Proposal PDF.
- **Where it's stored:** Local repo folder: `03-remediation/` / `00-admin/`
- **Handoff / gate to next step:** Remediation SOW is drafted and peer-reviewed internally.
- **Done when (definition of done):** Structured Remediation Proposal is compiled and prepared for client delivery.

### Step 14 — Send proposal to client for acceptance
- **Phase:** 3
- **Owner / who does it:** PM / Sales `[CONFIRM w/ Nicholas]`
- **Starts when (trigger):** Remediation Proposal finalized in Step 13.
- **Inputs needed first:** Completed Technical Remediation Proposal.
- **Tool(s):** URP / Autotask
- **What to do (actions):**
  1. Deliver the Technical Remediation Proposal package (including baseline scorecard) to the client.
  2. Coordinate a follow-up review call to walk through scope boundaries and costs.
  3. Request formal signature via the platform.
- **Output / artifact produced:** Executed/Signed Remediation Contract SOW.
- **Where it's stored:** Local repo folder: `00-admin/` (and Autotask Contract workspace).
- **Handoff / gate to next step:** Client accepts, signs, and returns the SOW.
- **Done when (definition of done):** Signed SOW for the remediation project is uploaded to `00-admin/`.

---

## Phase 4 — Acceptance, Project Setup & Docs
**Objective:** Schedule resources, configure policy frameworks, and execute all technical configuration items.

### Step 15 — Set up project plan
- **Phase:** 4
- **Owner / who does it:** PM
- **Starts when (trigger):** Signed technical remediation contract received in Step 14.
- **Inputs needed first:** Signed SOW and final Remediation Workbook scope.
- **Tool(s):** AT (Autotask PSA)
- **What to do (actions):**
  1. Create a "New Project" inside Autotask PSA using the "CMMC Remediation Implementation" template.
  2. Convert Remediation Workbook actions into distinct project tasks.
  3. Assign timelines, critical path milestones, and technical engineering resources.
- **Output / artifact produced:** Active Autotask Project Plan and tracking Gantt-chart.
- **Where it's stored:** Autotask PSA (and summary copied to `00-admin/`).
- **Handoff / gate to next step:** Project is scheduled and resources are officially assigned.
- **Done when (definition of done):** Project tasks are live in Autotask and the client kickoff meeting is scheduled.

### Step 16 — Generate required docs
- **Phase:** 4
- **Owner / who does it:** PM / Technical Engineer
- **Starts when (trigger):** Project planning completed in Step 15.
- **Inputs needed first:** Target gaps requiring structural policy coverage.
- **Tool(s):** URP (Policy Generation Tool `[CONFIRM w/ Nicholas on exact module name]`) / ITG
- **What to do (actions):**
  1. Query compliance templates for missing client policies (e.g., Access Control, Incident Response, Password Policy).
  2. Run the policy builder script inside URP to populate templates with client-specific meta-parameters.
  3. Hand off drafted policies to client management for review and sign-off.
- **Output / artifact produced:** Client Policy Suite and system configuration templates.
- **Where it's stored:** Local repo folder: `04-evidence/` (and staged in IT Glue).
- **Handoff / gate to next step:** Client approves draft policies for active operational implementation.
- **Done when (definition of done):** Customized policy packages are compiled and waiting for technical enforcement.

### Step 17 — Complete technical remediation tasks
- **Phase:** 4
- **Owner / who does it:** Technical Engineer
- **Starts when (trigger):** Policies drafted and target infrastructure configurations scheduled.
- **Inputs needed first:** Policy specifications, admin access keys, and Remediation Workbook details.
- **Tool(s):** Varied (RMM, Active Directory GPO, Microsoft Entra, Firewalls, endpoint agents).
- **What to do (actions):**
  1. *GPO Configuration:* Configure administrative Group Policy Objects (GPOs) for system auditing. Per Microsoft Docs ("Audit Policy Recommendations"), configure Advanced Audit Policy settings to ensure log collection tracks successful and failed logon attempts.
  2. *Identity Hardening:* Implement MFA constraints across all endpoints, administrative accounts, and VPN links. According to Microsoft Docs ("M365 conditional access policies"), enforce standard conditional access frameworks targeting CUI-touching environments.
  3. *Encryption:* Enforce storage environment hardening. Per Microsoft Docs ("BitLocker Group Policy settings"), configure full-volume XTS-AES 256-bit encryption for operating system drives.
  4. *Access Controls:* Revoke unneeded access pathways and restrict local administrative privileges across endpoints.
- **Output / artifact produced:** Hardened system environment configurations and technical service verification logs.
- **Where it's stored:** Autotask individual configuration tickets (and tracked in the project spreadsheet).
- **Handoff / gate to next step:** All technical engineering tasks are finished and peer-tested.
- **Done when (definition of done):** Technical engineering tickets for all assigned remediation lines inside Autotask are successfully closed.

---

## Phase 5 — Remediation, Evidence & Handoff
**Objective:** Audit configurations, consolidate the evidence package, present deliverables, and archive project artifacts.

### Step 18 — Update Remediation Workbook
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** Technical engineering items are marked complete in Step 17.
- **Inputs needed first:** Autotask configuration task resolution data.
- **Tool(s):** URP / Local Excel Engine.
- **What to do (actions):**
  1. Retrieve the master Remediation Workbook.
  2. Update progress markers to "Complete" for each resolved control point.
  3. Update implementation dates and reference evidence names in the workbook columns.
- **Output / artifact produced:** Finalized/Remediated Workbook showing resolved status.
- **Where it's stored:** Local repo folder: `03-remediation/`
- **Handoff / gate to next step:** Status updates match engineering validation notes.
- **Done when (definition of done):** Corrected workbook entries reflect active technical completion and are verified.

### Step 19 — Update RFT Baseline Assessment
- **Phase:** 5
- **Owner / who does it:** Technical Engineer
- **Starts when (trigger):** Workbook statuses updated in Step 18.
- **Inputs needed first:** Finalized configurations on client network.
- **Tool(s):** RFT (Compliance Manager) / RMM.
- **What to do (actions):**
  1. Initiate delta scans across the network utilizing the active Datto RMM deployment.
  2. Pull updated scan files into the target GRC environment inside RFT.
  3. Merge the new configurations into the master Requirements & Controls module to update the compliance baseline.
- **Output / artifact produced:** Updated RFT Compliance Reports.
- **Where it's stored:** RFT portal (and local repo backup folder: `02-assessment/`).
- **Handoff / gate to next step:** Delta scans verify successful remediation of system configurations.
- **Done when (definition of done):** Baseline in RFT is updated, showing zero unmitigated technical configuration gaps.

### Step 20 — Gather full evidence package
- **Phase:** 5
- **Owner / who does it:** PM / Technical Engineer
- **Starts when (trigger):** Updated compliance baseline confirmed in Step 19.
- **Inputs needed first:** Signed policies, screenshot evidence, configuration outputs, and updated compliance baselines.
- **Tool(s):** Varied / RFT / Local file explorer.
- **What to do (actions):**
  1. Compile all signed policy PDFs, technical control screenshots, and baseline config outputs.
  2. Systematically map files using a standardized naming taxonomy (e.g., `AC.L1-3.1.1_Access_Control_Policy.pdf` or `IA.L1-3.5.1_MFA_M365_Settings.png`).
  3. Verify that each control listed as completed has at least one valid supporting evidence artifact.
- **Output / artifact produced:** Fully compiled CMMC Evidence Package.
- **Where it's stored:** Local repo folder: `04-evidence/`
- **Handoff / gate to next step:** Quality review verifies evidence maps correctly to the target practices.
- **Done when (definition of done):** All 17 L1 practices (or 110 L2 practices) contain validated, named evidence records inside `04-evidence/`.

### Step 21 — Present package to client
- **Phase:** 5
- **Owner / who does it:** PM / Technical Engineer
- **Starts when (trigger):** Finalized CMMC Evidence Package completed in Step 20.
- **Inputs needed first:** Evidence Package, finalized Scorecard, and System Security Plan (SSP) draft.
- **Tool(s):** Varied (Screen-share / Client Presentation)
- **What to do (actions):**
  1. Conduct the final delivery meeting with client executives.
  2. Walk through the final compliant architecture state and the updated SPRS Scorecard.
  3. Hand off the compiled compliance folders, policies, and evidence directory.
  4. Secure a signature on the Client Project Closeout Acceptance Form.
- **Output / artifact produced:** Signed Client Project Closeout Form.
- **Where it's stored:** Local repo folder: `00-admin/`
- **Handoff / gate to next step:** Client formally signs the closeout acceptance documentation.
- **Done when (definition of done):** Closeout documentation is signed, establishing final delivery of artifacts.

### Step 22 — Upload full package to ITG
- **Phase:** 5
- **Owner / who does it:** PM
- **Starts when (trigger):** Signed Project Closeout Form saved in Step 21.
- **Inputs needed first:** Complete Evidence Package and signed policies.
- **Tool(s):** ITG (IT Glue) / RFT.
- **What to do (actions):**
  1. Access the client's IT Glue organization workspace.
  2. Create a standardized folder pathway: `Core Documentation > Compliance > CMMC`.
  3. Upload the final policies, system descriptions, SSP draft, and network maps.
  4. Confirm that all local repo folders from `00-admin/` through `05-poam/` are archived inside the RFT document safe.
- **Output / artifact produced:** Centralized, secure documentation directory in IT Glue.
- **Where it's stored:** IT Glue organization library.
- **Handoff / gate to next step:** Confirm IT Glue data sync completes.
- **Done when (definition of done):** The final compliance documentation library is uploaded to IT Glue, matching local folder trees.

---

## Appendices

### Appendix A: PM Sequential Checklist

- [ ] **Phase 1: Prospect & Proposal**
  - [ ] Step 1: Input baseline customer profile into URP.
  - [ ] Step 2: Conduct scoping/discovery meeting and map system boundaries.
  - [ ] Step 3: Run the CMMC Pricing tool and secure a signed Gap Assessment SOW.

- [ ] **Phase 2: Gap Assessment**
  - [ ] Step 4: Use Datto RMM to run the RFT scan agents across the target site.
  - [ ] Step 5: Generate the RFT Rapid Baseline Report and resolve asset disputes.
  - [ ] Step 6: Map raw scan outputs into the RFT GRC controls database.
  - [ ] Step 7: Conduct technical control review (policies, GPOs, firewalls).
  - [ ] Step 8: Generate the official Assessment Worksheets from the portal.
  - [ ] Step 9: Export the finalized baseline CMMC POA&M.

- [ ] **Phase 3: Remediation Workbook & Post-Assessment**
  - [ ] Step 10: Run the `build_remediation_workbook.py` script.
  - [ ] Step 11: Lead the client post-meeting to assign task responsibilities.
  - [ ] Step 12: Import workbook data to generate the SPRS Scorecard in URP.
  - [ ] Step 13: Compile the technical Remediation Proposal.
  - [ ] Step 14: Send the Remediation Proposal to the client and secure signatures.

- [ ] **Phase 4: Acceptance, Project Setup & Docs**
  - [ ] Step 15: Setup the implementation plan inside Autotask PSA.
  - [ ] Step 16: Draft policies and system documentation targets via URP.
  - [ ] Step 17: Execute technical configurations (GPOs, MFA, encryption).

- [ ] **Phase 5: Remediation, Evidence & Handoff**
  - [ ] Step 18: Mark remediation tasks complete inside the Remediation Workbook.
  - [ ] Step 19: Deploy delta scans to update the RFT compliance baseline.
  - [ ] Step 20: Package and name all supporting compliance evidence files.
  - [ ] Step 21: Present the deliverables package and obtain sign-off.
  - [ ] Step 22: Archive all final documentation in IT Glue and RFT.

---

### Appendix B: CMMC Glossary

*   **Plan of Action and Milestones (POA&M):** A document that details an organization's roadmap to resolve security weaknesses and gaps discovered during assessments, complete with milestones and resource allocations.
*   **Rapid Baseline Assessment (RBA):** An initial, scanning-driven evaluation of system assets and network configurations designed to define technical compliance scopes quickly.
*   **System Security Plan (SSP):** A formal document describing the operational boundaries, system network diagrams, policies, and active security controls applied to protect target environments (essential for CMMC Level 2).
*   **Control Family:** Logical clusters of security practices defined under NIST SP 800-171 / CMMC (e.g., Access Control, Identification and Authentication, Incident Response, Physical Protection).
*   **Federal Contract Information (FCI):** Information, not intended for public release, that is provided by or generated for the Government under a contract to develop or deliver a product or service.
*   **Controlled Unclassified Information (CUI):** Government-created or possessed information that requires safeguarding or dissemination controls consistent with applicable laws, regulations, and government-wide policies.

---

## Open Questions Log

Nicholas, please review and provide confirmation for the following items:

1.  **Who owns each step (RACI splits)?**
    *   *Step 1, 2, 3:* Does Sales completely own Step 1 & 3? Does the assigning engineer lead Step 2 technical reviews?
    *   *Step 10:* Does the PM or the engineer run the command-line script to generate the remediation workbook?
    *   *Step 14:* Who owns sending the proposal to the client for acceptance? Sales or the PM?
2.  **What are the exact URP module / interface names?**
    *   Verify the naming for:
        *   Step 1: Prospect profile form/intake interface.
        *   Step 12: SPRS scorecard generator feature/module.
        *   Step 13: Remediation proposal/SOW compiler module.
        *   Step 16: Policy template builder utility.
3.  **Are there additional client-facing approval gates?**
    *   Are the client stakeholders required to sign off on the baseline scoping boundary (Step 2) and baseline POA&M (Step 9) before moving to subsequent phases?
4.  **Are there target durations / SLAs for each phase?**
    *   What are the standard SLA expectations a PM should build into Autotask for Phase 1 through Phase 5 durations?
5.  **What is the definitive canonical repository for running engagements?**
    *   Is the local git repo directory `~/repos/cmmc-projects/` considered the master single source of truth, or is it a sync target secondary to the Autotask project files / IT Glue vault?
