# Self-Learner — Project Definition

> **Status:** Foundation / Product Definition  
> **Document role:** Primary project map and current product specification  
> **Last updated:** 2026-09-19

---

## 1. Project Overview

**Self-Learner** is a project-based learning platform designed for people with little or no technical background.

The platform teaches programming from very basic concepts and gradually develops the learner's ability to build real software with the help of artificial intelligence.

The long-term goal is not simply to turn learners into JavaScript developers. The platform aims to help learners develop both:

- programming and software-development skills
- AI engineering and AI-assisted software-development skills

The intended outcome is a learner who can understand programming concepts, define software problems, work with AI effectively, and turn ideas into working software.

The platform should avoid unnecessary depth and complexity when that depth does not contribute to the learner's ability to understand, build, or reason about software.

---

## 2. Product Goals

### Primary goals

1. Teach programming to complete beginners.
2. Start from fundamental programming concepts.
3. Teach JavaScript as the initial programming language.
4. Progress from simple programming exercises to real software projects.
5. Teach learners how to use AI as part of software development.
6. Develop practical AI engineering skills alongside programming.
7. Enable learners to build:
   - websites
   - desktop applications
   - eventually mobile applications
8. Use practical projects to demonstrate and validate learning.
9. Give learners continuous feedback about their work.
10. Provide a visible sense of progression and achievement.

### Secondary / future goals

The platform may eventually become a multi-course platform where other users can create and publish their own courses.

Courses may eventually be monetized through:

- paid chapters
- free chapters
- discount codes
- other paid learning experiences

These are future product directions and are not required for the initial implementation.

---

## 3. Target Users

### 3.1 Beginner learners

People who want to learn programming at an introductory level and build simple software for themselves.

Examples include students and people with no previous programming experience.

### 3.2 Practical builders

People who want enough programming knowledge to use AI-assisted development to solve practical needs.

Examples include:

- shop owners
- freelancers
- self-employed people
- small business owners

They may want to build things such as:

- a website for their business
- an online shop
- a service website
- an internal business tool

### 3.3 Hobbyist builders

People who want to learn programming and build software because they enjoy it or have personal ideas they want to implement.

---

## 4. Learning Philosophy

The learning experience is based on the following principles.

### 4.1 Learn by building

Learning should eventually lead to working software.

Projects should be practical and meaningful rather than purely academic.

Examples may include:

- calculator
- todo list
- personal finance manager
- statistics dashboard
- simple online store
- photo repository
- movie website
- messaging platform

The exact project curriculum will be designed separately.

### 4.2 Fundamentals before AI-assisted development

Learners must personally implement lesson exercises without AI.

This is important because basic programming concepts need to become understandable through direct practice.

AI is primarily introduced as a development partner when learners begin building larger projects.

### 4.3 AI is part of the curriculum

AI is not only an optional external tool.

The course itself teaches learners how to use AI effectively for software development and AI engineering.

This includes skills such as:

- defining problems clearly
- communicating requirements to AI
- analyzing generated code
- debugging with AI
- reviewing code with AI
- iterating on software with AI
- using AI agents
- understanding the limits of AI-generated software

### 4.4 Progressive learning

A concept does not need to be completely explained the first time it appears.

A concept may be introduced simply and revisited later with additional complexity.

For example:

```text
Chapter 1
  Variables — basic usage

Chapter 2
  Variables — additional concepts

Later chapters
  Variables — advanced or applied usage
```

The curriculum should build knowledge progressively rather than attempting to explain every aspect of a concept in its first lesson.

### 4.5 Avoid unnecessary complexity

The curriculum should avoid deep or complex subjects unless they provide meaningful value for the intended learner and their ability to build and understand software.

---

## 5. Learning Structure

The course has four primary levels of educational structure:

```text
Course
  └── Level
       └── Chapter
            └── Lesson
                 └── Exercise
```

Projects exist at two levels:

```text
Chapter Project
Level Project
```

---

## 6. Level

A **Level** is a group of related chapters.

The number of chapters in a level is not fixed.

The curriculum designer determines the appropriate number of chapters based on the concepts and projects that belong together.

A level ends with an optional larger project.

Completing all required chapter projects allows the learner to progress to the next level.

The optional Level Project is separate from level completion and is primarily used to earn a star.

---

## 7. Chapter

A **Chapter** contains multiple lessons and ends with a required Chapter Project.

```text
Chapter
  ├── Lesson
  ├── Lesson
  ├── Lesson
  └── Chapter Project
```

The Chapter Project must be completed and approved before the next chapter becomes available.

A chapter therefore has two important states:

