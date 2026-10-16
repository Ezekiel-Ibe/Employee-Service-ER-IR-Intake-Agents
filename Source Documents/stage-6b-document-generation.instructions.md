---
applyTo: "**/*Stage6B*.md"
description: "Repository instructions for generating Agent Factory Stage 6B - Solution Design Consolidation deliverables in Markdown for any business capability or business agent."
version: "1.0"
methodologyVersion: "Agent Factory Delivery Methodology - Stage 6B (Solution Design Consolidation)"
templateVersion: "Stage 6B Markdown structure 1.0"
skillFile: "stage-6b-SKILL.md"
lastUpdated: "2026-09-15"
classification: "KPMG confidential"
---

# Stage 6B - Solution Design Consolidation: Document Generation Instructions

These instructions define **what must be true** of a generated Stage 6B deliverable: applicability, output format, naming, source precedence, governance constraints, stage boundary and quality gates. The **procedure** for generating it is defined in the companion skill `stage-6b-SKILL.md`.

## 1. Repository paths and applicability

Apply these instructions whenever Stage 6B - Solution Design Consolidation content is authored, generated or reissued, specifically when working in or creating:

- any file whose name contains `Stage6B` or `Stage 6B`;
- any folder named for a Stage 6B consolidation deliverable or output;
- any working folder in which Stage 6 component designs for a single capability are being consolidated.

These instructions are capability-agnostic and agent-agnostic. They must be reusable for any business capability or business agent and must never be specialised to a single value stream, client or reference deliverable.

## 2. Stage boundary

Stage 6B **consolidates**. It does not design, and it does not build.

- Stage 6 component designs - behaviour specifications, data mappings, deterministic logic, AI instructions and prompts, response design, exception design, human intervention design, control design, integration and handover specifications, and unit test scenarios - are **fixed inputs**. Do not re-author them.
- Do not perform Stage 3 decomposition, Stage 4 classification or internal orchestration design, or Stage 5 / 5B data modelling.
- Do not perform Stage 7 build activities. Stage 6B may only **recommend** an implementation technology and state whether build readiness is evidenced.
- Where consolidation exposes a gap, inconsistency or error in a Stage 6 artefact, record it as a consolidation issue or action (`CIA-nn`). Never silently amend a component design.

## 3. Required output format

- Generate the deliverable and all supporting artefacts in **Markdown (`.md`)**. Do not produce Word (`.docx`) output unless the user explicitly instructs otherwise.
- Use GitHub-flavoured Markdown: ATX headings, pipe tables, fenced code blocks, and Mermaid fenced blocks for workflow, orchestration and handover diagrams.
- Every table must be well-formed: header row, separator row, consistent column count on every row, no empty cells without an explicit value or registered marker.
- Generate the **Contents** section from the final heading structure **after** all sections are assembled. Do not maintain the contents list independently while drafting. Every anchor must resolve to a heading that exists in the finished document.
- Design the logical solution, not the implementation. Diagrams, tables and narrative remain technology-agnostic outside the *Recommended Implementation Technology* section.
- Where a fillable template is supplied, use it for section structure and table headers only; reproduce the equivalent structure in Markdown.

### 3.1 Mandatory deliverable sections and order

1. Document Control
2. Contents
3. Executive Summary
4. Stage 6B Objective and Scope
5. Source Inventory and Evidence Map
6. Consolidated Solution Design
7. End-to-End Orchestration Assurance
8. Consolidated Control Coverage
9. Unit-Test Coverage Assessment
10. Readiness Assessment
11. Consolidated Issues, Risks and Actions Log
12. Recommended Implementation Technology
13. Controls, Evidence and Exit Criteria
14. Assumptions, Dependencies and Limitations
15. Appendices (diagrams, matrices, glossary)

Headings and order are mandatory. A mandatory section is never omitted; where evidence is insufficient, the section is retained and states explicitly what is missing.

### 3.2 Document control block

The Document Control table must record, as a minimum: skill name and version; instruction-file version; methodology version; template version; generation date; execution environment; source-pack fingerprint or source list; validation-script version; validation outcome; deliverable status; classification `KPMG confidential`.

## 4. Naming conventions

Primary deliverable:

```
<CAPABILITY-ID>_<Capability_Or_Agent_Name>_Stage6B_Solution_Design_Consolidation_v<major>.<minor>.md
```

Supporting artefacts, one file per artefact in the same folder:

