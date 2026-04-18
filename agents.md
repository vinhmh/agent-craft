# AI agents — Claude (CLI) vs Codex (context)

Personal notes comparing two agent shapes: one centered on the **terminal and automation**, one centered on **in-editor suggestions grounded in project context**. Same broad idea (model + agent behavior), different default surface and strength.

## Quick comparison

| | **Claude (CLI agent)** | **Codex (context agent)** |
| --- | --- | --- |
| **Where it lives** | CLI / terminal-oriented workflow | Editor and project-aware flow |
| **Model “brain”** | Claude-family (e.g. **Claude 3.5**) | **Codex** model at the core |
| **Main strength** | **Planning**, tools, real commands, feedback loops | **Knowing context** — repo, files, cursor, task |
| **Typical use** | **run → test → debug → fix** until pass or done | **Suggest code with context** — completions, refactors, explanations that fit *this* codebase |
| **How it extends itself** | Read files, run shell, self-research, iterate | Pull surrounding code and project signals into each suggestion |

Neither row is “better” in the abstract: CLI agents shine when the job is **drive the machine and close the loop**; context-heavy Codex shines when the job is **stay aligned with the code in front of you**.

---

## Claude — CLI agent

### What it is

In a **CLI environment**, Claude is an **AI agent**: it is not limited to a single reply in a chat window. It can maintain a task, reason about next steps, and act through interfaces the CLI exposes.

### Model as “brain”

The agent is driven by a **Claude-family model** (for example **Claude 3.5** in many setups) that acts as the **brain**: it decides what to do next, how to interpret tool output, and when the goal is met.

### Core abilities

- **Planning** — Break work into steps, revise the plan when new information appears, and sequence actions sensibly.
- **Tools** — Use capabilities such as **reading files on the system**, **running shell commands**, and **looking things up** so it can **self-research** instead of guessing.
- **Terminal integration** — Commands run in a real environment, so results (builds, tests, logs) feed back into the next decision.

### Automation loop

A common pattern is an iterative loop until success:

**run → test → debug → fix** (repeat until tests pass or the task’s definition of “done” is satisfied).

That loop is what makes the CLI agent useful for engineering workflows: it can drive the machine like a developer would, using feedback from each step.

---

## Codex — context and suggest

### What it is

Codex is an **AI agent** whose core is the **Codex model**: reasoning and actions are grounded in that model, not only as a chat-style assistant but as an agent that can work with your project over time.

### Main strength: context

The standout property is **knowing context**—the agent can take in what is already true in your codebase, files, and task, and use that as the basis for answers and edits. Suggestions are tied to **where you are and what you are doing**, not generic snippets disconnected from your project.

### What that enables

With strong context, Codex can **suggest code with context**: completions, refactors, and explanations that match your stack, patterns, and surrounding lines. The value is not only “correct code in the abstract” but code that **fits this repo and this moment**.

---

*Refine this file as products and your usage evolve.*
