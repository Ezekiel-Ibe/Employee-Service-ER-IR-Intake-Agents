---
title: Employee Service and ER IR Intake Agent Stage 5B Data Model Consolidation
stage: Stage 5B - Data Model Consolidation
businessAgent: Employee Service and ER IR Intake Agent (HR-MTS-001/002)
status: Draft - Ready for working review
version: v0.1
language: English (UK)
classification: KPMG Confidential
---

# Document Control

| Field | Value | Evidence |
|---|---|---|
| Capability | Employee Service and Case Resolution | [SRC-02, Stage 5 document control] |
| Stage 5 source document | HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5_Model_v0.1.md | [SRC-02, Appendix I] |
| Stage 4 source document | Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md | [SRC-03, source register] |
| Method authority | Stage 5B section in Delivery-Control/Stage_5.md | [SRC-01, Stage 5B section] |
| Design Authority state | Pending decision | [SRC-01, Approval gate] |

# Stage 5B - Data Model Consolidation

## Purpose

Consolidate Stage 5 workflow-step data models into one validated end-to-end data model and confirm it supports complete workflow execution, control evidence, and handover integrity. [SRC-01, Stage 5B purpose]

## Inputs

| Input | Consolidation use | Evidence |
|---|---|---|
| Stage 5 workflow-step models | Primary source for end-to-end entity and flow merge | [SRC-02, Appendix C] |
| Data classifications | Validates enterprise fit and unresolved gaps | [SRC-02, Appendix E] |
| Data gap log | Carries unresolved and resolved data gaps into single register | [SRC-02, Appendix F] |
| Workflow handovers | Validates between-step continuity | [SRC-02, Appendix G] |
| Overall AI Framework and control map | Validates control evidence support and human-capture points | [SRC-03, Overall AI Framework and HIP sections] |
| Agent inventory | Confirms producer and consumer accountability | [SRC-02, Appendix A] |
| Enterprise Business Data Objects overview | Aligns canonical object families and shared spine usage | [SRC-04, sections 2, 3, 10, 13] |
| Fabric enterprise-data-model repository | Aligns layer naming, standards, and workforce canonical entities | [SRC-05, enterprise-data-model/config/enterprise_model.yml; enterprise-data-model/sql/10_silver/070_workforce.sql] |

## Actions 1 to 13 and Consolidation Outcome

| Stage 5B action | Consolidation outcome | Status | Evidence |
|---|---|---|---|
| 1. Assemble all step data models | W-001 to W-010 model assembled into a unified register | Pass | [SRC-01, Actions]; [SRC-02, Appendix C] |
| 2. Walk end-to-end workflow | Full service and ER branches walked | Pass | [SRC-01, Actions]; [SRC-03, End-to-End Workflow] |
| 3. Trace every input to source | All major inputs traced; some ownership metadata pending | Pending | [SRC-02, Appendix C and H] |
| 4. Trace every output to consumer or storage | Consumer or storage defined for all major outputs | Pass | [SRC-02, Appendix C and G] |
| 5. Validate within-step exchanges | Within-step producer and consumer paths validated | Pass | [SRC-02, Appendix C] |
| 6. Validate between-step handovers | H-001 to H-008 validated for source and target continuity | Pass | [SRC-02, Appendix G] |
| 7. Confirm consistent entities and attributes | Naming consistent; enterprise admission decision for case entities still open | Pending | [SRC-02, Appendix D and H] |
| 8. Confirm agent-created data destinations | Destinations defined for route, response, timeline, and audit payloads | Pass | [SRC-02, Appendices C and D] |
| 9. Confirm human data capture points | Human capture points mapped to HIP-001 to HIP-005 | Pass | [SRC-03, HIP section]; [SRC-02, Appendix C] |
| 10. Identify missing data, attributes, relationships | Eight gaps retained and normalised | Pass | [SRC-02, Appendix F] |
| 11. Add and update as required | Missing items added as model proposals, not yet approved | Pass | [SRC-02, Appendix D and F] |
| 12. Repeat end-to-end check | Second-pass check completed with pending governance items | Pass | [SRC-06, CHK results] |
| 13. Prepare for Design Authority review | Submission pack prepared, approval pending | Pending | [SRC-01, Approval gate]; [SRC-06, DA record] |

