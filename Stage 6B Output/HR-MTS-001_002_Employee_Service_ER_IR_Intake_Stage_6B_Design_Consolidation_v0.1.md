---
title: Employee Service and ER IR Intake Agent Stage 6B Design Consolidation
stage: Stage 6B - Design Consolidation
capabilityId: HR-MTS-001/002
status: Draft for Design Authority preparation
version: v0.1
classification: KPMG confidential
language: UK English
---

# Document Control

| Item | Value | Evidence |
|---|---|---|
| Method authority | Stage 6B section in Delivery-Control Stage 6 methodology | [SRC-01, Stage 6B Objective/Actions/Outputs] |
| Primary source design | Stage 6 detailed design v0.1 | [SRC-02, full document] |
| Upstream lineage | Stage 4 classify and Stage 5B consolidated model | [SRC-03, Stage 4]; [SRC-04, Stage 5B] |
| Reuse evidence source | ABBA annotated catalogue | [SRC-05, rows 75, 78, 275, 277, 317] |
| Approval status | Pending | [SRC-01, Stage 6B approval gate] |

# Contents

1. Executive Summary
2. Stage 6B Objective and Scope
3. Source Inventory and Evidence Mapping
4. Stage 6B Action-by-Action Consolidation Results
5. Consolidated End-to-End Solution Design
6. Orchestration and Handover Assurance
7. Control Coverage Consolidation
8. Unit-Test Coverage Consolidation
9. Data and Logic Continuity Check
10. Consolidated CIA Issue and Action Log
11. Readiness Assessment and Decision
12. Recommended Implementation Technology
13. Controls and Evidence Register
14. Exit Criteria and Next Stage Gate
15. Appendices

# 1. Executive Summary

This Stage 6B package consolidates Stage 6 component designs into one end-to-end implementation-ready design baseline, validates continuity against Stage 4 and Stage 5B artefacts, and records all unresolved assumptions, constraints, issues and actions in a single controlled register.

Consolidation confirms complete design coverage for agents, controls, handovers and unit tests. Readiness remains conditional because named ownership and specific governance metadata are still pending from source artefacts.

Evidence: [SRC-01, Stage 6B outputs and checks]; [SRC-02, Stage 6 design sections 6 to 18]; [SRC-04, gap and ACO registers]

# 2. Stage 6B Objective and Scope

## 2.1 Objective

Consolidate all Stage 6 component designs into a coherent, complete and internally consistent end-to-end design package that can be advanced to implementation planning after governance checks. [SRC-01, Stage 6B Objective]

## 2.2 Scope

- Consolidation of component-level logic into one full process design.
- Validation of controls, handovers, data and tests.
- Consolidated CIA issue and action management.
- Readiness recommendation for next stage.

## 2.3 Out of Scope

- Build coding and deployment execution.
- Final governance approval sign-off (this remains external).

# 3. Source Inventory and Evidence Mapping

| Source ID | Artefact | Consolidation role |
|---|---|---|
| SRC-01 | Delivery-Control/Stage_6.md | Governing criteria for Stage 6B actions, checks and outputs |
| SRC-02 | Stage 6 Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage_6_Detailed_Design_v0.1.md | Primary design baseline to consolidate |
| SRC-03 | Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md | Original workflow, control and handover intent validation |
| SRC-04 | Stage 5 and 5B Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5B_Data_Model_Consolidation_v0.1.md | Data, relationship and unresolved gap continuity validation |
| SRC-05 | ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv | Reuse suitability and adaptation evidence |
| SRC-06 | Source Documents/stage-6b-document-generation.instructions.md and Source Documents/stage-6b-SKILL.md | Mandatory structure and status vocabulary |

# 4. Stage 6B Action-by-Action Consolidation Results

Status vocabulary applied: Pass, Fail, Pending, Not applicable.

