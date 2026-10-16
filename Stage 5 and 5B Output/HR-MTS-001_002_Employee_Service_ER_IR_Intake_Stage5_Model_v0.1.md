---
title: Employee Service and ER IR Intake Agent Stage 5 Model
stage: Stage 5 - Model
businessAgent: Employee Service and ER IR Intake Agent (HR-MTS-001/002)
status: Draft for working review
version: v0.1
language: English (UK)
classification: KPMG Confidential
---

# Document Control

| Field | Value | Evidence |
|---|---|---|
| Capability | Employee Service and Case Resolution | [SRC-04, section 6.4] |
| Agent identifier | HR-MTS-001/002 | [SRC-04, section 6.4] |
| Value stream | Manage Workforce Relations to Experience | [SRC-04, Part 1 value stream table] |
| Scope | Stage 5 data modelling only, per-step and between-step | [SRC-01, Stage 5 objective] |
| Prepared date | 2026-10-16 | [SRC-01, Stage 5 context] |
| Prepared for | Stage 5B consolidation and Design Authority preparation | [SRC-01, Stage 5B purpose] |

# Contents

1. Stage 5 - Model
2. Common Principles
3. Key Success Factors
4. Common Pitfalls
5. Appendix A - Agent Directory
6. Appendix B - ABBA and Reused Assets Referenced by Workflow
7. Appendix C - Workflow Step Data Model
8. Appendix D - Entities Consumed by Agents
9. Appendix E - Data Classification Summary
10. Appendix F - Data Gap Log Summary
11. Appendix G - Between-Step Handover Map
12. Appendix H - Assumptions, Constraints and Open Questions
13. Appendix I - Referenced Artefacts
14. Appendix J - Stage 5B Handover Note

# 1. Stage 5 - Model

## 1.1 Objective

Identify and model all data required within each workflow step and between workflow steps for the Employee Service and ER IR Intake capability, including source, ownership, lineage, and availability classification. [SRC-01, Stage 5 objective]; [SRC-05, Purpose]

## 1.2 Model at Two Levels

| Level | Definition in this capability | Evidence |
|---|---|---|
| Within each workflow step | Data exchanged between intake, triage, response, ER routing, controls, and human participants in each W-001 to W-010 step | [SRC-01, Model at two levels]; [SRC-02, Workflow Decomposition Catalogue] |
| Between workflow steps | Data handed from each workflow step to the next, including route decisions, case payloads, ER flags, and audit evidence | [SRC-01, Model at two levels]; [SRC-02, Handover register] |

## 1.3 Data Classification

Classification categories applied exactly as required:

| Classification | Definition | Applied use in this model | Evidence |
|---|---|---|---|
| Enterprise model | Already in enterprise model | Worker, Position, Organisation Unit, Employment, Compensation, Payroll Run, Payroll Line aligned to enterprise model and Fabric Silver or Gold structure | [SRC-01, Data classification]; [SRC-06, section 10 and Appendix A]; [SRC-07, enterprise-data-model/sql/10_silver/070_workforce.sql; enterprise-data-model/sql/20_gold/005_workforce_star.sql] |
| Other source | Exists elsewhere, not yet in enterprise model | Case, ERCase, SLA policy parameters, service knowledge articles, QA review packets | [SRC-01, Data classification]; [SRC-04, section 6.4 data schema] |
| Not available | Does not currently exist | Explicit confidence score field, explicit review_reason_code taxonomy, formal ER legal exposure codebook | [SRC-01, Data classification]; [SRC-03, TBC items] |
| Agent created | Created during workflow | Route decision payload, ER timeline draft, policy retrieval bundle, audit payload enrichments | [SRC-01, Data classification]; [SRC-04, section 6.4 generic script]; [SRC-02, W steps] |
| Human provided | Provided by human participant | HR advisor judgement, ER specialist determination notes, QA reviewer outcomes | [SRC-01, Data classification]; [SRC-02, HIP-001 to HIP-005] |

## 1.4 Inputs

