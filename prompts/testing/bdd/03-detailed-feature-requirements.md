# Detailed Feature Requirements & Acceptance Criteria

**Author:** Philip Daye (@pjdaye)  
**Language:** N/A  
**Use Case:** Set User Story Context  
**Tags:** user-story, acceptance-criteria  
**Parameters:**  

- `product_feature`: The name of the feature (usually the Epic Title)
- `product_under_test`: The name of the product under test
- `feature_requirements`: Describe the feature under test (epic and stories)

## Prompt

Review the following feature requirements for the `{{product_feature}}` feature of the `{{product_under_test}}`, delimited by triple quotes. Analyze the Epic and User Stories to extract critical features, acceptance criteria, and potential edge cases. Identify key functional areas and risk points. Provide a concise summary outlining the main components to be validated, highlighting any areas that may require special risk-based testing.

"""  
`{{feature_requirements}}`  
"""

Summarize the critical elements, edge cases, and risk areas.

## **Instructions for Use:**

1. **Identify Parameters:** Locate the placeholders in the prompt marked with {{brackets}}. These are the parameters that you need to customize.
2. **Customize Values:** Replace the placeholder parameters with the appropriate values for your use case. Refer to the "Parameters" section for more details.
3. **Run the Prompt:** Once customized, input the prompt into the Generative AI tool to get the desired outcome.
4. Carefully review the provided requirements and ensure that the generated summary covers all critical components.

## **Additional Notes:**

- If the model accepts file attachments, attach a visual of the GUI.