## Checks Performed

Controlled status vocabulary used: Pass, Fail, Pending, Not applicable.

| Check ID | Check | Result | Evidence |
|---|---|---|---|
| CHK-01 | Every input has a defined source | Pending | [SRC-02, Appendix C]; [SRC-02, Appendix H ACO-01] |
| CHK-02 | Every output has a defined consumer or storage | Pass | [SRC-02, Appendix C and G] |
| CHK-03 | Internal data exchanges are consistent | Pass | [SRC-02, Appendix C] |
| CHK-04 | Step handovers are consistent and complete | Pass | [SRC-02, Appendix G] |
| CHK-05 | Shared entities and attributes are consistent | Pending | [SRC-02, Appendix D]; [SRC-02, ACO-03] |
| CHK-06 | Agent-created data has a destination | Pass | [SRC-02, Appendices C and D] |
| CHK-07 | Human-provided data has a capture point | Pass | [SRC-03, HIP section]; [SRC-02, Appendix C] |
| CHK-08 | Control evidence is supported | Pass | [SRC-03, control points C-001 to C-010]; [SRC-02, Appendix C] |
| CHK-09 | Enterprise model alignment is achieved | Pending | [SRC-04, section 14]; [SRC-05, enterprise model standards] |
| CHK-10 | Stage 5B outputs are all produced | Pass | [SRC-06, outputs section below] |
| CHK-11 | Placeholder governance rule followed | Pass | [SRC-02, Appendix H and F] |
| CHK-12 | Approval gate status is truthful | Pass | [SRC-06, DA decision record] |

## Outputs

### 1. Unified End-to-End Data Model

| Entity ID | Entity | Role in workflow | Classification | Key producers | Key consumers | Evidence |
|---|---|---|---|---|---|---|
| E-001 | worker | Enterprise identity anchor for service and ER | Enterprise model | External systems and intake context | Triage, ER, audit | [SRC-02, Appendix D]; [SRC-04, section 10]; [SRC-05, silver.worker] |
| E-002 | case | Primary service or ER intake object | Other source | Intake and triage agents | Service workflow, ER escalation, audit | [SRC-02, Appendix D] |
| E-003 | er_case | ER classification and specialist handover object | Other source | ER risk agent | ER orchestrator and specialist | [SRC-02, Appendix D] |
| E-004 | route_decision | Deterministic route event | Agent created | Service triage | Orchestrator, response, ER intake | [SRC-02, Appendices C and D] |
| E-005 | response_draft | Bounded service response with citations | Agent created | Service response agent | QA control and employee channel | [SRC-02, Appendices C and D] |
| E-006 | policy_reference | Policy retrieval and citation object | Other source | Policy sources | Triage, response, ER timeline | [SRC-02, Appendix D] |
| E-007 | timeline_draft | ER assistive timeline artefact | Agent created | ER orchestrator | ER specialist | [SRC-02, Appendix D] |
| E-008 | handover_record | Human ownership transition evidence | Agent created and Human provided | Service and ER orchestrators | Human specialists and audit | [SRC-02, Appendix D] |
| E-009 | audit_event | Immutable closure evidence | Agent created | Audit agent | Governance and controls | [SRC-02, Appendix D] |
| E-010 | qa_review_outcome | Human QA quality evidence | Human provided | QA reviewer | Audit and governance | [SRC-02, Appendix D] |

### 2. Data Dictionary (Consolidated)

