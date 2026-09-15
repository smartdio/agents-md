# Changelog

English (canonical) | [简体中文](CHANGELOG.zh-CN.md)

## 2026-09-15

### Per-task sub-agent model selection

- Separated model capability from reasoning depth and allowed each subtask to use the least costly or fastest available model that still meets its acceptance criteria.
- Clarified that sub-agents need not share one model or match the main agent, while preserving the user's main-agent settings and actual tool capability boundaries.
- Updated the project-adoption prompt and orchestration reference in both languages.
- Added an optional prompt using GPT-6 as the main-agent baseline and GPT-5.6 (for example, `gpt-5.6-sol`) for suitable simpler subtasks, with independently selected reasoning depth, availability checks, unchanged acceptance standards, and escalation when needed.

## 2026-09-14

### Ready-to-use documentation URL

- Replaced the example prompt's source placeholder with the canonical GitHub README URL so it can be copied without editing the source field.

### Public documentation cleanup

- Removed machine-specific migration notes from both READMEs; public usage does not depend on private local paths.

### Project-specific workflow prompt

- Reframed the example prompt around designing a workflow suited to the target project's characteristics, scale, and existing practices, rather than merely importing rules.
- Aligned both README procedures with project inspection, selective adaptation, and reporting the rationale. Preserved existing constraints, incremental merging, and the AGENTS.md-only scope.

### Link-based adoption

- Added a README-first adoption workflow and copyable prompts for source repository/directory, README, or relevant document URLs and paths.
- Distinguished source and target projects, explicit adoption from read-only review, and merging from replacement. Repeated adoption updates existing rules without duplicating them.
- Required preservation of target-specific instructions, language, existing edits, and authorization boundaries, with valid references and a concise adoption report.
- This changes the source project's usage documentation only; no target project was modified and no remote repository was published.

### English source and Chinese localization

- Made AGENTS.md, the project README, reference documents, experience index, and changelog English-first.
- Preserved Chinese counterparts as `.zh-CN.md` files with language navigation and local-language links.
- Added translation synchronization guidance. Historical experience records remain in their original language with their original hashes; the earlier rehearsal does not certify the later translation.
- This is a language and documentation-layout change, not an intended policy change. Other projects remain untouched.
- Independent review found no substantive mismatch across the 23 policy clauses or the key reference boundaries. Corrected the Chinese README's maintenance target to the English source and rechecked its navigation links. This was translation and link verification, not a rerun of the historical 14-scenario rehearsal.

### Scheduling and takeover boundaries

- Addressed tabletop-review gaps: queue work or let the main agent handle suitable tasks when capacity is exhausted; stop affected obsolete work after requirements change and inspect partial artifacts before reassignment.
- Clarified that the main agent decides and schedules further delegation. Before taking over writes after loss of contact or replacement, inspect partial changes and confirm that the original executor and related operations have stopped writing. The reference explains that sending an interrupt does not establish that external operations have stopped.
- Based on tabletop review, not a performance benchmark. No token savings were measured or claimed; other project copies were not synchronized.

### Analysis role

- Made the analysis agent read-only by default, responsible for root-cause and solution research, with reasoning effort matched to problem difficulty. The main agent retains solution decisions and final acceptance.

### Policy simplification

- Merged repeated clauses while retaining coordination, specialist context continuity, reasoning configuration, acceptance, and shared-resource constraints.
- Moved full task briefs, reporting templates, and capability explanations into an on-demand reference. Simple delegation no longer requires a nine-field form.
- Added guidance for handling reference links when reusing the policy. Other project copies were unchanged; no task-level token savings were claimed.

### Initialization

- Created the maintenance project and imported the previously prepared AGENTS.md without changes.
- Added reference and experience entry points, with evidence collected before rules are generalized.
- The initial import did not modify the policy or overwrite other projects.
