# Initial Test Case Generation

**Author:** Philip Daye (@pjdaye)  
**Language:** Python, Javascript, Gherkin  
**Use Case:** Test Case Generation  
**Tags:** bdd, scenario, test-case, test-data, oracle  
**Parameters:**  

- `range_of_number`: Range of numbers, i.e. 3-5, for number of tests
- `product_feature`: The name of the feature (usually the Epic Title)
- `product_under_test`: The name of the product under test

## Prompt

Using the provided context, error hypotheses, and feature requirements, generate an initial draft of test assets for the `{{product_feature}}` feature of the `{{product_under_test}}`. Your output should include:

1. **BDD Gherkin Test Cases:** Create `{{range_of_number}}` scenarios with clear, descriptive names that follow the Given/When/Then format. Use Examples and Data Tables where appropriate. For instance, incorporate a table for input parameters, ensuring off-by-one values are included where needed.

2. **Test Data Generation Instructions:** Provide a script or code outline that generates test data using techniques such as equivalence partitioning, boundary value analysis (include off-by-one values), and pairwise testing. Use PICT as the default method (with sample input file instructions), and optionally note a built-in Python alternative.

3. **Oracle for Expected Results:** Include a code snippet or pseudocode that either pre-computes expected outcomes or dynamically validates test results based on the generated test data.

4. **Exploratory Testing Charters:** Provide 2–3 charters in bullet form, following this template:
    - **Target:** [what to explore]
    - **Techniques/Resources:** [methods/tools]
    - **Expected Outcome:** [what risks/information to uncover]

Focus on creating a concise yet comprehensive draft that covers core functional areas and identified risks.

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Check that the generated Gherkin tests are clear and include Scenario names, Examples, and Data Tables. Verify that the test data generation and Oracle scripts incorporate off-by-one values and handle overlapping boundaries appropriately.

## **Additional Notes:**

- Describe test techniques and how to do them.
- Give the model the information it needs for the level of comprehensiveness required.