| Input | Use in Stage 5 modelling | Evidence |
|---|---|---|
| Workflow steps | Drives W-001 to W-010 data decomposition | [SRC-01, Inputs]; [SRC-02, Workflow Decomposition Catalogue] |
| Agent inventory | Determines producer and consumer roles | [SRC-01, Inputs]; [SRC-02, Agent Landscape] |
| Component frameworks | Determines per-agent data boundaries | [SRC-01, Inputs]; [SRC-02, Appendix A] |
| Internal orchestration | Determines within-step exchange order | [SRC-01, Inputs]; [SRC-02, Internal orchestration model] |
| Workflow handovers | Determines between-step payload and shared keys | [SRC-01, Inputs]; [SRC-02, Handover register] |
| Control points | Determines control-consumed data and evidence needs | [SRC-01, Inputs]; [SRC-02, control points C-001 to C-010] |
| Overall AI Framework | Confirms autonomy and human boundary | [SRC-01, Inputs]; [SRC-02, Capability Context] |
| Enterprise data model | Confirms canonical entities and layer naming | [SRC-01, Inputs]; [SRC-06, sections 10, 14, Appendix A]; [SRC-07, enterprise-data-model/config/enterprise_model.yml] |
| ABBA reference | Supports reusable entity and attribute patterns | [SRC-01, Inputs]; [SRC-02, Appendix C reuse assessment]; [SRC-08, selected ABBA rows] |

## 1.5 Actions (1 to 10) and Results

| Action | Result for this capability | Evidence |
|---|---|---|
| 1. Identify input data for each agent and control | Inputs identified for all W-001 to W-010 steps | [SRC-01, Actions]; [SRC-02, W-001 to W-010] |
| 2. Identify data created or updated | Created and updated payloads mapped by step and operation | [SRC-01, Actions]; [SRC-02, Operations column] |
| 3. Identify data consumed by controls | Control-consumed fields mapped for C-001 to C-010 | [SRC-01, Actions]; [SRC-02, Control points] |
| 4. Identify data passed to other agents | Inter-agent data transfer mapped in within-step and handover records | [SRC-01, Actions]; [SRC-02, H-001 to H-008] |
| 5. Identify data handed to next step | Sequential handovers mapped with shared keys and payload | [SRC-01, Actions]; [SRC-02, workflow and handover sections] |
| 6. Define entity, attributes and relationships | Entity and relationship model defined in Appendices C, D and G | [SRC-01, Actions]; [SRC-04, Case and ERCase schema]; [SRC-06, enterprise object inventory] |
| 7. Classify data availability | Every named data item classified per mandatory categories | [SRC-01, Actions]; [SRC-01, Data classification] |
| 8. Log missing data | Missing fields and taxonomies logged as G-01 to G-08 | [SRC-01, Actions]; [SRC-03, unresolved TBC references] |
| 9. Add missing data to model | Missing items added as proposed attributes or control metadata fields | [SRC-01, Actions]; [SRC-05, non-negotiable rules] |
| 10. Record source and ownership | Source and role-based ownership fields captured for each major entity | [SRC-01, Actions]; [SRC-05, ownership terminology rules] |

## 1.6 Outputs

| Output | Delivery status | Evidence |
|---|---|---|
| Data model per workflow step | Complete for W-001 to W-010 | [SRC-01, Outputs]; Appendix C |
| Entity and attribute definitions | Complete with TBC markers for unresolved ownership metadata | [SRC-01, Outputs]; Appendix D |
| Relationships | Complete logical relationship set for service and ER intake model | [SRC-01, Outputs]; Appendix G |
| Data classifications | Complete by data item | [SRC-01, Outputs]; Appendix E |
| Data gap log | Complete with resolution categories | [SRC-01, Outputs]; Appendix F |
| Source and ownership | Role-level ownership complete; named-owner assignment pending | [SRC-01, Outputs]; Appendix H |
| Within-step and between-step data flows | Complete and cross-referenced to handovers | [SRC-01, Outputs]; Appendix C and Appendix G |

## 1.7 Practitioner Guidance Applied

| Guidance | Application in this deliverable | Evidence |
|---|---|---|
| Trace data through step and next step | Each workflow row includes next-step handover payload | [SRC-01, Practitioner guidance]; Appendix C |
| Be specific on entities and attributes | Attributes listed explicitly for case, ER, route, and audit payloads | [SRC-01, Practitioner guidance]; Appendix D |
| Do not assume data exists | Missing values explicitly classified as Not available and logged | [SRC-01, Practitioner guidance]; Appendix E and F |
| Add missing data directly and continue | Missing fields included as proposed attributes in model | [SRC-01, Practitioner guidance]; Appendix D and F |
| Use ABBA for common entities | ABBA references used for reuse alignment and naming support | [SRC-01, Practitioner guidance]; [SRC-08, relevant ABBA rows] |
| Maintain clear lineage and ownership | Source, producer, consumer, ownership columns maintained | [SRC-01, Practitioner guidance]; Appendix C and D |

