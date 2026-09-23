
# Technology Stack Selection

> **Status:** Draft / Pending Implementation
> **Document role:** Definitive specification for runtime, frameworks, database, and integrations
> **Last updated:** 2026-09-23

---

## 1. Overview

This document specifies the official technology choices for the Self-Learner platform. The choices prioritize end-to-end type safety, rapid iteration using TypeScript, simple deployment, and clean separation between web application delivery and untrusted code execution.

---

## 2. Core Architecture Stack

| Layer                         | Chosen Technology                      | Primary Purpose                                                                 |
| ----------------------------- | -------------------------------------- | ------------------------------------------------------------------------------- |
| **Language**            | TypeScript                             | Full-stack static typing across UI, API, schemas, and database ORM              |
| **Framework**           | Next.js (App Router)                   | Web application UI, Server Components, and API Route Handlers                   |
| **Styling & UI**        | Tailwind CSS                           | Component styling and responsive UI design                                      |
| **Database**            | PostgreSQL                             | Relational storage for users, courses, submissions, and progress                |
| **Database Hosting**    | Serverless Postgres (Neon / Supabase)  | Managed PostgreSQL with instant scaling and HTTP connections                    |
| **ORM / Query Builder** | Drizzle ORM                            | Type-safe database queries, schema migrations, and relational mapping           |
| **Validation**          | Zod                                    | Runtime type validation for API payloads, forms, and submission feedback        |
| **Authentication**      | Better Auth / Auth.js                  | OAuth integration (GitHub required for project submission), sessions, and roles |
| **State Management**    | React Query (TanStack Query) + Zustand | Client state management and server-data caching                                 |

---

## 3. Execution & AI Architecture (Phase 2 Integration)

- **AI Model Integration:** Vercel AI SDK or direct Google Gemini API for fast, structured JSON generation during exercise and project grading.
- **Code Execution / Sandboxing:** Submissions requiring execution will run in an isolated runtime (e.g., Docker container runner or micro-VM sandbox) separate from the primary web server to maintain security and avoid executing untrusted learner code on the core web application host.

---

## 4. Rationale

1. **Leveraging Existing Expertise:** The team brings strong React/Next.js/TypeScript experience, drastically reducing friction on full-stack web development.
2. **Unified Codebase:** Shared schemas between Drizzle ORM, Zod, and React components eliminate context switching and type mismatches.
3. **Decoupled Workflows:** Next.js handles user sessions, course rendering, and project state; dedicated external workers/lambdas will handle heavy background AI evaluation and code execution.
