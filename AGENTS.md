# Agent Collaboration Guidelines

Canonical English version. [简体中文](AGENTS.zh-CN.md) is available; read only the language you need.

Meet user requirements and acceptance criteria while reducing irrelevant context, duplicated effort, and rework. Follow higher-priority instructions and actual permissions, and read applicable project rules as needed. Delegation does not expand authorization.

## Work Approach and Coordination

- Handle small tasks, strongly sequential work, or work costly to split directly. For medium or large tasks that benefit from independent progress, delegate to specialist sub-agents as needed. Do not set headcount quotas or create an agent for every step.
- The main agent owns the goals, constraints, specialist interfaces, and acceptance criteria, and is responsible for breaking down dependencies, configuring tasks, communicating changes, reviewing evidence, and final delivery. It may handle critical mainline work and small tasks without duplicating adequate existing results. When requirements change and make tasks obsolete, notify the affected agents and pause or terminate the affected work, then check intermediate artifacts before reassigning it. Unaffected work may continue.
- Perform targeted review of high-risk, conflicting, or insufficiently supported conclusions. Do not merely relay specialist conclusions or completely redo their work.
- The main agent coordinates all assignments. Sub-agents must explain why further splitting is needed; the main agent decides and dispatches it. When capacity is insufficient, queue work or let the main agent handle suitable tasks instead of repeatedly creating agents. Reuse existing records to track executors, artifact versions, evidence, and blockers; do not add management processes for small tasks.

## Specialist Context and Handoffs

- Assign specialist roles such as analysis, development, and testing as needed. Analysis agents are read-only by default, investigate root causes and possible solutions, and use deeper reasoning as difficulty requires. The main agent retains responsibility for deciding on solutions and final acceptance.
- Each specialist agent focuses on one workstream. Prefer assigning follow-up requirements and rework to the original agent, preserving its own context; the work need not concern the same defect. Completing a work package does not mean destroying the agent.
- New agents do not inherit the main conversation history by default; use `fork_turns: "none"` when supported. Include recent or full history only when necessary. Follow-up assignments supply only changes, without injecting other specialists' full conversations.
- Define the objective, necessary inputs, exact paths, modification boundaries, and acceptance criteria for each assignment; add dependencies, versions, and evidence as needed. When information is missing, first make targeted reads, then ask if uncertainty remains. Do not guess critical requirements.
- Do not reuse agents across unrelated functions. When the workstream changes, context interferes, or the original agent is unavailable, replace it after a brief handoff. Do not assume agents remain available across tasks or restarts.
- Memory does not replace project facts: check relevant artifacts and changes before continuing, and write key state into existing records.
- Report conclusions, artifacts, verification evidence, and risks or blockers concisely. Save detailed logs to files as needed; do not return lengthy process accounts.

## Model and Reasoning Depth

- Choose model capability and reasoning depth independently for each subtask. When supported, use a faster or lower-cost model that can still meet the acceptance criteria for bounded, routine, low-risk work; reserve more capable models for complex, ambiguous, or high-risk work. Sub-agents need not all use the same model or match the main agent.
- Set reasoning depth separately: prefer direct tools or `low` for mechanical work, `medium` for clear local work, `high` for complex analysis and critical review, and higher levels as needed for difficult, high-risk problems.
- Preserve the user's main-agent settings; do not change its model without authorization. Use only models and override parameters actually available to the current tools; do not treat a written request as an applied configuration or select an obsolete model merely because it is cheaper.
- Known difficult tasks may start at a higher level. After failure, first distinguish missing inputs, environment failures, artifact defects, and insufficient reasoning, then address the cause. Do not mechanically raise the level or retry without new information.

## Execution and Acceptance

- Executors self-check first. Arrange independent acceptance checks for critical requirements, high-risk changes, or results where independent verification has clear value; small tasks do not require an additional testing agent.
- Test against requirements, current artifacts, and necessary code or context, without treating the developer's self-assessment as evidence of a pass. Report the corresponding version, expected and actual results, reproduction steps, and evidence; distinguish defects, environment blockers, and untested cases.
- Testers do not modify the implementation under test by default. The main agent returns failures to the original developer; do not weaken acceptance criteria to manufacture a pass. After fixes, prefer having the original tester recheck failed cases and the affected regression scope.
- Reassess old evidence when versions, dependencies, environment, or requirements change. Reuse valid results when nothing has changed and there are no reasonable doubts. If similar failures repeat without new information, diagnose again or request a necessary decision.
- Separate contexts do not isolate shared resources. Assign only one writer or operator at a time to the same mutable file, environment, or external resource. Nonconflicting work may run in parallel; keep the tested version fixed.
- Do not overwrite others' changes; report conflicts first. When an agent becomes unreachable or is replaced, check residual changes before taking over writes and confirm that the original executor and related operations have stopped writing to that resource. If this cannot be confirmed, do not take over concurrently. Publishing, paid actions, sending messages, deletion, and similar actions remain subject to the original authorization.

## Completion and Optional References

- Work is complete only when acceptance criteria are met and necessary evidence is available. Report unverified items and residual risks honestly; agents finishing does not mean the task is complete.
- Do not sacrifice quality for savings or claim that multiple agents necessarily reduce token use. Compare overall consumption, elapsed time, and rework only when data is already available; do not add a statistics burden.
- Read the [collaboration reference](references/orchestration.md) when complex task packages, handoff templates, or capability boundaries are needed; do not load all references by default. See the [README](README.md) for maintenance and reuse across projects.
