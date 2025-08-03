---
tags:
  - git
  - doumentation
version: "3"
---
## Production Branch

The Production Branch is the primary production-ready branch containing stable, tested code suitable for deployment.

**Branch Name:** `master` / `main`

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

Release branches facilitate the preparation for releases. Code from the relevant feature branches should be merged into a release branch for testing and validation. Once validated, the release branch should be merged into the `dev` branch for final release. This is only valid if we have staging environment. This is optional.

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

___
## Diagram
This diagram illustrates the flow and interaction between different branches, including feature, hotfix, release, development, and production branches.

![[gitflow.png]]

___

## General Guidelines
###  **Branching**  
- **Branch Creation:** Always create branches from the stable `dev` branch, except for hotfix branches, which are created from `master`.  
- **Branch Scope:** Keep branches small and focused on a single task or fix.  
- **Branch Cleanup:** Delete branches after merging to keep the repository clean.  

### **Commit Messages**  
- **Message Format:** Use the following format: `<type>: <subject>`  
- **Message Clarity:** Write clear, concise commit messages in the present tense that complete the sentence: "This commit will...".  

#### **Commit Types:**  

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

### **Tagging**  
- **Versioning:** Use semantic versioning (`MAJOR.MINOR.PATCH`).  
- **Tagging Convention:** Use tags like `v1.0.0`.  
- **Release Tags:** Tag releases after merging back to the `dev` branch and completing testing.  
### **Merging** 
- **Pull Latest Changes:** Before merging, ensure the latest changes from `dev` or `master` (for hotfixes) are pulled.  
- **Merge Process:**  
  1. **Fetch and update `dev` or `master`**  
  2. **Switch to the feature branch and update it**  
     - If conflicts occur, resolve them and commit:  
  3. **Push feature branch and create a Pull Request (PR)**  
  4. **Create PR and request review**  
     - Go to GitHub/GitLab/Bitbucket.  
     - Open a new PR targeting `dev` (`master` for hotfixes).  
     - Assign reviewers, add a description, and reference related issues.  
  5. **Merge PR after approval**  
     - Use **Squash & Merge** for clean history if applicable.  
     - Delete the branch after merging.  
#### **Merge Best Practices**  
✅ Keep feature branches small and merge frequently to avoid conflicts.  
✅ Always pull the latest changes before merging.  
✅ Use **Squash & Merge** for feature branches to keep a clean commit history.  .  
✅ **Hotfixes** should go to `master`, then be merged back into `dev`.  

---

### ✅ Must-Have Extensions For Better Development process

1. **[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)**  
   Enforces consistent code style and catches linting errors using your project's `.eslintrc` config.

2. **[SonarLint](https://marketplace.visualstudio.com/items?itemName=sonarsource.sonarlint-vscode)**  
   Performs static analysis to detect bugs, code smells, and security vulnerabilities in real time.

3. **[Prettier - Code Formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)**  
   Automatically formats your code (JS/TS/JSON/HTML) on save to keep it clean and consistent.

3. **[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)**  
   Highlights spelling mistakes in comments, strings, and code to avoid minor errors in documentation and variables.

4. **[Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)**  
   Provides a visual graph of your Git repo history, great for understanding branches and commits at a glance.

6. **[npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)**  
   Auto-completes module names when importing packages from `node_modules`.

7. **[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)**  
   Auto-completes file paths when importing local files or assets.
---