- learning progress through its lessons
- project completion

### Chapter completion

A chapter is considered completed when:

1. The required exercises in its lessons have been completed.
2. Its Chapter Project has been submitted.
3. The project has received a passing result.

---

## 8. Lesson

A **Lesson** is the smallest educational unit.

A lesson should normally require approximately **5–10 minutes** to learn.

A lesson contains:

1. explanation of the concept
2. examples
3. summary
4. one or more exercises

A lesson should focus on a clearly defined concept or small group of closely related concepts.

### Lesson prerequisites

Lessons within a chapter may depend on other lessons.

For example:

```text
Lesson 4
  └── depends on concepts from Lesson 2
```

These relationships should be explicitly defined and communicated to the learner.

For the initial course model, lesson relationships are primarily important within the same chapter.

---

## 9. Exercise

Every lesson contains at least one exercise.

An exercise exists to reinforce the concepts taught by that lesson.

### Exercise rules

An exercise:

- should be limited to concepts covered by its lesson
- should not require a new concept that the learner has not been taught
- should be simple enough for the learner to solve from the lesson
- should normally be completed without AI assistance

Examples include:

- writing one or more functions
- producing a specific output
- implementing a simple component
- applying a recently learned programming concept

### Exercise quantity

A lesson may contain two or three exercises.

The first exercise is required.

Additional exercises may be optional and can provide progressively more practice.

Example:

```text
Exercise 1 — Required
Exercise 2 — Optional
Exercise 3 — Optional
```

Completing the required exercise is sufficient to continue through the learning path.

### Exercise completion

Lesson exercises do not act as progression gates between lessons.

A learner may read later lessons without completing the previous lesson's exercise.

However, all required exercises within a chapter must be completed before the Chapter Project can be started.

---

## 10. Exercise Review

Exercises are reviewed automatically using AI.

The purpose of this review is feedback, not progression blocking.

The learner should complete the exercise without AI first.

After submission, the system may provide qualitative feedback such as:

- Excellent
- Very Good
- Good
- Average
- Needs More Practice
- Weak

The review should help the learner understand the quality of their work.

The review does not prevent the learner from continuing to the next lesson.

The platform may also provide a correct/sample solution so that the learner can compare their implementation with an expected solution.

Another intended learning skill is teaching the learner how to ask AI to analyze their own solution.

For example, the learner may ask AI to compare their code with the exercise requirements without immediately generating the solution for them.

---

## 11. Chapter Project

A **Chapter Project** is a practical project completed at the end of a chapter.

It is required.

The project should incorporate the important concepts taught in the chapter.

The difficulty should be appropriate for the learner's current level.

Early chapter projects may be very simple, while later projects become progressively more complex.

### AI-assisted development

Chapter Projects are intended to be developed with AI assistance.

The learner should practice turning a problem definition and requirements into working software with AI.

The important skill is not merely generating code. It is defining the problem correctly, understanding the requirements, directing AI, checking the result, and iterating.

### Submission

The learner submits the project through its Git repository.

The project should be reviewable from the submitted repository and any required links or artifacts.

### Review

A Chapter Project can be reviewed through:

- automated AI review
- manual review by an administrator

For automated review, the project contains a review specification/prompt describing:

- project requirements
- expected behavior
- evaluation criteria
- relevant constraints

The AI review produces:

- score from 0 to 100
- identified problems
- suggestions for improvement
- other useful feedback

### Passing threshold

The current initial target is:

```text
70 / 100
```

A score of 70 or higher passes the Chapter Project.

This threshold is configurable and may be revised after the curriculum and review system are validated.

If the score is below the threshold, the learner may retry the project.

There is currently no retry limit.

### Chapter progression

```text
Required lesson exercises completed
        +
Chapter Project passed
        ↓
Chapter completed
        ↓
Next Chapter unlocked
```

---

## 12. Level Completion

A level consists of multiple chapters.

A learner can progress to the next level after completing the required Chapter Projects of all chapters in the current level.

The Level Project is not required for progression.

Therefore:

```text
All Chapter Projects passed
        ↓
Level completed
        ↓
Next Level available
```

while:

```text
Level Project
        ↓
Optional
```

---

## 13. Level Project

A **Level Project** is an optional larger project associated with the end of a level.

It can combine concepts from:

- the current level
- previous levels

The project should be significantly more complete than a typical Chapter Project.

Where appropriate, it may require a complete software solution involving:

- frontend
- backend
- database

The project should solve a practical problem.

For example, a full Todo application could include:

```text
Frontend
Backend
Database
```

rather than being only a frontend interface.

