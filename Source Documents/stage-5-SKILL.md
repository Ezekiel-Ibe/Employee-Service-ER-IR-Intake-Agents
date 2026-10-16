---
name: stage-5-model-generator
description: Generate a complete Stage 5 - Model deliverable, in Markdown, for any business capability or business agent within the Agent Factory Delivery Methodology. Use when asked to create, regenerate, populate, validate or quality-check a Stage 5 data model document, including workflow-step data models, entity and attribute definitions, relationships, data classification, the data gap log, source and ownership, and within-step and between-step data flows.
---

# Stage 5 - Model Generator

## Goal
Create a review-ready Stage 5 Markdown deliverable for a business capability or business agent, fully traceable to the Stage 5 section of the methodology infographic and to supplied source material, without fabricating content and without copying facts from unrelated example deliverables. The completed deliverable is designed to be the primary input to the separate Stage 5B - Data Model Consolidation skill.

## When this skill should be used
Use this skill when the user asks to:
- Generate a Stage 5 data model document for a capability or agent.
- Model data within a workflow step or between workflow steps.
- Classify data availability, log data gaps, or add missing data to a model.
- Produce or update entity, attribute, relationship, source and ownership records for a workflow.
- Validate a Stage 5 deliverable against the methodology infographic, the fillable template or the completed example.
- Prepare a Stage 5 deliverable ready to be handed over to Stage 5B - Data Model Consolidation.

Do not use this skill for Stage 3 workflow decomposition, Stage 4 classification, Stage 5B consolidation (use the `stage-5b-model-consolidation-generator` skill instead), Stage 6 detailed design, or Stage 7 build.

## Expected workspace
The working folder should contain, or the user should provide access to:

```text
methodology-infographic.png          # Stage 5 infographic (authoritative; Stage 5 section only)
stage-3-workflow-decomposition.*      # approved workflow steps and performers
stage-4-classification-handover.*     # approved Stage 4 output
enterprise-data-model.*               # canonical entities/attributes/relationships
abba-asset-catalogue.*                # existing reusable agent assets
data-modelling-template.*             # companion workbook / template
entity-and-attribute-catalogues.*     # layer-specific catalogues (e.g. Silver/Gold)
optional-finished-stage-5-example.docx
optional-fillable-stage-5-template.docx
```

The exact filenames may differ. Identify files by content and purpose rather than relying only on names.

## Inputs

### Required
1. Stage 5 methodology infographic, or an equivalent written statement of its Objective, Model at Two Levels, Data Classification, Inputs, Actions, Outputs, Practitioner guidance, Controls and Evidence, Exit Criteria and Deliverable.
2. Business capability or business agent name and identifier(s).
3. Approved Stage 3 workflow steps and their performers (agents, controls, humans).
4. Approved Stage 4 classification/handover for the same capability.

### Optional but strongly recommended
- Enterprise data model (canonical entities, attributes, relationships, ownership), for comparison against the Stage 4 input.
- ABBA asset catalogue, to identify existing reusable data schemas before proposing new entities.
- Data modelling template or companion workbook (workflow, required data, entity model, dependencies, missing data, CRUD, data-quality rules, readiness, RACI, evidence tabs).
- Entity and attribute catalogues for each canonical layer in use.
- A reviewed Stage 5 example, for structure and quality comparison only.
- Prior data gap logs, if this is an update.

## Source-document hierarchy and precedence
Use sources in this strict order. Never blend precedence levels or let a lower-precedence source override a higher one.

