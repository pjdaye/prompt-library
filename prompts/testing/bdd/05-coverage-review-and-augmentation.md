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



# **Title:** Coverage Review & Augmentation

---

## **Prompt Structure:**

"Review the initial draft of test assets generated for the {{product_feature}} feature of the {{product_under_test}}. Identify any gaps or missing scenarios in terms of functional flows, edge cases, and risk areas. Compare the generated test cases against the detailed feature requirements and the original context.

For each gap, suggest one or two additional BDD test cases in Given/When/Then format, and recommend modifications to the data generation or oracle instructions if necessary. Also, note any redundant or overlapping test steps that should be consolidated."

Example:
"Upon reviewing the initial tests for the Loan Application feature, you notice that boundary conditions for the Borrower FICO score are underrepresented. Suggest an additional test case such as:

Scenario: Invalid Borrower FICO below minimum
  Given a borrower with a FICO score of 299
  When the application is submitted
  Then the system should reject the application

Also, highlight that the data generation script should merge overlapping boundary sets (e.g., between different loan programs) and remove duplicates."

---

## **Parameters:**

| **Parameter Name**     | **Description**                                  |
|------------------------|--------------------------------------------------|
| {{product_feature}}    | The name of the feature (usually the Epic Title) |
| {{product_under_test}} | The name of the product under test               |

---

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Identify any gaps or redundancies, and suggest additional test cases or modifications as needed.

---

## **Additional Notes:**

* Describer test techniques and how to do them.
* Give the model the information it needs for the level of comprehensiveness required.
