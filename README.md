# Prompt Template and Library Organization Guide

## Introduction  

This guide provides a reusable template and organizational standards for writing prompt files that can be shared. By following this template, developers can create prompts for various purposes (from code generation to chatbot interactions) in a consistent format. A well-structured prompt library makes it easier to find the right prompt for the task, promotes collaboration, and helps others learn prompt engineering by example ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=Building%20out%20your%20prompt%20library,when%20searching%20for%20valuable%20prompts)). The guidelines below outline the prompt file format, metadata to include, and how to organize the prompt library for maximum discoverability and reuse.

## Prompt File Template Format

Each prompt should be written in its own Markdown file. The file contains a header with metadata and the prompt content. Below is a template that prompt authors can copy and modify for each new prompt:

```markdown
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
```

Following is an explanation of each section in the template:

- **Prompt Title:** A short, descriptive title for the prompt. This should convey the task or outcome (e.g., “Generate Python Unit Tests” or “Summarize Text Document”). The title is used as a heading at the top of the file for quick identification. It often also serves as the file name (in lowercase with hyphens, as described below).  
- **Author:** The creator’s name or handle. This helps track who wrote or contributed the prompt (and can aid in version tracking or credit) ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=)). If multiple people update the prompt over time, you might list multiple authors or maintain a change log, but at minimum include the original author.  
- **Programming Language:** The target language or context for the prompt, if applicable. For prompts that involve code, specify the language (e.g., *Python*, *JavaScript*). If the prompt is not specific to a programming language, use a placeholder like “N/A”, “General”, or omit this field. This field makes it easy to filter prompts by language when browsing the repository.  
- **Use Case:** A one-line description of the prompt’s primary use case or scenario. Examples: *Code generation*, *Test writing*, *Refactoring*, *Data analysis*, *Content summarization*, etc. This provides context at a glance for what the prompt is meant to do. Keeping use cases consistent (choosing from a predefined set where possible) can help in organizing and searching the library.  
- **Tags:** A set of keywords to aid discoverability. Tags can include the domain, topic, or any other relevant descriptors (e.g., `unit-tests`, `bugfix`, `SQL`, `frontend`, `analysis`). Include both general and specific tags as needed ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=Building%20out%20your%20prompt%20library,when%20searching%20for%20valuable%20prompts)). These tags will help others search the repository for relevant prompts. For consistency, prefer lowercase and hyphen-separated multi-word tags.
- **Parameters:** An optional list of placeholders that can be substituted into the prompt. If the prompt is a template that expects certain inputs, list each parameter name and a brief description of what it represents. In the prompt content, parameters should be referenced with a clear syntax. We recommend using a notation like `{{parameter_name}}` (double curly braces) or `<parameter_name>` to denote variables that should be replaced with actual values. Using parameters makes prompts reusable across different inputs or projects ([GitHub - thibaultyou/prompt-library: AI Prompt Library: Curated prompts with metadata automation, documentation, and dynamic CLI. Execute AI prompts in CI pipelines or local workflows. Customizable toolkit for building AI-powered processes and personal assistants.](https://github.com/thibaultyou/prompt-library#:~:text=,your%20prompt%20library%20via%20Git)) – for example, a prompt template for generating a function can accept the function name and description as parameters instead of being hard-coded.  
- **Prompt Content:** This section (under a second-level heading like “## Prompt”) contains the actual text of the prompt that will be given to the AI. Write this as you would input it into the AI system, using any parameters defined above. It can be a single instruction, a series of instructions, or even a conversation snippet, depending on the use case. For instance, a prompt might say: *“Write a **{{function_name}}** in **{{language}}** that calculates the Fibonacci sequence.”* When using parameters, ensure they are clearly defined in the **Parameters** list and enclosed in the chosen placeholder format in the prompt text. If the prompt is complex, you can include additional context or examples in this section as needed (you might use Markdown formatting or comments within triple-backticks for code to clarify sections of the prompt). Keep the prompt content clear and focused on the task or question to get the best AI response.

> **Tip:** You may also include a brief **Description or Context** section (either as part of the prompt content or as a short paragraph before the prompt) if the prompt’s intent isn't obvious from the title and metadata. For example, explain what the prompt is designed to achieve or any assumptions it makes. This helps others understand and learn from your prompt. However, avoid making the prompt file too verbose – the key is that someone can quickly grasp the purpose and use of the prompt from the metadata and title alone.

## Repository Structure and Organization  

Organizing the prompt files in a logical folder structure is crucial for easy navigation ([How to Build an AI Prompt Library for Business](https://teamai.com/blog/prompt-libraries/building-a-prompt-library-for-my-team/#:~:text=Custom%20Prompt%20Library%20within%20our,AI%20chatbot%20system)). A well-planned structure, combined with consistent naming, will let developers quickly find prompts relevant to their needs without scanning every file. Here are the recommended practices for structuring the prompt library repository:

- **Central Prompts Directory:** Keep all prompt files within a common top-level directory (`prompts/`). This separates prompt content from other repository resources (like documentation or scripts).

- **Category Subfolders:** Within the prompts directory, group prompts into subfolders by use case. This organizes prompts by their primary purpose. For instance, you might have folders such as `code-generation/`, `refactoring/`, `testing/`, `documentation/`, `data-analysis/`, `content-writing/`, etc. This approach is useful for first thinking about *what* to do (the task).

- **Example Folder Layout:**  
  Here is an example of a prompt library structure organized by use case, with descriptive file names including language when relevant:

  ```text
  prompts/  
  ├── code-generation/  
  │   ├── python-generate-function.md  
  │   └── javascript-create-api-endpoint.md  
  ├── refactoring/  
  │   ├── python-refactor-legacy-code.md  
  │   └── general-improve-text-style.md  
  └── testing/  
      ├── java-create-unit-tests.md  
      └── python-generate-test-cases.md  
  ```  

- **File Naming Conventions:** Use clear and consistent naming for prompt files ([How to Build an AI Prompt Library for Business](https://teamai.com/blog/prompt-libraries/building-a-prompt-library-for-my-team/#:~:text=Once%20you%E2%80%99ve%20organized%20prompts%20into,identify%20what%20each%20one%20does)). Good practices include:
  - Use lowercase letters, numbers, and hyphens (`-`) or underscores (`_`) for word separation. Avoid spaces or special characters in file names.
  - Include key information in the file name, such as the topic or task, and optionally the target language if applicable. For example: `python-generate-unit-tests.md`, `summarize-text-document.md`, `sql-query-optimization.md`. This makes it possible to get an idea of the prompt's purpose from the file name alone.
  - Keep names reasonably short but descriptive. You don't need to encode every detail in the file name (the metadata inside the file will have more info), but the name should differentiate the prompt from others and hint at its function. Including the use-case or category in the name can help if it's not already obvious. For instance, `python-unit-test-generation.md` clearly indicates a testing-related prompt for Python.

- **README Files for Navigation:** Leverage README files to improve browsing and discovery:
  - **Main README:** The repository’s main `README.md` should introduce the library and list the high-level categories (and possibly highlight a few popular or exemplary prompts). It can include a table of contents or a simple bullet list of categories (linked to the respective folders). For example: “**Categories:** Code Generation | Refactoring | Testing | Content Writing | ...” with each linked to the folder path.
  - **Category README (Optional):** For each category folder, you can include a `README.md` that lists the prompts in that category along with a one-line description of each. This can be done manually or generated by script (for instance, by extracting each prompt’s title and use case from the metadata). This way, when someone clicks into a folder on GitHub, they immediately see an index of its prompts.  
  - **Index by Tag (Optional):** If your library grows large, you might consider maintaining an index of prompts by tag or language. This could be a Markdown file that groups prompts by common tags (e.g., all prompts tagged `machine-learning`, all prompts tagged `javascript`, etc.) with links to them. While not strictly necessary, it complements search functionality and helps users discover prompts across category boundaries.

- **Search and Discovery:** Thanks to the metadata in each prompt file, users can search the repository (using GitHub search or their editor) to find prompts by keyword, tag, or author. For example, searching the repository for "refactoring" or a tag like "database" will show all prompts that mention those terms. The consistent use of tags and structured metadata ensures the search results are meaningful. Including relevant tags and descriptive text in prompts will maximize the chances of finding the right prompt quickly ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=Building%20out%20your%20prompt%20library,when%20searching%20for%20valuable%20prompts)).

## Contributing New Prompts  

Contributions to the prompt library are welcome. To ensure consistency and quality, please follow these guidelines when adding or updating prompts:

1. **Follow the Template:** Start by copying the prompt template (shown above) into a new Markdown file. Fill in all the metadata fields:
   - Provide an informative title (and make sure the file name matches it closely, following naming conventions).
   - Fill in the **Author** with your name or handle (and co-authors if any).
   - Specify the **Language** if the prompt is language-specific; otherwise use "N/A" or "General".
   - State the **Use Case/Purpose** of the prompt clearly.
   - Add a few **Tags** that cover the technologies, topics, or styles involved. Check existing prompts for tag ideas and reuse tags when appropriate (to maintain consistency in tag vocabulary).
   - List any **Parameters** with descriptions. If your prompt is not meant to be parameterized, you can omit the Parameters section or state “None”.
2. **Write a Clear Prompt:** In the content section, write the prompt instructions clearly and concisely. Use the same tone and style as other prompts in the library (for example, if most prompts speak in imperative like “Write a function that…”, maintain that style). If your prompt uses parameters, double-check that you’ve used the exact placeholder names defined in the metadata. Consider adding a brief example or comment if the prompt’s usage might be confusing to new users.
3. **Test Your Prompt (if possible):** If you have access to an AI system (like an LLM) with which this prompt will be used (e.g., OpenAI GPT-4, GitHub Copilot, etc.), try it out to ensure it produces the intended results. This isn’t a strict requirement, but it helps verify that the prompt is effective. If the prompt requires certain conditions or setup, note that in the prompt content or a short comment.
4. **Place in Correct Folder:** Save the new prompt file under the appropriate category folder. If you feel none of the existing categories fit, you may create a new folder, but first consider whether your prompt could belong to an existing category with a slight adjustment. Keeping categories broad (but not too broad) will prevent over-fragmentation. Use your best judgment or open a discussion if unsure.
5. **Update Index (if applicable):** If the repository uses a main README table or category README to list prompts, add your new prompt to the relevant list. Typically, you would add a bullet with a link to your file and a short description. Ensure the list remains sorted (if there’s an ordering like alphabetical or grouped by sub-topic).
6. **Adhere to Style Guidelines:** Maintain the same formatting and style found in this guide and existing prompt files. For example, keep line lengths reasonable, use Markdown syntax correctly, and include any necessary blank lines for readability. Consistency in formatting helps others read and edit prompts easily.
7. **Avoid Sensitive or Proprietary Information:** Do not include any confidential code or data in your prompt examples. Prompts should be general and reusable. (If your prompt is inspired by a real scenario, sanitize any specifics.) Additionally, ensure the prompt does not violate any content guidelines (e.g., prompts should not encourage harmful or biased outputs – if your organization has rules for prompts, be sure to follow them ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=Your%20prompt%20library%20is%20another,This%20might%20include%20things%20like))).
8. **Submit via Pull Request:** If you are contributing to a shared repository on a platform like GitHub, create a pull request with your new prompt file (and any README updates). In the PR description, you can briefly state the purpose of the prompt and any notes. This allows maintainers to review the addition. Once approved, your prompt becomes part of the library for everyone to use.

By following these steps, the prompt library will stay well-organized and high quality. Contributors are encouraged to also read through a few existing prompt files to get a sense of the style and level of detail expected. The inclusion of metadata and structured content in each prompt is not only for consistency, but also to help future readers understand the prompt’s context and parameters quickly.

## Extensibility and Maintenance  

This template is meant to be extensible. Teams or communities using this repository can adapt it to their needs. For instance, you might decide to add additional metadata fields such as **Date Created**, **Last Updated**, or **Version** to track prompt evolution over time (versioning can be helpful in team environments to track changes ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=))). The structure is designed to be framework-independent, so you can use these prompts with various AI systems (from GitHub Copilot’s customization interface to standalone chatbot applications).

Remember to periodically review the prompt library:

- **Cleanup and Updates:** Remove or revise prompts that are outdated or no longer useful. For example, if a prompt was tailored to a specific model’s quirk and the model has improved, update the prompt accordingly. Keeping prompts up-to-date ensures the library remains a reliable resource.
- **Feedback Loop:** Encourage users of the prompts to provide feedback or improvements. Perhaps a prompt could be refined for clarity or effectiveness – contributors can iterate on prompt versions, which is facilitated by having the prompts under version control (Git).
- **Discoverability:** As the library grows, continue to refine the organization. If certain categories become too large, consider splitting or sub-categorizing them. If new themes emerge (e.g., many prompts about a certain domain like *security* or *UX writing*), incorporate those as tags or new categories as appropriate. The goal is to keep the library intuitive to navigate.

By maintaining a robust structure and template, this prompt library will serve not only as a collection of useful prompts for immediate use, but also as a learning tool. Developers can browse through well-documented examples to learn how to craft effective prompts for various scenarios. Consistent metadata, clear organization, and collaboration practices will ensure the library remains **extensible, discoverable, and valuable** for all users ([How to Build an AI Prompt Library for Business](https://teamai.com/blog/prompt-libraries/building-a-prompt-library-for-my-team/#:~:text=Custom%20Prompt%20Library%20within%20our,AI%20chatbot%20system)) ([RandallPine](https://www.randallpine.com/post/how-to-organize-and-scale-your-generative-ai-prompt-library#:~:text=Building%20out%20your%20prompt%20library,when%20searching%20for%20valuable%20prompts)).

*This read me file was generated by ChatGPT and edited by Philip Daye.*
