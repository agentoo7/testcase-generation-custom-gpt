# Functional Test Case Generation Workflow

This document provides detailed guidance for generating functional test cases from user story summaries.
All questions should include numbered options (e.g., 1, 2, 3) so the user can select quickly.

## Workflow Overview

The test case generation process involves the following key steps:

1. **Context Gathering** - Read project documentation and reference materials
2. **Input Verification** - Locate and validate the user story summary file
3. **Output Storage Configuration** - Locate and validate the location for output test case files
4. **User Story Analysis** - Map user story relationships and dependencies
5. **Test Case Generation** - Create test cases per user story following the template
6. **Validation** - Review against the quality checklist
7. **User Review and Approval** - Get user review and approval per user story
8. **Store Test Case** - Save approved test cases to the configured storage
9. **Iteration** - Repeat for all user stories
10. **Final Reporting** - Generate a summary report
11. **Generate Zephyr** - Generate a Zephyr-compatible CSV file for importing test cases into Zephyr

## Detailed Steps

### Step 1: Context Gathering

**Objective:** Understand project context and requirements.

**Actions:**
- Verify that the project context and requirements are provided.
- If not available, ask the user to provide them.
- The `template--functional-test-case.md` and `checklist--functional-testcase.md` files are already available. Ask the user if they want to override them.
- Users can use commands such as `view the system template for functional test case` to view the `template--functional-test-case.md` file.
- Users can use commands such as `view the system checklist for functional test case` to view the `checklist--functional-testcase.md` file.

**What to Extract:**
- Project name and code
- General business context of the project (details will be included later)
- Domain-specific terminology
- Quality standards
- Testing priorities


### Step 2: Input Verification

**Objective:** Ensure the user story summary file is available and readable.

**Actions:**
- Check if the user has provided a user story summary document. The user can either type the content or upload a file.
- If no user story summary is found, ask the user to provide the correct information.
- Read and extract all user stories.
- Identify user story IDs, titles, and acceptance criteria.

**Output:** List of all user stories requiring test cases


### Step 3: Output Storage Configuration

**Objective:** Define where to store the generated test cases.

**Actions:**
- Ask the user to specify where to store the test cases created based on user stories.
- Storage options include:
  - Jira (using Jira MCP)
  - File system
  - Google Drive


### Step 4: User Story Analysis

**Objective:** Understand relationships between user stories.

**Actions:**
- List all user stories from the summary.
- Identify dependencies between stories.
- Note related user stories.
- Document any cross-story test scenarios.
- Understand workflow sequences.

**Considerations:**
- Some user stories may require coordinated testing.
- Dependencies affect test data and preconditions.
- Related stories may share test scenarios.

---

### Step 5: Test Case Generation (Per User Story)

**Objective:** Generate comprehensive test cases for each user story.

#### 5.1 Extract User Story Details

For each user story, extract:
- User Story ID
- User Story Title
- Description/Narrative
- Acceptance Criteria
- Business Rules
- Related User Stories

#### 5.2 Plan Test Coverage

Determine what needs testing:
- **Happy Path**: Main success scenario
- **Alternative Flows**: Valid variations
- **Edge Cases**: Boundary conditions
- **Error Scenarios**: Invalid inputs and error handling
- **Negative Tests**: Invalid operations

#### 5.3 Generate Test Cases

**File Naming:** `{{us-id}}.md` (one file per user story)
**Output Location:** `{{us-id}}.md`

**Follow Template Structure:**
- Follow the `template.md` file.

#### 5.4 Ensure Complete Coverage

**Acceptance Criteria Mapping:**
- Every acceptance criterion must be covered.
- Map each criterion to specific test steps.
- Use checkboxes to track coverage.

**Coverage Types:**
- Positive testing (valid inputs, expected behavior)
- Negative testing (invalid inputs, error handling)
- Boundary testing (min/max values, limits)
- Edge cases (empty, null, special characters)
- Alternative flows (different paths to success)

---

### Step 6: Validation

**Objective:** Ensure test case quality before user review.

**Actions:**
1. Review the generated test case against `references/checklist.md`.
2. Verify completeness of all sections.
3. Check acceptance criteria coverage.
4. Validate test step clarity.
5. Ensure traceability to the user story.
6. Verify test data sufficiency.

**Quality Checks:**
- All template sections are completed.
- Clear, unambiguous language is used.
- Specific, measurable expected results are defined.
- Logical step sequence is followed.
- No implicit assumptions are made.
- Proper formatting is applied.

---

### Step 7: User Review and Approval

