
# Repository Structure Specification

> **Status:** Draft / Pending Implementation
> **Document role:** Directory map and navigation guide for developers and AI agents
> **Last updated:** 2026-09-23

---

## 1. Root Directory Structure

```text
self-learner/
├── .github/                  # CI/CD pipelines, workflows, and PR templates
│   └── workflows/
├── docs/                     # Project knowledge base and architecture docs
│   ├── architecture/         # Tech stack, repo structure, DB design
│   │   ├── stack.md
│   │   └── repository-structure.md
│   └── current-state.md      # Active development status
├── src/
│   ├── app/                  # Next.js App Router (pages, layouts, API routes)
│   ├── components/           # Shared UI components
│   │   └── components.md     # Directory index
│   ├── db/                   # Drizzle schema, migrations, and DB client connection
│   │   ├── schema/           # Entity schemas (users, courses, submissions)
│   │   └── db.md
│   ├── features/             # Domain-driven feature modules
│   │   ├── auth/             # Authentication logic
│   │   ├── course/           # Course, level, chapter, and lesson structures
│   │   ├── exercises/        # Automated exercise submission & AI grading
│   │   └── projects/         # Chapter & Level project submission workflows
│   ├── lib/                  # Shared utilities, AI SDK clients, helper functions
│   └── types/                # Shared global TypeScript types
├── AGENTS.md                 # Operating contract for AI coding agents
├── PROJECT.md                # Primary product specification and project map
└── package.json
```
