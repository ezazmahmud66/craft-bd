# Contributing to Craft BD

This document defines the collaboration and contribution rules for the Craft BD project.

## 1. General Workflow

Every meaningful change should follow this workflow:

Issue → Branch → Development → Testing → Pull Request → Review → Merge

## 2. Issue Requirement

Before starting a significant task, create or reference a related GitHub Issue.

Examples:

- Feature development
- Bug fixing
- Requirement change
- Documentation update
- Refactoring

## 3. Branch Naming Convention

Branches should describe the work being performed.

Examples:

- `feature/customer-login`
- `feature/custom-order`
- `fix/order-status-validation`
- `docs/srs-update`
- `chore/repository-structure`

Do not create branches using only developer names.

## 4. Commit Message Convention

Use the following format:

`type: short description`

Common types:

- `feat` — new feature
- `fix` — bug fix
- `docs` — documentation
- `test` — testing
- `refactor` — code restructuring
- `chore` — project configuration or maintenance
- `style` — formatting changes
- `perf` — performance improvement

Examples:

- `feat: add customer registration`
- `fix: prevent duplicate product reviews`
- `docs: update custom order requirements`

## 5. Pull Request Rules

Do not push completed feature work directly to `main`.

Each significant change should be submitted through a Pull Request.

A Pull Request should include:

- What was changed
- Why the change was required
- Related Issue
- Testing performed
- Screenshots when applicable

## 6. Code Review

At least one other team member should review significant Pull Requests before merging whenever possible.

Reviewers should check:

- Requirement satisfaction
- Code correctness
- Security concerns
- Maintainability
- Testing
- Documentation impact

## 7. Definition of Done

A task is considered complete when:

- The required work is implemented
- Relevant tests pass
- Acceptance criteria are satisfied
- The change has been reviewed
- Required documentation is updated
- The change is merged into `main`

## 8. Security

Never commit:

- Passwords
- API keys
- Access tokens
- Private credentials
- `.env` files containing secrets

Secrets must be stored using appropriate environment configuration.

## 9. Documentation

Important requirement, architecture, database, security, API, and workflow decisions should be documented and version controlled.

## 10. Professional Conduct

Team members should:

- Communicate clearly
- Avoid undocumented changes
- Review others' work respectfully
- Keep commits focused
- Maintain traceability between requirements, Issues, code, and tests