**Objective:** Get user approval before proceeding to the next user story.

**Presentation:**
Present the generated test case with:
- User story ID and title
- Number of test scenarios created
- Coverage summary (happy path, edge cases, errors)
- Any assumptions made
- Dependencies or prerequisites noted

**Approval Process:**
- WAIT for explicit user approval.
- The user can request changes.
- The user can approve individually or all at once.
- If changes are requested, update and re-present.

**Do NOT proceed** to the next user story without approval.

---

### Step 8: Store Test Case

**Objective:** Save the approved test case to the configured storage.

**Actions:**
- After user approval, save the file with the name `{{us-id}}.md`.
- Store in the location specified during Step 3.


### Step 9: Iteration

**Objective:** Generate test cases for all user stories.

**Process:**
1. After approval of the current user story, move to the next.
2. Repeat Steps 5-8 for each remaining user story.
3. Track progress.
4. Maintain consistency across test cases.

---

### Step 10: Final Reporting

**Objective:** Provide a comprehensive summary of test case generation.

**Report Contents:**
- Project information
- User stories processed
- Total test cases created
- Coverage statistics
- Test case distribution by priority/type
- Assumptions and notes
- Recommendations

**Report Formats:**
- Markdown: `testcase-generation-report.md`
- HTML: `testcase-generation-report.html`. This is optional. Ask you user before create it.
  - [ ] Use Mermaid for flowcharts
  - [ ] Use tree view for hierarchical structures
  - [ ] Collapsible header menu

---

### Step 11: Generate Zephyr

**Objective:** Export test cases for Zephyr integration.

**Actions:**
- Read the `zephyr-template.md` template
- Read the `zephyz-example.csv` example file.
- Create the `zephyr.csv` file. Make sure to follow the template and data exactly, focusing on test steps - separated into multiple rows
- Loop:
  - Read generated test case in `{{us-id}}.md` file
  - Convert test cases into zephyr data and append to `zephyr.csv` file Ensure all required fields are mapped correctly.
- Validate the CSV format before delivery.

---

## Best Practices

### Test Case Writing

1. **Be Specific**: Use exact field names, button labels, and UI elements.
2. **Be Clear**: Anyone should be able to execute the test.
3. **Be Complete**: Include all necessary information.
4. **Be Realistic**: Use plausible test data.
5. **Be Traceable**: Link clearly to the user story and acceptance criteria.

### Coverage Considerations

1. **Positive Scenarios**: Verify that expected functionality works.
2. **Negative Scenarios**: Verify that the system handles errors gracefully.
3. **Boundary Testing**: Test limits and edge conditions.
4. **Integration**: Consider interactions with other features.
5. **Security**: Validate permissions and data protection.

### Common Pitfalls to Avoid

1. **Ambiguous Steps**: Avoid vague terms like "appropriate" or "several."
2. **Missing Test Data**: Every input should have example values.
3. **Unmeasurable Results**: Expected results must be verifiable.
4. **Skipping Cleanup**: Always document post-conditions.
5. **Ignoring Edge Cases**: Don't forget boundary and error scenarios.
6. **Poor Traceability**: Always link to acceptance criteria.

---

## Decision Points

### When to Create Multiple Test Cases

Create separate test cases for:
- Different acceptance criteria with distinct workflows
- Complex scenarios with many variations
- Different user roles or permissions
- Different data types or conditions

### When to Combine into One Test Case

Combine when:
- Testing closely related functionality
- Steps naturally flow together
- Acceptance criteria are interdependent
- Splitting would create redundancy

---

## Output Structure

```
output/
└── functional-testcases/
    ├── US-001.md
    ├── US-002.md
    ├── US-003.md
    └── ...
```

Each file contains complete test case(s) for one user story.

---

## Quality Standards

Every test case must:
1. Follow the template structure exactly.
2. Pass all checklist items.
3. Cover all acceptance criteria.
4. Include positive, negative, and edge case scenarios.
5. Provide specific, executable steps.
6. Specify measurable expected results.
7. Include necessary test data.
8. Document assumptions clearly.
9. Maintain traceability to the user story.
10. Be reviewed and approved by the user.

---

## Automation Considerations

When evaluating automation:
- **Automation Feasibility**: Can it be automated?
- **Automation Priority**: Should it be automated?
- **Automation Approach**: How would you automate it?
- **Automation Challenges**: What makes it difficult?

**High-priority candidates for automation:**
- Regression tests
- Repetitive tests
- Data-driven tests
- Tests with deterministic results
- Tests run frequently