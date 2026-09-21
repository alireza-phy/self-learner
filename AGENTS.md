# AGENTS.md

> Repository-wide operating contract for AI coding agents.
>
> Applies to every AI agent working on this repository, including external agents and ChatGPT.

## 1. Purpose

This document defines how AI agents must work on the Self-Learner repository.

The repository is designed to be developed with AI assistance. Agents must not rely on conversational memory as their primary project knowledge.

The repository itself must provide enough structured information for an agent to:

1. understand the project,
2. locate the relevant functional area,
3. understand file responsibilities without opening every file,
4. identify affected documentation,
5. plan changes,
6. implement approved changes,
7. add and run tests,
8. validate the result,
9. prepare a Pull Request for human review.

Product requirements belong in `PROJECT.md` and relevant feature documentation. This document defines the AI development workflow.

---

## 2. Mandatory Starting Point

For every development task, bug fix, refactor, documentation request, or other repository change:

### Step 1 — Read `PROJECT.md`

Use `PROJECT.md` to understand:

- project purpose,
- product goals,
- product rules,
- major domain concepts,
- development principles,
- known constraints,
- known TBD decisions.

### Step 2 — Read `AGENTS.md`

Use this file to understand:

- repository navigation,
- documentation rules,
- development phases,
- testing rules,
- validation rules,
- Git workflow,
- human approval gates.

### Step 3 — Check for conflicts

If the requested task conflicts with an established project rule, requirement, architecture rule, or constraint:

1. do not silently override it,
2. identify the conflict,
3. explain the conflict,
4. propose the required documentation change,
5. wait for explicit human approval.

If approved:

1. update the governing documentation,
2. create the documentation commit,
3. continue with the approved workflow.

Do not modify project rules merely because another implementation is easier.

---

## 3. Documentation Is the Navigation Layer

Documentation is a first-class part of this repository.

Its purpose is not only to explain the project to humans, but also to reduce the amount of source code an AI agent must inspect.

Prefer:

```text
Documentation
    ↓
Relevant files
    ↓
Relevant code
```

instead of:

```text
Read every file
    ↓
Understand repository
```

The goal is to reduce token consumption, development latency, accidental changes, and confusion between unrelated implementations.

Correctness has priority over token reduction.

---

## 4. Documentation Hierarchy

The documentation system follows the repository hierarchy.

Typical structure:

```text
/
├── PROJECT.md
├── AGENTS.md
│
├── <root-area>/
│   ├── <area>.md
│   ├── <files>
│   │
│   └── <sub-area>/
│       ├── <sub-area>.md
│       └── <files>
```

The exact structure is determined by the actual project.

### `PROJECT.md`

Describes the project at the highest level:

- what it is,
- why it exists,
- who it is for,
- major product rules,
- major system areas,
- established decisions,
- TBD decisions.

It must remain high-level.

### `AGENTS.md`

Defines how AI agents work with the repository.

It does not replace feature documentation.

### Local area documentation

A Markdown file inside a functional or navigation area describes that area's responsibilities and provides a concise index of relevant files and subdirectories.

---

## 5. Documentation Coverage Rule

Not every directory requires a Markdown file simply because the directory exists.

Documentation is required when an area represents a meaningful:

- functional boundary,
- architectural boundary,
- reusable collection,
- navigation boundary.

However, a directory containing reusable files may need an index document even if it is not a complete subsystem.

For example:

```text
utils/
├── utils.md
├── formatDate.ts
├── formatCurrency.ts
├── parseApiError.ts
└── ...
```

`utils.md` should help an agent answer:

> Does this directory already contain something that can perform this task?

before opening every source file.

---

## 6. File Index Requirement

When a directory contains multiple relevant source files, its local documentation should maintain a concise file index.

The index should normally include:

- file name,
- responsibility,
- important public behavior,
- major consumers or dependencies when useful.

Example:

```text
| File | Responsibility |
|------|----------------|
| CourseCard.tsx | Displays a course summary |
| CourseProgress.tsx | Displays learner progress |
| CourseStatus.tsx | Displays course availability |
```

The index is a navigation aid, not an implementation manual.

If the index is insufficient to safely understand a candidate file, inspect that source file.

---

## 7. Documentation Chain

Documentation follows the repository hierarchy.

Example:

