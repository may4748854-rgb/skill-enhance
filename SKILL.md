---
name: skill-enhance
description: Create, enhance, harden, and prepare skills for release. Use this skill whenever the user wants to build a new skill, strengthen an existing skill, improve trigger accuracy, add README or eval materials, review whether a skill can reliably guide an LLM, or decide if a skill is ready to publish. Also use it when a skill needs stronger output contracts, artifact completeness checks, or publish-readiness review. Do not use it for ordinary copy editing, unrelated code refactors, or simple skill installation tasks.
---

# Skill Enhance

Use this skill to produce high-quality skills that are not only structurally valid, but also clear, triggerable, executable, testable, and publishable.

This skill is intentionally heavier than a lightweight skill scaffolder. Favor quality over speed when the user is creating or enhancing a skill that other agents or users will depend on.

## Trigger Boundary

Use this skill when the task is primarily about skill quality, including:

- creating a new skill from scratch
- enhancing an existing skill
- improving skill trigger accuracy
- strengthening a skill's output contract
- adding or refining README, evals, references, metadata, or release notes
- reviewing whether a skill can reliably guide an LLM
- checking whether a skill is ready to publish

Do not use this skill as the main path for:

- ordinary prose editing unrelated to skills
- general code refactoring unrelated to skills
- simple skill discovery or installation
- platform-specific publishing steps that do not affect the skill package itself

If the request is mixed, use this skill only for the skill-quality slice.

## Core Principle

Do not stop at "here is a draft."
The goal is to deliver a skill package or a concrete enhancement plan that closes the gap between:

- a loosely defined skill idea
- and a dependable skill another LLM can actually use well

Treat these as first-class quality dimensions:

1. trigger quality
2. execution clarity
3. output contract quality
4. artifact completeness
5. validation coverage
6. publish readiness

## Task Modes

Classify the request into one primary mode:

1. **New skill creation**
2. **Existing skill enhancement**
3. **Trigger optimization**
4. **Artifact completion**
5. **Quality review**
6. **Publish-readiness review**

If several modes are present, use this sequence:

1. summarize the current state and target
2. identify the quality gaps
3. decide what the skill must do and when it should trigger
4. define or rewrite the output contract
5. produce or revise the package artifacts
6. run the review gates
7. state whether the skill is publish-ready

## Workflow

### 1. Capture the real objective

Before writing anything, determine:

- is the user creating a new skill or enhancing an existing one
- who the skill is for
- what user requests should trigger it
- what the skill must produce when triggered
- whether the target is project-local, shareable, or release-ready

If an existing skill already exists, read it first and extract:

- current capability
- current trigger wording
- bundled artifacts
- gaps or inconsistencies

### 2. Define the skill contract

Do not write `SKILL.md` before the contract is clear.

At minimum, define:

- the skill's purpose
- positive trigger cases
- negative trigger cases
- expected output structure
- required artifacts
- validation expectations

Use `references/trigger-design.md` and `references/output-contracts.md`.

### 3. Build or revise the package

By default, a strong skill package should include:

- `SKILL.md`
- `README.md`
- `agents/openai.yaml`
- `evals/evals.json`
- relevant `references/`

Use `references/artifact-matrix.md` to decide which artifacts are required and which are optional.

Do not assume a valid `SKILL.md` alone is enough for a publish-quality skill.

### 4. Strengthen trigger quality

Review the trigger description for:

- under-triggering
- over-triggering
- ambiguous phrasing
- missing common request patterns
- missing exclusions

If needed, rewrite the description so the skill is more likely to trigger when useful, but less likely to hijack unrelated tasks.

### 5. Strengthen execution reliability

Check whether the skill instructions are actually actionable.

Specifically review:

- whether the workflow is clear
- whether decision points are explicit
- whether outputs are well specified
- whether the skill asks for real deliverables, not just abstract advice
- whether references are discoverable and scoped correctly

Use `references/review-checklist.md`.

### 6. Add validation coverage

Create realistic eval prompts whenever the skill is expected to produce repeatable, reviewable outputs.

Use `evals/evals.json` to cover:

- core happy-path creation or enhancement
- trigger-boundary cases
- artifact-completion cases
- publish-readiness cases
- at least one non-trigger or out-of-scope case

If the skill is subjective, the evals can still define expected output qualities rather than strict assertions.

### 7. Review publish readiness

Use `references/publish-readiness.md` and `references/skill-packaging.md`.

Before calling the work done, check:

- does the skill name make sense publicly
- does the description help discovery
- are human-facing docs separate from agent-facing instructions
- are bundled artifacts sufficient
- is the skill understandable without extra hidden context
- is there enough validation material for release review

State clearly whether the skill is:

- draft
- internally usable
- release-candidate
- publish-ready

## Output Contract

Default to this structure unless the user requests another format:

### 1. Task mode

State whether this is new creation, enhancement, trigger optimization, artifact completion, quality review, or publish-readiness review.

### 2. Current-state summary

Describe the current package or the requested target in 2-4 lines.

### 3. Key quality gaps or design goals

List the highest-impact issues or goals.

### 4. Recommended changes

Describe what to create, rewrite, or add.

### 5. Artifact plan

State which files are required, optional, missing, or already strong.

### 6. Review findings

Summarize trigger quality, execution reliability, output-contract quality, and publish-readiness findings.

### 7. Validation

State what was validated, what still needs validation, and whether the package is publish-ready.

## Quality Gates

The skill must explicitly check these gates when relevant:

### Trigger Boundary Review

Check whether:

- the description contains concrete usage contexts
- the skill would likely trigger when useful
- the skill excludes obvious false positives
- the trigger boundary is neither too broad nor too narrow

### Output Contract Review

Check whether:

- the skill tells the agent what to produce
- output structure is explicit
- required content is clear
- execution steps are not vague or purely advisory

### LLM Reliability Review

Check whether:

- the instructions are actionable
- the workflow has clear transitions
- important decisions are surfaced
- the skill drives toward delivery, not endless analysis

### Artifact Completeness Check

Check whether the package needs:

- `README.md`
- `agents/openai.yaml`
- `evals/evals.json`
- key references
- release notes or changelog copy

### Publish-Readiness Check

Check whether the package is understandable, verifiable, and suitable for public or team-wide use.

## Constraints

- Do not treat a valid frontmatter block as proof of a good skill.
- Do not produce a skill that only contains abstract theory.
- Do not skip trigger-boundary review when the skill is meant to be reused.
- Do not skip artifact completion if the user is aiming for release.
- Do not force heavyweight benchmarking when lightweight validation is enough.
- Do not claim publish readiness without checking docs, evals, and packaging materials.

## References

- `references/trigger-design.md`: how to design strong trigger boundaries
- `references/output-contracts.md`: how to define reliable skill outputs
- `references/review-checklist.md`: quality review checklist for skill reliability
- `references/publish-readiness.md`: release-oriented review criteria
- `references/artifact-matrix.md`: which artifacts are required or optional
- `references/skill-packaging.md`: packaging guidance for local, Git, and release contexts