## 1.8 Controls and Evidence

| Control expectation | Evidence in this deliverable | Evidence |
|---|---|---|
| Evidence of data trace | Full W and H mapping with source and destination | [SRC-01, Controls and evidence]; Appendix C and G |
| Data classification recorded | Every major item categorised | [SRC-01, Controls and evidence]; Appendix E |
| Missing data logged and added | Gaps logged and represented as model entries | [SRC-01, Controls and evidence]; Appendix F |
| Data lineage documented | Source-to-consumer lineage captured by step and handover | [SRC-01, Controls and evidence]; Appendix C and G |
| Source and ownership recorded | Role-level ownership included; named role resolution open | [SRC-01, Controls and evidence]; Appendix D and H |

## 1.9 Exit Criteria

Exit criteria status: Partially met.

| Exit criterion | Status | Rationale | Evidence |
|---|---|---|---|
| Every agent, control and handover has data requirements modelled | Pass | Data requirements mapped for A-001 to A-008 and H-001 to H-008 | [SRC-01, Exit criteria]; [SRC-02, Workflow and Handover catalogues] |
| Availability classified for all required data items | Pass | Classification completed and recorded | [SRC-01, Exit criteria]; Appendix E |
| Gaps added to model | Pass | Gaps logged and reflected in proposed model fields | [SRC-01, Exit criteria]; Appendix F |
| Ownership resolved to named owners | Pending | Role-level ownership present, named owner mapping not yet evidenced | [SRC-03, unresolved ownership items]; Appendix H |

## 1.10 Deliverable

Complete Stage 5 data model for each workflow step, ready for Stage 5B consolidation. [SRC-01, Deliverable]

## 1.11 Key Tools

- Enterprise data model
- ABBA assets
- Data modelling templates
- Entity and attribute catalogues

[SRC-01, Key tools]

# 2. Common Principles

- Model data at both levels: within-step and between-step.
- Classify every data item.
- Log and add missing data without pausing model progression.
- Maintain lineage, ownership and definition clarity.

[SRC-01, Common principles]

# 3. Key Success Factors

- Complete and accurate data trace from source to consumer.
- Consistent entity and attribute definitions across all steps.
- Early identification and logging of missing data.
- Clear handovers and control evidence coverage.

[SRC-01, Key success factors]

# 4. Common Pitfalls

- Missing handover payloads between workflow steps.
- Inconsistent entity and attribute naming.
- Assuming data exists without explicit classification.
- Failing to validate combined model readiness for Stage 5B.

[SRC-01, Common pitfalls]

# 5. Appendix A - Agent Directory

| Agent ID | Agent name | Workflow coverage | Primary data role | Evidence |
|---|---|---|---|---|
| A-001 | Intake Context Agent | W-001, W-002 | Creates and validates case intake payload | [SRC-02, Agent Landscape and W-001/W-002] |
| A-002 | Service Triage Agent | W-003 | Derives route decision | [SRC-02, W-003]; [SRC-04, triage_case] |
| A-003 | Service Response Agent | W-004, W-005 | Creates bounded response and provenance | [SRC-02, W-004/W-005] |
| A-004 | Service Workflow Orchestrator | W-003 to W-006 | Transmits service and ER route payloads | [SRC-02, orchestration and H-003 to H-005] |
| A-005 | ER Intake Risk Agent | W-007 | Derives ER risk and flags | [SRC-02, W-007]; [SRC-04, er_triage] |
| A-006 | ER Handover Orchestrator | W-008, W-009 | Creates ER policy and timeline pack and transmits handover | [SRC-02, W-008/W-009] |
| A-007 | Quality and Policy Control Agent | W-004, W-005, W-010 | Validates sensitivity and QA sampling controls | [SRC-02, D-002 and D-005] |
| A-008 | Audit and Evidence Agent | W-010 | Creates immutable audit evidence | [SRC-02, W-010]; [SRC-04, audit schema] |

# 6. Appendix B - ABBA and Reused Assets Referenced by Workflow

