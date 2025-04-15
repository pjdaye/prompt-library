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




# **Title:** Detailed Feature Requirements & Acceptance Criteria

---

## **Prompt Structure:**

"Review the following feature requirements for the {{product_feature}} feature of the {{product_under_test}}, delimited by triple quotes. Analyze the Epic and User Stories to extract critical features, acceptance criteria, and potential edge cases. Identify key functional areas and risk points. Provide a concise summary outlining the main components to be validated, highlighting any areas that may require special risk-based testing.

"""
{{feature_requirements}}
"""

Summarize the critical elements, edge cases, and risk areas."

Example:
"Review the following requirements for the Loan Application feature of the Greenacre Loan Application:

"""

## Epic

* As a loan applicant, I want to submit data to obtain a loan decision.

## User Stories\n\n### Submit for Approval (Back-end)

* Criteria include valid FICO ranges, Loan Amount between USD 50,000 and 1,000,000, etc.

### Acceptance Criteria

* The system uses given parameters to determine Approval, Program, and Rate.

### Display Approval (Front-end)

* Approved loans display appropriate messages and formatting.
"""

Summarize the critical elements, edge cases, and risk areas."

---

## **Parameters:**

| **Parameter Name**       | **Description**                                    |
|--------------------------|----------------------------------------------------|
| {{product_feature}}      | The name of the feature (usually the Epic Title)   |
| {{product_under_test}}   | The name of the product under test                 |
| {{feature_requirements}} | Describe the feature under test (epic and stories) |

---

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Carefully review the provided requirements and ensure that the generated summary covers all critical components.

---

## **Additional Notes:**

* If the model accepts file attachments, attach a visual of the GUI.