1. **Methodology infographic (Stage 5 section only)** - authoritative for what Stage 5 must cover: Objective, Model at Two Levels, Data Classification categories, Inputs, Actions (1-10), Outputs, Practitioner Guidance, Controls and Evidence, Exit Criteria, Deliverable, Key Tools. The Stage 5B section of the same infographic is context only; do not treat it as a Stage 5 source.
2. **Approved capability/agent source material** - Stage 3 workflow decomposition, Stage 4 handover, enterprise data model, ABBA asset catalogue, data modelling template, entity/attribute catalogues, workshop or SME evidence for this specific capability.
3. **The fillable Stage 5/5B template** - for the Stage 5 document structure, table headers, and reusable record patterns (workflow-step record, layer catalogues, classification/gap register, relationship register). Use only the Stage 5-relevant parts.
4. **A completed Stage 5/5B example deliverable** - reference only, for the structure, section ordering, writing style and level of detail of its Stage 5 section. It is never a fact source for a different capability.

When sources conflict, use the highest-precedence source, record the conflict as an open question (Appendix H / assumptions register), and continue - do not stop and do not silently resolve it.

## Input sufficiency behaviour
Do not stop solely because some information is missing. Generate the maximum supported document and:
- Mark missing factual fields `TBC - source required`.
- Record unresolved matters in the assumptions, constraints and open questions register.
- Mark data gaps in the data gap log rather than omitting them.
- Mark the exit criteria as not yet met, with the specific outstanding item, rather than overstating completion.

Only treat the following as blocking:
- No methodology infographic and no equivalent written description of Stage 5 requirements is available.
- No workflow, agent or capability context is available at all.
- The requested output location is inaccessible.

If any of these blocking conditions apply, ask the user for the missing item before generating content.

## Stage 5 workflow and deliverables (from the methodology infographic)
**Stage 5 - Model** (model data for each workflow step)
- Objective: identify and model all data required within each workflow step and between workflow steps.
- Model at two levels: within each workflow step (data exchanged between agents, controls and human participants); between workflow steps (data handed from one step to the next).
- Data classification: Enterprise model, Other source, Not available, Agent created, Human provided.
- Inputs: workflow steps, agent inventory, component frameworks, internal orchestration, workflow handovers, control points, Overall AI Framework, enterprise data model, ABBA reference.
- Actions 1-10: identify input data for each agent/control; identify data created/updated; identify data consumed by controls; identify data passed to other agents; identify data handed to the next step; define entity, attributes and relationships; classify data availability; log missing data; add missing data to the model; record the source and ownership.
- Outputs: data model per workflow step; entity and attribute definitions; relationships; data classifications; data gap log (added to model); source and ownership; within-step and between-step data flows.
- Practitioner guidance: trace data through the step and to the next step; be specific on entities and attributes; do not assume data exists - classify it; add missing data directly and continue; use ABBA to identify existing entities and common attributes; maintain clear lineage and ownership.
- Controls and evidence: evidence of data trace; data classification recorded; missing data logged and added; data lineage documented; source and ownership recorded.
- Exit criteria: every agent, control and handover has its data requirements modelled with availability classified and any gaps added.
- Deliverable: a complete data model for each workflow step, ready for consolidation.
- Key tools: enterprise data model; ABBA assets; data modelling templates; entity and attribute catalogues.

This skill produces the Stage 5 deliverable only. It does not perform Stage 5B consolidation, checks, approval-gate handling or Design Authority review - those are the responsibility of the separate Stage 5B skill, which consumes this skill's output.

## Step-by-step document-generation guidance

### Step 1: Inventory the inputs
Create an internal inventory: source name, type, approval status, relevant Stage 5 section(s), gaps or conflicts.

### Step 2: Read the methodology infographic
Extract every Stage 5 element listed above from the Stage 5 section of the infographic only. This becomes the section skeleton for the generated document. Do not omit or reorder these elements, and do not draw on the Stage 5B section.

### Step 3: Understand the enterprise data model
Read the supplied enterprise data model (canonical entities, attributes, relationships, layers, ownership). For every candidate data item in the capability's workflow, check whether it already exists in this model. Compare it against the Stage 4 input to confirm consistency before modelling. Use this to populate the "Enterprise model" classification and to avoid proposing duplicate entities.