```text
PROJECT.md
    ↓
src/src.md
    ↓
src/features/features.md
    ↓
src/features/courses/courses.md
    ↓
src/features/courses/projects/projects.md
    ↓
ProjectReview.ts
```

A source change does not automatically require every parent document to change. The agent must evaluate impact.

For example, an internal implementation change may require only:

```text
ProjectReview.ts
    ↓
projects.md
```

A public feature behavior change may require:

```text
projects.md
    ↓
courses.md
```

A major product behavior change may also require:

```text
PROJECT.md
```

---

## 8. Documentation Synchronization Rule

Whenever a task changes any of the following, related documentation must be reviewed:

- component or module responsibility,
- public behavior,
- API contract,
- data model,
- dependency relationship,
- directory responsibility,
- file responsibility,
- architecture,
- workflow,
- business rule,
- configuration contract,
- testing strategy,
- security constraint,
- integration behavior.

Update documentation only when the documented current state is no longer accurate or new information is needed for future development.

Do not document trivial implementation details unnecessarily.

---

## 9. Documentation Is Not a Change Log

Documentation describes the current system.

Do not continuously append historical development logs to feature documentation.

Git is responsible for history. Documentation is responsible for the current system.

Historical context should be documented only when it is genuinely necessary to understand a current technical decision.

---

## 10. Documentation Must Not Hide Conflicts

Never change documentation merely to make an existing implementation appear correct.

Forbidden:

```text
Requirement
    ↓
Current code conflicts
    ↓
Change documentation to match code
```

Correct:

```text
Requirement
    ↓
Current documentation
    ↓
Current code
    ↓
Conflict
    ↓
Report conflict
    ↓
Human decision
    ↓
Update documentation if approved
    ↓
Implement approved change
```

---

## 11. Task Analysis Workflow

After reading `PROJECT.md` and `AGENTS.md`, identify the smallest relevant documentation path.

Do not scan the entire repository unless the task genuinely requires repository-wide understanding.

Preferred process:

```text
User requirement
    ↓
PROJECT.md
    ↓
AGENTS.md
    ↓
Identify affected root area
    ↓
Read local area documentation
    ↓
Use file index to identify candidate files
    ↓
Read only relevant source files
    ↓
Identify dependencies
    ↓
Inspect additional files only when necessary
```

---

## 12. Two-Phase Development Workflow

Development is divided into two major phases.

### Phase A — Documentation / Planning

No production code changes are made during this phase.

The agent must:

1. read `PROJECT.md`,
2. read `AGENTS.md`,
3. identify affected areas,
4. read relevant local documentation,
5. inspect relevant source code as necessary,
6. identify documentation that must change,
7. update only the necessary documentation,
8. create a documentation commit,
9. stop for human review.

Source code may be inspected during this phase. Source code must not be modified during this phase.

### Phase B — Implementation

After documentation approval, the agent may implement the approved change.

---

## 13. Documentation Commit

Documentation-only changes must be committed separately.

Recommended format:

```text
docs: update documentation for <task>
```

This commit must contain documentation changes only. It must not contain production code or test code.

After creating it:

```text
STOP
```

Wait for explicit human approval.

---

## 14. Human Approval Gate 1

The human reviews:

- whether the task was understood correctly,
- whether affected areas are correct,
- whether proposed behavior is correct,
- whether documentation changes are correct,
- whether anything important was missed.

If rejected:

1. do not implement,
2. apply the feedback to documentation,
3. create/update the documentation commit,
4. wait for approval again.

---

## 15. Implementation

After documentation approval, implement the approved change.

The agent may:

- create files,
- modify files,
- delete files when justified,
- create directories,
- install dependencies required by the task,
- add or modify source code,
- add or modify configuration,
- add required assets,
- download permitted assets into the repository when necessary.

The normal file-operation scope is the repository.

---

## 16. Code Scope

Modify only files required by the approved task.

If implementation reveals a materially larger scope:

1. stop,
2. explain the new impact,
3. update relevant documentation,
4. obtain human approval when the change is significant.

Do not silently expand task scope.

---

## 17. Tests Are Part of Implementation

Tests are part of implementation planning and implementation.

The agent must determine which tests are required while planning the change.

During implementation:

1. add or update production code,
2. add or update necessary tests,
3. keep production and test changes logically separate.

