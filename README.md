# Skill Enhance

`skill-enhance` is a heavier, quality-first skill for building and enhancing other skills.

It is designed for cases where a valid `SKILL.md` is not enough and the goal is to produce a skill package that is clearer, more reliable for LLM execution, easier to validate, and closer to publishable quality.

## What This Skill Does

This skill helps with:

- creating a new skill from scratch
- enhancing an existing skill instead of only rewriting it
- improving trigger accuracy and trigger boundaries
- defining stronger output contracts
- filling in missing package artifacts
- reviewing whether a skill can reliably guide an LLM
- checking whether a skill is ready to publish

## What Makes It Different

Compared with a basic skill-creation flow, `skill-enhance` adds explicit quality gates for:

- trigger quality
- output-contract quality
- LLM execution reliability
- artifact completeness
- publish readiness

It is intentionally more thorough. The goal is not only to generate a skill, but to reduce the chance that the skill is vague, brittle, hard to discover, or incomplete.

## Typical Deliverables

Depending on the task, this skill may create or improve:

- `SKILL.md`
- `README.md`
- `agents/openai.yaml`
- `evals/evals.json`
- bundled `references/`
- release-note or changelog draft text

## When To Use It

Use this skill when:

- you want to build a serious reusable skill
- you need to harden an existing skill before release
- you are not confident the current skill can guide an LLM well
- the skill needs better triggers, docs, evals, or references
- you want a publish-readiness review instead of a light draft

## When Not To Use It

Do not use it when:

- you only need a tiny one-off local draft
- you are just installing or discovering skills
- the work is unrelated to skill design or packaging

## Bundled Files

- `SKILL.md`: agent-facing execution instructions
- `agents/openai.yaml`: display metadata and default prompt
- `evals/evals.json`: release-review eval prompts
- `references/`: quality and packaging guidance

## Example Prompts

- "Create a new skill that helps agents audit infrastructure migration plans, and make it publish-ready."
- "Strengthen this existing skill so it has better trigger boundaries and clearer outputs."
- "Review my skill package and tell me what is still missing before release."
- "Add README, evals, references, and release-note copy to this skill."
- "I think this skill under-triggers. Rewrite the description and review the boundary."

## Validation

This skill is intended to ship with structural validation and realistic eval prompts so the package can be reviewed before publication.