```
<CAPABILITY-ID>_Stage6B_Source_Inventory_and_Evidence_Map_v<major>.<minor>.md
<CAPABILITY-ID>_Stage6B_Component_Consolidation_Matrix_v<major>.<minor>.md
<CAPABILITY-ID>_Stage6B_Control_Coverage_Map_v<major>.<minor>.md
<CAPABILITY-ID>_Stage6B_Unit_Test_Coverage_Assessment_v<major>.<minor>.md
<CAPABILITY-ID>_Stage6B_Consolidated_Issues_Risks_Actions_Log_v<major>.<minor>.md
<CAPABILITY-ID>_Stage6B_Workflow_Diagrams_v<major>.<minor>.md
```

Rules:

- Underscores only; no spaces; no trailing punctuation.
- Start at `v0.1`; increment the minor version on each reissue; use `v1.0` only once Design Authority approval is evidenced.
- Identifier formats, applied consistently: components `CMP-nn`; workflow steps `WF-nn`; handovers `Hnn`; controls `Cnn`; exceptions `EXC-nn`; human intervention points `HIP-nn`; unit tests `UT-nn`; sources `SRC-nn`; consolidation issues, risks and actions `CIA-nn`; assumptions `ASM-nn`; decisions `DEC-nn`.
- Identifiers must be unique within the deliverable and must reuse the identifier already assigned in the approved source wherever one exists.

## 5. Source hierarchy and precedence (concise)

Apply strictly in order. A lower level never overrides a higher one.

1. **Stage 6B panel of the methodology infographic** (`DeliveryControl\Stage_6.md`, section "6B. Stage 6B - Solution Design Consolidation") - authoritative for Objective, Inputs, Actions, Outputs, Practitioner Guidance, Controls and Evidence, Exit Criteria, Design Authority approval and Deliverable. The "Stage 6 - Design" panel describes the inputs being consolidated; it is context, not a Stage 6B authority.
2. **Supplied Stage 6 component designs for this capability**, together with the Stage 4 classification, internal orchestration and approved Stage 5B data model they depend on - the primary factual evidence base.
3. **Other approved capability source material** - control point definitions, ABBA reuse assessments, business rules and constraints, SME-confirmed workflow, Overall and Component AI Frameworks, approval and decision records.
4. **Fillable Stage 6 / 6B template** - structure, table headers and record patterns only.
5. **Completed example deliverables** (for example `Reference/O2C-Deliverables/O2C_Capability_and_Agent_Catalogue_v1.md`) - **reference only**, for structure, ordering, tone and level of detail.

Where sources conflict, take the higher-precedence source, raise a `CIA-nn` entry recording both positions, and continue. Never silently resolve a conflict.

## 6. Non-negotiable governance constraints

1. **No fabrication.** Every factual statement must be derived from supplied source material. Do not invent components, controls, handovers, data entities, metrics, volumes, dates, owners, tooling or test results. Partial completion is always preferred to invention.
2. **No content copying from example deliverables.** Facts, figures, identifiers, narrative and tables from a completed example must not appear in a generated deliverable unless independently supported by this capability's own sources.
3. **Evidence on every factual row.** Every row of every factual table carries an `Evidence Reference` field at the most precise available location, for example `[SRC-01, section 4.2]`, `[SRC-03, table Control Register, C07]`, `[SRC-05, worksheet Entity Catalogue, row 18]`, `[SRC-07, Stage 6B panel, Actions 1-11]`. A document-level citation is insufficient where a section, table, row, worksheet or diagram element can be identified.
4. **Approval evidence.** Treat a source as approved only where at least one of the following exists: (a) an explicit `Approved` status in the source document control; (b) a supplied approval or decision record referencing the source; (c) an explicit user statement that the named source is approved. **Never infer approval** from filename, version number, folder location, author, last-modified date, or the absence of comments or tracked changes.
5. **No unsupported approval or readiness claims.** Do not record Design Authority approval, design-lead consolidation review, SME visibility, alignment sign-off, "all items resolved" or "build ready" as achieved unless evidenced. Absent evidence, record `Pending - evidence required` and raise a `CIA-nn` action.
6. **Technology-agnostic logical design.** Describe the "what", not the "how". Implementation technology appears only in the single, clearly-labelled *Recommended Implementation Technology* section, as a reasoned recommendation with options considered, evaluation criteria, dependencies and open decisions - never as an implementation specification.
7. **Traceability.** Every component, workflow step, control, handover, exception path, human intervention point and unit test traces to an identified source and, where relevant, to the approved Stage 5B data model.
8. **Existing identifiers versus extending identifiers.** Reuse baseline identifiers from approved sources. Where consolidation identifies a required but previously undefined handover or control, create a **proposed consolidation record** only if the requirement is directly derivable from approved source behaviour, and mark it: `Proposed`; `Pending Stage 6 owner confirmation`; `Linked to CIA-nn`; `Not part of the approved design baseline until formally accepted`. Do **not** assign a live `Hnn` or `Cnn` baseline identifier until the governing Stage 6 artefact is updated or the Design Authority explicitly approves the addition. Use provisional references `H-PROP-nn` and `C-PROP-nn`.
9. **Ownership.** Where no owner is evidenced, record `Owner: TBC - source required`. Do not assign an individual, team or role based on apparent subject matter. Add a separate governance action to assign the owner.
10. **Unresolved placeholders.** No unexplained placeholder, bracket token or template prompt may remain. The marker `TBC - source required` is permitted **only** where the missing fact is explicitly identified, a `CIA-nn` entry exists, the impacted section, workflow step or component is recorded, and the readiness impact is stated.
11. **Status model.** Use only these deliverable statuses, with these meanings:
    - `Draft` - structure or mandatory evidence extraction incomplete.
    - `Review-Ready` - structurally complete and evidence mapped, but reviews or actions remain open.
    - `Approved with actions` - Design Authority decision is evidenced and only explicitly accepted non-blocking actions remain.
    - `Build-Ready` - all blocking CIA items closed, required reviews evidenced, approval obtained and exit criteria met.
    - `Not Build Ready` - one or more blocking design, data, control, handover, test or approval items remain.
