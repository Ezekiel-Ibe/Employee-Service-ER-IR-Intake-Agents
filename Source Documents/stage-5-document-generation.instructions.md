---
applyTo: "**/stage-5/**,**/*stage*5*.md"
description: "Repository instructions for generating a Stage 5 - Model deliverable, in Markdown, for any business capability or business agent, ready for Stage 5B consolidation."
---

# Stage 5 - Model: Document Generation Instructions

## Purpose
Generate a complete, review-ready **Stage 5 - Model** deliverable, as a single Markdown (`.md`) document, for any business capability or business agent within the Agent Factory Delivery Methodology.

Stage 5:

1. Identifies and models all data required within each workflow step and between workflow steps.
2. Classifies every data item's availability against the enterprise data model.
3. Logs missing data and adds it directly to the model.
4. Records source and ownership for every data item.
5. Produces a complete, per-step data model ready for Stage 5B consolidation.

This file governs *how* Stage 5 content is generated. It is deliberately capability-agnostic: it must work for any agent, value stream or business capability, not only the reference Payroll Assurance example used for structural comparison.

This is a **Stage 5 only** instructions file. Stage 5B - Data Model Consolidation is a separate deliverable, generated using the `Stage5B-InstructionsAndSkills` instructions and skill, which take the Stage 5 output produced here as their primary input.

## Authoritative source hierarchy
Apply this order of authority when generating content. Do not blend or reorder it.

1. **Stage 5 section of the methodology infographic** (`DeliveryControl/Stage 5.png` or equivalent) - the authoritative source for Stage 5 Objective, Model at Two Levels, Data Classification, Inputs, Actions (1-10), Outputs, Practitioner Guidance, Controls and Evidence, Exit Criteria, Deliverable and Key Tools. Use only the "Stage 5 - Model" portion of the infographic. The "Stage 5B - Data Model Consolidation" portion is context only and must not be treated as a Stage 5 source or copied into the Stage 5 deliverable.
2. **Approved project source material** for the specific capability or agent being documented - Stage 3 workflow decomposition, Stage 4 classification/handover, enterprise data model, ABBA asset catalogue, data modelling template/workbook, entity and attribute catalogues, agent inventory, control requirements.
3. **The KPMG Agent Factory Stage 5/5B fillable template** - for the Stage 5 section structure, table headers and reusable Appendix record patterns (workflow-step record, layer catalogues, classification and gap register, relationship register). Use only the Stage 5-relevant parts of the template.
4. **The completed Stage 5/5B example deliverable** (e.g. `Stages_5_and_5B_Model_and_Data_Model_Consolidation.docx`) - **reference only**, for document structure, section ordering, writing style and level of detail of its Stage 5 section. It must never be used as a content source for a different agent or capability. Do not copy its facts, figures, identifiers or narrative into a new deliverable unless the same facts are independently supported by that capability's own source material.

If sources conflict, use the highest-authority source, record the conflict as an open question, and do not silently pick a version or invent a resolution.

## Required inputs

### Mandatory
- Stage 5 methodology infographic (or an equivalent written description of its content).
- Business capability or business agent name and identifier.
- Approved Stage 3 workflow decomposition (workflow steps, performers, handovers).
- Approved Stage 4 classification and Stage 4 to Stage 5 handover.
- Confirmed list of agents, controls and human participants in scope.

### Recommended
- Enterprise data model (canonical entities, attributes, relationships, e.g. `config/enterprise_model.yml` or equivalent), for comparison against the Stage 4 input.
- ABBA asset catalogue/register, so existing agent assets can be checked for reusable data schemas.
- Data modelling template or companion workbook (workflow, required data, entity model, dependencies, missing data, CRUD, data-quality rules).
- Entity and attribute catalogues (Silver/Gold or equivalent canonical layer definitions).
- Prior Stage 5 outputs and data gap logs for the same capability, where this is an update rather than a first pass.
- A finished Stage 5 example, for structure and quality comparison only.

