# Assignment 05: GitHub MCP Server Integration & Automated README Generator

## Objective

Learn how to integrate the GitHub MCP (Model Context Protocol) server with Claude Code and use it to create an automated README generator that analyzes a GitHub repository and generates professional documentation.

## Background

In our latest class, we explored MCP servers and learned how they extend Claude's capabilities. The GitHub MCP server allows Claude to read and interact with GitHub repositories, enabling automation of documentation, code analysis, and project management tasks. In this assignment, you'll connect the GitHub MCP server and create a practical tool that generates README files.

## Prerequisites

- Claude Code installed and configured
- A GitHub account
- A GitHub personal access token (we'll create one in the assignment)
- Basic understanding of README files
- A test repository (your own public repository)

---

## Part 1: Connecting GitHub MCP Server

### Step 1: Create a Fine-Grained Personal Access Token (10 points)

Fine-grained tokens are more secure than classic tokens - they limit access to specific repositories and permissions.

1. Go to GitHub and log in to your account
2. Click on your **Profile Picture** in the top right corner
3. Select **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens**
4. Click **Generate new token**
5. Fill in the token details:
   - **Token name:** `claude-code-github-mcp`
   - **Expiration:** Select 90 days (good security practice)
   - **Description:** "For Claude Code GitHub MCP integration - README generation"
6. Under **Repository access**, select:
   - **All repositories**
7. Under **Permissions**, checkmark all available permissions
8. Click **Generate token**
9. **⚠️ Copy the token immediately** - you won't be able to see it again! Save it somewhere safe for this assignment.

### Step 2: Configure Claude Code with GitHub MCP (15 points)

1. In your project folder, create a new file called `.mcp.json`
2. Add the following configuration (replace `{pat_token}` with your token from Step 1):
   ```json
   {
     "mcpServers": {
       "github": {
         "type": "http",
         "url": "https://api.githubcopilot.com/mcp",
         "headers": {
           "Authorization": "Bearer {pat_token}"
         }
       }
     }
   }
   ```
3. Replace `{pat_token}` with the actual personal access token you copied in Step 1
4. Save the file
5. **Close Claude Code completely**
6. **Reopen Claude Code** to load the new configuration
7. Verify the connection by running the command: `/mcp`
   - You should see the GitHub MCP server listed as connected

### Step 3: Test GitHub MCP Connection (10 points)

1. In Claude Code, run the command: `/mcp`
   - You should see GitHub MCP listed as connected
2. In Claude Code, ask Claude:
   ```
   Can you list the files in my GitHub repository [your-github-username/repo-name]?
   ```
3. If Claude successfully returns a list of files, your GitHub MCP is working!
4. **Document the result** - take a screenshot showing:
   - The `/mcp` command output showing GitHub MCP is connected
   - The repository files listed by Claude

---

## Part 2: Build the README Generator

### Step 4: Plan Your README Generator (15 points)

Create a document outlining your README generator plan:

1. **Repository Selection:** Which repository will you analyze?
   - (Your own OR a public repository you choose)
2. **README Structure:** What sections should the README include?
   - Project title and description
   - Features/highlights
   - Installation instructions
   - Usage examples
   - Project structure overview
   - Any other relevant sections
3. **Analysis Approach:** How will you ask Claude to analyze the repo?
   - Read key files (main code files, package.json, etc.)
   - Understand the project purpose
   - Identify main features
   - Note any configuration files

### Step 5: Generate README Using Claude (40 points)

1. Open Claude Code in your project workspace
2. Provide Claude with a detailed prompt like this:
   ```
   I want you to use the GitHub MCP server to help me create a professional README for my repository [owner/repo].

   Please:
   1. Read the repository structure using GitHub MCP
   2. Analyze the main code files to understand what the project does
   3. Look at any configuration files (package.json, requirements.txt, etc.)
   4. Generate a comprehensive README with these sections:
      - Project Title and Description
      - Key Features (2-3 bullet points)
      - Installation Instructions
      - How to Use (with examples if applicable)
      - Project Structure Overview
      - Any Other Relevant Information

   Format it as a professional markdown README.
   ```
3. **Document the process:**
   - Copy the generated README
   - Save it to a file called `GENERATED_README.md` in your project
   - Take screenshots showing:
     - Your prompt to Claude
     - Claude's response/generated README
     - Context usage during generation

### Step 6: Review and Improve (15 points)

1. **Read through the generated README** and identify:
   - What Claude got right
   - What needs improvement
   - Missing information
2. **Iterate with Claude:** Ask Claude to refine specific sections:
   ```
   The README looks good, but I'd like you to:
   - Add more details to the Installation section
   - Include usage examples
   - Add information about [specific feature]
   ```
3. **Document improvements:**
   - List 3-5 changes you made
   - Explain why each change improved the README
   - Save the final version as `FINAL_README.md`

---

## Part 3: Documentation & Analysis (BONUS - Extra 20 points)

**Complete this section for additional credit!**

### Bonus Step: Advanced GitHub MCP Exploration

Choose one of these bonus projects:

**Option A: Multiple Documentation Types**

- Generate not just a README, but also:
  - A CONTRIBUTING.md file
  - An ARCHITECTURE.md explaining code structure
  - A TROUBLESHOOTING.md for common issues
- Document how you prompted Claude for each

**Option B: Comparative Analysis**

- Generate READMEs for 2-3 different repositories
- Compare what Claude generated for each
- Document differences and why they occurred
- Create a report on GitHub MCP capabilities and limitations

**Option C: Custom Documentation Generator Skill**

- Create a custom Claude Code skill that automates README generation
- Document the skill structure
- Include example usage prompts
- Test it on at least 2 repositories

**Option D: Context Optimization Analysis**

- Document your context usage before, during, and after GitHub MCP integration
- Create a report showing:
  - Initial context footprint
  - Impact of adding GitHub MCP
  - Total context used for README generation
  - Optimization strategies you could use
- Explain findings in 1-2 pages

**Option E: Automated Repository Creation & Commits** ⭐ (Most Advanced)

- Use GitHub MCP to **create and commit files** to a repository
- Create a test repository (or use an existing one)
- Ask Claude to:
  - Generate documentation files (README, CONTRIBUTING, etc.)
  - Create these files in your repository
  - Commit the changes with meaningful commit messages
  - Push to GitHub automatically
- Document the automation process:
  - Prompts you used to trigger creation/commits
  - Screenshots of commits appearing on GitHub
  - Reflection on how this could automate real workflows
  - Advantages and limitations of automating commits via MCP
- This demonstrates how MCP servers can handle full development workflows!

---

## Submission Requirements

Submit a document/folder containing:

1. ✅ **GitHub MCP Setup Documentation**

   - Screenshot of Personal Access Token creation steps
   - Screenshot of Claude Code MCP configuration
   - Proof of successful connection (file listing test)
2. ✅ **README Generator Plan**

   - Repository selected and why
   - Planned README structure
   - Your analysis approach
3. ✅ **Generated README Files**

   - `GENERATED_README.md` (initial version)
   - `FINAL_README.md` (after improvements)
4. ✅ **Process Documentation**

   - Screenshots of prompts you gave Claude
   - Explanation of improvements made
   - Context usage during generation
5. ✅ **Bonus Materials** (if attempting bonus)

   - Additional documentation or analysis
   - Project files for custom skill (if applicable)

---

## Evaluation Criteria

| Criteria                                              | Points        |
| ----------------------------------------------------- | ------------- |
| GitHub Personal Access Token creation & documentation | 10            |
| Successful GitHub MCP configuration                   | 15            |
| Testing and proof of GitHub MCP connection            | 10            |
| README Generator plan (structure & approach)          | 15            |
| Generated README quality & completeness               | 30            |
| Improvements and iterations documented                | 15            |
| Overall documentation quality                         | 5             |
| **Subtotal (Base Assignment)**                  | **100** |
| **Bonus: Advanced GitHub MCP Exploration**      | **+20** |
| **TOTAL POSSIBLE**                              | **120** |

---

## Tips for Success

- **Start simple:** Focus on getting a good basic README first, then iterate
- **Read GitHub MCP errors carefully:** They'll guide you on what went wrong
- **Document as you go:** Take screenshots and notes at each step - don't do it all at the end
- **Use Claude iteratively:** You don't need to get it perfect in one prompt. Build it step by step
- **Test with different repositories:** Try your process on multiple repos to see how versatile GitHub MCP is
- **Monitor context usage:** Use `/context` command frequently to understand how GitHub MCP affects your context

---

## Common Issues & Solutions

**Issue: "GitHub token not found" error**

- **Solution:** Double-check your token is correctly set in the MCP configuration. Restart Claude Code after saving changes.

**Issue: "Repository not found" error**

- **Solution:** Verify the repository name format is `owner/repo` (e.g., `anthropics/claude-code`). Make sure your token has access to the repo.

**Issue: Generated README is too generic**

- **Solution:** Provide Claude with more specific instructions about your project. Ask it to read specific files and extract certain information.

**Issue: Context is getting too large**

- **Solution:** Be selective about which files you ask Claude to analyze. Focus on key files rather than the entire repository.

---

## Important Reminders

⚠️ **Security - CRITICAL:**

- **NEVER share your PAT token with anyone** - treat it like a password
- **NEVER commit your token to version control** - Add `.mcp.json` to `.gitignore` before committing
- Fine-grained tokens are more secure because they limit access to specific repositories and permissions

💡 **Permissions:** Fine-grained tokens are the best practice - they only have access to what they need (specific repositories and read-only operations). This is much safer than classic tokens with broad permissions.

🔄 **Iteration:** The first generated README might not be perfect. Use Claude's iteration capabilities to refine it.

📚 **Learning:** Pay attention to how GitHub MCP works - this understanding will help with future assignments using other MCP servers.

---

## Extension Ideas for Future Learning

- Create an issue analyzer that categorizes and summarizes GitHub issues
- Build a commit message improver that suggests better conventional commit formats
- Develop a project health analyzer that examines code quality, documentation, and best practices
- Create a release notes generator that pulls merged PRs and generates formatted release notes

---

**Deadline:** 14th February 2026

**Good luck!** You're learning cutting-edge AI integration techniques that companies are using to automate their documentation and development workflows.
