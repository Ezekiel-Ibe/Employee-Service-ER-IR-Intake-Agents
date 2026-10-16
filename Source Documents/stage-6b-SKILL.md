---
name: stage-6b-solution-design-consolidation-generator
description: "Consolidate approved Stage 6 component designs into one coherent, end-to-end, review-ready Stage 6B Solution Design Consolidation deliverable in Markdown, for any business capability or business agent in the Agent Factory Delivery Methodology. Use when asked to assemble component designs, validate end-to-end workflow, orchestration, handovers, control coverage, exception paths, human intervention consistency or unit-test coverage, assess build readiness, recommend implementation technology, or prepare a design package for Design Authority review."
version: "1.0"
license: "KPMG internal use - KPMG confidential"
metadata:
  methodologyVersion: "Agent Factory Delivery Methodology - Stage 6B (Solution Design Consolidation)"
  instructionsFile: "stage-6b-document-generation.instructions.md"
  instructionsVersion: "1.0"
  templateVersion: "Stage 6B Markdown structure 1.0"
  validationScriptVersion: "stage6b-validate 1.0"
  authoritativeSource: "DeliveryControl/Stage_6_Decompose_Infographic.md, section 6B"
---

# Stage 6B - Solution Design Consolidation Generator

## 1. Purpose

Produce a consolidated, end-to-end, review-ready Stage 6B Solution Design Consolidation deliverable in Markdown that:

- brings every Stage 6 component design together into one coherent solution;
- demonstrates, with evidence, that the solution meets the business outcome and aligns to the Overall AI Framework;
- evidences control coverage, exception handling, human intervention consistency and unit-test sufficiency end to end;
- states readiness honestly against the Stage 6B controls, evidence requirements and exit criteria;
- is fully traceable to supplied sources, with no fabricated content and no unsupported approval or readiness claim.

This skill executes the procedure. Output format, naming, source precedence, governance constraints and the stage boundary are defined in `stage-6b-document-generation.instructions.md` and are binding.

## 2. Activation criteria

Activate when the user asks to:

- generate, update or reissue a Stage 6B Solution Design Consolidation deliverable;
- assemble or consolidate multiple Stage 6 component designs into a single end-to-end design;
- validate end-to-end workflow flow, inputs and outputs across steps, internal orchestrations, workflow handovers, control coverage, exception paths and escalations, human intervention consistency, or unit-test coverage across a whole solution;
- confirm alignment of a consolidated design with the Overall AI Framework and the business outcome;
- produce a control coverage map, unit-test coverage assessment, readiness assessment, or consolidation issues, risks and actions log;
- recommend an implementation technology for an approved logical design;
- prepare a design package for Factory Design Authority review, or confirm readiness for Stage 7 - Build.

Do not activate for Stage 3 decomposition, Stage 4 classification or internal orchestration design, Stage 5 / 5B data modelling, Stage 6 component-level design, or Stage 7 build.

## 3. Understanding required before consolidation

Establish and record an evidenced understanding of each concept below before drafting. Where any is absent, record it as a gap; never infer it.

| Concept | What must be understood | Where normally evidenced |
| --- | --- | --- |
| Overall AI Framework | Solution-level framework the whole capability must conform to: purpose, guardrails, data handling, grounding, assurance expectations | Stage 3 / 4 framework artefact |
| Component AI Frameworks | Per-component application of the framework, including model use, prompt governance, grounding and citation rules | Stage 6 component designs |
| Agent classifications | Task, Insight, Orchestration, Control, Experience - per component, with rationale | Stage 4 classification artefact |
| Control points | Control definition, operation, frequency, evidence and audit trail for each workflow step | Control point definitions; Stage 6 control designs |
| ABBA reuse assessment outputs | Which assets are reused, adapted or newly built, and the design and test consequences | ABBA reuse assessment |
| Business rules and constraints | Deterministic rules, thresholds, tolerances, regulatory and policy constraints | Business rules repository; Stage 6 deterministic logic |
| SME-confirmed workflow definitions | The agreed end-to-end workflow, step sequence, actors, triggers and outcomes | SME-confirmed workflow artefact |
| Approved end-to-end data model | Entities, attributes, keys and lineage used by step inputs and outputs | Stage 5B data model |

## 4. Input discovery procedure