### Step 4: Understand the ABBA assets
Read the supplied ABBA asset catalogue/register. Identify which ABBA (or other reused) agent assets are invoked within the capability's workflow steps, and extract the data schema (entities, attributes, keys) each asset already uses or produces. Use this to identify existing entities and common attributes before defining new ones, per the infographic's practitioner guidance.

### Step 5: Understand the data modelling template
Read the supplied data modelling template or companion workbook. Note its structure (e.g. workflow, required data, entity model, dependencies, missing data, CRUD, data-quality rules, readiness, RACI, evidence) and use it as the working schedule for attribute-level detail referenced from, but not duplicated in full within, the Markdown deliverable.

### Step 6: Understand the entity and attribute catalogues
Read the supplied entity and attribute catalogues for each canonical layer in scope. Use exact entity and attribute names from these catalogues; do not paraphrase or invent naming.

### Step 7: Build a Stage 5 evidence model
Extract and normalise the following, only where supported by evidence:

```yaml
capability:
  id:
  name:
  value_stream:
  agents: []          # A01, A02, ... with id, name, type, role
  reused_assets: []    # ABBA or other asset IDs invoked, by which agent, in which step
  workflow_steps: []   # W01, W02, ... with owner, description

data_model:
  entities: []         # name, layer/class, grain, keys, attributes, owner, source
  relationships: []    # parent, child, cardinality, linking field(s)
  classifications: []  # data item, category, evidence, owner
  gaps: []             # id, description, impacted step(s), resolution category, owner, status

flows:
  within_step: []      # step, producer, consumer, payload, shared ids
  between_step: []     # handover id, source step, target step, shared key(s), data

exit_criteria:
  status:              # e.g. Met / Partially met / Not yet met
  evidence:

validation:
  assumptions: []       # ACO-xx, statement, type, source/reason, owner, status
  open_questions: []
```

Every populated field must trace to supplied evidence. Unsupported details remain `TBC - source required`.

### Step 8: Draft the workflow-step data model
For every workflow step in scope, capture inputs, outputs, control data, within-step exchanges, the handover to the next step, entities/relationships/classification, and any gaps - following Actions 1-10 in order.

### Step 9: Draft entities, relationships, classification and the gap log
Define entities and relationships using catalogue-exact names. Classify every data item. Log every gap with a resolution category, and add resolved/accepted items directly into the model narrative.

