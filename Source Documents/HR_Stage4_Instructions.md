---
title: HR Stage 4 Instructions
description: Reusable instructions for generating an Agent Factory Stage 4 Classify deliverable in Markdown.
applyTo: "**/*.md"
---

# HR Stage 4 Instructions

## Purpose
These instructions guide GitHub Copilot to generate a complete **Stage 4 – Classify** deliverable in Markdown for any business capability or business agent using the Agent Factory Delivery Methodology.

The generated output must be:
- in Markdown only;
- reusable across business capabilities and business agents;
- evidence-based and traceable to supplied source materials;
- aligned to Agent Factory governance principles;
- written in UK English; and
- focused on business capability decomposition rather than solution design.

## Authoritative source hierarchy
Apply the following source precedence strictly.

1. **Primary authority:** `DeliveryControl/Stage_4.md`  
   Use this methodology Visual Content Extract as the authoritative source for Stage 4 objective, inputs, activities, outputs, practitioner guidance, key success factors, common pitfalls, approved agent types, reuse expectations, and quality requirements. [SRC-01, sections Objective to Agent type legend]
2. **Engagement-specific business source materials and Stage 3 outputs**  
   Use these as the factual basis for workflow steps, decisions, exceptions, handovers, controls, approvals, and ownership. [SRC-02, relevant section or appendix]
3. **Reusable agent catalogue:** `Reference/ABBA-Reuse Agents/Annotated_Agents_H2RList.csv`  
   Use this to identify potentially reusable agents relevant to the capability being classified. [SRC-03, relevant row(s)]
4. **Reference example:** `Reference/PAA-Deliverables/Stage4/Payroll_Assurance_Agent_Stage_4_Classify_Capability_Based.md`  
   Use this only as a reference for document structure, section ordering, writing style, level of detail, diagram patterns, and expected deliverable shape. Do **not** copy unsupported business content. [SRC-04, relevant section]

If sources conflict, prefer the higher-ranked source and record the conflict in the Open Questions or Gap Register.

## What Stage 4 must achieve
Stage 4 must identify and classify the agents required for each workflow step and define the internal orchestration, handovers, and control points. [SRC-01, title and introductory statement]

For each workflow step, determine:
- which agents and controls are required to complete the work;
- how they interact internally;
- how the step connects to the previous and next steps; and
- how every agent is classified using the five approved agent types. [SRC-01, Objective]

A component AI Framework must be created for every agent. [SRC-01, Objective; SRC-01, activity 7]

## Required inputs
Do not finalise the Stage 4 deliverable unless the required inputs have been reviewed or explicitly recorded as missing.

| Input ID | Required input | Why it is required | Minimum expectation | Evidence |
|---|---|---|---|---|
| IN-01 | Stage 4 methodology Visual Content Extract | Governs Stage 4 method and quality expectations | Approved file available and reviewed | [SRC-01, sections Objective to Common pitfalls] |
| IN-02 | Stage 3 outputs | Provides overall AI framework, end-to-end workflow, workflow steps, decisions, exceptions, human intervention points, SME confirmation | Step-level decomposition available | [SRC-01, Inputs from Stage 3] |
| IN-03 | Engagement-specific source material pack | Provides factual content for the target capability | Process documents, SOPs, policy artefacts, SME notes, operating models, screenshots or equivalent | [SRC-02, precise location] |
| IN-04 | ABBA reuse catalogue | Supports reuse assessment | Current CSV reviewed for relevant capabilities and agent types | [SRC-03, relevant row(s)] |
| IN-05 | Completed Stage 4 example | Provides structural benchmark only | Example reviewed for presentation and section ordering | [SRC-04, relevant section] |

If a required input is missing:
- record the missing item in a Gap Register entry;
- record any resulting assumptions separately;
- limit the output to supported evidence;
- avoid fabricated completion statements.

## Expected outputs
The deliverable must include the outputs required by Stage 4 and any additional governance content needed for review readiness.

### Mandatory Stage 4 outputs from the methodology
- Agent inventory per workflow step [SRC-01, Outputs of Stage 4]
- Agent classifications [SRC-01, Outputs of Stage 4]
- Internal orchestration diagrams [SRC-01, Outputs of Stage 4]
- Handovers to previous and next steps [SRC-01, Outputs of Stage 4]
- Control point defined for every step [SRC-01, Outputs of Stage 4]
- Framework for every agent [SRC-01, Outputs of Stage 4]
- ABBA reuse assessment and variance log [SRC-01, Outputs of Stage 4]

