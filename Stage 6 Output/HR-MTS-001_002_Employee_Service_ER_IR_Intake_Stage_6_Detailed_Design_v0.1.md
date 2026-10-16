---
title: Employee Service and ER IR Intake Agent Stage 6 Detailed Design
stage: Stage 6 - Design
capabilityId: HR-MTS-001/002
status: Draft for peer review
version: v0.1
classification: KPMG confidential
language: UK English
---

# Document Control

| Item | Value | Evidence |
|---|---|---|
| Method source | Delivery-Control Stage 6 methodology | [SRC-01, Stage 6 Objective/Inputs/Actions/Outputs] |
| Upstream design inputs | Stage 4 classify output and Stage 5B consolidated data model | [SRC-02, Stage 4 sections]; [SRC-03, Stage 5B sections] |
| ABBA reuse reference | Annotated agents catalogue | [SRC-04, rows 75, 78, 275, 277, 317] |
| Scope | Detailed, technology-agnostic design for all agents, controls and handovers in W-001 to W-010 | [SRC-01, Stage 6 Objective] |
| Stage boundary | Logical design only; no implementation build details | [SRC-01, Practitioner guidance] |

# Contents

1. Executive Summary
2. Stage 6 Objective and Scope
3. Source Inventory and Evidence Map
4. Framework and Classification Baseline
5. End-to-End Workflow and Component Inventory
6. Detailed Component Designs
7. Deterministic Logic Specifications
8. AI Instructions and Prompt Specifications
9. Response and Citation Design
10. Exception, Escalation and Human Intervention Design
11. Control Operation and Audit Evidence Design
12. Integration and Handover Specifications
13. Unit Test Scenarios and Expected Results
14. ABBA Reuse Assessment
15. RACI Matrix
16. Assumptions, Risks, Dependencies and Open Questions
17. Coverage Metrics and Quality Gate Results
18. Stage 6 Exit Criteria and Stage 6B Readiness
19. Appendices

# 1. Executive Summary

This deliverable converts the approved logical architecture and consolidated data model into detailed, technology-agnostic component designs for the Employee Service and ER IR Intake capability. It covers the complete workflow W-001 to W-010, all mapped controls C-001 to C-010, human intervention points HIP-001 to HIP-005, and handovers H-001 to H-008, including normal and exception unit-test scenarios. [SRC-01, Stage 6 Actions and Outputs]; [SRC-02, Workflow, controls, HIP and handovers]; [SRC-03, unified model]

Design intent remains bounded by the approved autonomy boundary: bounded service auto-resolution is permitted, while ER determinations and all consequential ER outcomes remain human-led. [SRC-02, Capability context and HIP-003]

# 2. Stage 6 Objective and Scope

## 2.1 Objective

Produce detailed designs for each agent, control and workflow handover, including behaviour, data mappings, deterministic rules, AI instructions where applicable, exception handling, human interventions and unit test scenarios. [SRC-01, Stage 6 Objective and Outputs]

## 2.2 In Scope

- Service and ER intake components A-001 to A-008.
- Workflow steps W-001 to W-010.
- Controls C-001 to C-010.
- Handover contracts H-001 to H-008.
- Unit tests UT-001 to UT-024.

[SRC-02, Stage 4 component and workflow artefacts]

## 2.3 Out of Scope

- Physical API schemas and infrastructure deployment.
- Runtime hosting decisions.
- Stage 7 build implementation.

[SRC-01, Practitioner guidance and Next stage]

# 3. Source Inventory and Evidence Map

| Source ID | Artefact | Purpose in Stage 6 |
|---|---|---|
| SRC-01 | Delivery-Control/Stage_6.md | Authoritative Stage 6 and 6B method requirements |
| SRC-02 | Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md | Agent classifications, workflow, handovers, controls, decisions, HIPs |
| SRC-03 | Stage 5 and 5B Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5B_Data_Model_Consolidation_v0.1.md | Consolidated data entities, attributes, relationships, data gaps |
| SRC-04 | ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv | Reuse candidates and rationale support |
| SRC-05 | Source Documents/HR_Capability_and_Full_Agent_Catalogue_v1.md | Capability purpose, deterministic tool definitions, autonomy boundary |
| SRC-06 | Source Documents/Stage_6_document_generation.Instructions.md and Source Documents/Stage_6_SKILL.md | Stage 6 deliverable governance structure |