### Step 10: Draft within-step and between-step data flows
Describe the sequence of exchange within each step (using the capability's own performer roles - do not assume a fixed pattern applies unless the source material confirms it), and list every between-step handover with its shared key(s).

### Step 11: Confirm the exit criteria
State whether every agent, control and handover in scope has its data requirements modelled, availability classified and gaps added, citing the evidence. Do not mark the exit criteria as met without supporting evidence.

### Step 12: Assemble the Markdown document
Populate the document in this order: Document Control; Contents; Stage 5 sections 3.1-3.11; Common Principles; Key Success Factors; Common Pitfalls; Appendices A-J (Agent Directory; ABBA/Reused Assets; Workflow Step Data Model; Entities Consumed by Agents; Data Classification Summary; Data Gap Log Summary; Between-Step Handover Map; Assumptions/Constraints/Open Questions; Referenced Artefacts; Stage 5B Handover Note).

### Step 13: Run validation and quality checks
Perform these checks before delivery:

```text
Every Stage 5 infographic element is represented
Data classification categories match the infographic definitions exactly
Agent, step, handover, entity and gap identifiers are unique and consistent
Every workflow step in scope has a step record
Every handover references two valid step identifiers
Every entity referenced in a step record appears in the entity/classification appendices
Every gap referenced in the narrative appears in the gap log with a resolution category
No unresolved [placeholder] or TBC left unrecorded in the open-questions register
No fabricated names, systems, owners, dates or approvals
Exit-criteria status is truthful
No Stage 5B content (Purpose, Actions 1-13, Checks Performed, Approval Gate, Next Stage) has been drafted
UK English used throughout
Valid Markdown (headings, tables, lists render correctly)
```

### Step 14: Render and inspect
Confirm the Markdown renders cleanly (heading hierarchy, table alignment, list formatting) and that no source file (infographic, template, or the completed example) has been modified or overwritten.

### Step 15: Prepare the Stage 5B handover
Summarise, in the final Appendix, what the Stage 5B skill will need: number of workflow steps modelled, entities/relationships defined, gaps logged and open questions carried forward. Do not perform the Stage 5B consolidation itself - hand it over.

## Content rules by section

### Objective
State the specific capability's Stage 5 objective in the infographic's terms, applied to this capability - not generic restatement and not another capability's wording.

### Model at Two Levels
Clearly separate within-step exchanges from between-step handovers. Do not conflate the two.

### Data Classification
Use only the infographic's categories. Every data item must have exactly one classification with supporting evidence.

### Actions (1-10)
Record the actual result achieved for this capability, the evidence location, and any open condition - not the generic methodology description alone.

### Data Gap Log
Every gap needs: description, impacted step(s), resolution category, proposed action, owner, status. Gaps are added to the model directly; they are not blockers unless the capability's own governance says otherwise.

### Exit Criteria
Use only truthful states: `Met`, `Partially met`, `Not yet met`, with evidence for whichever applies.

## Validation and quality-assurance checks
The deliverable is complete only when:
- Structural completeness: all required sections and appendices are present, in order, with no unresolved placeholders.
- Methodology alignment: every Stage 5 infographic element is represented and accurately reflects this capability's own actions and evidence.
- Traceability and consistency: identifiers are unique and consistent across prose, tables and appendices; every step, gap and handover cross-references correctly.
- Accuracy and governance: no fabricated content; classifications and exit-criteria status are evidence-based and truthful; UK English and correct classification marking are used.
- Handover readiness: the document is structured and complete enough to be used, without rework, as the primary input to the Stage 5B skill.

## Preventing unsupported assumptions and fabricated content
- Never invent entity names, attributes, keys, relationships, systems, owners, dates or approval outcomes.
- Never copy facts, figures or identifiers from the completed example deliverable into a new capability's document.
- Where a fact is not supported, write `TBC - source required` and add a register entry rather than guessing.
- Where the example or template's illustrative content is retained by mistake, remove it before delivery.
- Clearly distinguish assumptions (reasonable, flagged as unconfirmed) from constraints (traceable to an approved source) from open questions (owned, with a resolution path).

## Handover to Stage 5B
The output of Stage 5 is the primary input to Stage 5B - Data Model Consolidation:
- Stage 5B reads this Stage 5 deliverable in full and does not repeat Stage 5's Actions 1-10; it consolidates, validates and prepares the model for Design Authority review.
- Ensure every workflow step, entity, relationship, classification and gap that Stage 5B will need to reference has a stable identifier before handover.
- Flag, in the Stage 5B Handover Note appendix, anything left `TBC - source required` or open, so Stage 5B can decide whether to proceed, pause or request the missing input.

## Output
Produce a single, review-ready Markdown file:

```text
[Capability_or_Agent_Name]_Stage5_Model_v[Version].md
```

Also return a concise completion note containing:
- Output filename.
- Sources used, by precedence level.
- Sections marked pending.
- Open questions or source conflicts.
- Exit-criteria status.
- Quality-check result.
- Confirmation that the file is ready for Stage 5B.

## Failure handling
- If a source cannot be read, continue with readable sources and list the inaccessible source in the completion note.
- If a required fact is missing, use a transparent `TBC - source required` marker rather than invented content.
- If the enterprise data model, ABBA catalogue or entity/attribute catalogues are not supplied, state this limitation, mark the affected sections pending, and do not guess canonical names.
- If the methodology infographic itself is unavailable, do not proceed - request it or an equivalent written description before generating the deliverable.
