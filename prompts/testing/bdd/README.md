# Instructions for the Test Professional

## Overall Workflow

1. **Preparation:**  
   - Populate the context placeholders (e.g., product_feature, product_under_test, quality_engineering_profile, etc.) with the relevant details.
   - Ensure that the complete parameter checklist (including all critical constraints) is accurately provided in the Contextual Setup prompt.
  
2. **Prompt Execution:**  
   - Execute the prompts in the defined order:
        1. [Contextual Setup](01-contextual-setup.md)
        2. [Error Hypothesis](02-error-hypothesis.md)
        3. [Detailed Feature Requirements](03-detailed-feature-requirements.md)
        4. [Initial Test Case Generation](04-initial-test-case-generation.md)
        5. [Coverage Review & Augmentation](05-coverage-review-and-augmentation.md)
        6. [Final Consolidation.](06-final-consolidation.md)
   - At each stage, review the model's output, and provide any clarifications if necessary. (This is where the human-in-the-loop comes into play; if an output is unclear or incomplete, refine the prompt accordingly.)

3. **Interim Checkpoints:**  
   - Use the summary checkpoints (after the context block and before each major generation step) to verify that all critical parameters are maintained.
   - In the Coverage Review and Final Consolidation stages, cross-check the test cases for redundancies and consistency.

4. **Execution Feedback Integration:**  
   - After running the generated test suite in your execution environment, collect execution metrics (e.g., failure rates, coverage reports, performance data).
   - Feed this execution feedback back into the prompts (especially in the Final Consolidation stage) to refine test cases further.

5. **Human Review:**  
   - During the final consolidation step, include your manual review notes on test quality, redundancy, and any recommended adjustments. Use these notes for continuous improvement in future iterations.

## Instructions for Individual Prompts

- **Contextual Setup and Objectives:**  
  Confirm that all key details are captured and provide a brief summary before moving forward.

- **Error Hypothesis:**  
  Independently analyze and rank risks; ensure that the model expands beyond the provided examples.

- **Detailed Feature Requirements:**  
  Carefully review the provided requirements and ensure that the generated summary covers all critical components.

- **Initial Test Case Generation:**  
  Check that the generated Gherkin tests are clear and include Scenario names, Examples, and Data Tables. Verify that the test data generation and Oracle scripts incorporate off-by-one values and handle overlapping boundaries appropriately.

- **Coverage Review & Augmentation:**  
  Identify any gaps or redundancies, and suggest additional test cases or modifications as needed.

- **Final Consolidation and Human Review:**  
  Review the consolidated test suite for completeness and consistency. Include your feedback and any execution insights.

## Efficiency Considerations

- **Balance Accuracy and Token Cost:**  
  Aim for clear, concise instructions that don’t sacrifice necessary detail. Use few-shot examples where possible to minimize verbosity.
- **Iterative Refinement:**  
  If outputs seem verbose or redundant, adjust the prompt with additional summarization or filtering instructions.
- **Reuse of Standard Step Definitions:**  
  Incorporate references to an existing step library to reduce redundancy in Gherkin test cases.
