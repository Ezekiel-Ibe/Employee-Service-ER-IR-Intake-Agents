# Stage 4 – Classify

**Branding:** KPMG

**Identify and classify the agents required for each workflow step and define the internal orchestration, handovers and control points.**

## Objective

For each workflow step, determine which agents (and controls) are required to complete the work, how they interact, and how the step connects to the next step.  
Classify every agent using the five approved agent types and create a Framework for each.

## Inputs from Stage 3

- Overall AI Framework
- End to end workflow
- Workflow steps
- Decisions, exceptions and human intervention points
- SME confirmation

## Stage 4 activities (per workflow step)

### 1. Analyse the workflow step

- Understand the purpose of the step
- Review required work and outcomes
- Consider decisions, exceptions and handovers

### 2. Identify agents and controls

- List all agents needed to complete the step
- Include any control mechanisms
- Include any human reviews or approvals

### 3. Classify each agent (five agent types)

- Classify every agent as one or more of:
  - Task
  - Insight
  - Orchestration
  - Control
  - Experience

### 4. Define internal orchestration

- Map the sequence and interactions between agents
- Define data and information flow between them

### 5. Define handovers

- Define input from previous step
- Define output to next step
- Specify data and information exchanged

### 6. Define control point

- Every step must have a control point
- Determine control type:
  - Control Agent
  - Deterministic rule
  - Human review
  - Human approval
  - Audit check
  - Embedded control

### 7. Create Framework for each agent

- Complete a component AI Framework for every agent
- Document purpose, inputs, outputs, behaviour, exceptions, controls, human interaction, etc.

### 8. Assess reuse using ABBA

- Search ABBA for relevant assets
- Record reuse assessment:
  - Reused unchanged
  - Adapted
  - Combined
  - No suitable asset
  - New design
- Record any variance from the business requirement

## Outputs of Stage 4

- Agent inventory per workflow step
- Agent classifications
- Internal orchestration diagrams
- Handovers to previous and next steps
- Control point defined for every step
- Framework for every agent
- ABBA reuse assessment and variance log

## Example – Workflow step: Validate contract

### Agents and controls identified

- Contract data retrieval agent (Task)
- Contract clause understanding agent (Insight)
- Validation orchestrator agent (Orchestration)
- Contract validation control (Control Agent)
- Commercial reviewer (Human approval)

### Internal orchestration (within the step)

1. Retrieve contract and related documents
2. Extract and interpret key contract clauses
3. Compare clauses against rules and policies
4. Control agent validates results and flags issues
5. Commercial reviewer approves or requests changes

#### Input from previous step

Customer, order and proposed terms

#### Output to next step

Validated contract and key terms

### Control point

**Contract validation control**

- **Type:** Control Agent
- **Checks:** Policy compliance, approved terms, mandatory clauses, red flags
- **Outcome:** Pass / Fail / Flag
- **Escalation:** Review by Commercial reviewer

### ABBA reuse assessment

- Existing ABBA asset found
- Adapted to include new escalation rule
- Variance from business requirement: None
- Reuse level: High

## Practitioner guidance

- Fully understand the purpose of the step before identifying agents
- Do not design solutions in this stage – focus on logical architecture
- Ensure every step has a control point
- Document handovers clearly – this is critical for end to end flow
- Use ABBA to save time and promote existing patterns

## Key success factors

- Clear classification drives good design
- Internal orchestration must be complete
- Controls must be proportionate to risk
- Handovers must be unambiguous
- Reuse where possible, design only when necessary

## Common pitfalls

- Missing a control point
- Classifying an agent into the wrong type
- Undefined handover data
- Creating agents that duplicate existing ABBA assets
- Not capturing human reviews or approvals

## Next stage

### 5. Model

Define the data required by agents, controls and handovers.

## Agent type legend

- Task
- Insight
- Orchestration
- Control
- Experience

---

**Document classification:** KPMG confidential  
**Footer:** Agent Factory Delivery Methodology | Page 10
