# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **process package** for Module 05 (CLI). It is a documentation deliverable, not a software project — there is no source code, build system, or test suite.

## Repository Structure

All content lives under `process-package/`:

- **README.md** — Project overview
- **SOP.md** — Standard Operating Procedure for the CLI process
- **CHANGELOG.md** — Version history of process changes
- **glossary.md** — Domain-specific terminology
- **diagrams/** — Process visualizations
  - `bpmn/process.bpmn` + `process.png` — BPMN 2.0 process diagram
  - `mermaid/process.mmd` + `process.svg` — Mermaid flowchart
- **artifacts/** — Supporting materials (`examples/`, `screenshots/`)
- **prompt-log/** — AI prompt interaction logs (`week05-cli-log.md`)

## Git Repository

The git repository is located inside `process-package/`, **not** at the `M05CLI` root. All git operations (commit, push, status, etc.) must be run from the `process-package/` directory.

- **Remote:** `https://github.com/JasonEG/M05CLI-process-package.git`
- **Branch:** `master`

## Working in This Repo

- All documents are Markdown. Edits should preserve existing heading structure.
- Diagrams exist in both source format (`.mmd`, `.bpmn`) and rendered format (`.svg`, `.png`). When updating a diagram, edit the source file; the rendered file should be regenerated.
- The `artifacts/examples/` and `artifacts/screenshots/` directories are for supporting evidence referenced by the SOP or README.
- The prompt log tracks AI-assisted interactions during development of this process package.
- The `validation-log.md` records cross-artifact consistency checks. When validating, append a new entry there.

## Where We Left Off

**Date:** 2026-02-15

Completed validations:
1. **SOP ↔ Mermaid ↔ BPMN** — PASS. All steps, decisions, and loop-backs match. BPMN includes additional Admin/Secretary tasks from the SOP roles section (intentional).
2. **Glossary ↔ SOP** — PASS with one minor gap. "Traditional Grades" (Step 7 screen) is not in the glossary but was deemed not necessary to add.

Next steps to pick up:
- Any further validation checks the user wants to run
- The `artifacts/examples/` and `artifacts/screenshots/` directories are still empty — may need supporting evidence added
- CHANGELOG could be updated if more changes are made