Tests must not be treated as an afterthought.

---

## 18. Separate Code and Test Commits

Production code and test code must be committed separately.

### Production implementation commit

Recommended format:

```text
feat: implement <task>
```

This commit contains production code and production configuration required by the implementation, plus directly required documentation when applicable.

It should not contain newly written test files or test-only changes unless an existing test must change for the production implementation to remain coherent.

### Test commit

Recommended format:

```text
test: add tests for <task>
```

This commit contains:

- new tests,
- test fixtures,
- test helpers,
- test-only configuration where appropriate.

The purpose is explicit human review:

```text
Commit 1 → What did the AI change in the product?
Commit 2 → How did the AI test those changes?
```

---

## 19. Implementation Review Gate

After creating the production implementation commit:

```text
STOP
```

Wait for explicit human approval.

The human reviews the implementation before final validation.

If rejected:

1. do not continue to final validation,
2. make the requested corrections,
3. update the implementation work,
4. wait for approval again.

---

## 20. Final Test and Validation Phase

After implementation and test work has been approved, perform final validation.

At minimum, when supported by the project:

```text
Tests
Lint
Type checking
Build
```

Additional validation may include:

- integration tests,
- end-to-end tests,
- formatting checks,
- static analysis,
- dependency checks,
- security checks,
- application-specific checks.

The exact commands belong to the project's technical configuration and documentation.

---

## 21. Validation Must Be Honest

Never claim that a check passed unless it actually ran successfully.

Use clear states:

```text
PASS
FAIL
NOT RUN
BLOCKED
```

If a check cannot run, report what was attempted, why it could not run, and what remains unverified.

Never treat `NOT RUN` or `BLOCKED` as `PASS`.

---

## 22. Pull Request

After implementation and validation succeed, prepare the final Pull Request.

The Pull Request should summarize:

- what changed,
- why it changed,
- documentation involved,
- tests added/changed,
- validation performed,
- known limitations,
- unresolved issues.

The Pull Request is the final review surface before merge.

---

## 23. Final Human Approval

The human must approve the Pull Request before merge.

The agent must not merge its own work unless an explicit future repository policy grants that permission.

Default workflow:

```text
Implementation
    ↓
Tests
    ↓
Validation
    ↓
Pull Request
    ↓
Human review
    ↓
Human approval
    ↓
Merge to main
```

---

## 24. Repository Boundaries

The agent's normal operating scope is the project repository.

The agent may create or modify project assets inside the repository when required.

Never commit:

- passwords,
- API keys,
- private tokens,
- credentials,
- private user data,
- production secrets.

Use the project's approved environment-variable or secret-management mechanism.

---

## 25. External Actions

Repository work may involve external services such as GitHub, AI providers, package registries, or deployment systems.

Distinguish between repository-local actions and external side effects.

External actions affecting production, real user data, billing, payments, external accounts, production databases, destructive infrastructure, secrets, or irreversible state require explicit authorization.

Technical capability is not equivalent to authorization.

---

## 26. Reuse Before Creating

Before creating a new utility, component, service, helper, hook, or reusable module:

1. read the relevant directory documentation,
2. search its file index,
3. identify existing candidates,
4. inspect the candidate source if necessary,
5. reuse or extend an appropriate implementation,
6. create a new file only when an existing implementation is unsuitable.

For directories such as `utils/`, `components/`, `hooks/`, and `services/`, the local Markdown index is the first search surface.

Do not read every source file unless the documentation is insufficient.

---

## 27. Avoid Unnecessary Refactoring

Do not refactor unrelated code while implementing a task.

A refactor is justified when it is:

- required for the requested feature,
- required to fix a directly related correctness issue,
- required by an established architecture contract,
- necessary to avoid duplication created by the implementation.

Unrelated refactors should be separate tasks.

---

## 28. Dependency Changes

Do not add a dependency merely because it makes a small task easier.

Before adding one:

1. inspect existing dependencies,
2. check whether the project already provides the capability,
3. determine whether the dependency is justified,
4. document the reason when it materially affects architecture or maintenance.

Dependency additions must be intentional.

---

## 29. Conflict Resolution

If information conflicts between:

```text
User requirement
PROJECT.md
AGENTS.md
Feature documentation
Source code
Tests
```

do not silently guess.

Identify whether the conflict is:

