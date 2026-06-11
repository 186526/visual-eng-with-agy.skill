# visual-eng-with-agy

An Oh My OpenAgent/OhMyOpenCode skill for routing complex styling-focused visual engineering tasks through a low-cost general agent that launches `agy` with Gemini 3.1 Pro.

The main skill instructions live in `SKILL.md`.

## Install

Place this directory at one of OpenCode's skill discovery paths, for example:

- Project-local: `.opencode/skills/visual-eng-with-agy/SKILL.md`
- User-global: `~/.config/opencode/skills/visual-eng-with-agy/SKILL.md`

Restart the OpenCode session after adding the skill.

## Intended Use

Load this skill only when complex styling, layout, visual polish, animation, responsive presentation, or screenshot-driven visual QA should be performed by `agy` using Gemini 3.1 Pro. Use a regular general agent for frontend logic, state, data flow, API wiring, event handling, non-visual component behavior, and simple styling tweaks.

## Core Rule

The delegate should execute complex visual passes by launching `agy` with Gemini 3.1 Pro whenever available. For complex visual work, first ask `agy` to split the task into atomic visual changes, then run a separate `agy` execution for each change to avoid broad diffs and timeouts. If the task is frontend logic or a simple styling tweak, route it to a regular general agent. If `agy` is unavailable, blocked by authentication, or cannot access Gemini 3.1 Pro, report the blocker and fall back first to OMO's configured visual-engineering agent, then to the best available general agent if needed.