1. Establish the capability or agent name and identifier from the user request or the working folder.
2. Enumerate the working folder and any user-supplied paths. Identify candidate sources by **content and purpose**, not filename alone.
3. Classify each discovered file:
   - **Required inputs:** Stage 6B panel of the methodology infographic; capability or agent identity; all Stage 6 component designs; Stage 6 unit test scenarios; SME-confirmed end-to-end workflow; approved Stage 5B data model; control point definitions; ABBA reuse assessments; Overall AI Framework.
   - **Optional inputs:** separately stated Component AI Frameworks; business rules repository extract; approved organisational technology standards or constraints; prior SME or Design Authority review notes; fillable Stage 6 / 6B template; a completed Stage 6B example deliverable (reference only); approval or decision records; existing issue or risk logs.
4. Register every source in the Source Inventory as `SRC-nn` with title, path, version, date, type, approval status, approval evidence and the purpose for which it is used.
5. Ask the user only for genuinely blocking items (section 5). For non-blocking gaps, proceed and log.
6. Never treat a source as approved on inference. Record `Approval status: Not evidenced` where no qualifying evidence exists and raise a `CIA-nn` item.

## 5. Sufficiency and blocker logic

**Blocking - stop and request input:**

- No Stage 6 component designs, or equivalent component-level design evidence, exist for the capability; there is nothing to consolidate.
- No capability or agent identity can be established.
- The only available design material is an example deliverable for a different capability.

**Non-blocking - proceed, mark, log:**

- Unit test scenarios missing for some components.
- Control definitions missing for some workflow steps.
- ABBA reuse assessment, Overall AI Framework statement or data model detail incomplete.
- No approval or review evidence supplied.
- No technology standards or constraints supplied.

For every non-blocking gap: mark the affected field `TBC - source required`; raise a `CIA-nn` entry naming the missing fact, the impacted section, workflow step or component, the owner (`TBC - source required` where unevidenced), the required action and the readiness impact.

## 6. Extraction and normalisation

1. **Extract** from each source: components, workflow steps, inputs and outputs, internal orchestration paths, handovers, controls, exception paths, escalations, human intervention points, unit tests, assumptions, risks, dependencies and decisions.
2. **Normalise identifiers** to the defined formats (`CMP-nn`, `WF-nn`, `Hnn`, `Cnn`, `EXC-nn`, `HIP-nn`, `UT-nn`, `SRC-nn`, `CIA-nn`, `ASM-nn`, `DEC-nn`). Always reuse the identifier already assigned in an approved source and record any source alias alongside the normalised identifier.
3. **Normalise terminology** across components: one term per concept for entities, statuses, actors, response types and control names. Record every terminology conflict as a `CIA-nn` item rather than silently standardising a contested term.
4. **Record evidence** for every extracted fact at the most precise available location, for example `[SRC-02, section 5.3]`, `[SRC-04, table Handover Register, H03]`, `[SRC-06, worksheet Test Scenarios, row 42]`, `[SRC-07, Stage 6B panel, Actions 1-11]`.
5. **Do not merge** two source records into one unless the sources state they are the same; otherwise keep both and log the ambiguity.
6. **Do not extend the baseline silently.** Newly-identified handovers and controls follow the proposed-record rules in the instructions file (`H-PROP-nn`, `C-PROP-nn`; `Proposed`; `Pending Stage 6 owner confirmation`; `Linked to CIA-nn`; not part of the approved baseline until formally accepted).

## 7. End-to-end consolidation workflow

Execute in order. Steps map one-to-one to Stage 6B Actions 1-11 in the infographic.

