# Define Error Hypothesis

**Author:** Philip Daye (@pjdaye)
**Language:** N/A
**Use Case:** Risk Analysis
**Tags:** risk-analysis, error-hypothesis
**Parameters:**  

- `parameter1`: Description of this placeholder.  
- `parameter2`: Description of this placeholder.

## Prompt

[Write the prompt instructions here, using placeholders like `{{parameter1}}` where appropriate.]




## **Prompt Structure:**

"Error hypotheses are assumptions about potential failure points within a system that help guide test data selection and scenario creation. Common examples include:

* **Decisions:** Issues in logic (e.g., off-by-one errors, faulty decision-making).
* **Translations:** Errors in data conversion between system layers.
* **Assumptions:** Failures due to unverified or invalid assumptions.

Do not limit your analysis to these examples. Based on the feature requirements for the {{product_under_test}}, independently evaluate and identify additional error hypotheses—including performance, concurrency, integration, security, and domain-specific risks.

For each identified error hypothesis, provide a brief justification and rank the top {{number_to_output}} risks based on both likelihood and potential impact."

Example:
"For the Greenacre Loan Application, besides common error models, consider risks such as performance bottlenecks under high load, concurrency issues during simultaneous submissions, and security vulnerabilities in data handling. Provide a brief rationale for each and rank the top three risks based on likelihood and impact."

---

## **Parameters:**

| **Parameter Name**     | **Description**                    |
|------------------------|------------------------------------|
| {{product_under_test}} | The name of the product under test |
| {{number_to_output}}   | The request number of outputs      |

---

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Independently analyze and rank risks; ensure that the model expands beyond the provided examples.

---

## **Additional Notes:**

* Add any additional error models for consideration.
