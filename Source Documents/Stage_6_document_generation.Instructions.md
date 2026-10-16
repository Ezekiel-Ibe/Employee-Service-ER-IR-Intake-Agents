---
applyTo: "**/*.md"
description: "Repository-level governance rules for generating, reviewing, validating and assessing Stage 6 Agent Factory detailed-design deliverables."
---

# Stage 6 document-generation instructions

## Applicable paths

These rules govern Stage 6 work performed anywhere in this repository and, in particular:

- source packs used to prepare a Stage 6 design;
- Stage 6 Markdown deliverables and their supporting registers;
- reviews, validations, gap analyses and Stage 6B readiness assessments;
- the reusable Stage 6 workflow in `Script\Stage 6\Skills\Stage_6_SKILL.md`.

Use these rules for any business capability, business agent, component, control or workflow handover. Generate Markdown (`.md`) unless the user explicitly requests another format.

## Authoritative sources and precedence

Apply the following hierarchy from highest to lowest precedence:

1. The supplied approved Agent Factory methodology, with `DeliveryControl/Stage_6.md` as the repository authority for Stage 6 objective, inputs, actions, outputs, practitioner guidance, controls and evidence, exit criteria and deliverable.
2. Approved engagement-specific business evidence, including SME-confirmed workflow definitions, business rules, policies, constraints, control requirements and approval records.
3. Approved Overall AI Framework and Component AI Frameworks.
4. Approved Stage 4 classifications, internal orchestration, workflow, handovers and control-point outputs.
5. Approved Stage 5B end-to-end data model, including entities, attributes, relationships, ownership, lineage and data gaps.
6. Approved ABBA assets and the applicable ABBA reuse assessment or catalogue.
7. Approved templates, Agent Factory standards and pattern libraries.
8. Completed Stage 6 examples, including `Reference/PAA-Deliverables/Stage6/Payroll_Assurance_Agent_Stage_6A_Updated_Detailed_Design.md`, for structure, ordering, writing style and expected depth only.
9. The current task brief for output location, scope and user-specific requirements, provided it does not contradict an approved governance source.

The embedded methodology summary in any prompt or generated document is a navigation aid only. If it differs from the supplied approved methodology, the approved methodology governs. Record the difference, decision and impact in the source inventory/evidence map; never silently reconcile conflicting sources.

Do not treat an example, template, previous deliverable or ABBA catalogue entry as factual evidence for the capability being designed. Do not copy example content unless the same fact is independently supported by the current source pack.

If sources at the same precedence conflict, preserve both statements, mark the affected item `TBC - source required`, classify its severity, and request clarification from the appropriate accountable role. Never choose a convenient interpretation without evidence.

## Required naming and identifier conventions

- Write in UK English.
- Use the deliverable filename pattern `<Capability-or-Agent-ID>_<Capability-or-Agent-Name>_Stage_6_Detailed_Design_v<major>.<minor>.md` unless the user provides an approved naming standard.
- Replace spaces and unsupported filename characters with underscores; preserve approved identifiers exactly.
- Do not renumber inherited identifiers. Carry Stage 4 and Stage 5B identifiers unchanged and record any source aliases.
- Allocate new identifiers sequentially and uniquely within the deliverable:
  - `SRC-###` source;
  - `CMP-###` design component when no approved component ID exists;
  - `W-###` workflow step only when no inherited workflow ID exists;
  - `BR-###` business or deterministic rule;
  - `AI-###` AI instruction or prompt specification;
  - `RSP-###` response design;
  - `EX-###` exception;
  - `HIP-###` human intervention point;
  - `C-###` control;
  - `INT-###` integration;
  - `H-###` workflow handover;
  - `UT-###` unit-test scenario;
  - `ABBA-###` reuse assessment;
  - `ASM-###` assumption;
  - `CON-###` constraint;
  - `OQ-###` open question;
  - `RSK-###` risk;
  - `GAP-###` gap or missing-information item;
  - `VAL-###` validation check;
  - `ACT-###` action.
- Cross-references must resolve to one defined record. IDs must not be reused for different records.
- Use source citations in the form `[SRC-###, precise section/table/row]`. A path alone is not precise evidence where a section, table or row can be named.

## Non-negotiable governance rules

