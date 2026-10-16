# Stages 5 and 5B – Model and Data Model Consolidation

**Branding:** KPMG

**Define all data required by every agent, control and workflow handover, then consolidate into a unified, end-to-end data model.**

## Stage 5 – Model

**Stage marker:** 5 in a dark blue circle.

**Model data for each workflow step**

### Objective

Identify and **model** all data required within each workflow step and between workflow steps.

### Model at two levels

#### Within each workflow step

Data exchanged between agents, controls and human participants in the step

**Illustrated flow:** Agent → Control → Human participant

#### Between workflow steps

Data handed from one workflow step to the next

**Illustrated flow:** Step n → Step n+1 → Step n+2

A bidirectional arrow is shown between the “Within each workflow step” and “Between workflow steps” models.

### Data classification

Classify every data item using one of the following:

**Visual classification key:**

- Green circle with a white tick: Enterprise model
- Blue circular marker: Other source
- Orange warning triangle with an exclamation mark: Not available
- Purple circle with a white plus sign: Agent created
- Pink human-participant icon: Human provided

- **Enterprise model**
  - Already in the enterprise data model
- **Other source**
  - Exists elsewhere, not yet in model
- **Not available**
  - Does not currently exist
- **Agent created**
  - Created during workflow
- **Human provided**
  - Provided by a human participant

### Inputs

- Workflow steps
- Agent inventory
- Component Frameworks
- Internal orchestration
- Workflow handovers
- Control points
- Overall AI Framework
- Enterprise data model
- ABBA reference

### Actions

1. Identify input data for each agent and control
2. Identify data created or updated
3. Identify data consumed by controls
4. Identify data passed to other agents
5. Identify data handed to the next step
6. Define entity, attributes and relationships
7. Classify data availability
8. Log missing data
9. Add missing data to the model
10. Record the source and ownership

### Outputs

- Data model per workflow step
- Entity and attribute definitions
- Relationships
- Data classifications
- Data gap log (added to model)
- Source and ownership
- Within-step and between-step data flows

### Practitioner guidance

- Trace data through the step and to the next step
- Be specific on entities and attributes
- Do not assume data exists – classify it
- Add missing data directly and continue
- Use ABBA to identify existing entities and common attributes
- Maintain clear lineage and ownership

### Controls and evidence

- Evidence of data trace
- Data classification recorded
- Missing data logged and added
- Data lineage documented
- Source and ownership recorded

### Exit criteria

Every agent, control and handover has its data requirements modelled with availability classified and any gaps added.

### Deliverable

A complete data model for each workflow step, ready for consolidation.

### Key tools

- Enterprise data model
- ABBA assets
- Data modelling templates
- Entity and attribute catalogues

## Stage 5B – Data Model Consolidation

**Stage marker:** 5B in a purple circle.

**Consolidate and approve the end-to-end data model**

### Purpose

Bring the data models from all workflow steps together to confirm the complete, end-to-end data model supports the full workflow.

### Inputs

- Data models from all workflow steps
- Data classifications
- Data gap log (with added items)
- Workflow handovers
- Overall AI Framework
- Agent inventory
- Control requirements

### Actions

1. Assemble all step data models
2. Walk the end-to-end workflow
3. Trace every input to a source
4. Trace every output to a consumer or storage
5. Validate within-step data exchanges
6. Validate between-step handovers
7. Confirm consistent entities and attributes
8. Confirm agent created data destinations
9. Confirm human data capture points
10. Identify missing data, attributes or relationships
11. Add and update as required
12. Repeat end-to-end check
13. Prepare for Design Authority review

### Checks performed

- Every input has a defined source
- Every output has a defined consumer or storage
- Internal data exchanges are consistent
- Step handovers are consistent and complete
- Shared entities and attributes are consistent
- Agent created data has a destination
- Human provided data has a capture point
- Control evidence is supported
- Enterprise model alignment is achieved

### Outputs

- Unified end-to-end data model
- Data dictionary
- Relationship model
- Resolved data gap log
- End-to-end data flow map
- Design Authority decision record

### Controls and evidence

- End-to-end data trace map
- Data model version
- Change log for added data
- Evidence of cross-check completion
- Design Authority approval decision and date

### Approval gate

Factory Design Authority (including SME)

Approval confirms the data model supports the complete workflow.

If not approved: return affected items to Stage 5, Model.

### Deliverable

Approved, end-to-end data model ready to support detailed design.

### Key tools

- Enterprise data model
- Data modelling templates
- ABBA assets
- Data lineage tools

## Visual structure and colour coding

- Stage 5 content uses dark blue section headers and borders.
- Stage 5B content uses purple section headers and borders.
- The two modelling levels are presented side by side, with a grey bidirectional arrow between them.
- “Within each workflow step” is shown with agent, control-shield and human-participant icons connected left to right.
- “Between workflow steps” is shown as three rounded boxes labelled Step n, Step n+1 and Step n+2, connected left to right.
- Stage 5 and Stage 5B each have separate Deliverable and Key tools panels on the right.
- The bottom row contains Common principles, Key success factors, Common pitfalls and Next stage panels.

## Common principles

- Model at both levels – within the step and between steps
- Classify every data item
- Log and add missing data – no separate approval required for additions
- Maintain clear lineage, ownership and definitions

## Key success factors

- Complete and accurate data trace
- Consistent entity and attribute definitions
- Early identification of missing data
- Clear handovers and evidence for controls

## Common pitfalls

- Missing handover data between steps
- Inconsistent entity or attribute definitions
- Assuming data exists without classifying it
- Not validating the combined model end-to-end

## Next stage

Proceed to **Stage 6 – Design** with an approved end-to-end data model.

---

**Document classification:** KPMG confidential  
**Footer:** Agent Factory Delivery Methodology | Page 11
