# Final Consolidation and Self-Review

**Author:** Philip Daye (@pjdaye)  
**Language:** Python, Javascript, Gherkin  
**Use Case:** Final Test Case Generation  
**Tags:** test-case, test-data, oracle  
**Parameters:**  

- `product_feature`: The name of the feature (usually the Epic Title)
- `product_under_test`: The name of the product under test

## Prompt

Consolidate the refined test assets for the `{{product_feature}}` feature of the `{{product_under_test}}` into a final, organized test suite. In this final step, perform a comprehensive self-review to ensure:

1. All key scenarios, edge cases, and risk areas have been addressed.
2. Test design techniques (e.g., equivalence partitioning, boundary value analysis, pairwise testing, decision tables) are consistently applied.
3. The Gherkin test cases are clear, concise, and include well-structured Scenario names, Examples, and Data Tables.

Additionally, review the generated tests for redundant or overlapping steps—reusing existing steps where applicable.

Incorporate any execution feedback (e.g., failure rates, performance metrics) and human reviewer comments. Include a dedicated section for human feedback, noting any areas where manual intervention is recommended. Output the final consolidated test suite along with reviewer suggestions for further refinement.

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Review the consolidated test suite for completeness and consistency. Include your feedback and any execution insights.

## **Additional Notes:**

- Describer test techniques and how to do them.
- Give the model the information it needs for the level of comprehensiveness required.