### Required review-ready document sections
Use these exact top-level headings unless the governing methodology is formally updated:
- `# Executive Summary`
- `# Overall AI Framework`
- `# End-to-End Workflow`
- `# Workflow Decomposition Catalogue`
- `# Handover and Interaction Register`
- `# Decision Catalogue`
- `# Exception Catalogue`
- `# Human Intervention Points`
- `# SME Validation and Confirmation`
- `# Stage 4 to Stage 5 Handover`
- `# Appendices`

## Non-negotiable generation rules
- The methodology Visual Content Extract is the authoritative source for Stage 4 activities, inputs, outputs and expected deliverables. [SRC-01, sections Objective, Inputs from Stage 3, Stage 4 activities, Outputs of Stage 4]
- The completed Stage 4 example is a **reference document only**. [SRC-04, overall document usage]
- Content must **not** be copied from the example unless independently supported by cited source material.
- Maintain traceability back to supplied source materials.
- Focus on business capability decomposition and logical business architecture, not technical solution design. [SRC-01, Practitioner guidance]
- Use UK English throughout.
- Apply governance principles proportionate to business and control risk. [SRC-01, Key success factors; SRC-01, Common pitfalls]

## Evidence citation standard
Use evidence references in the form:
- `[SRC-01, section 4.2]`
- `[SRC-03, worksheet Entity Catalogue, row 18]`
- `[SRC-02, appendix B, process map step 12]`

Rules:
- Every factual table row must contain at least one evidence reference.
- Document-level citations are insufficient where a more precise source location is available.
- If a precise source location is not available, cite the smallest available unit.
- If no evidence exists, do not present the claim as fact.

