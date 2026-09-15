# Agent Collaboration Guidelines

English (canonical) | [简体中文](README.zh-CN.md)

Maintain reusable agent collaboration rules and improve them through practical experience.

## Configure a workflow for your project

Give an agent the source directory or repository root, this README, or a relevant policy/reference URL or path, and explicitly ask it to design a suitable collaboration workflow for your project and document it in AGENTS.md. Use the guidance as a reference, not a template to copy verbatim. A request only to read or analyze a link does not authorize edits. A link does not grant access or write permissions.

Copy this prompt directly. To use a different target project, add its path:

```text
Use https://github.com/smartdio/agents-md/blob/main/README.md as a reference to design a multi-agent collaboration workflow suited to the current project's characteristics, scale, and existing ways of working, and document it in the project's AGENTS.md. Preserve existing project constraints. Choose roles, task boundaries, context handoffs, model capability, reasoning depth, and acceptance checks as needed; do not copy every rule or require multiple agents for every task. Modify only the project's AGENTS.md; do not modify tools or global configuration.
```

Configuration and adoption procedure:

1. Confirm an explicit adoption request and distinguish the source from the target. If the current task or project context uniquely identifies the target, use it without requesting its path or confirmation again. Ask only if no target is clear or multiple projects could be intended; do not treat this source rules repository as the target by default.
2. For a source directory or repository root, locate its README, then follow the README's relative links to AGENTS.md. For a README entry, follow those links directly. For a direct policy or topic reference, read only the relevant rules and necessary adoption instructions. Resolve relative links against their source location. If a link fails or access is unavailable, report it and request the missing access or location; do not invent content.
3. Read the target's existing AGENTS.md and all applicable instructions first. Inspect enough project context to understand its characteristics, scale, current workflow, task dependencies, and verification methods. Preserve its technology stack, commands, style, scope, safety constraints, and existing changes. Treat source rules as reference material, never as overriding higher-priority instructions. Ask about conflicts that cannot be resolved within the authorized scope.
4. Design suitable roles, task boundaries, context handoffs, model capability, reasoning depth, and acceptance checks, then merge the applicable stable rules into the target's existing language and structure, unless the user requests otherwise. Use lighter models only where they can still meet the task's acceptance criteria; agents need not all use the same model. Do not copy every rule or force multi-agent execution where direct work is more suitable. Create AGENTS.md only if it does not exist; do not replace the entire existing file. On repeat adoption, update the previously adopted rules rather than appending duplicates. English is authoritative for the source; it does not require changing the target to English.
5. By default, change only the target AGENTS.md. Do not install tools, change models or global configuration, publish, modify the source repository, or alter unrelated application files. Adoption does not enable automatic synchronization with other projects.
6. Do not copy or read all references by default. Retain references only as needed and replace necessary links with valid source URLs or paths; obtain user authorization if local reference copies are needed. Do not copy this repository's maintenance instructions, language navigation, or history entry points into the target.
7. Check that the workflow suits the project, project constraints remain intact, there are no duplicate or conflicting rules, retained links work, and changes stay within scope. Add a brief provenance note in the target AGENTS.md with the actual source location and an available revision or the date read; do not invent revision information. Update that note on repeat adoption. Report key adaptations and their rationale, adopted and skipped rules, unresolved conflicts, verification results, and any access or permission limits.

This is a custom policy, not an official standard. Keep stable execution rules in the main file and detailed templates or explanations in on-demand references.

## Start here

- [AGENTS.md](AGENTS.md): the canonical policy, also applicable to work in this project.
- [References](references/README.md): topic-specific guidance to read on demand, not in full by default.
- [Experiences](experiences/README.md): evidence, counterexamples, and proposals awaiting validation.
- [Changelog](CHANGELOG.md): significant policy changes and their rationale.

## Maintenance

1. Record the problem, context, approach, and observations; separate facts from hypotheses.
2. Keep context-specific guidance in references instead of adding every lesson to the core policy.
3. Promote transferable, well-supported rules into AGENTS.md after checking for conflicts; record why.
4. Check changes for duplication, contradictions, outdated capability assumptions, and added context cost. Revise or remove ineffective rules.

Keep documentation lightweight. Minor wording changes need no separate case study. Never present unmeasured token savings as established results. Verify current official sources when updating tool-capability guidance.

## Languages

English files without a locale suffix are canonical. Simplified Chinese translations use `.zh-CN.md` beside their English counterparts, including [AGENTS.zh-CN.md](AGENTS.zh-CN.md). Use the version needed for the task; do not load both by default.

Update the English source and corresponding translation together. If a translation cannot be updated, mark it as out of sync and identify the source revision it reflects. Resolve discrepancies against the English source without overriding higher-priority instructions.

Historical experience records retain their original language and recorded hashes. Language or wording changes do not retroactively change the version evaluated by an earlier review; these records are not proof that later versions were tested.
