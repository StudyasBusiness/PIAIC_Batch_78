# Assignment 04: Custom Skill Validation

## Objective

Learn how to validate your custom Claude skills using the skill-validator skill to ensure proper structure, documentation, and adherence to best practices.

## Background

In class, we created our own custom skills using the skill-creator-skill. Now it's time to validate that our skills are properly structured and follow the recommended guidelines. This assignment will teach you how to use the skill-validator skill to check your work.

## Prerequisites

- Completed skill creation in class
- A custom skill in your `.claude/skills` folder
- The `skill-creator-skill` already present in your `.claude/skills` folder

## Instructions

### Step 1: Download the Skill-Validator Skill (10 points)

1. Navigate to the Claude Code Skills Lab repository:

   ```
   https://github.com/panaversity/claude-code-skills-lab
   ```
2. **Download the repository** using one of these methods:

   **Option A: Clone the repository (Recommended)**

   ```bash
   git clone https://github.com/panaversity/claude-code-skills-lab.git
   ```

   **Option B: Download as ZIP**

   - Click the green "Code" button on the GitHub page
   - Select "Download ZIP"
   - Extract the ZIP file to a location on your computer
3. After downloading, navigate to the `.claude/skills` folder in the downloaded repository
4. Locate the `skill-validator` folder inside `.claude/skills`
5. **Copy** the entire `skill-validator` folder (with all its contents)
6. **Paste** the `skill-validator` folder into your project's `.claude/skills` directory
7. After this step, your project's `.claude/skills` folder should contain:

   - `skill-creator-skill/` (from class)
   - `your-custom-skill/` (the skill you created in class)
   - `skill-validator/` (newly added)

### Step 2: Validate Your Custom Skill (40 points)

1. Open Claude code in your project
2. Ask Claude to validate your custom skill using a simple prompt such as:

   ```
   Please use the skill-validator skill to validate my [your-skill-name] skill.
   ```
3. Wait for Claude to run the validation and provide results
4. **If the validation passes, document the validation results. For this you can ask claude code to do it.**

#### Step 4: Domain Expertise Testing (20 points)

**Important Disclaimer:** The skill-validator skill validates the **structure, documentation, and technical aspects** of your skill. It does **NOT** validate the domain expertise or the actual functionality of your skill's logic.

You are responsible for testing whether your skill:

- Performs its intended function correctly
- Provides accurate domain-specific outputs
- Handles edge cases appropriately
- Meets your specific use case requirements

#### Domain Testing Documentation

**Test Cases:**

1. **Test Case 1:**

   - **Description:** [What you tested]
   - **Expected Result:** [What should happen]
   - **Actual Result:** [What actually happened]
   - **Status:** [Pass/Fail]
2. **Test Case 2:**

   - **Description:** [What you tested]
   - **Expected Result:** [What should happen]
   - **Actual Result:** [What actually happened]
   - **Status:** [Pass/Fail]
3. **Test Case 3:**

   - **Description:** [What you tested]
   - **Expected Result:** [What should happen]
   - **Actual Result:** [What actually happened]
   - **Status:** [Pass/Fail]

[Add more test cases as needed]

**Improvements Made Based on Domain Testing:**

- [Improvement 1]
- [Improvement 2]
- [Add more as needed]

---

## Submission Requirements

Submit a document (this file completed) that includes:

1. ✅ Screenshot showing your `.claude/skills` folder with all three skills
2. ✅ Complete validation results from Step 2
3. ✅ Documentation of implemented recommendations from Step 3
4. ✅ Domain testing results from Step 4

## Evaluation Criteria

| Criteria                                         | Points        |
| ------------------------------------------------ | ------------- |
| Successful download and setup of skill-validator | 10            |
| Complete validation results documented           | 20            |
| Proper documentation of validation output        | 20            |
| Implementation of recommendations (if any)       | 15            |
| Re-validation after improvements                 | 15            |
| Domain expertise testing with test cases         | 15            |
| Overall documentation quality                    | 5             |
| **Total**                                  | **100** |

## Tips for Success

- Read the validation output carefully - it provides valuable insights
- Don't ignore recommendations even if validation passes
- Test your skill thoroughly with real-world scenarios
- Keep iterating on your skill based on testing results
- The validation process is iterative - it's okay to run it multiple times
- Document everything for your learning and future reference

## Important Reminders

⚠️ **Disclaimer:** The skill-validator validates **structure and format only**. You must test the actual functionality and domain expertise yourself.

💡 **Iteration is Key:** Don't expect perfection on the first try. Use validation feedback to continuously improve your skill.

🔄 **Keep Improving:** Even after passing validation, continue to refine your skill based on real-world usage and feedback.

---

**Deadline:** 31st Jan 2026

Good luck! This validation process will help you create robust, well-structured skills that follow best practices.
