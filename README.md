# Process Package

Module 05 — Grade Finalization CLI Process Package

This repository contains the process documentation for finalizing quarter/semester grades in PowerSchool, including an SOP, process diagrams, and supporting artifacts.

## Repository Structure

```
process-package/
├── README.md              # This file
├── SOP.md                 # Standard Operating Procedure (JSON format)
├── CHANGELOG.md           # Version history
├── glossary.md            # Domain terminology
├── diagrams/
│   ├── bpmn/
│   │   ├── process.bpmn   # BPMN 2.0 XML source
│   │   └── process.png    # Rendered BPMN diagram
│   └── mermaid/
│       ├── process.mmd    # Mermaid flowchart source
│       └── process.svg    # Rendered Mermaid diagram
├── artifacts/
│   ├── examples/          # Supporting examples
│   └── screenshots/       # Supporting screenshots
└── prompt-log/
    └── week05-cli-log.md  # AI prompt interaction log
```

## Regenerating Diagrams

The rendered diagram files (`process.png` and `process.svg`) are generated from their respective source files. After editing a source file, regenerate the rendered output using the commands below.

### Prerequisites

Install both tools globally via npm:

```bash
npm install -g @mermaid-js/mermaid-cli bpmn-to-image
```

Verify the installations:

```bash
mmdc --version
bpmn-to-image --help
```

### Mermaid Flowchart

**Source:** `diagrams/mermaid/process.mmd`
**Output:** `diagrams/mermaid/process.svg`

```bash
mmdc -i diagrams/mermaid/process.mmd -o diagrams/mermaid/process.svg -t default
```

### BPMN Process Diagram

**Source:** `diagrams/bpmn/process.bpmn`
**Output:** `diagrams/bpmn/process.png`

```bash
bpmn-to-image "diagrams/bpmn/process.bpmn:diagrams/bpmn/process.png"
```

> **Note:** Both commands should be run from the `process-package/` directory.