12. **UK English.** Use UK spelling and conventions throughout (organisation, prioritise, recognise, behaviour, analyse, catalogue, programme, licence as a noun). Do not use US spellings.
13. **Confidentiality.** Mark every generated deliverable `KPMG confidential` in Document Control and in the closing footer. Do not include client-identifying detail beyond that present in the supplied sources, and never transfer content between capabilities or clients.

## 7. Practitioner guidance to apply

- Think end-to-end, not component by component.
- Challenge assumptions; record each challenged assumption as `ASM-nn` with its evidence status and challenge outcome.
- Ensure consistency of language, responses and controls across all components.
- Confirm the user journey is coherent from trigger to business outcome.
- Validate that nothing is missed - data, control, handover, exception, human intervention.
- Prepare explicitly for Design Authority review.

## 8. Controls, evidence and exit criteria to be evidenced

The deliverable must report status and evidence reference for each Stage 6B control and evidence requirement: consolidation review by design lead; SME visibility; Design Authority review and approval; evidence of alignment to business outcome.

It must also report position against each Stage 6B exit criterion: all items resolved; Design Authority approval; build ready confirmed; deliverable ready for onward use following Stage 6B consolidation. Each is either evidenced with a citation or recorded as `Pending - evidence required` with a `CIA-nn` action.

## 9. Validation and quality gates

The deliverable is not complete until the validation checker defined in `stage-6b-SKILL.md` has been executed and its outcome recorded in Document Control. The gate covers, as a minimum:

- valid YAML frontmatter on generated framework files, and a complete document control block on the deliverable;
- required headings present, correctly spelled and in the mandated order;
- filename conformity;
- unique identifiers and conformant identifier formats, including `H-PROP-nn` and `C-PROP-nn`;
- no broken cross-references;
- no unregistered `TBC - source required` markers;
- valid `CIA-nn` references in both directions;
- every workflow step appearing in the control coverage map;
- every handover appearing in the unit-test coverage assessment;
- every component appearing in the component consolidation matrix;
- every factual table row containing an evidence reference;
- Design Authority status not marked approved without qualifying evidence;
- valid and complete Markdown tables;
- valid Mermaid block syntax;
- no unresolved template text;
- UK-English conformance, flagging exceptions where practical;
- Contents regenerated from final headings with every anchor resolving.

If a check fails, fix and re-run. If a check cannot pass because evidence is absent, record it as a blocking `CIA-nn` item and set the status to `Draft` or `Not Build Ready` as applicable. Never suppress a failed check.

## 10. Reference to the Stage 6B skill

Execution detail - activation criteria, input discovery, sufficiency and blocker logic, extraction and normalisation, the end-to-end consolidation workflow, when to open supporting resources, validation execution, output assembly, partial-completion behaviour, completion response and failure handling - is defined in the companion skill file `stage-6b-SKILL.md` (skill name `stage-6b-solution-design-consolidation-generator`). Follow that skill when generating a Stage 6B deliverable; these instructions define the applicable constraints, format and governance, not the procedure.

---

**Classification:** KPMG confidential