## Non-negotiable rules
- Generate the deliverable in **Markdown (`.md`)**. Do not produce or overwrite a Word document unless specifically instructed otherwise.
- Model data at **both levels**: within each workflow step, and between workflow steps.
- Classify **every** data item using one of the infographic's data classification categories: Enterprise model, Other source, Not available, Agent created, Human provided.
- Never fabricate entity names, attributes, keys, relationships, owners, source systems, approval dates or evidence links. Where information is not supported by source material, write `TBC - source required` and add an entry to the assumptions, constraints and open questions register.
- Distinguish confirmed facts from assumptions, constraints and open questions at all times.
- Log missing data in the data gap log and add it directly to the model narrative - do not treat logging a gap as requiring a separate approval step, but do record any decision needed to resolve it.
- Maintain clear, unbroken lineage from source system/layer, through agent or control, to consumer, for every data item.
- Keep Stage 5 focused on **business capability data decomposition** - what data exists, where it comes from, who owns it and how it flows. Do not perform solution design, physical schema design or technology selection.
- Maintain traceability: every generated fact must be attributable to a numbered input source in the evidence map (see below).
- Use UK English throughout (e.g. "modelled", "organisation", "authorised", "recognise").
- Apply the confidentiality classification stated in the project source material; default to `KPMG Confidential` if none is specified.
- This document is reusable across capabilities. Do not hard-code Payroll Assurance (or any other single agent's) names, IDs, entities or figures into the instructions or generated boilerplate.
- Do not draft or embed Stage 5B content in the Stage 5 deliverable. Stop at the Stage 5 deliverable and hand over to the Stage 5B instructions/skill.

## Required identifier and naming conventions
Use stable, sequential identifiers, consistent with Stage 3/Stage 4 conventions where the same items are referenced:

- Workflow steps: `W01`, `W02`, ...
- Agents: `A01`, `A02`, ... (as defined at Stage 3/4; do not renumber)
- ABBA / reused agent assets: use their native asset ID (e.g. `VA-xxxx`) unchanged
- Between-step handovers: `H01`, `H02`, ...
- Data gaps: `G-01`, `G-02`, ... (or the project's existing gap-log numbering if one already exists)
- Relationships: `R01`, `R02`, ...
- Assumptions, constraints and open questions: `ACO-01`, `ACO-02`, ...
- Entity names: lower_snake_case, singular, matching the enterprise model's layer convention (e.g. `silver.worker`, `gold.fact_payroll_line`) where such a convention exists; otherwise state the convention used and keep it consistent throughout.
- File name: `[Capability_or_Agent_Name]_Stage5_Model_v[Version].md`

Never reuse an identifier for a different item. Cross-references must use the same identifier everywhere in the document, and must remain stable so Stage 5B can reference them without renumbering.

## Generation workflow

### 1. Build an inventory and evidence map
Before drafting, list every supplied source (file/name, type, approval status, relevant section) and identify gaps or conflicts. Maintain an internal evidence map linking every generated fact to a numbered source.

### 2. Extract the infographic requirements
From the Stage 5 section of the infographic, extract and confirm (do not paraphrase away):
- Stage 5 Objective and "model at two levels" definition (within-step, between-step).
- Data classification categories and their exact definitions.
- Stage 5 Inputs, the 10 Actions, Outputs, Practitioner guidance, Controls and evidence, Exit criteria, Deliverable, Key tools.
- Common principles, key success factors and common pitfalls that apply to Stage 5.

### 3. Analyse the capability/agent source pack
Extract only supported information for:
- Agents in scope (ID, name, type, role) and any ABBA/reused agent assets they invoke.
- Workflow steps in scope and their owning agent/control/human performer.
- Data each agent/control/human consumes, creates, updates or exchanges within a step.
- Data handed from one workflow step to the next, and the shared key(s) used.
- Candidate entities, attributes and relationships, and whether each already exists in the enterprise model.
- Source systems, ownership and stewardship for each data item.
- Known data gaps and any prior decisions about them.

### 4. Draft the workflow-step data model
For **every workflow step in scope**, produce a step record covering:
- Step ID, name and owning performer (agent/control/human).
- Inputs consumed (with source: enterprise model entity, named source system, another agent's output, or a human participant).
- Data created or updated (with created-vs-updated and consumer/storage).
- Data consumed by controls, and the rule/threshold/policy applied.
- Data passed to other agents/controls within the step.
- Data handed to the next step, with shared key(s).
- Entities, attributes and relationships touched, and their data classification.
- Gaps identified for this step, if any.

### 5. Draft entity, attribute, relationship and classification content
- Define each entity: name, layer/class, business grain, key(s), critical attributes, source lineage, owner, consumers.
- Define each relationship: parent/child, cardinality, linking field(s).
- Classify every data item using the infographic's categories, with evidence for the classification.
- Record source system and business/data owner for every entity and item.

### 6. Build the data gap log
For every gap: description, impacted workflow step(s), resolution category (e.g. remains at source, application-layer, agent-created/transient, candidate for future model admission), proposed action, owner and status. Add resolved or accepted gaps directly to the model narrative; do not leave silent omissions.

### 7. Document within-step and between-step data flows
- Within-step: show the sequence of exchange between performers in a step (e.g. task -> function/insight -> control -> experience -> orchestrator, or the capability's own performer pattern - do not assume the Payroll Assurance pattern applies elsewhere).
- Between-step: list every handover (`Hxx`) with source step, target step, shared key(s) and the data/state exchanged.

### 8. Confirm the exit criteria
State whether every agent, control and handover in scope has its data requirements modelled, availability classified and gaps added, with evidence. Do not mark the exit criteria met without supporting evidence.

### 9. Prepare the Stage 5B handover note
Summarise, for the Stage 5B instructions/skill: number of workflow steps modelled, number of entities/relationships defined, number of gaps logged, and any open questions that must be considered during consolidation. Do not perform the consolidation itself.

## Document structure (generate in this order)
1. Document Control (title, scope, agents/workflow in scope, version, classification, owner, status).
2. Contents.
3. Stage 5 - Model
   - 3.1 Objective
   - 3.2 Model at Two Levels (Within Each Workflow Step; Between Workflow Steps)
   - 3.3 Data Classification
   - 3.4 Inputs
   - 3.5 Actions (Steps 1-10)
   - 3.6 Outputs
   - 3.7 Practitioner Guidance
   - 3.8 Controls and Evidence
   - 3.9 Exit Criteria
   - 3.10 Deliverable
   - 3.11 Key Tools
4. Common Principles.
5. Key Success Factors.
6. Common Pitfalls.
7. Appendix A - Agent Directory.
8. Appendix B - ABBA / Reused Agent Assets Referenced by Workflow.
9. Appendix C - Workflow Step Data Model (per-step records for every `Wxx` in scope).
10. Appendix D - Entities Consumed by Agents (by layer/class).
11. Appendix E - Data Classification Summary.
12. Appendix F - Data Gap Log Summary.
13. Appendix G - Between-Step Handover Map.
14. Appendix H - Assumptions, Constraints and Open Questions.
15. Appendix I - Referenced Artefacts.
16. Appendix J - Stage 5B Handover Note.

Preserve this order and every mandatory section, even when a section can only be marked pending.

## Writing standards
- Use concise, professional, evidence-based language.
- Name entities and attributes exactly as they appear in the enterprise model or source catalogue; do not paraphrase technical names.
- Use tables for structured registers (inputs, outputs, classifications, gaps, handovers, relationships) and short prose for interpretation, consistent with the reference example's style.
- Expand an acronym at first use.
- Keep the Objective statement traceable to the detailed sections that follow it.
- Do not copy narrative, figures or identifiers from the Payroll Assurance (or any other) example into a new capability's deliverable.

## Assumptions, constraints, open questions and missing information
- Maintain a single register (Appendix H) using identifiers `ACO-01`, `ACO-02`, ...
- Record: statement, type (assumption/constraint/open question/missing information), impacted section(s), source or reason, owner, status.
- An assumption may only be recorded where it is reasonable, clearly flagged as unconfirmed, and does not misrepresent unverified content as fact.
- A constraint must be traceable to an approved source (policy, control, system limitation) or explicitly marked as proposed.
- An open question must have an owner and, where known, a target forum or date for resolution.
- Missing information must never be silently invented; mark the field `TBC - source required` and add the corresponding register entry.

## Validation and quality gates
The document is ready for review only when all checks pass.

### Structural completeness
- All sections in the required order are present, including appendices, even where marked pending.
- No unresolved placeholder or bracketed text remains.
- The document is valid, well-formed Markdown (headings, tables, lists render correctly).

### Methodology alignment
- Every element of the Stage 5 infographic (Objective, Model at Two Levels, Data Classification, Inputs, Actions 1-10, Outputs, Practitioner Guidance, Controls and Evidence, Exit Criteria, Deliverable, Key Tools) is represented.
- The data classification categories are used consistently and match the infographic definitions.
- No Stage 5B content (Purpose, Actions 1-13, Checks Performed, Approval Gate, Next Stage) has been drafted in this deliverable.

### Traceability and consistency
- Agent, workflow step, handover, entity and gap identifiers are unique and consistent across prose, tables and appendices.
- Every workflow step in scope has a step record; every step record's identifier appears in the between-step handover map where a handover exists.
- Every entity referenced in a step record appears in the entity/classification appendices.
- Every data gap referenced in the narrative appears in the gap log appendix with a resolution category.
- Every claim of "complete" or "modelled" is supported by cited evidence.

### Accuracy and governance
- No fabricated entities, attributes, systems, owners, dates or approvals.
- Data classifications are evidence-based, not assumed.
- Exit criteria status is truthful and reflects the actual state of the work.
- UK English and the correct confidentiality classification are used throughout.

## Output requirements
Produce:
- One Markdown file: `[Capability_or_Agent_Name]_Stage5_Model_v[Version].md`.
- A short generation summary listing: sources used, sections marked pending, open questions, and quality-gate result.
- Do not overwrite the methodology infographic, the fillable template, or any approved example deliverable.
- Confirm the file is ready to be used as the primary input to the Stage 5B instructions and skill.
