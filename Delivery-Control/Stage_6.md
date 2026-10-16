# Stage 6 – Design

**Branding:** KPMG

**Produce detailed, technology-agnostic designs for each agent, control and workflow handover, including unit test scenarios.**

## 6. Stage 6 – Design

**Detailed design for each component**

### Objective

Convert the logical architecture and approved data model into detailed designs that specify the behaviour, data, controls, exceptions and test scenarios for every component.

### Inputs

- Overall AI Framework
- Component AI Frameworks
- Agent classifications
- Internal orchestration (Stage 4)
- Approved end-to-end data model (Stage 5B)
- Control points
- ABBA reuse assessment
- Business rules & constraints
- SME confirmed workflow

### Actions

1. Review Framework & classification for the component
2. Define purpose, trigger and objectives
3. Define inputs and outputs using the data model
4. Define detailed behaviour and decision logic
5. Define deterministic calculations
6. Define AI instructions / prompts (where applicable)
7. Design responses and citations
8. Define exception handling and escalation paths
9. Define human intervention points
10. Define control operation, evidence and audit
11. Define integrations and handovers
12. Create unit test scenarios and expected results
13. Document assumptions, risks and limitations

### Outputs

- Detailed design for each agent, control and workflow handover
- User stories
- Behaviour specification
- Data mappings (inputs/outputs)
- Deterministic logic specification
- AI instructions/prompts
- Response design
- Exception handling design
- Human intervention design
- Control design & audit evidence
- Integration and handover specifications
- Unit test scenarios & expected results
- Assumptions, risks and dependencies

### Practitioner guidance

- Design the 'what' not the 'how' – remain technology agnostic
- Trace every input/output to the data model
- Ensure control is defined for every workflow step
- Use ABBA assets to accelerate design and avoid duplication
- Write unit tests for normal and exception scenarios
- Be explicit about human interactions and approvals

### Controls and evidence

- Design peer review
- Unit test coverage review
- Control point validation
- SME visibility
- Evidence of ABBA reuse assessment
- Assumption and risk log

### Exit criteria

- All components have detailed designs
- Unit test scenarios defined for every component
- All controls and handovers designed
- Ready for consolidation (6B)

### Key tools & references

- Design templates
- ABBA assets
- Agent pattern library
- Data model
- Business rules repository

### Deliverable

Detailed, technology-agnostic design package for every component, including unit test scenarios, ready for solution design consolidation.

## 6B. Stage 6B – Solution Design Consolidation

**Consolidate and approve the complete solution design**

### Objective

Bring all component designs together to confirm they form one coherent, end-to-end solution that meets the business outcome and is ready for build.

### Inputs

- All component designs from Stage 6
- Unit test scenarios
- End-to-end workflow
- Approved end-to-end data model (Stage 5B)
- Control point definitions
- ABBA reuse assessments

### Actions

1. Assemble all component designs
2. Validate end-to-end workflow flow
3. Validate inputs/outputs across steps
4. Validate internal orchestrations
5. Validate workflow handovers
6. Validate control coverage for every step
7. Validate exception paths and escalations
8. Validate human intervention consistency
9. Validate unit test coverage is sufficient
10. Confirm alignment with Overall AI Framework and business outcome
11. Document open issues and required actions

### Outputs

- Consolidated solution design
- End-to-end orchestration view
- Control coverage map
- Unit test coverage report
- Readiness assessment
- Recommended implementation technology
- Consolidation issues & actions log

### Practitioner guidance

- Think end-to-end, not component by component
- Challenge assumptions
- Ensure consistency of language, responses and controls
- Confirm user journey is coherent
- Validate that nothing is missed (data, control, handover, exception)
- Prepare for Design Authority review

### Controls and evidence

- Consolidation review by design lead
- SME visibility
- Design Authority review and approval
- Evidence of alignment to business outcome

### Exit criteria

- All items resolved
- Design Authority approval
- Build ready confirmed

### Design Authority approval

Approved by the Factory Design Authority (SME member) who confirms the solution is complete and build ready.

### Deliverable

Approved build-ready solution design package with recommended technology and unit test coverage.

## Agent type legend

- **Task** – Executes work or actions
- **Insight** – Analyses and provides insights
- **Orchestration** – Coordinates flow and activities
- **Control** – Ensures compliance and accuracy
- **Experience** – User interface and engagement

## Success factors

- Complete and consistent designs
- Clear controls and handovers
- Comprehensive unit test scenarios
- Alignment to business outcome
- SME engagement throughout

## Common pitfalls

- Incomplete exception handling
- Missing control points
- Inconsistent handovers
- Unclear human interventions
- Insufficient unit test coverage

## Next stage

### 7. Build

Proceed to Stage 7 – Build. Parallel build of components with unit testing and individual technical reviews.

---

**Document classification:** KPMG confidential  
**Footer:** Agent Factory Delivery Methodology | Page 12