# 4. Framework and Classification Baseline

| Component | Classification | Primary objective | Workflow coverage | Evidence |
|---|---|---|---|---|
| A-001 Intake Context Agent | Task | Register and validate intake context | W-001, W-002 | [SRC-02, Agent Landscape and W-001/W-002] |
| A-002 Service Triage Agent | Task, Insight | Deterministic route decision | W-003 | [SRC-02, W-003, D-001] |
| A-003 Service Response Agent | Task, Experience | Draft and issue bounded response | W-004, W-005 | [SRC-02, W-004/W-005] |
| A-004 Service Workflow Orchestrator | Orchestration | Route service and ER branches | W-003 to W-006 | [SRC-02, workflow and H-003/H-005] |
| A-005 ER Intake Risk Agent | Task, Insight | ER risk classification and flags | W-007 | [SRC-02, W-007, D-003] |
| A-006 ER Handover Orchestrator | Orchestration | Build specialist ER handover package | W-008, W-009 | [SRC-02, W-008/W-009] |
| A-007 Quality and Policy Control Agent | Control | Sensitivity and QA control checks | W-004, W-005, W-010 | [SRC-02, D-002, D-005] |
| A-008 Audit and Evidence Agent | Control, Task | Immutable closure and decision evidence | W-010 | [SRC-02, W-010] |

# 5. End-to-End Workflow and Component Inventory

## 5.1 Workflow Sequence

W-001 -> W-002 -> W-003 -> branching to W-004/W-006/W-007 -> W-008 -> W-009 -> W-010.

[SRC-02, End-to-End Workflow diagram and decomposition catalogue]

## 5.2 Design Components

| CMP ID | Component | Type | Linked Step(s) | Linked Controls | Linked Handovers |
|---|---|---|---|---|---|
| CMP-001 | Intake Context Agent (A-001) | Agent | W-001, W-002 | C-001, C-002 | H-001, H-002 |
| CMP-002 | Service Triage Agent (A-002) | Agent | W-003 | C-003 | H-003, H-004, H-005 |
| CMP-003 | Service Response Agent (A-003) | Agent | W-004, W-005 | C-004, C-005 | H-003, H-008 |
| CMP-004 | Service Workflow Orchestrator (A-004) | Agent | W-003, W-006 | C-006 | H-004, H-005, H-008 |
| CMP-005 | ER Intake Risk Agent (A-005) | Agent | W-007 | C-007 | H-005, H-006 |
| CMP-006 | ER Handover Orchestrator (A-006) | Agent | W-008, W-009 | C-008, C-009 | H-006, H-007, H-008 |
| CMP-007 | Quality and Policy Control Agent (A-007) | Control component | W-004, W-005, W-010 | C-004, C-005, C-010 | H-008 |
| CMP-008 | Audit and Evidence Agent (A-008) | Control component | W-010 | C-010 | H-008 |

# 6. Detailed Component Designs

## CMP-001 Intake Context Agent

- Purpose: capture front-door case and validate mandatory context.
- Trigger: new employee or manager query.
- Inputs: worker_id, channel, query_text, initial category hints.
- Outputs: triage_packet_v1 with case_id and validation flags.
- Behaviour:
  1. Create case shell.
  2. Validate mandatory fields.
  3. Classify stream_hint as service or potential ER.
  4. Emit missing_data_flags when evidence is incomplete.
- Exceptions: EX-005 insufficient context.
- Human boundary: if required identity context is missing, route to human service path.
- Data mapping: E-001 worker, E-002 case.

Evidence: [SRC-02, W-001/W-002]; [SRC-03, E-001/E-002]

## CMP-002 Service Triage Agent

- Purpose: execute deterministic route logic.
- Trigger: validated triage_packet_v1.
- Inputs: case category, priority, SLA attributes, policy rule set.
- Outputs: route_decision payload with reason code and timestamp.
- Behaviour:
  1. Apply triage_case deterministic rules.
  2. Produce route outcome auto_resolve, route_human, or escalate_er.
  3. Persist route evidence for audit.