### Stage 6 scope and design stance

- Design the **what**, not the implementation **how**.
- Produce detailed, technology-agnostic logical design. Do not select products, hosting, model vendors, programming languages, APIs, deployment patterns or physical infrastructure unless an approved Stage 6 source explicitly requires them; record such implementation matters for Stage 6B or later.
- Focus on business capability decomposition, component behaviour, logical data, decisions, controls, exceptions, handovers, human accountability and testable outcomes.
- Review the Overall AI Framework, every applicable Component AI Framework, agent classification and Stage 4 internal orchestration before elaborating component behaviour.
- Trace every input and output to the approved Stage 5B data model. Use catalogue-exact entity and attribute names. If no approved mapping exists, record `TBC - source required` and a classified gap; do not invent a canonical entity.
- Define a control for every workflow step and specify objective, trigger, operation, owner, mode, evidence produced, failure response and linked tests.
- Assess every identified candidate capability for ABBA reuse. Catalogue similarity is not evidence that reuse is approved or technically viable.
- Define normal and exception unit-test scenarios for every design component.
- State every human interaction and approval explicitly. An agent may prepare, recommend, route or record a decision but must not assume human accountability or approval authority.
- Maintain segregation of duties between recommendation, approval, consequential action and evidence review where supported by the control model.

### Evidence and unsupported information

- Every factual assertion, design choice, table row and validation result must cite supporting source material or the generated deliverable section that proves it.
- An Evidence column must contain factual support from the generated document; it must not merely repeat the status.
- Never report `Pass` unless the cited evidence is present and demonstrates the check.
- Where evidence is unavailable, use the exact text `TBC - source required` and create a linked register entry classified as:
  - **Critical** — absence could invalidate the design, breach a mandatory control, remove required approval, create material regulatory/operational exposure, or prevent safe Stage 6B progression;
  - **Major** — material incompleteness requiring resolution or an accepted action before build readiness, but not necessarily preventing a controlled Stage 6B review;
  - **Minor** — limited clarification or presentational incompleteness with no material effect on design integrity.
- A TBC does not automatically prevent Stage 6B progression. The readiness decision must consider severity, affected controls, owner, action, due point and accepted risk.
- Do not invent owners, approval, review completion, dates, thresholds, policies, data mappings, test results or ABBA suitability.
- Record assumptions as assumptions, not facts. Each assumption requires rationale, impact, validation owner, validation action, due point, status and evidence.
- Keep separate controlled registers for assumptions, constraints, open questions, risks and missing information. Cross-link related entries rather than combining their meanings.
- Request clarification where missing or conflicting information materially affects the requested result. Until clarified, retain a controlled TBC rather than making an unsupported assumption.

### Roles, responsibilities and accountability

Every Stage 6 deliverable must include a RACI matrix covering every workflow activity. Use only evidenced role names; unknown roles are `TBC - source required` and linked to a gap.

RACI rules:

- **Responsible (R):** performs or coordinates the activity; one or more allowed.
- **Accountable (A):** owns the outcome or approval; exactly one per activity unless an approved governance source explicitly defines joint accountability.
- **Consulted (C):** provides required two-way input before completion.
- **Informed (I):** receives the outcome or evidence.
- Human accountability cannot be assigned to an AI agent.
- Component execution responsibility does not imply business accountability.
- Recommendation and approval must remain distinct where a consequential decision is involved.
- The RACI must reconcile with human intervention, control-owner, data-owner, handover producer/consumer and approval records.

At minimum, consider these roles where they exist in evidence: business/capability owner, business SME, process owner, component performer, human approver, control owner, data owner, data steward, source-system owner, risk/compliance reviewer, Design Lead, peer reviewer and Factory Design Authority. Do not add them if the source pack does not establish their relevance.

### Required quality measures

Calculate each applicable measure using explicit numerator, denominator, percentage, status and evidence. Do not exclude an item from the denominator without documenting the non-applicability rationale.

