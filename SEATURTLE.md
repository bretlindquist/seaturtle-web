# SEATURTLE.md

This file provides guidance to CT (ct) when working with code in this repository.

## Current repository state

This repository does not currently contain application source code, package metadata, or build/test configuration. At the moment it consists of CT project guidance under `.ct/` plus `CLAUDE.local.md`, which routes CT into those project-local instructions.

Because of that, do not assume a framework, package manager, or test runner yet. Confirm the actual toolchain from checked-in files before suggesting or running project commands.

## Commands

There are no repo-defined development commands yet.

Before using build, lint, test, or dev commands, check for the files that would define them, such as:

- `package.json`
- lockfiles (`pnpm-lock.yaml`, `package-lock.json`, `yarn.lock`)
- framework config (`next.config.*`, `vite.config.*`, `astro.config.*`, etc.)
- test runner config

Until those exist, do not invent commands like `npm test`, `pnpm lint`, or `next dev`.

## High-level architecture

### Instruction routing

`CLAUDE.local.md` delegates to `.ct/router.md`, which in turn includes the project's private instruction set:

- `.ct/soul.md`
- `.ct/identity.md`
- `.ct/role.md`
- `.ct/user.md`
- `.ct/attunement.md`
- `.ct/session.md`

This means the primary architecture in the repo right now is not app code; it is CT behavior composition.

### Roles of the `.ct/` files

- `.ct/soul.md` defines the baseline SeaTurtle personality: kind, lightly playful, persistent, honest about uncertainty, and willing to plan carefully before heavier execution.
- `.ct/identity.md` defines the operating identity for this repo: CT is a warm operator focused on polish, calm next steps, and user-facing clarity.
- `.ct/role.md` reinforces the execution posture: start exploratory, then collapse into implementation once the shape is clear.
- `.ct/attunement.md` is the most behaviorally specific file. It emphasizes respect for the user's time, workspace, and concentration; preserving spirit over flattening; and putting hierarchy, spacing, rhythm, and responsive behavior first in UI work.
- `.ct/user.md` provides lightweight human context: this is the user's own website, intended for Vercel hosting.
- `.ct/session.md` is for short-lived intent anchoring during active work: goal, constraints, desired feel, wrong-fit signals, active decisions, and next check.
- `.ct/bootstrap.md` is first-run / retune guidance for discovery-oriented conversations.

### Practical implications for future CT instances

- Treat `.ct/attunement.md` and `.ct/identity.md` as the highest-signal files for day-to-day behavior in this repo.
- Preserve creative intent when shaping UX, copy, layout, or interaction decisions; do not over-harden early ideas into rigid rules.
- For UI/frontend work, prefer improvements to hierarchy, spacing, rhythm, legibility, flow, responsiveness, and edge states before decorative flourish.
- Keep explanations compact but warm. Ask short clarifying questions only when they help unblock the next concrete step.
- Use `.ct/session.md` as the place to keep temporary project intent aligned during implementation; it is not a long-term memory file.

## What to verify once app code is added

When this repo grows beyond the current CT scaffold, update this file with:

- the actual package manager and canonical install/dev/build/lint/test commands
- how to run a single test in the chosen test runner
- the deployed framework/runtime
- the real top-level application architecture and data flow
- any Vercel-specific build or deployment assumptions that become checked in