- Exceptions: EX-001 ambiguous categorisation, EX-002 non-standard or high-priority case.
- Human boundary: no direct approval, but route_human and escalate_er force human-owned branches.
- Data mapping: E-002 case, E-004 route_decision.

Evidence: [SRC-02, W-003, D-001]; [SRC-05, triage_case]

## CMP-003 Service Response Agent

- Purpose: generate bounded service response with citations.
- Trigger: route_decision auto_resolve.
- Inputs: route payload, policy references, knowledge content.
- Outputs: response_draft, citation_list, response_record.
- Behaviour:
  1. Draft response from bounded playbook.
  2. Attach citations and provenance.
  3. Send to control check for sensitivity and confidence gating.
  4. Issue response when approved.
- Exceptions: EX-003 low-confidence or sensitive response, EX-005 insufficient policy context.
- Human boundary: HIP-002 required when sensitivity or confidence flags trigger review.
- Data mapping: E-005 response_draft, E-006 policy_reference.

Evidence: [SRC-02, W-004/W-005, D-002]; [SRC-03, A-005]

## CMP-004 Service Workflow Orchestrator

- Purpose: coordinate route branch movement and assignment.
- Trigger: route_decision or review outcome.
- Inputs: route_decision, review decision outcomes.
- Outputs: human_service_handover_v1 or er_escalation_payload.
- Behaviour:
  1. Branch to response path, human service path, or ER path.
  2. Package route rationale for receiving performer.
  3. Record assignment acknowledgement status.
- Exceptions: EX-001, EX-002, EX-003.
- Human boundary: HIP-001 on service handover.
- Data mapping: E-004 route_decision, E-008 handover_record.

Evidence: [SRC-02, W-003/W-006, H-004/H-005]

## CMP-005 ER Intake Risk Agent

- Purpose: perform deterministic ER risk triage.
- Trigger: ER escalation payload.
- Inputs: case context, stream indicators, ER-related flags.
- Outputs: er_triage_payload_v1 with risk_type, severity and flags.
- Behaviour:
  1. Apply er_triage deterministic rule set.
  2. Set union, psychosocial and legal exposure flags.
  3. Emit no-auto-action marker for downstream controls.
- Exceptions: EX-004 flagged ER exposure.
- Human boundary: does not determine outcome; specialist ownership mandatory.
- Data mapping: E-003 er_case.

Evidence: [SRC-02, W-007, D-003]; [SRC-05, er_triage]

## CMP-006 ER Handover Orchestrator

- Purpose: construct specialist-ready ER package.
- Trigger: er_triage_payload_v1.
- Inputs: ER risk payload, policy references.
- Outputs: policy_bundle, timeline_draft, specialist handover packet.
- Behaviour:
  1. Retrieve policy context.
  2. Draft timeline.
  3. Route to ER specialist or specialist-plus-counsel path.
  4. Record acceptance and handover evidence.
- Exceptions: EX-004, EX-005.
- Human boundary: HIP-003 and HIP-004 enforce specialist control.
- Data mapping: E-006 policy_reference, E-007 timeline_draft, E-008 handover_record.

Evidence: [SRC-02, W-008/W-009, D-004, H-007]

## CMP-007 Quality and Policy Control Agent

- Purpose: enforce review and QA control gates.
- Trigger: service draft creation, response issuance, or closure path.
- Inputs: response_draft, sensitivity indicators, sampling criteria.
- Outputs: review_required flag, qa_selection outcome.
- Behaviour:
  1. Evaluate sensitivity and confidence conditions.
  2. Route to human review when criteria met.
  3. Select eligible auto-resolved cases for QA sampling.
- Exceptions: EX-003.
- Human boundary: QA and review outcomes are human-provided decisions.
- Data mapping: E-005 response_draft, E-010 qa_review_outcome.

Evidence: [SRC-02, D-002, D-005, HIP-002, HIP-005]

## CMP-008 Audit and Evidence Agent

- Purpose: create immutable closure evidence.
- Trigger: terminal outcomes from service or ER paths.
- Inputs: route history, handover outcomes, QA outcomes.
- Outputs: audit_event and completion record.
- Behaviour:
  1. Validate evidence completeness.
  2. Persist immutable audit event payload.
  3. Mark completion status as service closed or human-owned handover recorded.
