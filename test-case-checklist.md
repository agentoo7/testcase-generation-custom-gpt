# Functional Test Case Quality Checklist

Use this checklist to validate test cases before finalizing and approval.

## 1. Test Case Identification and Metadata

- [ ] Test Case ID follows naming convention: `{{PROJECT-CODE}}-TC-{{US-ID}}-{{SEQUENCE}}`
- [ ] Test Case Title is clear, concise, and descriptive
- [ ] User Story ID is correctly referenced
- [ ] Creation date and author are documented
- [ ] Priority level is assigned (Critical/High/Medium/Low)
- [ ] Test type is specified (Functional/Integration/Regression/Smoke)
- [ ] Execution type is indicated (Manual/Automated/Both)
- [ ] Risk level is assessed (High/Medium/Low)

## 2. Test Objective and Scope

- [ ] Test objective clearly states what is being tested
- [ ] Purpose is understandable to anyone reading it
- [ ] Scope explicitly defines what is covered and NOT covered
- [ ] Test case maps to user story
- [ ] Acceptance criteria are linked

## 3. Pre-conditions

- [ ] System state requirements are clearly defined
- [ ] Required test data is specified
- [ ] User permissions/roles are documented
- [ ] Environment requirements are listed
- [ ] Pre-conditions are specific and unambiguous
- [ ] No implicit assumptions are left undocumented

## 4. Test Steps

- [ ] Each step is numbered sequentially
- [ ] Each step describes ONE specific action
- [ ] Steps use clear, imperative language
- [ ] Steps include specific UI elements
- [ ] Test data is specified for each step requiring input
- [ ] Expected result is defined for each step
- [ ] Expected results are specific and measurable
- [ ] Steps follow a logical sequence

## 5. Expected Final Result

- [ ] Overall expected outcome is clearly stated
- [ ] All acceptance criteria are addressed
- [ ] Success criteria are explicitly defined
- [ ] Results can be objectively verified
- [ ] Expected results align with user story

## 6. Post-conditions and Cleanup

- [ ] Expected system state after test is documented
- [ ] Cleanup steps are provided (if needed)
- [ ] Cleanup ensures system returns to testable state

## 7. Test Data Requirements

- [ ] All required input data fields are listed
- [ ] Data types are specified
- [ ] Valid and invalid value examples are provided
- [ ] Expected output fields are listed

## 8. Alternative Flows and Scenarios

- [ ] Significant alternative flows are included
- [ ] Conditions triggering alternative flows are clear
- [ ] Steps and expected results for alternatives are documented

## 9. Exception and Error Scenarios

- [ ] Expected error conditions are identified
- [ ] Error triggers are documented
- [ ] Expected error messages are specified
- [ ] Recovery steps are provided

## 10. Boundary and Edge Cases

- [ ] Boundary values are tested (min/max)
- [ ] Zero/null/empty scenarios are covered
- [ ] Special characters are considered
- [ ] Expected behavior is documented

## 11. Negative Test Scenarios

- [ ] Invalid data type scenarios are included
- [ ] Out-of-range values are tested
- [ ] Expected rejection/validation is documented
- [ ] Security considerations are tested

## 12. Acceptance Criteria Mapping

- [ ] Every acceptance criterion is addressed
- [ ] Each criterion maps to test steps/scenarios
- [ ] Coverage is explicitly documented

## 13. Non-Functional Considerations

- [ ] Performance expectations noted (if applicable)
- [ ] Usability considerations documented
- [ ] Security requirements verified
- [ ] Accessibility noted (if applicable)

## 14. Automation Considerations

- [ ] Automation feasibility evaluated
- [ ] Automation priority assigned
- [ ] Automation approach suggested

## 15. Documentation Quality

- [ ] Clear, professional language used
- [ ] Grammar and spelling correct
- [ ] Formatting follows template
- [ ] Easy to read and understand

## Overall Assessment

- [ ] **APPROVED** - Ready for use
- [ ] **APPROVED WITH MINOR CHANGES** - Acceptable with adjustments
- [ ] **REVISION REQUIRED** - Needs significant updates
- [ ] **REJECTED** - Does not meet minimum standards