### Level Project submission

The learner submits links to the relevant Git repositories or project components.

### Level Project review

The same two review modes are supported:

- automated AI review
- manual administrator review

The AI review is based on a detailed project specification and evaluation criteria.

The review produces:

- score from 0 to 100
- identified problems
- suggestions
- additional feedback

The current initial target threshold is:

```text
80 / 100
```

This threshold is configurable and may be revised later.

### Retry

If the project does not reach the passing threshold, the learner may revise and resubmit it.

There is currently no retry limit.

### Star

A learner receives a star when their Level Project passes.

Important distinction:

```text
Level completion != Star
```

A learner may complete a level and unlock the next level without receiving a star.

A star is specifically earned by successfully completing the optional Level Project.

---

## 14. Progression Model

The progression model is:

```text
Course
  ↓
Level
  ↓
Chapter
  ↓
Lessons
  ↓
Required Exercises
  ↓
Chapter Project
  ↓
Chapter Completed
  ↓
Next Chapter
  ↓
All Chapters Completed
  ↓
Level Completed
  ↓
Next Level
```

Separately:

```text
Level Project
  ↓
Review
  ↓
Passing Score
  ↓
Star
```

---

## 15. Retry Policy

For the initial product:

- lesson exercises can be attempted as needed
- Chapter Projects can be retried without a fixed limit
- Level Projects can be retried without a fixed limit

The exact retry UX and attempt history model will be defined during system design.

---

## 16. Course Content Model

The initial course is based on **JavaScript**.

The intended learning path eventually progresses toward:

```text
JavaScript
    ↓
Web Development
    ↓
Desktop Applications
    ↓
Mobile Applications
```

The exact technologies, frameworks, libraries, and curriculum order are not yet finalized.

The course should prioritize transferable programming concepts before introducing framework-specific complexity.

---

## 17. Gamification

The learning experience should include a visual progression system to increase motivation and make learning progress tangible.

The initial concept is a visual journey or road.

The learner is represented by a character whose appearance and equipment evolve as the learner progresses.

For example:

```text
Early learner
  ↓
Primitive character
  ↓
More knowledge
  ↓
New equipment
  ↓
More advanced character
  ↓
Advanced learner
  ↓
AI Engineer
```

Potential progression signals include:

- completed lessons
- completed chapters
- completed levels
- stars
- project milestones

The exact visual design, game mechanics, character system, rewards, and progression rules are not yet finalized.

---

## 18. Course Access and Monetization

The platform is intended to support paid educational content.

The current product direction is:

- chapters are paid by default
- individual chapters or content may be free
- discount codes may be supported

Additional monetization may be introduced later.

Future versions may also allow users to create and publish courses that other users can purchase or access.

Monetization and marketplace functionality are future product directions and should not unnecessarily complicate the initial MVP.

---

## 19. Future Course Marketplace

A future version of the platform may allow users to become course creators.

Potential model:

```text
Course Creator
      ↓
Create Course
      ↓
Publish Course
      ↓
Other Users
      ↓
Enroll / Purchase
      ↓
Complete Course
```

This implies that the long-term platform may contain:

- official courses
- community-created courses
- course publishing
- course discovery
- course purchasing
- creator functionality

The marketplace is not part of the initial MVP unless explicitly added later.

---

## 20. High-Level Product Components

The final platform is expected to contain at least the following conceptual areas:

```text
Authentication
User Profile
Course Catalog
Course Content
Learning Progress
Lessons
Exercises
Exercise Review
Chapter Projects
Project Submission
AI Project Review
Manual Project Review
Level Projects
Stars / Achievements
Gamification
Git Repository Integration
Administration
```

Potential future components include:

```text
Payments
Discount Codes
Course Marketplace
Course Creator Tools
Creator Revenue
Advanced AI Agents
```

The technical architecture for these components will be defined separately.

---

## 21. Project-Based AI Workflow

Projects should teach a repeatable AI-assisted development workflow.

The intended high-level process is:

```text
Understand the problem
        ↓
Define requirements
        ↓
Plan the solution
        ↓
Work with AI
        ↓
Implement
        ↓
Run and test
        ↓
Analyze the result
        ↓
Fix problems
        ↓
Submit
        ↓
Receive review
        ↓
Iterate if necessary
```

The platform should gradually teach learners to become less dependent on blindly accepting AI output and more capable of evaluating and directing AI.

---

## 22. Project Review Model

The project review system should support two review modes.

### Automated review

```text
Project Requirements
        +
Evaluation Criteria
        +
Submitted Project
        ↓
AI Agent
        ↓
Score
Feedback
Problems
Suggestions
```