- Exceptions: EX-005 where evidence required for closure is incomplete.
- Human boundary: governance review remains human-accountable.
- Data mapping: E-009 audit_event.

Evidence: [SRC-02, W-010, H-008]; [SRC-03, audit_event dictionary]

# 7. Deterministic Logic Specifications

| Rule ID | Component | Logic | Inputs | Output | Evidence |
|---|---|---|---|---|---|
| BR-001 | CMP-002 | triage_case category/priority/SLA branch logic | category, priority, sla_hours, policy rules | route_code | [SRC-05, triage_case]; [SRC-02, D-001] |
| BR-002 | CMP-005 | er_triage risk and severity classification | ER flags and case context | risk_type, severity, exposure flags | [SRC-05, er_triage]; [SRC-02, D-003] |
| BR-003 | CMP-007 | sensitivity and confidence review gate | response_draft indicators | review_required boolean | [SRC-02, D-002] |
| BR-004 | CMP-007 | QA sample determination | response status and policy | qa_selected boolean | [SRC-02, D-005] |
| BR-005 | CMP-008 | audit completeness validation | closure payload and references | audit_validity result | [SRC-02, C-010 and W-010] |

# 8. AI Instructions and Prompt Specifications

| AI ID | Component | Allowed task | Grounding requirement | Prohibited behaviour | Human trigger |
|---|---|---|---|---|---|
| AI-001 | CMP-003 | Draft bounded service response | Must cite policy references and knowledge evidence | No out-of-policy advice, no ER determinations | HIP-002 when low confidence or sensitivity |
| AI-002 | CMP-006 | Draft ER timeline summary | Must use triage output plus policy references | No legal determination, no final ER judgement | HIP-003 and HIP-004 always required for outcome |

Evidence: [SRC-01, Action 6 and 7]; [SRC-02, W-004/W-008, HIP controls]

# 9. Response and Citation Design

| Response ID | Audience | Response type | Required fields | Citation requirement | Approval boundary | Evidence |
|---|---|---|---|---|---|---|
| RSP-001 | Employee or manager | Bounded service response | response_text, action guidance, policy refs | Minimum one policy citation and version reference | Human review when triggered by BR-003 | [SRC-02, W-004/W-005, C-004] |
| RSP-002 | HR advisor | Human service handover | case summary, route rationale, unresolved fields | Include decision trace to D-001 or D-002 | HR advisor accepts ownership | [SRC-02, H-004, HIP-001] |
| RSP-003 | ER specialist | ER intake package | risk classification, flags, policy bundle, timeline draft | Include source policy references and triage evidence | Specialist approval for consequential action | [SRC-02, H-007, HIP-003/HIP-004] |
| RSP-004 | Governance reviewer | Audit closure record | route history, decision refs, timestamps, actor info | Include source snapshot reference | Governance review remains human accountable | [SRC-02, W-010, C-010] |

# 10. Exception, Escalation and Human Intervention Design

| Exception ID | Trigger | Containment action | Escalation path | Linked HIP | Evidence |
|---|---|---|---|---|---|
| EX-001 | Ambiguous service categorisation | Stop auto path and route human | HR advisor | HIP-001 | [SRC-02, EX-001] |
| EX-002 | Non-standard/high-priority service | Route human with full context | HR advisor | HIP-001 | [SRC-02, EX-002] |
| EX-003 | Low-confidence or sensitive response | Require human review | Reviewer then advisor if needed | HIP-002 | [SRC-02, EX-003, HIP-002] |
| EX-004 | Flagged ER exposure | Mandatory specialist path | Specialist plus counsel when needed | HIP-003, HIP-004 | [SRC-02, EX-004] |
| EX-005 | Insufficient context or policy evidence | Block unsupported automation | Advisor or specialist | HIP-001/HIP-003 | [SRC-02, EX-005] |

# 11. Control Operation and Audit Evidence Design

