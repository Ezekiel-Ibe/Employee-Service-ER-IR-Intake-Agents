# Employee-Service-ER-IR-Intake-Agents

A structured HR agent-design repository for the **Employee Service & ER/IR Intake** capability within the **Manage Workforce Relations to Experience** value stream.

This repository captures the end-to-end design journey for the capability, from early decomposition through detailed design guidance, reusable agent references, and stage-based output artefacts. It is focused on **business capability decomposition, governance, controls, and reusable agent design** rather than implementation code.

## Repository at a glance

This repo contains the supporting materials for designing and documenting the Employee Service and ER/IR Intake agent capability, including:

- the core **capability catalogue** for HR agent value streams;
- the **Stage 3 decomposition deliverable** for the Employee Service & ER/IR Intake Agent;
- **reuse catalogue** material for identifying candidate reusable agents;
- stage-specific instructions and skill definitions for later design phases;
- stage output folders used to organise generated deliverables and working artefacts.

## What this repository covers

The repository centres on a single HR value stream:

### Manage Workforce Relations to Experience
Purpose: **Continuous Workforce Safeguarding**

The capability is split across two related agent responsibilities:

- **Employee Service** — front-door employee/manager support, triage, bounded self-service, and routing to human support where needed;
- **ER/IR Intake** — employee relations / industrial relations intake, risk classification, policy retrieval, timeline drafting, and human-led escalation.

Together, the capability is designed to:

- lower cost-to-serve;
- enforce consistent policy handling;
- protect employee experience;
- ensure sensitive ER matters remain human-led;
- preserve auditability, provenance, and governance controls.

## Repository structure

### `Source Documents/`
Foundational reference material used to define and govern the capability and downstream stage work.

Key documents include:

- `HR_Capability_and_Full_Agent_Catalogue_v1.md`
- `HR_Stage4_Instructions.md`
- `Stage_6_SKILL.md`
- `stage-5-SKILL.md`
- `stage-5b-SKILL (1).md`
- Stage 5/6 document generation instruction files

These documents define the HR agent landscape, the methodology for stage-based deliverables, and the rules for producing review-ready design artefacts.

### `Stage 3 Output/`
Contains the Stage 3 decomposition deliverable for the capability.

Notable file:

- `Employee_Service_ER_IR_Intake_Agent_Stage3_Decompose.md`

This artefact documents the capability summary, workflow, decisions, exceptions, human intervention points, assumptions, TBCs, and handover context needed for later stages.

### `ABBA-Reuse-Agents/`
Contains the reusable agent catalogue used to assess whether existing ABBA assets can be reused or adapted.

Notable file:

- `Annotated_Agents_H2RList.csv`

This catalogue helps identify candidate reusable agents across HR value streams, including service, payroll, learning, workforce planning, and employee relations capabilities.

### `Stage 4 Output/`
Stage 4 output area for classification deliverables and related artefacts.

### `Stage 5 and 5B Output/`
Stage 5 / 5B output area for approved data model and consolidation deliverables.

### `Stage 6 Output/`
Stage 6 output area for detailed-design artefacts.

### `Stage 6B Output/`
Stage 6B output area for consolidated or follow-on Stage 6 materials.

## Core capability summary

The Employee Service & ER/IR Intake capability is designed around a controlled, human-aware agent model:

- **bounded self-service** can be auto-resolved where policy coverage is clear;
- **non-standard or high-priority service cases** route to an HR advisor;
- **ER cases** are classified and handed to human specialists;
- **policy and law context** is retrieved to support grounded, cited responses;
- **audit trail and provenance** are preserved across all major outcomes.

## Key design principles

Across the repository, the following principles are consistently reinforced:

- **technology-agnostic design**;
- **human approval for consequential outcomes**;
- **segregation of duties**;
- **auditability and provenance**;
- **controlled handling of missing evidence and open questions**;
- **reuse first, new design only when necessary**;
- **clear separation of deterministic logic and AI-assisted narration**.

## Main artefacts

### Stage 3 deliverable
- Decomposes the capability into workflow steps, decisions, exceptions, and human intervention points.
- Establishes the baseline for downstream stage work.

### HR capability catalogue
- Defines the HR value streams and agent estate.
- Includes business outcomes, ownership patterns, data model foundations, tool catalogue, compliance framework, and agent-level engineering detail.

### Stage 4 and Stage 6 instruction files
- Provide reusable methodology for generating structured Markdown deliverables.
- Emphasise evidence-based, governed, UK English documentation.
- Define required headings, quality gates, validation rules, and reuse expectations.

### ABBA reuse catalogue
- Supports analysis of candidate reusable agents.
- Helps avoid duplication and align with existing patterns.

## Who this repository is for

This repository is useful for:

- HR transformation and operations teams;
- business analysts and process designers;
- agent solution designers;
- delivery leads and governance reviewers;
- SMEs reviewing capability decomposition;
- teams preparing Stage 4, Stage 5/5B, or Stage 6 artefacts.

## Expected usage

Typical usage of this repository is to:

1. review the HR capability catalogue;
2. study the Stage 3 decomposition;
3. assess reuse candidates in the ABBA catalogue;
4. generate or refine later-stage design documents;
5. maintain stage outputs in the relevant output folders.

## Notes on repository status

- The repository currently appears to be documentation-heavy rather than code-heavy.
- The existing top-level README is minimal, so this README expands the repository description and explains the full set of contents.
- The repository is well-suited as a design and governance workspace for HR agent capability modelling.

## Suggested next steps

If you are using this repository actively, the next logical steps are:

- review the Stage 3 decomposition for the Employee Service & ER/IR Intake capability;
- confirm the reused or adapted ABBA agent candidates;
- generate the Stage 4 classification deliverable;
- align Stage 5 / 5B data model work;
- prepare Stage 6 detailed design outputs.

---

## File map

- `README.md` — repository overview
- `Source Documents/` — methodology and governing source materials
- `ABBA-Reuse-Agents/Annotated_Agents_H2RList.csv` — reusable agent catalogue
- `Stage 3 Output/Employee_Service_ER_IR_Intake_Agent_Stage3_Decompose.md` — Stage 3 decomposition deliverable
- `Stage 4 Output/` — Stage 4 artefacts
- `Stage 5 and 5B Output/` — Stage 5 / 5B artefacts
- `Stage 6 Output/` — Stage 6 artefacts
- `Stage 6B Output/` — Stage 6B artefacts
