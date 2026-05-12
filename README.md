# Skill Enhance

`skill-enhance` is a quality-first skill for creating, improving, reviewing, and locally customizing other skills.

It is designed for users who want more than a minimal `SKILL.md`. Instead of stopping at a rough draft, it helps produce a skill package that is clearer, easier to trigger, easier for an LLM to follow, better documented, easier to validate, and closer to release quality.

## What It Does

`skill-enhance` helps agents:

- create a new reusable skill from an idea, workflow, or target outcome
- improve an existing skill that is vague, weak, incomplete, or inconsistent
- optimize a local skill package so it better matches the user's own workflow
- review whether a skill is actually ready to publish

Typical improvement areas include:

- trigger boundary design
- workflow solidification
- output-contract design
- README improvement
- eval design
- metadata completion
- reference-document structuring
- release-readiness review

## Why It Exists

Many skills are structurally valid but still weak in real use.

Common problems include:

- the skill triggers too often or not often enough
- the instructions are valid but not reliable for another LLM to execute
- the package is missing README, evals, metadata, or references
- the skill works only for the original author
- the package looks complete but is not ready for release

`skill-enhance` is built to close those gaps.

## Who It Is For

This skill is useful for:

- users building a new skill for Codex, Claude Code, or similar agent systems
- users improving a skill they already wrote
- users adapting a downloaded or installed local skill
- users preparing a skill for internal sharing or public release

## What You Get

Depending on the task, `skill-enhance` may create, revise, or review:

- `SKILL.md`
- `README.md`
- `agents/openai.yaml`
- `evals/evals.json`
- `references/` documents
- release-note or changelog draft text

The goal is not just file generation. The goal is a stronger skill package.

## Core Use Cases

### Create a New Skill

Use this when you have a target capability and want a reusable skill package instead of a quick draft.

Typical outcomes:

- a clear trigger boundary
- a fixed workflow
- a defined output contract
- a more complete package structure

### Improve an Existing Skill

Use this when a skill already exists but needs stronger structure, wording, or packaging.

Typical outcomes:

- better trigger accuracy
- clearer instructions
- improved package completeness
- stronger release-facing quality

### Optimize a Local Skill

Use this when the target skill already exists on the local machine and needs to better match the user's workflow.

This includes:

- project-local skills
- self-created skills
- locally downloaded hub skills
- skills stored by Codex or Claude Code
- `skill-enhance` itself

When local modification is requested, the skill is expected to:

- identify the target skill and path
- check whether the current environment can access the path
- check whether the current environment can write to the path
- confirm the path and the edit intent before changing files

If the target cannot be safely modified, it should say so clearly and stay in analysis mode.

### Review Release Readiness

Use this when you want to know whether a skill is still missing documentation, metadata, evals, references, or other publish-facing artifacts.

Typical outcomes:

- missing-artifact review
- trigger-quality review
- output-contract review
- publish-readiness judgement
- concrete next-step recommendations

## Why It Is Different

`skill-enhance` is intentionally heavier than a lightweight scaffolder.

It does not stop at "here is a draft." It is designed to ask whether the skill:

- triggers at the right time
- gives another LLM enough structure to follow
- produces the right kind of output
- includes the expected supporting artifacts
- can be validated
- is actually ready to ship

## How To Use It

In most cases, the user does not need to understand the package layout in detail.

A request can be simple:

- "Create a publish-ready skill for X."
- "Improve this skill so it triggers more accurately."
- "Review this skill and tell me what is missing before release."
- "Optimize the skill at this local path, but confirm before editing."

The skill should then identify the right task mode and move through a fixed workflow.

## Standard Workflow

The default workflow is:

1. identify the task mode
2. check local editability when a local skill is involved
3. define the trigger boundary and output contract
4. build or revise the necessary artifacts
5. run review gates
6. report readiness

`SKILL.md` is the source of truth for the exact execution rules.
This README is the user-facing overview.

## Standard Package Layout

For a reusable skill, the default package layout is:

```text
skill-name/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── evals/
│   └── evals.json
└── references/
```

Not every skill needs every file on day one, but reusable or publishable skills should usually move toward this structure.

## When To Use It

Use `skill-enhance` when you want:

- a better skill, not just a quick draft
- a stronger trigger boundary
- a clearer workflow for LLM execution
- a more complete skill package
- a publish-readiness review
- a safe way to improve a locally available skill

## When Not To Use It

Do not use it when:

- you only need a tiny throwaway draft
- you only want to discover or install a skill
- the work is unrelated to skill creation, skill optimization, or skill packaging

## Example Prompts

- "Create a new skill that turns incident notes into an operational runbook and make it release-ready."
- "Improve this skill so it triggers more precisely and has a clearer output contract."
- "Review this skill package and tell me what is missing before publication."
- "Optimize the skill at this local path, but check whether you can edit it before making changes."
- "Improve the README, evals, and metadata for this downloaded skill."

## Validation

This skill is designed to support:

- structural validation
- realistic eval prompts
- fixed workflow guidance
- package completeness review
- publish-readiness judgement

That makes it suitable for local iteration, internal hardening, and release preparation.
