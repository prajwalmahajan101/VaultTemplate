---
tags:
  - git
  - doumentation
  - study_notes
version: "1"
---
## Production Branch

The Production Branch is the primary production-ready branch containing stable, tested code suitable for deployment.

**Branch Name:** `master` / `main`

**Create From:** Final validated release from the `dev` branch.

**When to Create:** Only for production releases after thorough testing.

---

## Development Branch

The Development Branch (`dev`) serves as the main working branch where stable and thoroughly tested code resides. All features and bug fixes must undergo comprehensive code review and testing before merging into this branch.

**Branch Name:** `dev`

**Create From:** Initial repository setup or after creating a production release branch.

**When to Create:** At the start of a new project or after a production release.

---

## Feature Branches

Feature branches are created for developing new features that are not yet part of the stable codebase. Each feature branch should originate from the stable `dev` branch and should be merged back after completion and successful review.

**Naming Convention:**
`feature/{feature_name}`

**Examples:**
- `feature/mqtt_publisher`
- `feature/mission_plan`

**Create From:** `dev`

**When to Create:** When starting development of a new feature.

**Key Guidelines:**
- Ensure features are independently functional.
- Maintain small, focused branches for easier review and testing.
- Delete feature branches after merging.

---

## Bug Fix Branches

Bug fix branches address specific bugs identified in the codebase. These branches should be created from the stable `dev` branch. Upon resolving and validating the bug fix, the branch must be merged back into `dev`.

**Naming Convention:**
`bugfix/{ticket_id_or_bug_description}`

**Examples:**
- `bugfix/QF_212`
- `bugfix/side_filter_issue`

**Create From:** `dev`

**When to Create:** When a bug is identified that needs fixing.

**Key Guidelines:**
- Clearly describe the bug being fixed.
- Keep bug-fix branches minimal, focusing only on the identified issue.
- Ensure proper regression testing before merging.
- Delete bug fix branches once merged and tested.

---

## Hotfix Branches

Hotfix branches are created for critical issues or bugs that need immediate attention and cannot wait for the next release cycle. These branches should be created from the `master` / `main` branch and merged back into both `master` and `dev` after the fix.

**Naming Convention:**
`hotfix/{ticket_id_or_bug_description}`

**Examples:**
- `hotfix/payment_gateway_issue`
- `hotfix/security_patch`

**Create From:** `master` / `main`

**When to Create:** For urgent production issues requiring immediate resolution.

**Key Guidelines:**
- Address only the critical issue at hand.
- Perform targeted testing specific to the fix.
- Ensure both `master` and `dev` branches reflect the fix after merging.

---

## Release Branch (Staging)

Release branches facilitate the preparation for releases. Code from the relevant feature branches should be merged into a release branch for testing and validation. Once validated, the release branch should be merged into the `dev` branch for final release.

**Naming Convention:**
`release/{version_number}`

**Create From:** `dev`

**When to Create:** When preparing for a version release.

**Steps:**
1. Create a new branch from `dev` with the correct naming convention.
2. Merge the required feature branches into this branch.
3. Perform comprehensive testing and validation.
4. Merge it back into the `dev` branch.
5. Tag the commit with the release version (e.g., `2.1.1`).

**Key Guidelines:**
- Ensure all merged features and bug fixes are complete and tested.
- Follow semantic versioning for tagging.

---
## Diagram
This diagram illustrates the flow and interaction between different branches, including feature, bugfix, hotfix, release, development, and production branches.

![[Pasted image 20250115113211.png]]
___
## General Guidelines
### Branching
- **Branch Creation:** Always create branches from the stable `dev` branch, except for hotfix branches which are created from `master`.
- **Branch Scope:** Keep branches small and focused on a single task or fix.
- **Branch Cleanup:** Delete branches after merging to keep the repository clean.
### Commit Messages
- **Message Format:** Use the following format: `<type>: <subject>`
- **Message Clarity:** Write clear, concise commit messages in the present tense that complete the sentence: "This commit will...".

**Commit Types:**

| Type       | Description                                        |
| ---------- | -------------------------------------------------- |
| `feat`     | Introduces a new feature or enhancement.           |
| `fix`      | Fixes a bug or error in the codebase.              |
| `chore`    | Routine maintenance tasks or tooling improvements. |
| `docs`     | Updates to documentation only.                     |
| `test`     | Adding or modifying tests without changing code.   |
| `refactor` | Code restructuring without changing functionality. |
| `hotfix`   | Critical fix for production issues.                |

- **Examples:**
	- `feat: add MQTT publisher support` (This commit will add MQTT publisher support)
	- `fix: resolve side filter issue` (This commit will resolve the side filter issue)
- **Atomic Commits:** Ensure commits represent a single, logical change.
- **Commit Length:** Keep commit messages concise but descriptive.
- **Referencing:** Reference related tickets or issues when applicable.
### Tagging
- **Versioning:** Use semantic versioning (`MAJOR.MINOR.PATCH`).
- **Tagging Convention:** Use tags like `v1.0.0`.
- **Release Tags:** Tag releases after merging back to the `dev` branch and completing testing.
***Notes***:  All changes must be reviewed and approved before merging. Ensure adequate testing, including unit, integration, and regression tests. 
___