## Mermaid authoring and validation rules
- Embed workflow diagrams and process maps as fenced ````mermaid` blocks in the Markdown deliverable.
- When a Mermaid node or subgraph label must display on two lines, use a **single-line, double-quoted label containing `<br/>`**, for example `A["First line<br/>Second line"]`.
- Do **not** use literal line breaks inside Mermaid labels.
- Before completion, validate every Mermaid block with an available Mermaid parser or renderer such as GitHub preview, `mmdc`, or another available parser.
- If no Mermaid parser or renderer is available in the task environment, do not claim rendered validation; record that limitation as a constraint and still perform robust static syntax checks for fence balance, diagram declaration, identifier consistency, and `<br/>` label conformance.

## Naming conventions

### File naming
- Deliverable output: `<Capability_or_Agent_Name>_Stage_4_Classify.md`
- Instruction file: `HR_Stage4_Instructions.md`
- Skill file: `HR_Stage4_Skills.md`

### Identifier conventions
Use stable, unique identifiers throughout the deliverable.

| Identifier type | Prefix | Example | Rule |
|---|---|---|---|
| Workflow step | W | W-001 | Sequential and unique |
| Agent | A | A-001 | Sequential and unique |
| Handover | H | H-001 | Sequential and unique |
| Decision | D | D-001 | Sequential and unique |
| Exception | E | E-001 | Sequential and unique |
| Human intervention point | HIP | HIP-001 | Sequential and unique |
| Control point | C | C-001 | Sequential and unique |
| Assumption | ASM | ASM-001 | Sequential and unique |
| Constraint | CON | CON-001 | Sequential and unique |
| Open question | OQ | OQ-001 | Sequential and unique |
| Gap | GAP | GAP-001 | Sequential and unique |
| Source | SRC | SRC-01 | Sequential and reused consistently |

## Ownership terminology rules
The following ownership concepts must remain distinct and must not be collapsed into one generic ownership field unless the evidence genuinely shows the same person or role performs multiple responsibilities:
- Business owner
- Data owner
- Data steward
- Source system owner
- Producing performer
- Consuming performer
- Control owner

If evidence for a required field is unavailable, mark it `TBC` temporarily and register it in Open Questions or Gaps.

## Stage 4 methodology activities to apply
For each workflow step, apply all eight Stage 4 activities.

### 1. Analyse the workflow step
- Understand the purpose of the step. [SRC-01, activity 1]
- Review required work and outcomes. [SRC-01, activity 1]
- Consider decisions, exceptions and handovers. [SRC-01, activity 1]

### 2. Identify agents and controls
- List all agents needed to complete the step. [SRC-01, activity 2]
- Include any control mechanisms. [SRC-01, activity 2]
- Include any human reviews or approvals. [SRC-01, activity 2]

### 3. Classify each agent
Classify every agent using the five approved agent types:
- Task
- Insight
- Orchestration
- Control
- Experience  
[SRC-01, activity 3; SRC-01, Agent type legend]

### 4. Define internal orchestration
- Map the sequence and interactions between agents. [SRC-01, activity 4]
- Define data and information flow between them. [SRC-01, activity 4]

### 5. Define handovers
- Define input from previous step. [SRC-01, activity 5]
- Define output to next step. [SRC-01, activity 5]
- Specify data and information exchanged. [SRC-01, activity 5]

### 6. Define control point
Every step must have a control point. [SRC-01, activity 6]
Possible control types include:
- Control Agent
- Deterministic rule
- Human review
- Human approval
- Audit check
- Embedded control  
[SRC-01, activity 6]

### 7. Create Framework for each agent
For every agent, document at least:
- purpose;
- inputs;
- outputs;
- behaviour;
- exceptions;
- controls;
- human interaction.  
[SRC-01, activity 7]

### 8. Assess reuse using ABBA
- Search ABBA for relevant assets. [SRC-01, activity 8]
- Record reuse assessment as one of:
  - Reused unchanged
  - Adapted
  - Combined
  - No suitable asset
  - New design  
  [SRC-01, activity 8]
- Record any variance from the business requirement. [SRC-01, activity 8]

## Workflow modelling rules
The workflow model must:
- represent the business capability end to end;
- remain at business-operating level rather than UI-click or implementation level; [SRC-01, Practitioner guidance]
- include workflow purpose, inputs, outputs, decisions, exceptions, controls, and handovers;
- distinguish human-performed, agent-supported, and control activities;
- show how each step connects to previous and next steps.

### Standard operation field
Every workflow step record must include an explicit `Operation` field using only one or more of the following values:
- `Create`
- `Read`
- `Update`
- `Delete`
- `Transmit`
- `Validate`
- `Approve`
- `Derive`

Do not leave CRUD behaviour implicit in narrative text.

## Reuse assessment guidance
Use the ABBA catalogue to identify candidate reusable agents relevant to the capability under analysis.

At minimum, assess relevance using:
- business process;
- taxonomy;
- end-to-end value stream;
- agent type;
- agent description.

Record for each candidate:
- AgentID;
- Agent name;
- Agent type;
- capability relevance;
- reuse assessment outcome;
- required adaptation or variance;
- evidence reference.

Examples from the provided ABBA catalogue include payroll-related reusable candidates such as:
- `VA-1246 Payroll data validator` [SRC-03, row 323]
- `VA-1248 Automated payroll calculations agent` [SRC-03, row 325]
- `VA-1249 Payroll administration workflow manager` [SRC-03, row 326]
- `VA-1252 Payroll compliance monitor` [SRC-03, row 329]
- `VA-1253 Payroll experience agent` [SRC-03, row 330]

These examples illustrate how to identify relevant assets; they must not be assumed applicable outside the supported capability context.

## Required section guidance

### 1. Executive Summary
Summarise:
- the capability or business agent classified;
- scope boundary;
- total agents identified and classification mix;
- major controls and approval themes;
- reuse outcomes;
- principal assumptions, constraints, open questions, and gaps.

### 2. Overall AI Framework
Describe:
- the logical agent landscape;
- principal actors and entry points;
- grouping of agents by type;
- internal orchestration model;
- relationship of controls to workflow;
- where human approvals and interventions occur.

### 3. End-to-End Workflow
Describe:
- workflow trigger;
- normal flow;
- major decisions;
- exception routes;
- control points;
- end-state outcomes.

### 4. Workflow Decomposition Catalogue
For each workflow step, include at least:
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
- Related decision IDs
- Related exception IDs
- Assigned or candidate agent
- Agent type
- Control point(s)
- Evidence reference

### 5. Handover and Interaction Register
For each handover, include at least:
- Handover ID
- Source step or source agent
- Destination step or destination agent
- Information or artefact transferred
- Producing performer
- Consuming performer
- Control owner
- Preconditions
- Postconditions
- Failure mode
- Evidence reference

### 6. Decision Catalogue
For each decision, include at least:
- Decision ID
- Decision name
- Triggering step
- Decision question
- Decision logic or criteria
- Required evidence
- Decision owner
- Approval requirement
- Possible outcomes
- Downstream impact
- Evidence reference

### 7. Exception Catalogue
For each exception, include at least:
- Exception ID
- Exception name
- Trigger condition
- Affected step(s)
- Severity or priority
- Containment action
- Escalation route
- Resolution owner
- Closure criteria
- Evidence reference

### 8. Human Intervention Points
For each intervention point, include at least:
- HIP ID
- Human role
- Trigger
- Required action
- Reason human judgement is needed
- Input artefacts
- Output artefacts
- Approval or control linkage
- Timing expectation if known
- Evidence reference

### 9. SME Validation and Confirmation
Document:
- expected review participants;
- review purpose;
- evidence completeness checks;
- unresolved issues;
- formal validation statements required;
- residual risks or dependencies.

### 10. Stage 4 to Stage 5 Handover
Specify what is passed into Stage 5, including:
- approved Stage 4 agent model;
- workflow decomposition catalogue;
- decision catalogue;
- exception catalogue;
- handover and interaction register;
- control and approval map;
- reuse assessment and variance log;
- outstanding assumptions, constraints, open questions, and gaps.

## Rules for assumptions, constraints, open questions, and missing information
Maintain explicit registers for:
- Assumptions
- Constraints
- Open Questions
- Gaps / Missing Information

Rules:
- Every assumption must be necessary, minimal and clearly labelled.
- Every constraint must describe how the deliverable is limited.
- Every open question must identify what evidence or decision is still required.
- Every gap must reference the impacted section(s) and effect on completeness or confidence.
- No `TBC` marker may remain unregistered.

## Governance controls and human approvals
The deliverable must:
- ensure every workflow step has a control point; [SRC-01, activity 6; SRC-01, Common pitfalls]
- identify whether the control is a control agent, deterministic rule, human review, human approval, audit check, or embedded control; [SRC-01, activity 6]
- show where human reviews or approvals are required; [SRC-01, activity 2; SRC-01, Common pitfalls]
- keep controls proportionate to risk; [SRC-01, Key success factors]
- keep handovers unambiguous; [SRC-01, Key success factors]
- prefer reuse where possible and design only when necessary. [SRC-01, Key success factors]

## Validation and quality gates before completion
Do not mark the deliverable complete until all quality gates below have passed.

### Quality gate 1: Source completeness
- Source register created.
- Source hierarchy applied correctly.
- All mandatory sources reviewed or logged as missing.

### Quality gate 2: Structural completeness
- Required headings present.
- Required Stage 4 outputs included.
- Appendix order correct.

### Quality gate 3: Evidence traceability
- Every factual table row contains at least one evidence citation.
- Narrative claims are cited where practical.
- Example-derived patterns are not presented as unsupported facts.

### Quality gate 4: Identifier integrity
- All identifiers are unique.
- Cross-references resolve.
- Handover sources and destinations are valid.

### Quality gate 5: Governance completeness
- Every workflow step has a control point.
- Human reviews and approvals are explicit.
- Ownership roles remain distinct.

### Quality gate 6: Reuse discipline
- ABBA has been searched.
- Reuse outcome recorded.
- Variances from business needs captured.

### Quality gate 7: Document readiness
- File name conforms.
- Markdown tables are valid.
- No unregistered `TBC` markers remain.
- UK spelling applied where practical.

## Formal validation checklist
Use this checklist before final completion.

| Check ID | Validation check | Pass criteria |
|---|---|---|
| VAL-01 | Required headings | All mandated headings present |
| VAL-02 | Appendix order | Appendices appear in required order |
| VAL-03 | Identifier uniqueness | No duplicate IDs across W/A/H/D/E/HIP/C/ASM/CON/OQ/GAP |
| VAL-04 | Broken cross references | Every referenced identifier exists |
| VAL-05 | Handover validity | Each handover source and destination exists in the workflow or agent model |
| VAL-06 | Gap references | Each gap references impacted section(s) |
| VAL-07 | TBC registration | No unregistered `TBC` markers remain |
| VAL-08 | Filename conformity | File name matches required pattern |
| VAL-09 | Markdown table structure | Tables have valid headers and separators |
| VAL-10 | Evidence coverage | Every factual table row has at least one evidence citation |
| VAL-11 | UK spelling | UK English applied where practical |

## Validation script template
Use or adapt the following validation script where automated checking is required.

```python
from __future__ import annotations
import re
from pathlib import Path

