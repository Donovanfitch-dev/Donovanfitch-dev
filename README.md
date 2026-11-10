# Donovan Fitch

AI systems engineer. I build agent systems that take real actions, and the execution, control and
release machinery that makes them safe to operate.

## Focus

- **Agent orchestration.** Durable task execution: leases, fencing, retries, checkpoints,
  idempotent side effects.
- **Control points.** Policy evaluation, human approval and audit trails between "the agent
  decided" and "it happened".
- **Reliability.** Explicit failure handling: fallbacks, circuit breakers, at-least-once delivery
  with idempotent receivers.
- **Operational automation.** Evidence-based release gates, CI, and model routing treated as
  reviewable policy.

TypeScript, Python, Next.js, SQL.

## Public repositories

Most of my engineering work is in private repositories. The six below are new public reference
implementations, notes and a playbook on problems I have worked on there. They were implemented
with AI coding agents (Claude Code), share no code or data with any private system, and each
README states what is checked and what is not.

| Repository | What it demonstrates | Stack |
| --- | --- | --- |
| [governed-agent-systems](https://github.com/Donovanfitch-dev/governed-agent-systems) | Design notes and a failure-mode checklist for agents that are allowed to act | Markdown |
| [agent-task-runtime](https://github.com/Donovanfitch-dev/agent-task-runtime) | Lease-based task runtime with fencing tokens, checkpoints and a transactional outbox | Python, SQLite |
| [agent-approval-console](https://github.com/Donovanfitch-dev/agent-approval-console) | Approval gate for agent-proposed actions: risk policy, idempotent execution, hash-chained audit log | Next.js, TypeScript |
| [evidence-gate](https://github.com/Donovanfitch-dev/evidence-gate) | Release readiness decided from evidence, with three verdicts: GO, NO_GO, UNDETERMINED | TypeScript |
| [llm-routing-gateway](https://github.com/Donovanfitch-dev/llm-routing-gateway) | Policy-based model routing with explained decisions, fallbacks and replay testing | TypeScript |
| [claude-execution-playbook](https://github.com/Donovanfitch-dev/claude-execution-playbook) | Decision guides and prompt templates for running coding tasks with Claude: model and effort choice, subagents versus workflows, scope and release boundaries, verification. Unofficial; not affiliated with Anthropic | Markdown, Python |

## Working principles

- A check that did not run is reported as unknown, never as a pass.
- Agents propose; a separate control point decides and executes exactly what was approved.
- Assume the worker dies halfway: leases, idempotency keys and an outbox.
- Autonomy is granted in stages: read-only, shadow, gated, then bounded.

## Contact

[donovanfitch.com](https://donovanfitch.com)