| ABBA ID | ABBA asset | Mapping to this capability | Reuse disposition in Stage 5 modelling | Evidence |
|---|---|---|---|---|
| VA-1331 | HR inquiry responder | Front-door service request response context | Adapted schema for bounded response and provenance | [SRC-02, Appendix C]; [SRC-08, row VA-1331] |
| VA-1333 | Support services workflow manager | Service routing and assignment patterns | Adapted for deterministic service and ER branch flows | [SRC-02, Appendix C]; [SRC-08, row VA-1333] |
| VA-1205 | Investigation case manager | ER intake case handling | Adapted for intake-only, human-led determination model | [SRC-02, Appendix C]; [SRC-08, row VA-1205] |
| VA-1208 | ER compliance monitor | ER controls and compliance evidence | Reused control intent | [SRC-02, Appendix C]; [SRC-08, row VA-1208] |
| VA-1240 | Employee relations workflow manager | ER handover orchestration | Adapted for strict no-auto-action ER boundary | [SRC-02, Appendix C]; [SRC-08, row VA-1240] |

# 7. Appendix C - Workflow Step Data Model

| Step | Producer | Consumer | Inputs consumed | Data created or updated | Control-consumed data | Handover payload | Primary entities | Data classification mix | Source and ownership |
|---|---|---|---|---|---|---|---|---|---|
| W-001 | Employee or manager | A-001 | query_text, worker_id, channel | case_id, intake_timestamp, stream_hint | required field presence | intake_packet_v1 | case, worker | Human provided, Other source, Enterprise model | Case system owner TBC; Worker enterprise owner TBC |
| W-002 | A-001 | A-002 | case.category, case.priority, policy_ref | triage_ready_flag, missing_data_flags | completeness_check_result | triage_packet_v1 | case, policy_reference, worker | Other source, Agent created, Enterprise model | Knowledge source owner TBC |
| W-003 | A-002 | A-004 | triage_packet_v1, sla_ruleset | route_decision, route_reason_code | rule_result_trace | route_payload_v1 | case, route_decision, policy_rule | Agent created, Other source | HR operations owner TBC |
| W-004 | A-003 | A-007 | route_payload_v1, knowledge_content | response_draft, citation_list | sensitivity_flag, confidence_indicator | review_payload_v1 | response_draft, knowledge_article, case | Agent created, Other source, Not available | Response quality owner TBC |
| W-005 | A-003 | Employee or manager | approved_response | response_sent_timestamp, response_status | qa_eligibility_flag | qa_input_payload_v1 | case, response_record | Agent created, Other source | Service owner TBC |
| W-006 | A-004 | HR advisor | route_human_payload | advisor_assignment, handover_note | assignment_ack_flag | human_service_handover_v1 | case, handover_record | Agent created, Human provided, Other source | HR advisor owner TBC |
| W-007 | A-005 | A-006 | er_escalation_payload | er_risk_type, severity, exposure_flags | er_no_auto_action_check | er_triage_payload_v1 | er_case, case, worker | Agent created, Other source, Enterprise model | ER specialist owner TBC |
| W-008 | A-006 | ER specialist | er_triage_payload_v1, policy_library | policy_bundle, timeline_draft | legal_flag_presence | er_specialist_pack_v1 | er_case, policy_bundle, timeline_draft | Agent created, Other source | ER policy owner TBC |
| W-009 | A-006 | ER specialist | er_specialist_pack_v1 | specialist_acceptance_status | acceptance_control_status | er_handover_complete_v1 | er_case, handover_record | Human provided, Agent created, Other source | ER specialist owner TBC |
| W-010 | A-008 | Governance record | route history, review outcomes, handover status | audit_event, lineage_record, completion_status | audit_completeness_check | audit_record_v1 | audit_event, case, er_case, worker | Agent created, Other source, Enterprise model | Governance owner TBC |

# 8. Appendix D - Entities Consumed by Agents