| Attribute ID | Entity | Attribute | Definition | Classification | Ownership | Evidence |
|---|---|---|---|---|---|---|
| A-001 | case | case_id | Primary identifier for case lifecycle | Other source | Case system owner TBC | [SRC-02, Appendix D] |
| A-002 | case | worker_id | Worker link for case context and traceability | Enterprise model linkage | HR data owner TBC | [SRC-02, Appendix D]; [SRC-04, section 10] |
| A-003 | case | stream | Service or ER route context | Other source | HR operations owner TBC | [SRC-02, Appendix D] |
| A-004 | route_decision | route_code | Output of deterministic triage routing | Agent created | HR operations owner TBC | [SRC-02, Appendix D] |
| A-005 | response_draft | confidence_indicator | Control signal for review gating | Not available (proposed) | QA control owner TBC | [SRC-02, Appendix F G-02] |
| A-006 | er_case | severity | ER risk severity for escalation | Other source | ER specialist owner TBC | [SRC-02, Appendix D] |
| A-007 | er_case | legal_exposure_flag | Legal exposure indicator used for specialist-plus-counsel route | Other source | ER specialist owner TBC | [SRC-03, D-004]; [SRC-02, Appendix F G-04] |
| A-008 | handover_record | accepted_by | Human accepter for ownership transition | Human provided | Operations owner TBC | [SRC-02, Appendix D] |
| A-009 | audit_event | decision_ref | Link to route or review decision in audit trail | Agent created | Governance owner TBC | [SRC-02, Appendix D] |
| A-010 | qa_review_outcome | review_reason_code | Controlled reason for QA decision | Not available (proposed) | QA control owner TBC | [SRC-02, Appendix F G-03] |

### 3. Relationship Model

| Relationship ID | Parent | Child | Cardinality | Link field(s) | Status | Evidence |
|---|---|---|---|---|---|---|
| R-001 | worker | case | 1:N | worker_id | Confirmed | [SRC-02, Appendices C and D] |
| R-002 | case | er_case | 1:0..1 | case_id | Confirmed | [SRC-02, Appendix D] |
| R-003 | case | route_decision | 1:N | case_id | Confirmed | [SRC-02, Appendix D] |
| R-004 | case | response_draft | 1:N | case_id | Confirmed | [SRC-02, Appendix D] |
| R-005 | case | handover_record | 1:N | case_id | Confirmed | [SRC-02, Appendices D and G] |
| R-006 | er_case | timeline_draft | 1:N | case_id | Confirmed | [SRC-02, Appendix D] |
| R-007 | case | audit_event | 1:N | case_id | Confirmed | [SRC-02, Appendix D] |
| R-008 | case | qa_review_outcome | 1:N | case_id | Confirmed | [SRC-02, Appendix D] |
| R-009 | case | policy_reference | N:N | policy_id with case-policy bridge | Proposed | [SRC-02, Appendix F G-07] |

### 4. Resolved Data Gap Log

| Gap ID | Consolidation result | Status | Evidence |
|---|---|---|---|
| G-01 | Retained as unresolved governance assignment task | Pending | [SRC-02, Appendix F] |
| G-02 | Kept as proposed attribute in consolidated dictionary | Pending | [SRC-02, Appendix F and Data Dictionary] |
| G-03 | Kept as proposed controlled reference field | Pending | [SRC-02, Appendix F and Data Dictionary] |
| G-04 | Kept as proposed ER codebook extension | Pending | [SRC-02, Appendix F and Data Dictionary] |
| G-05 | Kept as proposed retention metadata extension | Pending | [SRC-02, Appendix F] |
| G-06 | Kept as proposed handover SLA metadata extension | Pending | [SRC-02, Appendix F] |
| G-07 | Kept as proposed policy version lineage extension | Pending | [SRC-02, Appendix F] |
| G-08 | Kept as enterprise-mapping decision item for Design Authority | Pending | [SRC-02, Appendix F]; [SRC-05, source-mapping-register.csv pattern] |

### 5. End-to-End Data Flow Map

| Flow ID | From | To | Payload | Shared key | Evidence |
|---|---|---|---|---|---|
| F-001 | Intake channel | W-001 | Initial request and identity | worker_id | [SRC-02, Appendix G H-001] |
| F-002 | W-002 | W-003 | triage_packet_v1 | case_id | [SRC-02, Appendix G H-002] |
| F-003 | W-003 | W-004 | auto-resolve route payload | case_id | [SRC-02, Appendix G H-003] |
| F-004 | W-003 or W-004 | W-006 | human service handover payload | case_id | [SRC-02, Appendix G H-004] |
| F-005 | W-003 | W-007 | ER escalation payload | case_id | [SRC-02, Appendix G H-005] |
| F-006 | W-007 | W-008 | ER triage payload | case_id | [SRC-02, Appendix G H-006] |
| F-007 | W-008 | W-009 | ER specialist pack | case_id | [SRC-02, Appendix G H-007] |
| F-008 | W-005 or W-006 or W-009 | W-010 | closure and evidence payload | case_id | [SRC-02, Appendix G H-008] |

