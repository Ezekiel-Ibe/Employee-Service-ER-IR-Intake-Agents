---
title: HR Stage 4 Skill
description: Reusable GitHub Copilot skill for generating an Agent Factory Stage 4 Classify deliverable in Markdown.
applyTo: "**/*.md"
---

# HR Stage 4 Skill

## Purpose
This skill guides GitHub Copilot to produce a **review-ready Stage 4 – Classify deliverable** in Markdown for any business capability or business agent within the Agent Factory Delivery Methodology.

It ensures the generated deliverable:
- follows the Stage 4 methodology;
- uses `DeliveryControl/Stage_4.md` as the primary authority;
- uses the completed example only as a structural reference;
- is evidence-based and traceable to supplied source material;
- distinguishes workflow, decision, exception, control, handover, and human approval constructs correctly;
- supports governance-led review and Stage 5 handover;
- remains focused on business capability decomposition rather than solution design. [SRC-01, Practitioner guidance]

## When to use this skill
Use this skill when:
- a Stage 4 Classify deliverable needs to be created in Markdown;
- a Stage 3 or equivalent decomposition already exists;
- source materials are available to support evidence-based classification;
- the objective is to classify business capability work into reusable and/or bespoke agent capabilities;
- the output must be reusable and method-compliant.

Do **not** use this skill when:
- the task is solution architecture or technical design rather than business capability classification;
- source materials are absent and the user expects speculative output;
- the request is only for a short summary rather than a full Stage 4 deliverable;
- the methodology source hierarchy cannot be honoured.

## Required inputs

| Input ID | Input | Required | Usage | Evidence |
|---|---|---|---|---|
| IN-01 | Stage 4 methodology Visual Content Extract (`DeliveryControl/Stage_4.md`) | Yes | Primary authority for objectives, activities, outputs and quality expectations | [SRC-01, sections Objective to Common pitfalls] |
| IN-02 | Completed Stage 4 example (`Reference/PAA-Deliverables/Stage4/Payroll_Assurance_Agent_Stage_4_Classify_Capability_Based.md`) | Yes | Structural and stylistic reference only | [SRC-04, sections Executive Summary to Stage 4 Output Summary] |
| IN-03 | Reuse agent catalogue (`Reference/ABBA-Reuse Agents/Annotated_Agents_H2RList.csv`) | Yes | Candidate reuse identification | [SRC-03, relevant row(s)] |
| IN-04 | Stage 3 or equivalent decomposition source | Yes | Workflow steps, decisions, exceptions, handovers, human interventions | [SRC-01, Inputs from Stage 3] |
| IN-05 | Engagement-specific source materials | Yes | Factual evidence base | [SRC-02, precise location] |

## Optional inputs

| Input ID | Input | Usage |
|---|---|---|
| OPT-01 | Existing taxonomy or process hierarchy | Helps align naming and scoping |
| OPT-02 | SME notes or review comments | Clarifies ambiguity and unresolved items |
| OPT-03 | Existing governance/control catalogues | Supports control ownership and approval mapping |
| OPT-04 | Existing handover templates | Can inform register shape if consistent with methodology |

## Source hierarchy and precedence
Apply this order of precedence:

1. `DeliveryControl/Stage_4.md` — authoritative Stage 4 method source. [SRC-01, sections Objective to Agent type legend]  
2. Engagement-specific source documents and decomposition artefacts. [SRC-02, precise location]  
3. `Reference/ABBA-Reuse Agents/Annotated_Agents_H2RList.csv` — reuse catalogue. [SRC-03, relevant row(s)]  
4. `Reference/PAA-Deliverables/Stage4/Payroll_Assurance_Agent_Stage_4_Classify_Capability_Based.md` — reference example for structure and presentation only. [SRC-04, relevant section]  

If a lower-precedence source conflicts with a higher-precedence source, prefer the higher-precedence source and log the conflict as an open question or gap.

## Stage 4 workflow and deliverables
The skill must produce a Stage 4 Classify deliverable with the following mandatory sections:
- Executive Summary
- Overall AI Framework
- End-to-End Workflow
- Workflow Decomposition Catalogue
- Handover and Interaction Register
- Decision Catalogue
- Exception Catalogue
- Human Intervention Points
- SME Validation and Confirmation
- Stage 4 to Stage 5 Handover
- Appendices

The deliverable must also include the methodology outputs:
- agent inventory per workflow step;
- agent classifications;
- internal orchestration diagrams;
- handovers to previous and next steps;
- a control point for every step;
- a framework for every agent;
- ABBA reuse assessment and variance log. [SRC-01, Outputs of Stage 4]