| Entity ID | Entity name | Layer or class | Key attributes used in Stage 5 | Primary steps | Classification | Source | Ownership status |
|---|---|---|---|---|---|---|---|
| E-001 | worker | Enterprise model (Silver or Gold conformed) | worker_id, worker_number, status, organisation context | W-001, W-007, W-010 | Enterprise model | enterprise model and Fabric workforce slice | Data owner TBC |
| E-002 | case | Capability source | case_id, worker_id, stream, category, priority, sla_hours, channel, auto_resolvable | W-001 to W-010 | Other source | HR case system and Stage 4 schema | Source owner TBC |
| E-003 | er_case | Capability source | case_id, worker_id, risk_type, severity, status, flags | W-007 to W-010 | Other source | ER system and Stage 4 schema | Source owner TBC |
| E-004 | route_decision | Agent-created payload | route_code, reason_code, decision_timestamp, decision_agent_id | W-003, W-004, W-006, W-007 | Agent created | A-002 deterministic output | Process owner TBC |
| E-005 | response_draft | Agent-created payload | response_text, citation_list, confidence_indicator, sensitivity_flag | W-004, W-005 | Agent created and Not available (for formal confidence field standard) | A-003 output | QA owner TBC |
| E-006 | policy_reference | Other source | policy_id, policy_section, policy_version, retrieval_timestamp | W-002, W-004, W-008 | Other source | policy and knowledge systems | Policy owner TBC |
| E-007 | timeline_draft | Agent-created payload | timeline_id, sequence_events, target_dates, assumptions | W-008, W-009 | Agent created | A-006 output | ER owner TBC |
| E-008 | handover_record | Agent and human record | handover_id, source_step, target_step, accepted_by, accepted_at | W-006, W-009, W-010 | Agent created and Human provided | orchestration and specialist actions | Operations owner TBC |
| E-009 | audit_event | Governance record | audit_id, case_id, action_type, actor, timestamp, decision_ref, source_snapshot_ref | W-010 | Agent created | A-008 and governance log | Governance owner TBC |
| E-010 | qa_review_outcome | Human-provided record | qa_case_ref, reviewer_id, review_result, review_reason_code | W-005, W-010 | Human provided and Not available (formal reason code taxonomy pending) | QA workflow | QA control owner TBC |

# 9. Appendix E - Data Classification Summary

| Data item | Classification | Reason | Evidence |
|---|---|---|---|
| worker_id and worker context | Enterprise model | Worker is in active enterprise object inventory and Fabric workforce model | [SRC-06, section 10 and Appendix A]; [SRC-07, silver.worker and gold.dim_worker] |
| case and er_case core fields | Other source | Defined in capability schema, not listed as canonical enterprise objects in supplied enterprise model | [SRC-04, section 6.4 data schema]; [SRC-06, scope description] |
| route_decision payload | Agent created | Produced by deterministic triage | [SRC-04, triage script]; [SRC-02, W-003] |
| response draft and citations | Agent created | Drafted in bounded service flow | [SRC-04, section 6.4 generic script]; [SRC-02, W-004] |
| confidence_indicator standard taxonomy | Not available | Field needed for control evidence but not defined in supplied schemas | [SRC-03, unresolved confidence control references] |
| HR advisor and ER specialist judgement notes | Human provided | Produced by human participants at intervention points | [SRC-02, HIP-001 to HIP-004] |
| audit completeness evidence | Agent created | Written at closure by audit agent | [SRC-02, W-010]; [SRC-04, audit schema] |

# 10. Appendix F - Data Gap Log Summary

| Gap ID | Gap description | Impacted steps | Resolution category | Proposed action | Owner | Status | Evidence |
|---|---|---|---|---|---|---|---|
| G-01 | Named data owners not specified for case, er_case, and policy entities | W-001 to W-010 | Governance metadata completion | Capture named owners during SME review | Capability governance lead | Open | [SRC-03, ownership TBC items] |
| G-02 | confidence_indicator field lacks governed scale and threshold metadata | W-004, W-005 | Add missing control attribute | Define confidence scale and threshold policy attributes | QA control owner | Open | [SRC-02, D-002 and EX-03 context] |
| G-03 | review_reason_code taxonomy not defined | W-004, W-005, W-010 | Add missing reference data | Introduce controlled reason code list | QA control owner | Open | [SRC-02, HIP-002, HIP-005] |
| G-04 | ER legal exposure codebook not explicit in schema | W-007, W-008 | Add missing ER reference attribute | Define legal and psychosocial flag codebook | ER specialist owner | Open | [SRC-02, D-004, EX-004] |
| G-05 | retention schedule fields for audit_event not explicitly defined | W-010 | Add missing governance attributes | Add retention_class and retention_expiry fields | Governance owner | Open | [SRC-03, retention TBC] |
| G-06 | handover acceptance SLA target not explicitly modelled | W-006, W-009 | Add missing handover control metric | Add handover_due_by and handover_breach_flag fields | HR operations owner | Open | [SRC-03, SLA and timing gaps] |
| G-07 | policy source versioning strategy not explicit | W-002, W-004, W-008 | Add missing lineage attribute | Add policy_version and policy_effective_date | Policy owner | Open | [SRC-02, H-002 and H-006] |
| G-08 | Enterprise mapping for case and er_case to canonical model unresolved | W-001 to W-010 | Cross-model mapping task | Run enterprise source-mapping review for case entities | Data architecture owner | Open | [SRC-06, source basis and governance status]; [SRC-07, source-mapping-register.csv pattern] |

