# Orchestration Reference: Templates and Capability Boundaries

English (canonical) | [简体中文](orchestration.zh-CN.md)

Read only for complex delegation, handoffs, or capability questions. The root AGENTS.md defines the core policy. Use these templates as needed, not as mandatory forms on every turn.

## Complex task brief

```text
Role and workstream:
This turn's objective / exclusions:
Necessary background and confirmed decisions:
Inputs, exact paths, and artifact versions:
Files / resources that may be modified:
Interfaces, dependencies, and constraints to preserve:
Acceptance criteria and applicable verification commands:
Reusable evidence:
Deliverables and reporting format:
```

A simple task only needs a clear objective, inputs, modification boundaries, and acceptance criteria. Follow-ups to the same agent should contain changes only: do not repeat stable background or omit new constraints.

## Results and replacement handoffs

```text
Status: complete / partial / blocked
Conclusion: concise findings and necessary rationale
Artifacts: modified paths and version identifiers
Verification: checks performed, results, and evidence paths
Risks: unverified items, limitations, or possible impacts
Next step: specific matters requiring the coordinator's attention
```

When replacing an agent, also include necessary decisions, unresolved issues, and unsuccessful approaches already ruled out. Do not require the full conversation history. Retain detailed logs only when useful for later work; do not output internal reasoning traces.

Loss of contact does not establish that execution has stopped. Sending an interrupt does not establish that external tools or background operations have stopped. Before taking over a resource, inspect partial changes and confirm that the original executor and related operations have stopped writing. If this cannot be confirmed, do not assign a new executor to take over writing concurrently; unaffected independent work may continue.

## Capability boundaries

- AGENTS.md is behavioral guidance, not an executable scheduler. It cannot guarantee tool capabilities or configuration changes.
- Sub-agent model selection and reasoning effort are separate decisions. Model availability and per-agent overrides depend on the current interface; a default sub-agent model does not require every sub-agent to use it when an explicit supported override is available.
- Omitting the main conversation at creation does not mean clearing the specialist's context on every turn. Continue using the actual original agent identifier; creating a new agent with the same name does not restore it.
- An agent may not remain accessible across new tasks, restarts, or recovery. Project files preserve key state, not the complete agent session.
- Available model and reasoning overrides depend on the current interface. If an existing agent cannot change them dynamically, first consider supplying precise information or handing off only a bounded difficult question to a more capable or higher-effort agent; the entire workstream need not be discarded.

Capability reference: [OpenAI subagent documentation](https://learn.chatgpt.com/docs/agent-configuration/subagents). These boundaries are carried forward from the initial policy. Recheck them when tools change; do not treat them as permanent capability promises.

## Cost evaluation

Parallel work may reduce elapsed time but does not guarantee lower total consumption. When measurements are already available, include the main agent and all subagents, and compare quality and rework alongside consumption. Distinguish tokens, cached billing, and subscription quotas. Without measurements, say that savings cannot be quantified; do not introduce an expensive process merely to prove savings.