REQUIRED_HEADINGS = [
    "# Executive Summary",
    "# Overall AI Framework",
    "# End-to-End Workflow",
    "# Workflow Decomposition Catalogue",
    "# Handover and Interaction Register",
    "# Decision Catalogue",
    "# Exception Catalogue",
    "# Human Intervention Points",
    "# SME Validation and Confirmation",
    "# Stage 4 to Stage 5 Handover",
    "# Appendices",
]

ID_PATTERNS = {
    "W": r"\bW-\d{3}\b",
    "A": r"\bA-\d{3}\b",
    "H": r"\bH-\d{3}\b",
    "D": r"\bD-\d{3}\b",
    "E": r"\bE-\d{3}\b",
    "HIP": r"\bHIP-\d{3}\b",
    "C": r"\bC-\d{3}\b",
    "ASM": r"\bASM-\d{3}\b",
    "CON": r"\bCON-\d{3}\b",
    "OQ": r"\bOQ-\d{3}\b",
    "GAP": r"\bGAP-\d{3}\b",
}

EVIDENCE_PATTERN = re.compile(r"\[SRC-\d{2},[^\]]+\]")
TBC_PATTERN = re.compile(r"\bTBC\b")
TABLE_ROW_PATTERN = re.compile(r"^\|.*\|\s*$")
REFERENCE_PATTERN = re.compile(r"\b(?:W|A|H|D|E|HIP|C|ASM|CON|OQ|GAP)-\d{3}\b")