- **Traceability** = design elements with at least one valid source reference ÷ total applicable design elements × 100.
- **Data Model Alignment** = inputs and outputs mapped to approved data-model entities ÷ total documented inputs and outputs × 100.
- **Human Intervention Coverage** = human intervention points with roles, responsibilities and outcomes defined ÷ total identified human intervention points × 100.
- **Unit Test Coverage** = design components with both normal and exception test scenarios ÷ total design components × 100.
- **ABBA Reuse Assessment Coverage** = candidate capabilities reviewed for ABBA reuse ÷ total candidate capabilities identified × 100.
- **Control Coverage** = workflow steps with mapped controls ÷ total workflow steps × 100.
- **Workflow Handover Coverage** = workflow handovers with producer, consumer, payload and control defined ÷ total workflow handovers × 100.
- **RACI Coverage** = workflow activities with a complete RACI assignment ÷ total workflow activities × 100.

Status thresholds for every measure:

- **Pass:** 100%.
- **Partial:** 80–99%.
- **Fail:** below 80%.

Show counts as well as rounded percentages. A mathematically calculated Pass is not an approval and must not be presented as one. If the denominator is zero, report `Not applicable`, explain why and do not report 100%.

### Mandatory controls, evidence and acceptance gates

Before completion, validate and evidence:

- design peer review;
- unit-test coverage review;
- control-point validation;
- SME visibility;
- ABBA reuse assessment;
- assumption and risk log;
- source hierarchy and conflict handling;
- data-model mapping;
- identifier uniqueness and cross-reference integrity;
- complete RACI and human approval boundaries;
- workflow/control/handover reconciliation;
- all eight measurable coverage calculations;
- absence of unsupported Pass or approval claims.

A review-ready Stage 6 deliverable must demonstrate or accurately report the status of these exit criteria:

1. all components have detailed designs;
2. every component has normal and exception unit-test scenarios;
3. all controls and workflow handovers are designed;
4. the package is ready for Stage 6B Solution Design Consolidation, with any residual TBCs classified and governed.

Do not claim Stage 6 completion, SME approval, peer review or Stage 6B readiness without evidence. Use `Partial`, `Fail`, `Not evidenced` or `TBC - source required` as appropriate.

## Output format

Stage 6 deliverables must be review-ready Markdown and include, at minimum:

1. YAML frontmatter and document control;
2. executive summary, scope and success criteria;
3. source inventory, hierarchy and evidence map;
4. framework, classification and Stage 4 orchestration review;
5. purpose, triggers, objectives and user stories;
6. end-to-end workflow and component inventory;
7. detailed behaviour for every component;
8. input/output mapping to the approved Stage 5B data model;
9. deterministic logic specifications;
10. AI instructions and prompts where applicable, including grounding, prohibited behaviour and human boundary;
11. response and citation designs;
12. exception handling and escalation designs;
13. human intervention and approval designs;
14. control operation, audit evidence and control-to-step mapping;
15. logical integration specifications;
16. workflow handover specifications with producer, consumer, payload and control;
17. unit-test scenarios and expected results for normal and exception cases;
18. ABBA reuse assessment and variance decisions;
19. RACI matrix;
20. assumptions, constraints, open questions, risks, missing information and actions;
21. coverage metrics and quality-gate results;
22. Stage 6 controls-and-evidence assessment;
23. exit-criteria and Stage 6B readiness assessment;
24. appendices and traceability matrices as needed.

Tables that make factual or validation claims must include an Evidence column. The final section must state overall status, unresolved Critical/Major/Minor items, required human approvals and the evidence-based Stage 6B recommendation.

## Stage boundary

Stage 6 converts the logical architecture and approved data model into detailed logical designs specifying behaviour, data, controls, exceptions, human interactions, integrations, workflow handovers and tests. It does not:

- consolidate all designs into the final end-to-end solution design;
- select or recommend implementation technology;
- define physical APIs, infrastructure, deployment or build configuration;
- implement components or execute production tests;
- grant Design Authority approval.

Those matters belong to Stage 6B or later unless the governing approved methodology explicitly states otherwise. Stage 6B readiness assessment may identify what remains for consolidation but must not perform or claim the Stage 6B approval itself.

## Relevant skill

Use `Script\Stage 6\Skills\Stage_6_SKILL.md` to execute Generate, Review, Validate, Gap Analysis and Stage 6B Readiness Assessment modes. The skill must apply all rules in this file; where the skill and these instructions differ, these instructions govern.