### 6. Design Authority Decision Record

| Decision ID | Reviewing body | Decision | Decision date | Conditions | Next action | Evidence |
|---|---|---|---|---|---|---|
| DA-001 | Factory Design Authority including SME | Pending | TBC - source required | Resolve ownership assignments and enterprise mapping for case entities | Carry unresolved items to DA working session | [SRC-01, Approval gate]; [SRC-02, Appendix H and F] |

## Controls and Evidence

| Control evidence requirement | Stage 5B evidence status | Evidence |
|---|---|---|
| End-to-end data trace map | Complete | [SRC-06, end-to-end flow map section] |
| Data model version | Complete | [SRC-02, version v0.1] |
| Change log for added data | Complete | [SRC-06, Stage 5B change log] |
| Cross-check completion evidence | Complete with pending checks | [SRC-06, checks performed] |
| Design Authority approval decision and date | Pending | [SRC-06, DA-001] |

## Approval Gate

Approval body: Factory Design Authority including SME.

Approval status: Pending.

If not approved, affected items return to Stage 5 model refinement, specifically G-01 to G-08 and ACO-01 to ACO-05. [SRC-01, Approval gate]

## Deliverable

Draft consolidated end-to-end data model package prepared for Design Authority review, with explicit pending governance and mapping items. [SRC-01, Deliverable]

## Key Tools

- Enterprise data model
- Data modelling templates
- ABBA assets
- Data lineage tools

[SRC-01, Key tools]

## Next Stage

Proceed to Stage 6 design only after Design Authority approval or conditional approval with controlled remediation actions. [SRC-01, Next stage]

# Stage 5B Change Log

| Change ID | Change description | Source basis | Status |
|---|---|---|---|
| CL-001 | Consolidated Stage 5 per-step entities into one unified model | [SRC-02, Appendices C and D] | Complete |
| CL-002 | Normalised relationship IDs R-001 to R-009 | [SRC-02, Appendices D and G] | Complete |
| CL-003 | Merged gap log into Stage 5B pending register | [SRC-02, Appendix F] | Complete |
| CL-004 | Added enterprise alignment evidence from Enterprise Business Data Objects overview | [SRC-04, sections 2, 3, 10, 13] | Complete |
| CL-005 | Added enterprise model technical alignment references from Fabric repository | [SRC-05, enterprise_model.yml and workforce SQL] | Complete |

# Conversion Evidence Record

| Field | Value |
|---|---|
| Source Stage 5 file | HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5_Model_v0.1.md |
| Conversion required | No format conversion required; source already Markdown |
| Semantic differences introduced | None |
| Reviewer status | Pass |

# ACO Register

| ACO ID | Type | Statement | Owner | Status | Evidence |
|---|---|---|---|---|---|
| ACO-01 | Missing information | Named owners for key entities and controls remain unresolved | Capability governance lead | Pending | [SRC-02, Appendix H] |
| ACO-02 | Open question | Canonical admission decision for case and er_case unresolved | Data architecture owner | Pending | [SRC-02, Appendix H]; [SRC-05, modelling standard] |
| ACO-03 | Missing information | Confidence and QA reason code standards not yet supplied | QA control owner | Pending | [SRC-02, Appendix F] |
| ACO-04 | Constraint | Stage 5B remains evidence-based and cannot infer approval outcomes | Design Authority chair | Active | [SRC-01, Approval gate] |
| ACO-05 | Missing information | DA decision date and formal approval evidence not available | Design Authority secretariat | Pending | [SRC-06, DA-001] |

# Source Index

| SRC ID | Artefact |
|---|---|
| SRC-01 | Delivery-Control/Stage_5.md |
| SRC-02 | Stage 5 and 5B Output/HR-MTS-001_002_Employee_Service_ER_IR_Intake_Stage5_Model_v0.1.md |
| SRC-03 | Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md |
| SRC-04 | Delivery-Control/Enterprise_Business_Data_Objects_Overview_extracted.txt |
| SRC-05 | Neill-KPMG/fabric-layer repository, enterprise-data-model folder artefacts |
| SRC-06 | This Stage 5B consolidation working package |
