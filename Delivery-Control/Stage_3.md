# Stage 3 – Decompose

**Branding:** KPMG

**Create the overall AI Framework and decompose the business capability into an end to end workflow**

## Objective

Translate the defined business capability into an overall AI Framework and an end to end workflow.  
Break the capability down into its workflow steps that will be analysed and designed in the subsequent stages.

## Inputs from Stage 2

- Defined business capability
- Confirmed outcome
- Scope, users and success measures
- Constraints

## Stage 3 activities

### 1. Review and understand the capability

- Deep dive the defined capability
- Clarify intent and boundaries
- Validate success measures
- Note assumptions, constraints and open questions

### 2. Create overall AI Framework

- Capture the purpose and intended outcomes
- Define inputs, outputs and value
- Identify users, systems and dependencies
- Record human involvement and guardrails

### 3. Map the end to end workflow

- Identify the trigger that starts the workflow
- Map the high level sequence of business activities
- Identify decisions, exceptions and handovers
- Identify human intervention points

### 4. Decompose into workflow steps

- Break the workflow into discrete steps
- Keep steps at the right level of granularity
- Ensure steps collectively deliver the intended outcome

### 5. Define handovers and interactions

- Define the handoff from previous step
- Define the output to the next step
- Note any data or information exchanged
- Confirm who or what performs the step

### 6. Validate with SME

- Walk through the end to end workflow with the SME
- Confirm accuracy of steps, decisions and handovers
- Agree any changes required
- Confirm workflow is complete

### 7. Obtain SME confirmation

- SME confirms the workflow accurately represents the business process
- Decomposition is complete
- Steps collectively deliver the intended outcome

## Outputs of Stage 3

- **Overall AI Framework**  
  for the business agent
- **End to end workflow**  
  high level process map
- **Workflow steps**  
  decomposed list of activities
- **Decisions and exceptions**
- **Human intervention points**
- **SME confirmation**  
  that the workflow reflects the business process

## Example – Order Capture and Validation (O2C)

### Trigger

**Order received**  
(Email, EDI, Portal)

### Workflow

#### 1. Capture order

Extract order header and line items

#### 2. Validate customer

Verify customer and hierarchy information

#### 3. Validate contract

Check contract existence and terms

#### 4. Validate pricing

Check price book and contract pricing

#### 5. Check credit

Assess credit exposure and limits

#### 6. Route exception

Create and route issues for resolution

#### 7. Approve order

Obtain approval if required

#### 8. Release order

Confirm and release for fulfilment

### End state

**Valid order ready for fulfilment**

### Diagram legend

- Workflow step
- Step sequence
- Information / data handoff
- Human intervention point

## Practitioner guidance

- Focus on the business process, not on how it will be built
- Use outcomes and decisions to identify the right steps
- Ensure no material activity is missed
- Keep steps at the right level of detail for design

## Key success factors

- Clear understanding of the business intent
- Accurate workflow mapping and decomposition
- Early SME engagement and collaboration
- Complete handover definitions between steps

## Common pitfalls

- Designing solution details too early
- Steps too granular or too high level
- Missing exceptions and human interventions
- Unclear handovers and data exchanges

## Next stage

### 4. Classify

Classify each workflow step into the five agent types and define the agents and controls required.

---

**Document classification:** KPMG confidential  
**Footer:** Agent Factory Delivery Methodology | Page 6