| Control ID | Step | Control objective | Operation | Evidence produced | Failure response |
|---|---|---|---|---|---|
| C-001 | W-001 | Ensure complete intake metadata | Required field validation | intake validation log | route for clarification |
| C-002 | W-002 | Ensure triage readiness | completeness and policy reference check | triage readiness flag | route human |
| C-003 | W-003 | Deterministic route governance | triage logic execution and capture | route decision trace | exception path EX-001/EX-002 |
| C-004 | W-004 | Sensitive content and confidence gate | review trigger rule check | review flag and reason | HIP-002 |
| C-005 | W-005 | Provenance on issued response | citation presence check | response provenance record | do not issue response |
| C-006 | W-006 | Human assignment assurance | assignment acknowledgement | handover acceptance status | escalation to service lead |
| C-007 | W-007 | No-auto-action ER boundary | ER classification and no-auto marker | ER triage evidence | specialist escalation |
| C-008 | W-008 | Human-determination boundary | package assist-only validation | package integrity record | hold for specialist review |
| C-009 | W-009 | Specialist acceptance assurance | accept/reject and receipt tracking | specialist acceptance record | escalate to ER lead |
| C-010 | W-010 | Audit completeness and immutability | closure evidence completeness check | immutable audit event | reopen evidence collection |

Evidence: [SRC-02, control map and decomposition rows]

# 12. Integration and Handover Specifications

| Handover ID | Producer | Consumer | Payload | Shared key | Preconditions | Expected result | Evidence |
|---|---|---|---|---|---|---|---|
| H-001 | Employee or manager | A-001 | query and identity payload | worker_id | request created | intake record created | [SRC-02, H-001] |
| H-002 | A-001 | A-002 | triage packet | case_id | validation complete | triage executed | [SRC-02, H-002] |
| H-003 | A-004 | A-003 | auto-resolve route payload | case_id | D-001 auto_resolve | response drafted | [SRC-02, H-003] |
| H-004 | A-004 | HR advisor | service handover packet | case_id | route_human or review-trigger | advisor accepts case | [SRC-02, H-004] |
| H-005 | A-004 | A-005 | ER escalation payload | case_id | D-001 escalate_er | ER triage starts | [SRC-02, H-005] |
| H-006 | A-005 and policy source | A-006 | risk output plus policy inputs | case_id | ER risk classification available | specialist package drafted | [SRC-02, H-006] |
| H-007 | A-006 | ER specialist | ER specialist pack | case_id | D-004 complete | specialist ownership accepted | [SRC-02, H-007] |
| H-008 | Service or ER components | A-008 | closure and evidence payload | case_id | terminal path reached | audit event persisted | [SRC-02, H-008] |

# 13. Unit Test Scenarios and Expected Results

| UT ID | Component | Scenario type | Scenario | Expected result | Evidence |
|---|---|---|---|---|---|
| UT-001 | CMP-001 | Normal | Complete intake payload | case created and triage packet emitted | [SRC-02, W-001/W-002] |
| UT-002 | CMP-001 | Exception | Missing worker_id | EX-005 route to human clarification | [SRC-02, EX-005] |
| UT-003 | CMP-002 | Normal | Auto-resolve eligible case | route_decision auto_resolve | [SRC-02, D-001] |
| UT-004 | CMP-002 | Exception | Ambiguous category | EX-001 route_human | [SRC-02, EX-001] |
| UT-005 | CMP-002 | Exception | High-priority non-standard case | EX-002 route_human | [SRC-02, EX-002] |
| UT-006 | CMP-003 | Normal | Bounded service response with policy context | cited response drafted and passed to C-004 | [SRC-02, W-004] |
| UT-007 | CMP-003 | Exception | Low-confidence draft | HIP-002 invoked | [SRC-02, D-002, HIP-002] |
| UT-008 | CMP-003 | Exception | Sensitive content flagged | route to human review | [SRC-02, EX-003] |
| UT-009 | CMP-004 | Normal | route_human branch | H-004 package created and assigned | [SRC-02, H-004] |
| UT-010 | CMP-004 | Exception | Assignment acknowledgement timeout | escalation recorded | [SRC-02, C-006 intent] |
| UT-011 | CMP-005 | Normal | ER escalation input valid | risk classification produced | [SRC-02, W-007] |
| UT-012 | CMP-005 | Exception | Legal exposure flag present | specialist-plus-counsel path indicated | [SRC-02, D-004] |
| UT-013 | CMP-006 | Normal | ER package assembly | policy bundle and timeline created | [SRC-02, W-008/W-009] |
| UT-014 | CMP-006 | Exception | Missing policy reference | EX-005 recorded and human escalation | [SRC-02, EX-005] |
| UT-015 | CMP-007 | Normal | Draft below risk threshold | review not required | [SRC-02, D-002] |
| UT-016 | CMP-007 | Normal | Auto-resolved case eligible for QA | qa_selected true/false persisted | [SRC-02, D-005] |
| UT-017 | CMP-007 | Exception | Missing QA metadata | control fail and escalation | [SRC-03, G-03] |
| UT-018 | CMP-008 | Normal | Complete closure payload | immutable audit record created | [SRC-02, W-010] |
| UT-019 | CMP-008 | Exception | Missing decision reference | audit completeness fail | [SRC-02, C-010] |
| UT-020 | Workflow | Normal | Service path end-to-end | W-001 to W-005 to W-010 complete | [SRC-02, workflow map] |
| UT-021 | Workflow | Normal | Human service path end-to-end | W-001 to W-006 to W-010 complete | [SRC-02, workflow map] |
| UT-022 | Workflow | Normal | ER path end-to-end | W-001 to W-007 to W-009 to W-010 complete | [SRC-02, workflow map] |
| UT-023 | Workflow | Exception | Policy data unavailable in ER path | EX-005 and HIP-003 escalation triggered | [SRC-02, EX-005, HIP-003] |
| UT-024 | Workflow | Exception | QA sample selected but no reviewer outcome | governance gap logged and not closed | [SRC-03, G-03] |

