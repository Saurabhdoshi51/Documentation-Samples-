# AI-Assisted Resource ID Automation for DITA in Oxygen XML

## Project Overview

While working with DITA-based product documentation in Oxygen XML Author, I needed to add a resourceid element with a ux-context-string attribute to a large number of topics. Adding these IDs manually was repetitive and time-consuming, especially when working with help files containing hundreds or thousands of topics.

I worked on an automation workflow to reduce this manual effort. The workflow uses an XML-based script to generate and insert resource IDs, followed by a Python script to clean up and standardize the generated values.

I used ChatGPT to help develop and refine the scripts, along with VS Code and Oxygen XML Author to work on the automation and documentation files.

## ⚠️ Problem Statement
Oxygen XML Author provides XML refactoring capabilities that can help add elements and attributes across multiple topics. However, generating a different ux-context-string value for each topic still required additional manual work to add the topic name as IDs.

Manually adding these IDs across a large documentation set could take considerable time and introduce inconsistencies, such as unwanted spaces, special characters, or formatting differences.

The objective was to automate the repetitive parts of this process while keeping the existing DITA content intact.

## 💡Solution

I developed a two-stage workflow to generate and clean up resource IDs.

### Stage 1: Generate and Insert Resource IDs

I created an XML-based script to automate the insertion of the resourceid element and generate the ux-context-string attribute for DITA topics.

The script was intended to reduce the need to add the same element manually to individual topics. It also provided a way to apply a consistent naming pattern, including a prefix or suffix where required.

Tool used: Oxygen XML Author and VS Code

Configuration: [Add the exact Oxygen XML configuration or execution steps here.]

### Stage 2: Clean and Standardize the Generated IDs

After generating the IDs, I used a separate Python script to clean up the ux-context-string values.

This step addressed unwanted spaces and special characters so that the generated values followed a consistent naming pattern. Keeping this as a separate step made it easier to manage ID generation and value cleanup independently.

Tool used: Python and VS Code

Cleanup rules: [Add the exact rules implemented by the Python script, including which characters are removed or replaced.]

## End-to-End Workflow
1. Identify the DITA topics that require resource IDs.

2. Run the XML-based automation to insert the resourceid element and generate the attribute values.

3. Run the Python script to clean and standardize the generated values.

4. Review the resulting topics to check that the IDs follow the expected format and that the DITA content remains intact.

The final review step should reflect the checks actually performed during the project.

## Implementation Details

The workflow was designed around the following requirements:

* **Reduce manual effort:** Avoid adding resource IDs to every topic individually.

* **Maintain consistency:** Apply a common naming pattern across the documentation set.

* **Support naming conventions:** Allow a prefix or suffix where required.

* **Clean generated values:** Use Python to standardize the attribute values after generation.

* **Preserve existing content:** Keep the changes focused on the intended resource ID information and avoid unnecessary changes to other topic content.

[Confirm each requirement against the current versions of both scripts before publishing this section.]

## Before and After Examples

The demo/before_after_examples.md file contains examples showing the changes made during the automation process.

The examples should cover:

1. A DITA topic before the resource ID is inserted.

2. The same topic after the XML-based automation runs.

3. The topic after the Python cleanup script processes the generated value.

See *[Before and After Examples](demo/before_after_examples.md)*.

## Tools Used

* Oxygen XML Author
* XML/XSLT-based automation
* Python (v3.14)
* VS Code
* ChatGPT for assistance with script development and refinement
* Git

## Outcome

The workflow reduced the need for repetitive manual editing when adding resource IDs to large DITA help files. It also provided a separate cleanup step to standardize the generated values.

The approach can be useful when working with large documentation sets where the same structural change needs to be applied consistently across multiple topics.

For the wider documentation workflow, consistent topic IDs also support the work required to integrate F1 contextual help into the product.

[Add measured time savings or the number of topics processed here if you have reliable figures.]

## Further Improvements

Potential improvements include documenting the scripts' execution steps, adding more before-and-after examples, and expanding the checks used to identify invalid or duplicate IDs.

These improvements would make the workflow easier to reproduce and maintain across different DITA documentation projects.

Please refer to the image below, where all the elements and attributes are visible (resourceid is already added)   

<img width="1447" height="375" alt="image" src="https://github.com/user-attachments/assets/19c9ac8b-6867-410e-b221-d065200d694d" />