def find_duplicates(values: list[str]) -> list[str]:
    seen = set()
    duplicates = set()
    for value in values:
        if value in seen:
            duplicates.add(value)
        seen.add(value)
    return sorted(duplicates)


def main(file_path: str) -> int:
    text = Path(file_path).read_text(encoding="utf-8")
    lines = text.splitlines()
    errors: list[str] = []

    for heading in REQUIRED_HEADINGS:
        if heading not in text:
            errors.append(f"Missing heading: {heading}")

    declared_ids: set[str] = set()
    for label, pattern in ID_PATTERNS.items():
        matches = re.findall(pattern, text)
        duplicates = find_duplicates(matches)
        if duplicates:
            errors.append(f"Duplicate {label} IDs: {', '.join(duplicates)}")
        declared_ids.update(matches)

    for ref in sorted(set(REFERENCE_PATTERN.findall(text))):
        if ref not in declared_ids:
            errors.append(f"Broken cross reference: {ref}")

    for i, line in enumerate(lines, start=1):
        if TBC_PATTERN.search(line) and not re.search(r"\b(?:GAP|OQ)-\d{3}\b", line):
            errors.append(f"Unregistered TBC marker at line {i}")

    for i, line in enumerate(lines, start=1):
        if TABLE_ROW_PATTERN.match(line) and not line.startswith("|---"):
            if i >= 3 and TABLE_ROW_PATTERN.match(lines[i-2]):
                if not EVIDENCE_PATTERN.search(line):
                    errors.append(f"Possible missing evidence citation in table row at line {i}")

    if errors:
        print("VALIDATION FAILED")
        for error in errors:
            print(f"- {error}")
        return 1

    print("VALIDATION PASSED")
    return 0


if __name__ == "__main__":
    raise SystemExit(main("Stage4_Classify.md"))
```

## Acceptance criteria
The Stage 4 deliverable is acceptable only if:
- it is written in Markdown only;
- it is reusable for any business capability or business agent;
- it follows the Stage 4 methodology source precedence;
- it includes all mandatory Stage 4 outputs;
- it includes the review-ready governance sections listed above;
- it uses the evidence citation standard consistently;
- it applies explicit operation values;
- it preserves ownership distinctions;
- it includes validation and quality gates;
- it is suitable for SME review and Stage 5 handover.