# 14. ABBA Reuse Assessment

| ABBA ID | Asset | Stage 6 design use | Design variance decision | Evidence |
|---|---|---|---|---|
| ABBA-001 (VA-1331) | HR inquiry responder | Pattern reference for bounded front-door responses | Adapted to enforce deterministic route and citation controls | [SRC-04, row 275]; [SRC-02, C-004/C-005] |
| ABBA-002 (VA-1333) | Support services workflow manager | Pattern reference for orchestration branches | Adapted to include explicit ER escalation branch | [SRC-04, row 277]; [SRC-02, H-004/H-005] |
| ABBA-003 (VA-1205) | Investigation case manager | Pattern reference for ER intake handling | Adapted to keep ER decisions human-only | [SRC-04, row 75]; [SRC-02, HIP-003] |
| ABBA-004 (VA-1208) | ER compliance monitor | Pattern reference for ER control and compliance checks | Reused control intent; mapped to C-007/C-009 | [SRC-04, row 78]; [SRC-02, controls] |
| ABBA-005 (VA-1240) | Employee relations workflow manager | Pattern reference for ER orchestration | Adapted for no-auto-action and acceptance evidence | [SRC-04, row 317]; [SRC-02, W-008/W-009] |

# 15. RACI Matrix

| Activity ID | Activity | Responsible | Accountable | Consulted | Informed | Evidence |
|---|---|---|---|---|---|---|
| WF-001 | Intake registration and validation | Intake Context Agent operator | HR Operations owner TBC | Data steward TBC | Governance reviewer | [SRC-02, W-001/W-002] |
| WF-002 | Deterministic service routing | Service Triage Agent operator | HR Operations owner TBC | Policy owner TBC | Service lead | [SRC-02, W-003, D-001] |
| WF-003 | Bounded response drafting and issuance | Service Response Agent operator | HR Operations owner TBC | QA reviewer TBC | Employee or manager | [SRC-02, W-004/W-005] |
| WF-004 | Human service handover | Service Workflow Orchestrator operator | HR advisor lead TBC | HR Operations owner TBC | Governance reviewer | [SRC-02, W-006, H-004] |
| WF-005 | ER risk triage and package creation | ER Intake Risk and Handover operators | ER specialist lead TBC | Policy owner TBC, counsel as needed | Governance reviewer | [SRC-02, W-007/W-009] |
| WF-006 | QA sampling and review | Quality and Policy Control operator | QA control owner TBC | HR operations and governance | Service lead | [SRC-02, D-005, HIP-005] |
| WF-007 | Audit and closure evidence | Audit and Evidence operator | Governance owner TBC | HR operations and ER specialist | Audit stakeholders | [SRC-02, W-010, C-010] |

