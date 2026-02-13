# Week 05 CLI Log

## Entry 1 — Mermaid Flowchart Generation

**Date:** 2026-02-11
**Tool:** Claude Code (CLI)

### Prompt

> Read SOP.md and generate Mermaid flowchart code (flowchart TD) that matches the procedure exactly.
> - Include explicit Start and End.
> - Every decision has labeled branches.
> - Do NOT invent steps. If missing, mark as [TBD] as a note.
> Write the output to diagrams/mermaid/process.mmd.

### What Was Done

1. Read `process-package/SOP.md` to extract the full procedure (10 steps, 3 decision points).
2. Generated a `flowchart TD` Mermaid diagram mapping every SOP step and decision to a node.
3. Wrote the output to `process-package/diagrams/mermaid/process.mmd`.

### Key Decisions

- Two End nodes were created: one for the normal completion path and one for the early "No action needed" exit (Step 1, "No" branch).
- Decision branches loop back exactly as described in the SOP (Decision 2 "No" → Step 4; Decision 3 "No" → Step 7).
- Secretary follow-up actions were noted as `[TBD]` since the SOP itself marks them as TBD.
- No steps were invented; every node maps directly to an SOP step or decision.

### Output

- `process-package/diagrams/mermaid/process.mmd`

---

## Entry 2 — Git Repository Setup and GitHub Publish

**Date:** 2026-02-13
**Tool:** Claude Code (CLI)

### Prompt

> Create a git repository for the process-package folder. Set up a .gitignore, make an initial commit, and create a remote repo under https://github.com/jasoneg.

### What Was Done

1. Initialized a new Git repository in `process-package/`.
2. Created a `.gitignore` with common OS and editor exclusions (Thumbs.db, .DS_Store, .vscode/, .idea/, etc.).
3. Staged all 10 project files and committed with the message "Initial commit: Module 05 CLI process package".
4. Installed the GitHub CLI (`gh`) via `winget` and authenticated via browser-based device flow.
5. Created a new public GitHub repository: `JasonEG/M05CLI-process-package`.
6. Pushed the initial commit to the `master` branch on the remote.

### Key Decisions

- Repository was created as **public** to align with typical coursework sharing requirements.
- Used `gh repo create` with `--source=.` and `--push` to create the remote and push in one step.
- The `.gitignore` covers Windows, macOS, and common editor artifacts without being overly broad.

### Output

- GitHub repository: https://github.com/JasonEG/M05CLI-process-package
- `.gitignore` added to project root