| Action | Consolidation activity performed | Result | Evidence |
|---|---|---|---|
| 1. Gather all Stage 6 designs | Collected single Stage 6 baseline and mapped section lineage | Pass | [SRC-02, all sections] |
| 2. Walk through complete workflow | Walked W-001 to W-010 with all branches | Pass | [SRC-02, sections 5, 12, 13] |
| 3. Verify each agent role and handover continuity | Validated A-001 to A-008 and H-001 to H-008 continuity | Pass | [SRC-02, sections 4, 6, 12] |
| 4. Check deterministic and AI logic consistency | Verified BR-001 to BR-005 and AI-001/AI-002 against boundaries | Pass | [SRC-02, sections 7 and 8] |
| 5. Verify control operation and audit paths | Validated C-001 to C-010 operations and evidence outputs | Pass | [SRC-02, section 11] |
| 6. Confirm test coverage for normal and exception paths | Verified UT-001 to UT-024 coverage and mapping | Pass | [SRC-02, section 13] |
| 7. Confirm unresolved assumptions/issues are logged | Merged unresolved ownership and governance dependencies into CIA register | Pass | [SRC-02, section 16]; [SRC-04, gaps and ACO] |
| 8. Final readiness review for implementation handoff | Completed readiness scoring and gate recommendation | Pending | [Section 11 in this document] |

# 5. Consolidated End-to-End Solution Design

## 5.1 Unified Process Blueprint

| Process phase | Primary component set | Output state | Human boundary |
|---|---|---|---|
| Intake and validation | CMP-001 | triage-ready case context | Human clarification if context insufficient |
| Deterministic triage | CMP-002 + CMP-004 | route decision and branch payload | route_human and escalate_er enforce human ownership |
| Service response path | CMP-003 + CMP-007 | bounded response or reviewer-routed case | Human review required on sensitivity/low confidence |
| ER path | CMP-005 + CMP-006 | specialist-ready ER package | Specialist and counsel decisions remain human-led |
| Closure and evidence | CMP-008 + CMP-007 | immutable audit evidence and completion status | Governance accountability remains human-held |

Evidence: [SRC-02, sections 6, 10, 11, 12]

## 5.2 Consolidated Component-to-Workflow Map

| Component | Step coverage | Data entities used | Controls covered |
|---|---|---|---|
| CMP-001 | W-001, W-002 | E-001, E-002 | C-001, C-002 |
| CMP-002 | W-003 | E-002, E-004 | C-003 |
| CMP-003 | W-004, W-005 | E-005, E-006 | C-004, C-005 |
| CMP-004 | W-003, W-006 | E-004, E-008 | C-006 |
| CMP-005 | W-007 | E-003 | C-007 |
| CMP-006 | W-008, W-009 | E-006, E-007, E-008 | C-008, C-009 |
| CMP-007 | W-004, W-005, W-010 | E-005, E-010 | C-004, C-005, C-010 |
| CMP-008 | W-010 | E-009 | C-010 |

Evidence: [SRC-02, sections 6 and 11]; [SRC-04, unified model]

# 6. Orchestration and Handover Assurance

| Check ID | Assurance question | Result | Observation | Evidence |
|---|---|---|---|---|
| ORC-001 | Are all handovers from Stage 4 represented in Stage 6 design? | Pass | H-001 to H-008 are explicitly specified | [SRC-02, section 12]; [SRC-03, handover register] |
| ORC-002 | Are branch outcomes complete for service and ER flows? | Pass | auto_resolve, route_human, escalate_er all represented with downstream handling | [SRC-02, sections 5 and 12] |
| ORC-003 | Are handover preconditions and expected outcomes explicit? | Pass | Preconditions and expected outcomes listed in each handover contract | [SRC-02, section 12] |
| ORC-004 | Are failure modes and escalation paths defined? | Pass | Exception catalogue maps failures to escalation and HIP points | [SRC-02, section 10] |
| ORC-005 | Is handover ownership complete and named? | Pending | Role-level ownership exists; named ownership remains unresolved | [SRC-02, section 16]; [SRC-04, G-01] |

# 7. Control Coverage Consolidation

| Control | Coverage in Stage 6 | Coverage quality | Result |
|---|---|---|---|
| C-001 to C-003 | Intake and triage gates are explicit | Strong | Pass |
| C-004 to C-005 | Service response and provenance controls are explicit | Strong, dependent on confidence taxonomy finalisation | Pending |
| C-006 | Human assignment acknowledgement is explicit | Moderate, SLA threshold pending | Pending |
| C-007 to C-009 | ER no-auto-action and specialist acceptance controls are explicit | Strong | Pass |
| C-010 | Audit completeness and immutability defined | Strong, retention metadata still pending | Pending |

Evidence: [SRC-02, section 11]; [SRC-04, G-02, G-05, G-06]

# 8. Unit-Test Coverage Consolidation