1. **Assemble all component designs.** Build the Component Consolidation Matrix: component, classification, purpose, trigger, owner, source, evidence reference, consolidation status.
2. **Validate end-to-end workflow flow.** Sequence every `WF-nn` from trigger to business outcome. Identify orphan steps, unreachable steps, loops without exit and missing terminations. Render a Mermaid flow diagram.
3. **Validate inputs and outputs across steps.** Confirm each step's outputs satisfy the next step's inputs and that every field traces to a Stage 5B entity and attribute. Log every break in data continuity.
4. **Validate internal orchestrations.** Confirm intra-component orchestration from Stage 4 / 6 is consistent with the consolidated flow, and that decision branches are complete and, where required, mutually exclusive.
5. **Validate workflow handovers.** For each handover record sending and receiving component, trigger, payload, acknowledgement, failure behaviour and SLA where evidenced. Required but undefined handovers become `H-PROP-nn` proposed records.
6. **Validate control coverage for every step.** Build the Control Coverage Map: every `WF-nn` appears with its control or controls, control type, operation, frequency, evidence, audit trail and owner. Uncontrolled steps are blocking items. Required but undefined controls become `C-PROP-nn` proposed records.
7. **Validate exception paths and escalations.** Confirm each step has defined failure behaviour, an exception path, an escalation route and a resolution outcome. Log unhandled exception classes.
8. **Validate human intervention consistency.** Confirm every `HIP-nn` has a consistent trigger, role, decision rights, timebox, fallback and evidence capture across components. Log divergent patterns for the same decision type.
9. **Validate unit-test coverage is sufficient.** Build the Unit-Test Coverage Assessment mapping every component, workflow step, control, handover, exception path and human intervention point to `UT-nn` tests covering normal and exception scenarios. Identify untested items as gaps.
10. **Confirm alignment with the Overall AI Framework and business outcome.** State, with evidence, how the consolidated design satisfies the framework and delivers the stated outcome. Log every unproven alignment claim.
11. **Document open issues and required actions.** Consolidate everything logged into the Consolidated Issues, Risks and Actions Log (`CIA-nn`) with type, description, impacted section or step, severity, blocking flag, owner, required action, status and evidence reference.

Throughout, apply the practitioner guidance: think end-to-end, not component by component; challenge assumptions; ensure consistency of language, responses and controls; confirm the user journey is coherent; validate that nothing is missed across data, control, handover and exception; and prepare explicitly for Design Authority review.

## 8. How and when to open supporting resources

- **Always open first:** the Stage 6B panel of `DeliveryControl\Stage_6.md`, to anchor Objective, Inputs, Actions, Outputs, Practitioner Guidance, Controls and Evidence, Exit Criteria, Design Authority approval and Deliverable.
- **Open in full before drafting:** all Stage 6 component designs, unit test scenarios, SME-confirmed workflow, control point definitions, Stage 5B data model, ABBA reuse assessment and the Overall AI Framework.
- **Open during the relevant step only:** business rules and constraints (steps 3-4); technology standards or constraints (Recommended Implementation Technology only); prior review notes (Readiness Assessment).
- **Open last, for structure only:** the fillable template and any completed example deliverable, such as `Reference/O2C-Deliverables/O2C_Capability_and_Agent_Catalogue_v1.md`. Read them only after evidence-based content exists, to compare structure, ordering, tone and depth. Never return to them for facts.
- **Never open** artefacts from other capabilities or clients as a content source.

## 9. Validation execution

After assembling all sections, run the validation checker and record its outcome in Document Control. Checks:

1. Valid YAML frontmatter on generated framework files; complete document control block on the deliverable.
2. Required headings present, correctly spelled and in the mandated order.
3. Filename conformity with the naming convention.
4. All identifiers unique.
5. All identifiers conform to the defined formats, including `H-PROP-nn` and `C-PROP-nn`.
6. No broken cross-references; every referenced identifier and anchor exists.
7. No unregistered `TBC - source required` marker; each has a `CIA-nn`, an impacted item and a stated readiness impact.
8. Every `CIA-nn` reference resolves to a log entry, and every log entry is referenced where relevant.
9. Every workflow step appears in the control coverage map.
10. Every handover appears in the unit-test coverage assessment.
11. Every component appears in the component consolidation matrix.
12. Every factual table row contains an evidence reference at the most precise available location.
13. Design Authority status is not recorded as approved without qualifying approval evidence; likewise consolidation review, SME visibility, alignment to business outcome, "all items resolved" and "build ready".
14. All Markdown tables are valid and complete, with consistent column counts and header and separator rows.
15. All Mermaid blocks use valid syntax.
16. No unresolved template text, bracket tokens or prompts remain.
17. UK-English conformance where practical; flag exceptions.
18. Contents regenerated from the final headings, with every anchor resolving.

Re-run after any fix. Record: checks run; pass or fail per check; failures remaining with their `CIA-nn` links; validation-script version.

