# [Prompt Title]

**Author:** [Your Name or GitHub Handle]  
**Language:** [Programming Language or "N/A"]  
**Use Case:** [Primary purpose, e.g. "Code generation", "Refactoring"]  
**Tags:** [comma-separated keywords, e.g. tag1, tag2, ...]  
**Parameters:**  

- `parameter1`: Description of this placeholder.  
- `parameter2`: Description of this placeholder.

## Prompt

[Write the prompt instructions here, using placeholders like `{{parameter1}}` where appropriate.]



# **Title:** Initial Test Case Generation

---

## **Prompt Structure:**

"Using the provided context, error hypotheses, and feature requirements, generate an initial draft of test assets for the {{product_feature}} feature of the {{product_under_test}}. Your output should include:

1. **BDD Gherkin Test Cases:** Create {{range_of_number}} scenarios with clear, descriptive names that follow the Given/When/Then format. Use Examples and Data Tables where appropriate. For instance, incorporate a table for input parameters, ensuring off-by-one values are included where needed.

2. **Test Data Generation Instructions:** Provide a script or code outline that generates test data using techniques such as equivalence partitioning, boundary value analysis (include off-by-one values), and pairwise testing. Use PICT as the default method (with sample input file instructions), and optionally note a built-in Python alternative.

3. **Oracle for Expected Results:** Include a code snippet or pseudocode that either pre-computes expected outcomes or dynamically validates test results based on the generated test data.

4. **Exploratory Testing Charters:** Provide 2–3 charters in bullet form, following this template:
    * **Target:** [what to explore]
    * **Techniques/Resources:** [methods/tools]
    * **Expected Outcome:** [what risks/information to uncover]

Focus on creating a concise yet comprehensive draft that covers core functional areas and identified risks."

Example:
"Scenario: Valid Loan Application with Boundary FICO Values
  Given a borrower with the following attributes:
      | Attribute          | Value        |
      | Borrower FICO      | 299          |
      | Co-Borrower FICO   | 0            |
      | Loan Amount        | 500000       |
      | Loan Type          | Fixed        |
    When the loan application is submitted
    Then the system should reject the application due to invalid FICO score

    Examples:
      | Borrower FICO | Co-Borrower FICO | Loan Amount | Expected Outcome     |
      | 299           | 0                | 500000      | Application Rejected |
      | 300           | 0                | 500000      | Application Approved |
      | 851           | 0                | 500000      | Application Rejected |

Test Data Generation Instructions: Provide a PICT input file that outlines combinations for FICO, Loan Amount, etc., and include a note on merging overlapping boundary values. Optionally, offer a Python snippet as an alternative.
  
Oracle:
 Provide pseudocode that takes input values (e.g., FICO score, Loan Amount) and returns expected values (Approval, Program, Rate), handling edge cases appropriately.
  
Exploratory Testing Charters:

* Explore the loan application submission process under high concurrency to uncover performance bottlenecks.
* Investigate UI behavior when multiple input errors occur simultaneously."

---

## **Parameters:**

| **Parameter Name**     | **Description**                                  |
|------------------------|--------------------------------------------------|
| {{range_of_number}}    | Range of numbers, i.e. 3-5, for number of tests  |
| {{product_feature}}    | The name of the feature (usually the Epic Title) |
| {{product_under_test}} | The name of the product under test               |

---

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Check that the generated Gherkin tests are clear and include Scenario names, Examples, and Data Tables. Verify that the test data generation and Oracle scripts incorporate off-by-one values and handle overlapping boundaries appropriately.

---

## **Additional Notes:**

* Describer test techniques and how to do them.
* Give the model the information it needs for the level of comprehensiveness required.