| Coverage dimension | Target | Actual | Result | Evidence |
|---|---|---|---|---|
| Component normal path tests | 8 components | 8 components | Pass | [SRC-02, UT-001, UT-003, UT-006, UT-009, UT-011, UT-013, UT-015, UT-018] |
| Component exception tests | 8 components | 8 components | Pass | [SRC-02, UT-002, UT-004, UT-005, UT-007, UT-008, UT-010, UT-012, UT-014, UT-017, UT-019] |
| Workflow path tests | 3 primary paths | 3 paths | Pass | [SRC-02, UT-020, UT-021, UT-022] |
| Cross-path exception tests | 2 priority scenarios | 2 scenarios | Pass | [SRC-02, UT-023, UT-024] |
| Traceability to controls | Full trace expected | Full trace present | Pass | [SRC-02, Appendix B] |

# 9. Data and Logic Continuity Check

| Continuity check | Result | Notes | Evidence |
|---|---|---|---|
| Stage 5B entities used in Stage 6 components | Pass | E-001 to E-010 traced to component designs | [SRC-02, section 6]; [SRC-04, unified model] |
| Deterministic logic alignment to Stage 4 decisions | Pass | BR-001 and BR-002 align with D-001 and D-003 | [SRC-02, section 7]; [SRC-03, decision catalogue] |
| Human intervention continuity from Stage 4 to Stage 6 | Pass | HIP-001 to HIP-005 preserved and linked to tests | [SRC-02, sections 10 and 13]; [SRC-03, HIP catalogue] |
| Governance gap carry-forward integrity | Pass | G-01 to G-08 reflected as risks/dependencies | [SRC-02, section 16]; [SRC-04, gap log] |
| Named ownership completeness | Pending | TBC values remain and must be resolved pre-build | [SRC-02, section 16]; [SRC-04, G-01] |

# 10. Consolidated CIA Issue and Action Log

| CIA ID | Type | Description | Source lineage | Severity | Owner | Action | Target stage | Status |
|---|---|---|---|---|---|---|---|---|
| CIA-001 | Constraint | Stage 6 design is technology-agnostic and cannot include build-level solutioning | Stage 6 method requirement | Medium | Delivery lead TBC | Preserve logic-only design in this package | Stage 6B | Pass |
| CIA-002 | Issue | Named owners for data/control domains remain unresolved | G-01, ACO-01 | Critical | Capability governance lead TBC | Confirm named business, data and control owners | Pre-Stage 7 | Pending |
| CIA-003 | Issue | Confidence indicator taxonomy not standardised | G-02 | High | QA control owner TBC | Define confidence scale, threshold and review trigger semantics | Pre-Stage 7 | Pending |
| CIA-004 | Issue | QA review reason code taxonomy not standardised | G-03 | High | QA control owner TBC | Create controlled reason code set and publish governance note | Pre-Stage 7 | Pending |
| CIA-005 | Issue | ER legal exposure codebook not fully defined | G-04 | High | ER specialist owner TBC | Define legal/psychosocial codebook and route criteria | Pre-Stage 7 | Pending |
| CIA-006 | Issue | Audit retention metadata attributes incomplete | G-05 | Medium | Governance owner TBC | Add retention class and expiry metadata rules | Stage 7 design-to-build | Pending |
| CIA-007 | Issue | Handover acceptance SLA fields not defined | G-06 | Medium | HR operations owner TBC | Define handover due-by and breach indicators | Stage 7 design-to-build | Pending |
| CIA-008 | Issue | Policy version lineage controls not finalised | G-07 | Medium | Policy owner TBC | Add policy effective date and version management rules | Stage 7 design-to-build | Pending |
| CIA-009 | Open question | Canonical enterprise admission decision for case and er_case unresolved | G-08, ACO-03 | High | Data architecture owner TBC | Design Authority decision and mapping update | Pre-Stage 7 | Pending |
| CIA-010 | Assumption | Human reviewer/specialist capacity will meet control timing | Stage 6 risk carry-forward | Medium | Operations lead TBC | Validate staffing and rota coverage | Pre-Stage 7 | Pending |

# 11. Readiness Assessment and Decision

## 11.1 Readiness Scoring