## Deliverable objectives
The deliverable must:
- classify the business capability into an evidence-based agent model;
- identify reusable agents where supported;
- define orchestration, controls, decisions, handovers, and human interventions;
- preserve traceability to source evidence;
- remain reusable across business capabilities;
- stay focused on business capability decomposition rather than implementation design. [SRC-01, Practitioner guidance]

## Step-by-step generation guidance

### Step 1: Register and label sources
Create a source register using `SRC-01`, `SRC-02`, etc.
For each source, capture:
- title;
- file name;
- role in the analysis;
- precedence level.

### Step 2: Derive the Stage 4 method requirements
Read the methodology Visual Content Extract first.
Extract and apply:
- objective;
- required inputs;
- required activities;
- required outputs;
- practitioner guidance;
- key success factors;
- common pitfalls;
- quality expectations. [SRC-01, sections Objective to Common pitfalls]

This source governs the work even if the example document uses different wording.

### Step 3: Use the example only as a structural comparator
From the completed example, derive only:
- document structure;
- section ordering;
- style and level of detail;
- useful presentation patterns such as matrices, registers, framework views, and diagrams. [SRC-04, relevant sections]

Do not copy factual content into the new deliverable unless independently supported by source evidence.

### Step 4: Analyse the decomposition and source materials
Review the Stage 3 decomposition and supporting business source pack.
Identify and catalogue:
- workflow steps;
- triggering events;
- inputs and outputs;
- performers and ownership roles;
- decisions and criteria;
- exception conditions and routes;
- handovers and interactions;
- human interventions and approvals;
- control points and governance requirements.

### Step 5: Perform reuse assessment
Review `Reference/ABBA-Reuse Agents/Annotated_Agents_H2RList.csv` to identify candidate reusable agents.
Assess relevance using:
- business process match;
- taxonomy alignment;
- agent type fit;
- description similarity;
- workflow coverage.

Categorise each candidate as:
- Reused unchanged
- Adapted
- Combined
- No suitable asset
- New design  
[SRC-01, activity 8]

Also record any variance from the business requirement. [SRC-01, activity 8]

### Step 6: Build the workflow model
Construct an end-to-end business workflow that:
- is evidence-based;
- is capability-led;
- includes normal, decision, exception, and approval paths;
- includes explicit data and information movement;
- remains at logical business architecture level rather than implementation design. [SRC-01, Practitioner guidance]

### Step 7: Build the workflow decomposition catalogue
Each workflow row must include at least:
- Workflow Step ID
- Step name
- Step objective
- Operation
- Producing performer
- Consuming performer
- Business owner
- Data owner
- Data steward
- Source system owner
- Inputs
- Outputs
- Trigger
- Related decisions
- Related exceptions
- Candidate or assigned agent
- Agent type
- Control points
- Evidence reference

### Step 8: Derive and classify agents
Group workflow responsibilities into evidence-supported capability agents.
Use only methodology-approved Stage 4 classifications:
- Task
- Insight
- Orchestration
- Control
- Experience [SRC-01, activity 3; SRC-01, Agent type legend]

Do not create agents solely to fill an expected pattern.
Where no evidence supports a separate agent, keep the model simpler.

### Step 9: Model handovers and interactions
Create a Handover and Interaction Register.
Each entry must show:
- source;
- destination;
- transferred artefact or information;
- producing performer;
- consuming performer;
- control owner;
- preconditions;
- postconditions;
- failure mode;
- evidence citation.

### Step 10: Model decisions and exceptions
Create separate catalogues for decisions and exceptions.
Ensure every major branch in the workflow is represented in one or both catalogues.
Capture criteria, ownership, impacts, escalation routes, and closure logic.

### Step 11: Model human intervention and approval points
Create a Human Intervention Points section or register.
For each point, state:
- why human judgement is required;
- what evidence is presented;
- whether the point is approval, review, exception resolution, override, or validation;
- what outputs are produced.

### Step 12: Add SME validation and Stage 5 handover content
Document:
- what SMEs must validate;
- which items remain open;
- what is ready for Stage 5;
- what Stage 5 must resolve or consume.

### Step 13: Validate before completion
Run the formal quality checks before finalising the document.
Do not present the deliverable as complete if key sections, evidence, IDs, or controls are missing.