# 16. Assumptions, Risks, Dependencies and Open Questions

| ID | Type | Statement | Severity | Action |
|---|---|---|---|---|
| ASM-001 | Assumption | Policy references remain available for both service and ER flows | Major | Validate source uptime and fallback during Stage 6B |
| ASM-002 | Assumption | Human reviewers and specialists are available within required operating windows | Major | Define operating SLAs in Stage 6B actions log |
| RSK-001 | Risk | Missing confidence taxonomy weakens review gating consistency | Major | Close G-02 with controlled threshold definition |
| RSK-002 | Risk | Undefined review_reason_code limits QA analytics | Major | Close G-03 with governed reason set |
| RSK-003 | Risk | Ownership unresolved for key controls can delay approvals | Critical | Resolve named owners before build-ready claim |
| OQ-001 | Open question | Should case and er_case be promoted to enterprise canonical model | Major | Data architecture decision via Design Authority |
| DEP-001 | Dependency | Approved Stage 5B data model remains baseline for all I/O mappings | Critical | Freeze references at Stage 6B consolidation |

Evidence: [SRC-03, G-01 to G-08 and ACO register]

# 17. Coverage Metrics and Quality Gate Results

| Metric | Numerator | Denominator | Result | Status | Evidence |
|---|---|---|---|---|---|
| Component design coverage | 8 | 8 | 100% | Pass | Sections 6 and 13 |
| Unit test coverage (normal and exception) | 8 components with both types | 8 | 100% | Pass | UT-001 to UT-019 |
| Workflow control coverage | 10 steps with controls | 10 | 100% | Pass | Section 11 |
| Handover specification coverage | 8 specified handovers | 8 | 100% | Pass | Section 12 |
| Data mapping alignment coverage | 8 components mapped to Stage 5B entities | 8 | 100% | Pass | Sections 6 and 7 |
| ABBA assessment coverage | 5 assessed candidates | 5 identified | 100% | Pass | Section 14 |
| Human intervention coverage | 5 HIPs explicitly linked | 5 | 100% | Pass | Sections 10 and 15 |
| Ownership completeness | 0 named final owners confirmed | 8 critical ownership loci | 0% | Fail | Section 16, RSK-003 |

# 18. Stage 6 Exit Criteria and Stage 6B Readiness

| Exit criterion | Status | Evidence |
|---|---|---|
| All components have detailed designs | Pass | Section 6 |
| Unit test scenarios defined for every component | Pass | Section 13 |
| All controls and handovers designed | Pass | Sections 11 and 12 |
| Ready for consolidation (6B) | Partial | Ownership and governance metadata still unresolved |

Stage 6B recommendation: Ready with controlled gaps.

Reasoning: logical design, controls, handovers, deterministic rules, AI boundaries, and tests are complete; unresolved items are primarily ownership and governance metadata tracked as explicit risks and actions. [SRC-01, Stage 6 Exit criteria]; [SRC-03, open gap register]

# 19. Appendices

## Appendix A - Consolidation Input Pack

- Stage 4 classify output
- Stage 5 model output
- Stage 5B consolidated model
- ABBA reuse catalogue references

## Appendix B - Detailed Control-to-Test Trace

| Control | Linked tests |
|---|---|
| C-001 | UT-001, UT-002 |
| C-002 | UT-001, UT-003 |
| C-003 | UT-003, UT-004, UT-005 |
| C-004 | UT-006, UT-007, UT-008 |
| C-005 | UT-006, UT-015 |
| C-006 | UT-009, UT-010 |
| C-007 | UT-011, UT-012 |
| C-008 | UT-013, UT-014 |
| C-009 | UT-013, UT-022 |
| C-010 | UT-018, UT-019, UT-024 |

## Appendix C - Source References

- [SRC-01] Delivery-Control/Stage_6.md
- [SRC-02] Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md
- [SRC-03] Stage 5 and 5B Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5B_Data_Model_Consolidation_v0.1.md
- [SRC-04] ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv
- [SRC-05] Source Documents/HR_Capability_and_Full_Agent_Catalogue_v1.md
- [SRC-06] Source Documents/Stage_6_document_generation.Instructions.md and Source Documents/Stage_6_SKILL.md