1. outdated documentation,
2. an implementation problem,
3. a requirement change,
4. an architectural conflict,
5. an ambiguity requiring human clarification.

If the resolution changes an established product or architecture decision, human approval is required.

---

## 30. When to Read More Code

The goal is not to minimize file reads at all costs. The goal is to minimize unnecessary file reads.

Read additional files when necessary to understand:

- dependencies,
- API contracts,
- shared types,
- public interfaces,
- side effects,
- data flow,
- test requirements,
- architecture constraints.

Documentation is a navigation aid, not a substitute for source inspection when source inspection is required for correctness.

---

## 31. When Documentation Is Insufficient

If local documentation does not provide enough information:

1. inspect relevant source code,
2. understand the actual behavior,
3. update documentation if the missing information is useful for future navigation,
4. continue if the change remains within approved scope.

Documentation should become progressively more useful as the project grows.

---

## 32. New Directory Rule

When creating a new directory, determine whether it represents:

- a functional boundary,
- an architectural boundary,
- a reusable collection,
- a meaningful navigation boundary.

If documentation is required, create its local Markdown documentation as part of the documentation phase.

The local document should explain:

1. directory responsibility,
2. important subdirectories,
3. important files,
4. relevant dependencies,
5. important rules or constraints,
6. where to look next.

---

## 33. New File Rule

When creating a new source file:

1. determine which directory documentation indexes it,
2. add it to that index when relevant to navigation,
3. describe its responsibility briefly,
4. avoid documenting obvious implementation details.

A relevant new file must not become invisible to future AI agents.

---

## 34. Removing or Renaming Files

When removing or renaming a file:

1. update the local documentation index,
2. update parent documentation when necessary,
3. inspect imports and usages,
4. update tests,
5. update architecture documentation if the system boundary changes.

---

## 35. Documentation Style

Documentation should be:

- concise,
- structured,
- factual,
- current,
- easy for AI agents to scan,
- easy for humans to review.

Prefer:

```text
File → Responsibility
Directory → Responsibility
Feature → Behavior
Dependency → Reason
```

Use tables, lists, headings, and small diagrams when they improve navigation.

Do not duplicate information across many documents unless the duplication serves a clear navigation purpose.

---

## 36. Source of Truth

Use this general model:

```text
Product definition
    → PROJECT.md

AI development rules
    → AGENTS.md

Functional behavior
    → Local feature documentation

File/directory navigation
    → Local directory documentation

Actual implementation
    → Source code

Expected behavior verification
    → Tests

Historical changes
    → Git
```

When these sources disagree, investigate the discrepancy rather than silently choosing one.

---

## 37. Required Task Report

After completing a task, the agent should be able to report:

```text
Task
- What was requested

Documentation
- What documentation was read
- What documentation changed

Implementation
- What production files changed

Tests
- What tests were added or changed

Validation
- Tests
- Lint
- Typecheck
- Build
- Other checks

Git
- Documentation commit
- Implementation commit
- Test commit
- Pull Request

Status
- Ready for human review
- Blocked
- Requires clarification
```

The exact presentation may vary, but the information should remain available.

---

## 38. Non-Negotiable Workflow

Default workflow:

```text
1. Read PROJECT.md
2. Read AGENTS.md
3. Identify relevant documentation
4. Read relevant documentation
5. Inspect relevant source code as necessary
6. Identify documentation changes
7. Update documentation only
8. Commit documentation changes
9. STOP — human approval
10. Implement approved changes
11. Add/update tests as part of implementation
12. Commit production code
13. Commit test changes separately
14. STOP — human review
15. Run final tests
16. Run validation
17. Create Pull Request
18. STOP — final human approval
19. Merge
```

This workflow is the default unless the human explicitly changes it.

---

## 39. Core Principle

The repository should become increasingly understandable to both humans and AI agents as it grows.

Every development cycle should improve one or more of:

```text
Code quality
Documentation quality
Test coverage
Automation
AI navigability
```

The project must not grow into a state where an AI agent needs to read the entire repository to make a small localized change.

The desired model is:

```text
Small task
    ↓
Small documentation path
    ↓
Small code path
    ↓
Small test path
    ↓
Small reviewable commits
    ↓
Predictable validation
```

This is the fundamental operating model of the Self-Learner repository.