# 11. Appendix G - Between-Step Handover Map

| Handover ID | Source step | Target step | Shared key(s) | Payload exchanged | Evidence |
|---|---|---|---|---|---|
| H-001 | External trigger | W-001 | worker_id, channel | initial query and identity payload | [SRC-02, H-001] |
| H-002 | W-002 | W-003 | case_id | triage_packet_v1 | [SRC-02, H-002] |
| H-003 | W-003 | W-004 | case_id, route_code | auto-resolve route payload | [SRC-02, H-003] |
| H-004 | W-003 or W-004 | W-006 | case_id | human service handover payload | [SRC-02, H-004] |
| H-005 | W-003 | W-007 | case_id, worker_id | ER escalation payload | [SRC-02, H-005] |
| H-006 | W-007 | W-008 | case_id, risk_type | ER triage output and flags | [SRC-02, H-006] |
| H-007 | W-008 | W-009 | case_id | ER specialist pack and timeline draft | [SRC-02, H-007] |
| H-008 | W-005 or W-006 or W-009 | W-010 | case_id | closure and evidence payload | [SRC-02, H-008] |

# 12. Appendix H - Assumptions, Constraints and Open Questions

| ACO ID | Type | Statement | Impacted sections | Owner | Status | Evidence |
|---|---|---|---|---|---|---|
| ACO-01 | Missing information | Named owners for business, data and controls remain TBC | Appendices C, D, F | Capability governance lead | Open | [SRC-03, ownership gaps] |
| ACO-02 | Constraint | Stage 5 remains logical and business-level, not physical database implementation | Entire document | Delivery lead | Active | [SRC-01, practitioner guidance]; [SRC-05, non-negotiable rules] |
| ACO-03 | Open question | Should case and er_case be admitted as canonical enterprise entities or remain domain-source entities? | Appendix D and F | Data architecture owner | Open | [SRC-06, model scope]; [SRC-07, modelling standard and source mapping] |
| ACO-04 | Missing information | Formal confidence and review reason standards are not provided | Appendices D, E, F | QA control owner | Open | [SRC-02, D-002 and HIP-005] |
| ACO-05 | Open question | What are approved handover and audit retention SLAs for this capability? | Appendix F and control evidence | HR operations and governance owners | Open | [SRC-03, retention and SLA TBC references] |

# 13. Appendix I - Referenced Artefacts

| SRC ID | Artefact | Purpose |
|---|---|---|
| SRC-01 | Delivery-Control/Stage_5.md | Authoritative Stage 5 and Stage 5B method statements |
| SRC-02 | Stage 4 Output/Employee_Service_ER_IR_Intake_Agent_Stage_4_Classify.md | Stage 4 workflow, handovers, controls, HIPs, and agent inventory |
| SRC-03 | Stage 3 Output/Employee_Service_ER_IR_Intake_Agent_Stage3_Decompose.md | Stage 3 baseline, unresolved ownership and governance gaps |
| SRC-04 | Source Documents/HR_Capability_and_Full_Agent_Catalogue_v1.md | Capability schema, deterministic tools, and business boundaries |
| SRC-05 | Source Documents/stage-5-document-generation.instructions.md and Source Documents/stage-5-SKILL.md | Stage 5 document structure and rules |
| SRC-06 | Delivery-Control/Enterprise_Business_Data_Objects_Overview_extracted.txt | Enterprise business object overview and governance context |
| SRC-07 | Neill-KPMG/fabric-layer enterprise-data-model repository evidence | Canonical layer patterns, workforce tables, standards, and governance files |
| SRC-08 | ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv | Reused asset references for service and ER patterns |

# 14. Appendix J - Stage 5B Handover Note

| Item | Value |
|---|---|
| Workflow steps modelled | 10 |
| Major entities modelled | 10 |
| Between-step handovers mapped | 8 |
| Gaps logged | 8 |
| Exit criteria status | Partially met |
| Stage 5B primary focus | End-to-end consolidation, consistency checks, enterprise alignment decision on case and er_case, and Design Authority decision record |

Ready for Stage 5B consolidation with explicit pending items carried forward under ACO and Gap registers.