## Workflow modelling rules
- Model the workflow at business-operating level, not UI click level. [SRC-01, Practitioner guidance]
- Sequence steps in a logically coherent end-to-end flow.
- Include trigger, action, output, and recipient where supported.
- Every step must have a control point. [SRC-01, activity 6]
- Use explicit `Operation` values only:
  - Create
  - Read
  - Update
  - Delete
  - Transmit
  - Validate
  - Approve
  - Derive
- Include both normal path and materially relevant alternative paths.
- Use unique IDs for all workflow steps.

## Decision and exception modelling rules

### Decision rules
- Every significant workflow branch should map to a decision entry.
- Define the decision question clearly.
- Record the decision owner and approval requirement separately.
- State downstream impacts for each possible outcome.
- Do not invent criteria not present in source material.

### Exception rules
- Every material failure, break, or non-standard path should map to an exception entry.
- Record the trigger condition, containment action, escalation route, resolution owner, and closure criteria.
- Distinguish exception handling from standard decisioning.

## Handover and interaction modelling rules
- Every material transfer of work, information, case ownership, or approval artefact must be registered.
- Source and destination must both exist in the workflow or agent model.
- Handovers must identify producing and consuming performers separately.
- Where controls govern a handover, identify the control owner explicitly.
- Handover entries must identify invalid or failed handover scenarios where evidenced.
- Handovers must be unambiguous. [SRC-01, Key success factors]

## Human intervention and approval rules
- Mandatory human interventions must not be hidden inside narrative.
- Distinguish review, approval, escalation, override, validation, and exception-resolution roles.
- Maintain separation between recommendation and approval for employee-impacting, financial, regulatory, or compliance-sensitive actions.
- Human approval cannot be implied; it must be evidenced and explicitly modelled.
- Ensure human reviews or approvals are captured. [SRC-01, activity 2; SRC-01, Common pitfalls]

## Evidence and traceability rules
- Use evidence references in the format `[SRC-01, section 4.2]` or `[SRC-03, worksheet Entity Catalogue, row 18]`.
- Every factual table row must have at least one evidence reference.
- Prefer precise references over document-level citations.
- If the evidence is insufficient, record a gap or open question rather than inventing detail.

## Mermaid authoring and validation rules
- Embed workflow diagrams and process maps as fenced ````mermaid` blocks in the Markdown deliverable.
- When a Mermaid node or subgraph label must display on two lines, use a **single-line, double-quoted label containing `<br/>`**, for example `A["First line<br/>Second line"]`.
- Do **not** use literal line breaks inside Mermaid labels.
- Before completion, validate every Mermaid block with an available Mermaid parser or renderer such as GitHub preview, `mmdc`, or another available parser.
- If no Mermaid parser or renderer is available in the task environment, do not claim rendered validation; record that limitation as a constraint and still perform robust static syntax checks for fence balance, diagram declaration, identifier consistency, and `<br/>` label conformance.

## Ownership terminology rules
Do not collapse the following concepts:
- Business owner
- Data owner
- Data steward
- Source system owner
- Producing performer
- Consuming performer
- Control owner

If evidence is missing, mark the field `TBC` and register it in a gap or open question.

## Unsupported assumptions and anti-fabrication rules
The skill must prevent fabricated content.

Do not:
- infer facts that are not supported by the source pack;
- copy example facts into a new deliverable;
- assume reuse suitability without evidence;
- assume mandatory approvals unless evidenced;
- design implementation details beyond what Stage 4 requires.

If information is missing:
- mark it `TBC` temporarily;
- register it in a gap or open question;
- explain the impact on completeness.

## Validation and quality assurance checks
Before completion, verify:
- required headings are present;
- appendix order is correct;
- all IDs are unique;
- all cross references resolve;
- handover sources and destinations are valid;
- gap references exist and point to impacted sections;
- no unregistered `TBC` markers remain;
- filename conforms;
- Markdown tables are well formed;
- UK spelling has been applied where practical.

## Suggested appendix order
1. Source Register  
2. Reuse Assessment and Variance Log  
3. Assumptions Register  
4. Constraints Register  
5. Open Questions Register  
6. Gap Register  
7. Validation Checklist  

## Review-ready output standard
The final output must be:
- written in UK English;
- in Markdown format only;
- structurally complete;
- evidence-based;
- review-ready for SME validation;
- suitable for Stage 5 handover.

## Minimum acceptance test
The skill output passes only if:
- the methodology source governs the deliverable;
- the example is used only as a reference pattern;
- all mandatory sections are present;
- all factual tables include row-level citations;
- workflow operations use the standardised operation field values;
- ownership distinctions are preserved;
- every step has a control point;
- reuse assessment and variance handling are included;
- the deliverable contains explicit validation results or checklist content.