| Dimension | Weight | Score (0-5) | Weighted result | Evidence basis |
|---|---|---|---|---|
| Workflow and orchestration completeness | 20% | 5 | 1.00 | H-001 to H-008 and all branches complete |
| Control design completeness | 20% | 4 | 0.80 | Controls complete, some governance metadata pending |
| Data and logic continuity | 20% | 4 | 0.80 | Entity mapping complete, enterprise admission decision pending |
| Test coverage completeness | 20% | 5 | 1.00 | Normal and exception tests complete |
| Governance and ownership readiness | 20% | 2 | 0.40 | Multiple named-owner and taxonomy dependencies unresolved |
| Total | 100% |  | 4.00 / 5.00 |  |

## 11.2 Readiness Decision

Decision: Conditional Ready for Stage 7 planning with controlled preconditions.

Mandatory preconditions before build execution:

1. Resolve CIA-002 ownership assignments.
2. Resolve CIA-003 and CIA-004 QA taxonomy items.
3. Resolve CIA-005 ER exposure codebook controls.
4. Confirm Design Authority position on CIA-009 canonical mapping.

# 12. Recommended Implementation Technology

This section is intentionally included only in Stage 6B, per governance guidance.

| Design area | Recommended technology direction | Rationale | Dependency |
|---|---|---|---|
| Workflow orchestration | Event-driven workflow orchestration with explicit state transitions | Strong alignment to handover contracts and audit trace requirements | Ownership and SLA metadata closure |
| Deterministic routing and control rules | Rules engine or declarative policy evaluation layer | Aligns with triage_case and er_triage deterministic intent | Confidence and ER codebook finalisation |
| Data model and lineage | Canonical data model integration with enterprise workforce entities plus domain case entities | Supports continuity from Stage 5B and governance traceability | DA decision on case and er_case canonical status |
| Audit evidence | Immutable audit event logging with decision references | Required for C-010 and closure evidence integrity | Retention policy metadata finalisation |
| Human review and specialist handovers | Work queue model with explicit acceptance events and SLA markers | Supports HIP and handover controls C-006 and C-009 | Named ownership and SLA thresholds |

# 13. Controls and Evidence Register

| Evidence ID | Required evidence | Produced in Stage 6/6B | Status |
|---|---|---|---|
| EV-001 | End-to-end consolidated design map | Sections 5 and 6 | Pass |
| EV-002 | Logic consistency check records | Sections 4 and 9 | Pass |
| EV-003 | Control operation matrix | Section 7 | Pass |
| EV-004 | Unit-test coverage matrix | Section 8 | Pass |
| EV-005 | Consolidated CIA register | Section 10 | Pass |
| EV-006 | Readiness decision and rationale | Section 11 | Pass |
| EV-007 | Approval evidence and date | Not yet available from source | Pending |

# 14. Exit Criteria and Next Stage Gate

| Stage 6B exit criterion | Result | Evidence |
|---|---|---|
| All Stage 6 designs consolidated into one coherent design | Pass | Sections 5 and 6 |
| Complete workflow walk-through performed | Pass | Section 4 action 2 and section 6 |
| Logic, controls and tests validated end-to-end | Pass | Sections 7 to 9 |
| Issues and assumptions consolidated with actions | Pass | Section 10 |
| Readiness recommendation produced | Pass | Section 11 |
| Approval decision and date captured | Pending | Section 13, EV-007 |

Next stage gate recommendation: proceed to Stage 7 planning only if CIA-002, CIA-003, CIA-004, CIA-005 and CIA-009 have named accountable owners and agreed closure plans.

# 15. Appendices

## Appendix A - Consolidation Crosswalk

| Stage 4/5B artefact | Stage 6 design section | Stage 6B validation section |
|---|---|---|
| Workflow decomposition W-001 to W-010 | Stage 6 section 5 and 6 | Stage 6B sections 4 and 5 |
| Controls C-001 to C-010 | Stage 6 section 11 | Stage 6B section 7 |
| Handover register H-001 to H-008 | Stage 6 section 12 | Stage 6B section 6 |
| HIP catalogue | Stage 6 section 10 | Stage 6B sections 6 and 9 |
| Stage 5B gap log G-01 to G-08 | Stage 6 section 16 | Stage 6B section 10 |

## Appendix B - Source References

- [SRC-01] Delivery-Control/Stage_6.md
- [SRC-02] Stage 6 Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage_6_Detailed_Design_v0.1.md
- [SRC-03] Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md
- [SRC-04] Stage 5 and 5B Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5B_Data_Model_Consolidation_v0.1.md
- [SRC-05] ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv
- [SRC-06] Source Documents/stage-6b-document-generation.instructions.md and Source Documents/stage-6b-SKILL.md