## 10. Output assembly

Assemble the mandatory sections in the order defined in the instructions file. Section content requirements:

- **Document Control** - skill name and version; instruction-file version; methodology version; template version; generation date; execution environment; source-pack fingerprint or source list; validation-script version; validation outcome; deliverable status; classification `KPMG confidential`.
- **Contents** - generated from the final headings after assembly.
- **Executive Summary** - purpose, scope, consolidation outcome, readiness status, count of blocking items, key decisions required.
- **Stage 6B Objective and Scope** - from the infographic Stage 6B panel, with in-scope and out-of-scope components.
- **Source Inventory and Evidence Map** - `SRC-nn` register with version, date, approval status, approval evidence and use.
- **Consolidated Solution Design** - component consolidation matrix; consolidated behaviour narrative; consolidated data flow against the Stage 5B model; terminology, response and control consistency findings.
- **End-to-End Orchestration Assurance** - end-to-end flow diagram; internal orchestration validation; handover register including proposed records; exception and escalation validation; human intervention consistency.
- **Consolidated Control Coverage** - control coverage map keyed by `WF-nn`; coverage summary; uncontrolled steps; proposed controls.
- **Unit-Test Coverage Assessment** - coverage matrix by component, step, control, handover, exception and human intervention point; normal and exception scenario coverage; gaps.
- **Readiness Assessment** - position against each Stage 6B exit criterion (all items resolved; Design Authority approval; build ready confirmed; deliverable ready for onward use), each evidenced or marked `Pending - evidence required`.
- **Consolidated Issues, Risks and Actions Log** - the full `CIA-nn` register.
- **Recommended Implementation Technology** - reasoned recommendation, options considered, evaluation criteria, dependencies, constraints and open decisions; all other sections remain technology-agnostic.
- **Controls, Evidence and Exit Criteria** - consolidation review by design lead; SME visibility; Design Authority review and approval; evidence of alignment to business outcome; each with status and evidence reference.
- **Assumptions, Dependencies and Limitations** - `ASM-nn` register with evidence status and challenge outcome.
- **Appendices** - diagrams, matrices and glossary.

Write supporting artefacts as separate Markdown files using the defined naming convention and cross-reference them from the deliverable.

## 11. Partial-completion behaviour

Where evidence is insufficient for full consolidation but not blocking:

- generate every section that can be supported, and retain every mandatory section with an explicit statement of what is missing;
- use `TBC - source required` only under the registered-marker rules;
- set the status to `Draft` where mandatory extraction is incomplete, or `Not Build Ready` where the structure is complete but blocking items remain;
- list, in the Executive Summary, the specific inputs required to progress and their owners where evidenced.

Never fabricate content to complete a section.

## 12. Completion response

On completion, report:

1. Files created, with paths.
2. Deliverable status from the status model, with the reason.
3. Counts: components consolidated; workflow steps; controls mapped; uncontrolled steps; handovers, baseline and proposed; exception paths; human intervention points; unit tests mapped; coverage gaps; `CIA-nn` items split into blocking and non-blocking.
4. Validation outcome: checks run, pass or fail, and any remaining failures with their `CIA-nn` links.
5. Exit-criteria position: all items resolved (yes or no); Design Authority approval (evidenced or pending); build ready (confirmed or not confirmed).
6. The specific inputs or decisions needed next.

Do not claim approval, sign-off or build readiness that is not evidenced.

## 13. Failure handling

- **Unreadable or inaccessible source:** record it in the Source Inventory as unreadable, raise a `CIA-nn` item, continue with the remaining sources and state the impact.
- **Conflicting sources:** apply the source hierarchy, raise a `CIA-nn` item recording both positions, and continue without silently resolving.
- **Ambiguous identifier mapping:** retain both identifiers, mark the mapping unconfirmed, raise a `CIA-nn` item.
- **Validation check cannot pass because evidence is absent:** record it as a blocking `CIA-nn` item and set the status accordingly; never suppress the check.
- **Request to copy example content, assert approval without evidence, or assign an unevidenced owner:** decline, explain the governance rule, and offer the compliant alternative of `TBC - source required` plus a logged action.
- **Blocking input missing:** stop, state precisely what is required and why, and do not generate a speculative deliverable.

---

**Classification:** KPMG confidential
