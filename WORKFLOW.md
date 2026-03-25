# Project Workflow

All contributors and AI agents must adhere to the following workflow when executing tasks in this project. This process is adapted from the robust standards established in our reference projects.

1. **Review Documentation:**
   Begin every task by reading and reviewing all documents located in the repository (such as `README.md`, `VISION.md`, and any files in a `docs/` folder) to understand the current architecture, guidelines, and context.

2. **Design First:**
   - Verify that the current task matches up with an existing design document.
   - If no existing design covers the current task, you must write a new design document and commit it to the repository **before** beginning any implementation work. Local brainstorming files are not sufficient.

3. **Branching & Iterative Development:**
   - Always create a new branch for each task or feature (e.g., `feature/mvp-setup`, `fix/board-orientation`).
   - Commit often and push to your branch frequently to record history.

4. **Implementation & Testing Strategy:**
   - Implementation should proceed only after design approval.
   - All features must be covered by automated tests. We rely heavily on **E2E testing via Playwright**. Ensure your changes pass all relevant tests before completion.

5. **Pull Requests:**
   - Create a Pull Request (PR) for your changes using `gh pr create`.
   - Use a markdown file for the PR body if helpful (e.g., `gh pr create --body-file PR_DESCRIPTION.md`).
   - **Crucial**: The PR body MUST include the **original User Prompt(s)** and any **relevant User Comments** that initiated or directed the work.
   - **VERBATIM**: Copy the text exactly as written. Do not summarize, edit, or truncate. Include the full text of the prompt. This ensures context is preserved in the history without ambiguity.

6. **Completion:**
   - Ensure all changes are checked in, pass all relevant tests, and are pushed to GitHub.
   - Create a pull request for your branch before declaring "Job's done!"
