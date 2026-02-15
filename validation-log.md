# Validation Log

## Entry 1 — SOP / Mermaid / BPMN Consistency Check

**Date:** 2026-02-15
**Validator:** Claude Code (CLI)

### Scope

Cross-validated that the three process artifacts describe the same workflow:

- `SOP.md` (source of truth)
- `diagrams/mermaid/process.mmd`
- `diagrams/bpmn/process.bpmn`

### Steps Comparison

| SOP Step | Description | Mermaid | BPMN |
|----------|-------------|---------|------|
| — | *(Admin sends reminder)* | Not present | `Task_SendReminder` |
| 1 | Determine if it's time to finalize grades | `Start` + `D1` | `Gateway_1` |
| 2 | Log in to PowerSchool | `S2` | `Task_2` |
| 3 | Open PowerTeacher Pro | `S3` | `Task_3` |
| 4 | Navigate to Score Sheet, verify grades | `S4` | `Task_4` |
| 5 | Open Traditional Grade Calculations, verify weights | `S5` | `Task_5` |
| 6 | Save grade calculation changes | `S6` | `Task_6` |
| 7 | View final grade (Traditional) | `S7` | `Task_7` |
| 8 | Mark Final Grade Status as complete | `S8` | `Task_8` |
| 9 | Repeat for all classes | `D3` | `Gateway_3` |
| 10 | Email Secretary, log out | `S10` | `Task_10` |
| — | *(Secretary receives email)* | Not present | `Task_ReceiveConfirmation` |

### Decisions Comparison

| Decision | SOP | Mermaid | BPMN |
|----------|-----|---------|------|
| Is it time to finalize? | Step 1: Yes → Step 2, No → End | `D1`: Yes → S2, No → EndNoAction | `Gateway_1`: Yes → Task_2, No → EndEvent_NoAction |
| Is final grade correct? | Step 7: Yes → Step 8, No → Step 4 | `D2`: Yes → S8, No → S4 | `Gateway_2`: Yes → Task_8, No → Task_4 |
| All classes finalized? | Step 9: Yes → Step 10, No → Step 7 | `D3`: Yes → S10, No → S7 | `Gateway_3`: Yes → Task_10, No → Task_7 |

### Result

**PASS** — All three artifacts are consistent.

### Notes

- The BPMN diagram includes two additional tasks not in the Mermaid diagram: `Task_SendReminder` (Administrator lane) and `Task_ReceiveConfirmation` (Secretary lane). These represent roles documented in the SOP's roles section but not included as numbered steps. This is an intentional expansion from when lanes were added (prompt log Entry 4), not an inconsistency.
- The Mermaid diagram covers only the Teacher's 10 numbered steps, which is its intended scope.
- All three decision points and their loop-back targets match exactly across all artifacts.

---

## Entry 2 — Glossary / SOP Consistency Check

**Date:** 2026-02-15
**Validator:** Claude Code (CLI)

### Scope

Validated that all glossary terms are accurate and that all key terms from the SOP are represented in `glossary.md`.

### Roles

| Glossary Term | In SOP? | Match? |
|---------------|---------|--------|
| **Teacher** | Yes — `roles[0]`, actor on all 10 steps | PASS |
| **Secretary** | Yes — `roles[1]`, receives confirmation (Step 10) | PASS |
| **Principal** | Yes — `roles[2]`, sends reminder email | PASS |

### Systems & Tools

| Glossary Term | In SOP? | Match? |
|---------------|---------|--------|
| **PowerSchool** | Yes — Step 2 (login), Step 10 (grades stored), prerequisites | PASS |
| **PowerTeacher Pro** | Yes — Step 3 (open under a class) | PASS |
| **Score Sheet** | Yes — Step 4 (Grading → Score Sheet) | PASS |
| **Traditional Grade Calculations** | Yes — Step 5 (Settings → Traditional Grade Calculations) | PASS |
| **Final Grade Status** | Yes — Step 8 (mark as complete) | PASS |

### Process Terms

| Glossary Term | In SOP? | Match? |
|---------------|---------|--------|
| **Grading Period** | Yes — referenced in scope, prerequisites, multiple steps | PASS |
| **Quarter** | Yes — referenced throughout (quarter or semester) | PASS |
| **Semester** | Yes — referenced throughout (quarter or semester) | PASS |

### Result

**PASS** — All glossary entries are accurate and match the SOP.

### Notes

- One SOP screen name ("Traditional Grades" from Step 7: Grading → Grades → Traditional) is not defined in the glossary, though the related "Traditional Grade Calculations" is. Deemed not necessary to add.