### Manual review

```text
Submitted Project
        ↓
Administrator
        ↓
Score
Feedback
Problems
Suggestions
```

Both review paths should ultimately produce a consistent review result that can be used by the progression system.

The detailed review architecture and security model are TBD.

---

## 23. Project Knowledge System

Documentation is a first-class part of this repository.

Documentation is not an afterthought.

The project will use a structured **Project Knowledge System** so that humans and AI agents can understand the current state of the project without repeatedly reading the entire repository.

### Core principle

Documentation should describe the current system:

- what it is
- why it exists
- how it behaves
- what its responsibilities are
- what it depends on
- what constraints apply

Historical information should not be stored unless it is necessary to understand the current system.

### Documentation granularity

Documentation is organized around functional areas and responsibilities rather than individual files.

One documentation file may describe a directory containing many source files.

A separate Markdown file should only be created when the area has enough conceptual complexity to justify it.

### Documentation graph

Documents should reference related documents where useful.

Conceptually:

```text
PROJECT.md
    ↓
Architecture
    ↓
Feature Documentation
    ↓
Implementation
```

The documentation graph should make it possible to navigate from high-level project goals to the relevant implementation area.

### Documentation update rule

When a feature or architectural area changes, its documentation must be reviewed and updated if the change affects the documented behavior, responsibilities, structure, rules, contracts, or dependencies.

---

## 24. PROJECT.md Role

`PROJECT.md` is the primary entry point for understanding the repository.

It should contain high-level project information and point toward more detailed documentation.

It should not become a dump of every implementation detail.

The intended navigation model is:

```text
PROJECT.md
    ↓
Relevant documentation
    ↓
Relevant source code
    ↓
Relevant tests
```

---

## 25. AI Agent Development

The repository is intended to be usable by an AI coding agent connected directly to the Git repository.

The agent should operate using the repository's documentation and development rules rather than relying on conversation history.

The intended workflow is:

```text
Task / Issue
    ↓
Read PROJECT.md
    ↓
Find relevant documentation
    ↓
Understand current behavior
    ↓
Inspect relevant code
    ↓
Plan change
    ↓
Modify code
    ↓
Update tests
    ↓
Update documentation when required
    ↓
Run validation
    ↓
Commit / Pull Request
```

The exact AI agent will be selected during the project foundation phase.

Potential tools may include AI coding agents such as Claude Code, Cursor, Jules, or another suitable repository-connected agent.

The selection should be based on current capabilities, GitHub integration, repository access, testing/terminal capabilities, automation, and control/security requirements.

---

## 26. Testing Strategy

Testing is a required part of the project.

The project should gradually introduce appropriate levels of testing, including where useful:

```text
Unit Tests
Component / Integration Tests
End-to-End Tests
```

Tests should protect important behavior and provide confidence for automated development.

The exact testing framework, coverage expectations, test organization, and testing policy are TBD and will be defined during the technical foundation phase.

---

## 27. CI/CD

CI/CD is a required part of the project.

The repository should automatically validate changes through a CI pipeline.

The intended high-level flow is:

```text
Push / Pull Request
        ↓
Install dependencies
        ↓
Lint
        ↓
Type checking
        ↓
Tests
        ↓
Build
        ↓
Additional validation
        ↓
Deployment
```

The exact pipeline and deployment strategy are TBD.

CI/CD should eventually work together with the AI agent so that automated changes are validated before being accepted.

---

## 28. Development Principles

The project should follow these principles:

1. Keep the product understandable.
2. Prefer simple solutions over unnecessary abstraction.
3. Build incrementally.
4. Keep documentation synchronized with the implementation.
5. Use practical projects to validate learning.
6. Do not use AI to replace fundamental programming practice.
7. Use AI deliberately for larger project development.
8. Make important behavior testable.
9. Automate repetitive validation.
10. Keep AI agents constrained by explicit repository rules.
11. Avoid premature architecture decisions.
12. Clearly mark undecided requirements as TBD rather than guessing.
13. Preserve a clear distinction between:
    - lesson learning
    - exercise practice
    - chapter completion
    - level completion
    - star achievement
14. Prefer small, verifiable changes.
15. Treat the repository documentation as part of the project itself.

---

## 29. Current Product Decisions

The following decisions are currently established:

| Area | Current decision |
|---|---|
| Initial programming language | JavaScript |
| Primary learner | Beginner / non-technical user |
| Learning model | Course → Level → Chapter → Lesson |
| Lesson duration | Approximately 5–10 minutes |
| Lesson exercise | Required exercise + optional additional exercises |
| Lesson exercise AI use | Learner should solve without AI |
| Exercise review | AI feedback |
| Exercise review as progression gate | No |
| Chapter project | Required |
| Chapter project AI use | AI-assisted |
| Chapter project review | AI or manual |
| Chapter project passing target | 70/100 initially |
| Level project | Optional |
| Level project scope | Larger, potentially full-stack |
| Level project review | AI or manual |
| Level project passing target | 80/100 initially |
| Level project retry | Unlimited initially |
| Star | Earned by passing Level Project |
| Level progression | Requires all Chapter Projects |
| Chapter progression | Requires Chapter Project |
| Lesson progression | Does not require previous exercise |
| Curriculum style | Progressive / revisiting concepts |
| Gamification | Planned |
| AI coding agent | Required future integration |
| Testing | Required |
| CI/CD | Required |
| Documentation system | Required |
| Course marketplace | Future direction |
| Monetization | Future direction |

---

## 30. Open / TBD Decisions

The following are intentionally not finalized yet.

### Curriculum

- Exact number of levels
- Exact number of chapters per level
- Exact lesson sequence
- Exact projects
- Exact technology progression
- Exact desktop application technology
- Exact mobile application technology
- AI engineering curriculum
- Definition of advanced curriculum milestones

### Review

- Exact AI review architecture
- AI review model/provider
- Review prompt structure
- Review security and sandboxing
- Whether AI review and manual review use exactly the same scoring rubric
- Final passing thresholds
- Score calculation rules
- Handling ambiguous or incomplete submissions

### Technical architecture

- Frontend framework and version
- Backend technology
- Database
- Authentication system
- Hosting
- File/object storage
- GitHub integration architecture
- AI provider(s)
- AI agent infrastructure

### Testing

- Testing frameworks
- Required test types by feature
- Coverage expectations
- E2E infrastructure
- Test data strategy

### CI/CD

- CI provider
- Deployment provider
- Environments
- Release strategy
- Production deployment rules

### Gamification

- Character system
- Visual progression
- Reward types
- Star mechanics beyond the current Level Project rule
- Achievements
- Road/map design

### Monetization

- Payment provider
- Pricing model
- Chapter/course purchase model
- Discount code rules
- Creator revenue model
- Marketplace policies

---

## 31. Initial Development Philosophy

The project will be developed in small, explicit milestones.

Before implementing a significant feature:

1. Identify the relevant product requirement.
2. Read the relevant documentation.
3. Identify affected areas.
4. Inspect the relevant code.
5. Define the intended change.
6. Implement the smallest appropriate solution.
7. Add or update tests.
8. Update affected documentation.
9. Run automated validation.
10. Review the resulting state.

The project should not rely on the conversational memory of a developer or AI agent as its primary source of project knowledge.

The repository itself should contain the knowledge necessary to continue development.

---

## 32. Initial Foundation Milestones

The first development phase should establish the project foundation before building the educational product itself.

Suggested order:

```text
1. Project Knowledge System
2. Development / AI Agent rules
3. Technology stack selection
4. Repository structure
5. Application foundation
6. Testing foundation
7. CI/CD foundation
8. Authentication foundation
9. Course domain model
10. First learning flow
```

The exact implementation order may change after technical investigation.

---

## 33. Documentation Map

The documentation system will evolve as the project grows.

Expected high-level documentation areas include:

```text
PROJECT.md
    ↓
docs/
    ├── architecture.md
    ├── current-state.md
    └── ...
```

Feature-specific documentation should live near the functional area it describes where practical.

The documentation structure is expected to grow with the system rather than being fully designed upfront.

---

## 34. Definition of Success

The initial product should eventually demonstrate that a complete beginner can:

```text
Start with no programming knowledge
        ↓
Learn programming fundamentals
        ↓
Complete exercises without AI
        ↓
Build increasingly practical projects with AI
        ↓
Use Git and a repository
        ↓
Submit working projects
        ↓
Receive automated or human feedback
        ↓
Improve and retry
        ↓
Complete levels
        ↓
Earn stars through larger projects
        ↓
Build increasingly complete software
```

The long-term success criterion is not simply completion of lessons.

The goal is to develop learners who can understand software problems and use programming knowledge plus AI effectively to build real solutions.

---

## 35. Document Maintenance Rule

This document represents the current high-level product definition.

When a major product decision changes, `PROJECT.md` must be updated so that it continues to represent the current state of the project.

Detailed implementation information should generally be moved into specialized documentation rather than expanding this file indefinitely.

`PROJECT.md` should remain a high-level map, not a complete implementation manual.
