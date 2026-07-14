# Huffmaster RACI Dashboard

Interactive view of the Huffmaster deployment workflow, built from the `Workflow_Actions` tab of the AppSheet RACI source workbook.

**Live dashboard:** https://daviddlr-lab.github.io/Huffmaster-RACI-Dashboard/

## What it shows

The workflow runs left to right through six stages, each closed by an approval gate:

`ENGAGEMENT → Gate 1 → STRATEGY → Gate 2 → EXECUTION → Gate 3 → NOTICE TO LAUNCH → Gate 4 → MONITOR → Gate 5 → CLOSE-OUT → Gate 6`

Each stage column holds the actions that live inside it. Click any action to drill into its tasks and subtasks.

| | Count |
|---|---|
| Stages | 6 |
| Gates | 6 |
| Actions (processes) | 112 |
| Tasks | 413 |
| Subtasks | 189 |
| Total rows | 719 |

## Features

- **Search** across every action, task, owner, and swimlane
- **Drill-down** — click an action to expand its tasks and subtasks
- **Expand all / Collapse all**
- **Light and dark mode** — toggles in the header, remembers your choice, defaults to your OS setting
- **Swimlane color coding** — Sales, Operations Field, Operations Staffing, Travel, Finance / Accounting, Project Management, Executive / Admin

## Observations from the data

- **Notice to Launch carries a third of the workflow** — 44 actions and 230 rows, versus 11–18 actions in every other stage. The clearest candidate for splitting or automating.
- **21 actions have no tasks beneath them**, mostly in that same stage — either genuinely single-step, or the checklist detail was never filled in.
- **Action 6.10 (Accounting) is the only one with an unmapped swimlane** — 12 rows with no lane assigned.

## Files

- `index.html` — the dashboard, fully self-contained (no build step, no dependencies, no network calls)
- `workflow_actions.csv` — the source data it was generated from

## Source mapping

Stage comes from column E, Action / Task from column H. Hierarchy is reconstructed from `Process ID` and `Parent ID`; gates from the `Gate` column; swimlanes from `Primary Swimlane`; ownership from the RACI columns.
