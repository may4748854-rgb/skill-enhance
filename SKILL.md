---
name: skill-enhance
description: Create, enhance, harden, and prepare skills for release. Use this skill whenever the user wants to build a new skill, strengthen an existing skill, improve trigger accuracy, add README or eval materials, review whether a skill can reliably guide an LLM, or decide if a skill is ready to publish. Also use it when the user wants to improve a locally available skill, including a self-created skill, a hub-downloaded skill, a skill stored by Codex or Claude Code, or skill-enhance itself. When local skill modification is requested, verify that the target can actually be accessed and edited in the current environment; if it cannot, say so clearly. If local editing is possible, confirm the target path and the user's edit intent before making changes. Do not use it for ordinary copy editing, unrelated code refactors, or simple skill installation tasks.
---

# Skill Enhance

Use this skill to produce high-quality skills that are not only structurally valid, but also clear, triggerable, executable, testable, and publishable.

This skill is intentionally heavier than a lightweight skill scaffolder. Favor quality over speed when the user is creating or enhancing a skill that other agents or users will depend on.

## Trigger Boundary

Use this skill when the task is primarily about skill quality, including:

- creating a new skill from scratch
- enhancing an existing skill
- improving a locally stored or installed skill
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
7. local edit safety

## Task Modes

Classify the request into one primary mode:

1. **New skill creation**
2. **Existing skill enhancement**
3. **Local skill modification**
4. **Trigger optimization**
5. **Artifact completion**
6. **Quality review**
7. **Publish-readiness review**

If several modes are present, use this sequence:

1. summarize the current state and target
2. identify the quality gaps
3. decide what the skill must do and when it should trigger
4. if local modification is requested, verify access and confirm the target path
5. define or rewrite the output contract
6. produce or revise the package artifacts
7. run the review gates
8. state whether the skill is publish-ready

## Workflow

### 1. Capture the real objective

Before writing anything, determine:

- is the user creating a new skill or enhancing an existing one
- is the user asking to modify a local skill package
- who the skill is for
- what user requests should trigger it
- what the skill must produce when triggered
- whether the target is project-local, shareable, or release-ready

If an existing skill already exists, read it first and extract:

- current capability
- current trigger wording
- bundled artifacts
- gaps or inconsistencies

### 1.5 Check local editability before modifying an existing local skill

If the request involves changing a locally available skill, do not jump straight into edits.

First determine:

- whether the target skill path is known
- whether the current environment can access that path
- whether the current environment can write to that path
- whether the user is asking for analysis only or actual modification

If the path is unclear, ask the user to confirm the target path or clearly identify the skill.

If the path is known but the environment cannot modify it, say so clearly and stop short of claiming the change can be applied.

If the path is writable, confirm the target path and edit intent before making changes.

Treat these as separate states:

- **analyzable but not editable**
- **editable after confirmation**
- **ready to modify now**

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

### 8. Handle local-skill modification safely

When the target is a local skill package, explicitly report:

- the target skill name
- the target path
- whether the path was user-provided or inferred
- whether the environment can edit it
- whether user confirmation was received before edits

Never silently modify a local installed skill on assumption alone.

## Output Contract

Default to this structure unless the user requests another format:

### 1. Task mode

State whether this is new creation, enhancement, local skill modification, trigger optimization, artifact completion, quality review, or publish-readiness review.

### 2. Current-state summary

Describe the current package or the requested target in 2-4 lines.

### 3. Local target status

If a local skill is involved, state:

- target skill
- target path
- whether the path is confirmed
- whether the environment appears able to modify it
- whether user confirmation is still required
If no local skill is involved, say that this section is not applicable.

### 4. Key quality gaps or design goals

List the highest-impact issues or goals.

### 5. Recommended changes

Describe what to create, rewrite, or add.

### 6. Artifact plan

State which files are required, optional, missing, or already strong.

### 7. Review findings

Summarize trigger quality, execution reliability, output-contract quality, and publish-readiness findings.

### 8. Validation

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

### Local Modification Check

Check whether:

- the target local skill is clearly identified
- the path is known or confirmed
- the environment appears able to edit it
- the user has confirmed the path and edit intent before modification
- the response clearly distinguishes analysis from applied edits

## Constraints

- Do not treat a valid frontmatter block as proof of a good skill.
- Do not produce a skill that only contains abstract theory.
- Do not skip trigger-boundary review when the skill is meant to be reused.
- Do not skip artifact completion if the user is aiming for release.
- Do not force heavyweight benchmarking when lightweight validation is enough.
- Do not claim publish readiness without checking docs, evals, and packaging materials.
- Do not claim a local skill was modified unless the target path was accessible and the user confirmed the edit.
- Do not infer write access from mere path existence.
- Do not silently edit a downloaded or installed local skill without path confirmation.

## References

- `references/trigger-design.md`: how to design strong trigger boundaries
- `references/output-contracts.md`: how to define reliable skill outputs
- `references/review-checklist.md`: quality review checklist for skill reliability
- `references/publish-readiness.md`: release-oriented review criteria
- `references/artifact-matrix.md`: which artifacts are required or optional
- `references/skill-packaging.md`: packaging guidance for local, Git, and release contexts
