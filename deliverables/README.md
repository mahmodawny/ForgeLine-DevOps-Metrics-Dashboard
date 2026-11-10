# ForgeLine DevOps Metrics Dashboard

## Contribution Guidelines

**Project:** ForgeLine DevOps Metrics Dashboard
**Purpose:** Establish consistent Software Configuration Management (SCM) practices and contribution workflows.

---

## 1. Project Overview

This project documents the development workflow and configuration management practices used by the ForgeLine engineering team.

It focuses on Git, GitHub, command-line operations, code reviews, debugging, and linting.

The objective is to maintain a controlled development process that protects the main branch and ensures reliable contributions.

## 2. Repository Structure

```text
deliverables/
├── docs/
│   ├── SCM_Workflow_Diagram.md
│   ├── Command_Sequences.txt
│   └── Debugging_and_Linting_Summary.md
└── README.md
```

## 3. Software Configuration Management (SCM)

Software Configuration Management is the process of controlling, tracking, and managing changes to software configuration items throughout the development lifecycle.

The project uses Git to track changes and GitHub to support collaboration and code review.

### Key Terms

- **Configuration Item (CI):** A file or component managed and tracked within the repository.
- **Working Copy:** The local files where developers make changes.
- **Staging Area:** The area where selected changes are prepared for a commit.
- **Local Repository:** The local Git database containing project history.
- **Upstream Repository:** The remote repository used to share and retrieve changes.
- **Feature Branch:** An isolated branch used to develop changes without directly modifying main.

## 4. Branching Strategy

The project follows a feature-branch workflow.

- `main` represents the stable project baseline.
- Each new task should be developed in a separate feature branch.
- Developers must avoid making direct changes to `main`.
- Feature branches should be updated with the latest changes from `main` before integration.

### Branch Naming Convention

Use descriptive branch names:

```bash
feature/metrics-documentation
feature/refresh-interval
bugfix/configuration-error
```

### Create a Feature Branch

```bash
git switch main
git pull origin main
git switch -c feature/your-task-name
```

## 5. GitHub Issues and Task Tracking

GitHub Issues are used to document and track development tasks and problems.

### Issue Creation Workflow

1. Open the repository on GitHub.
2. Select the Issues tab.
3. Click New Issue.
4. Enter a clear title and description.
5. Add relevant labels, such as `documentation`, `bug`, or `enhancement`.
6. Assign the issue to the responsible developer.
7. Submit the issue.

Each issue should describe the expected result and provide enough information for the assigned developer to complete the task.

## 6. Development and Git Workflow

Developers should follow these steps when working on a Configuration Item.

### Step 1: Check Repository Status

```bash
git status
git branch
```

### Step 2: Make Changes

Modify the required files in the working copy.

### Step 3: Stage Changes

```bash
git add filename
```

### Step 4: Review Staged Changes

```bash
git diff --cached
```

### Step 5: Commit Changes

```bash
git commit -m "Describe the changes"
```

### Step 6: Push the Feature Branch

```bash
git push -u origin feature/your-task-name
```

## 7. Pre-Submission Verification

Before submitting a Pull Request, developers must review their changes.

### Git Diff Review

```bash
git diff
git diff --cached
git diff --check
git status
```

### Local Linting

Run the configured linting command:

```bash
npm run lint:check
```

Resolve reported errors and warnings before submitting changes.

Developers should also remove unintended files, temporary code, and debugging statements.

## 8. Pull Request and Peer Review

All feature branches must be integrated into `main` through a Pull Request.

### Pull Request Workflow

1. Push the feature branch to GitHub.
2. Open the repository.
3. Select Pull Requests.
4. Click New Pull Request.
5. Set `main` as the base branch.
6. Select the feature branch as the compare branch.
7. Add a descriptive title and summary.
8. Submit the Pull Request.
9. Request peer review.
10. Address review comments and requested changes.
11. Wait for the required approvals and successful checks.
12. Merge the Pull Request after approval.

### Branch Protection

The `main` branch should be protected using GitHub repository rules.

Direct changes should be restricted, and merging should require peer review and successful required checks.

## 9. Merge Conflict Resolution

A merge conflict occurs when Git cannot automatically combine changes made to the same part of a file.

### Basic Resolution Workflow

1. Fetch the latest remote changes:

```bash
git fetch origin
```

2. Merge the latest main branch into the feature branch:

```bash
git merge origin/main
```

3. Check the repository status:

```bash
git status
```

4. Open the conflicting file and inspect the conflict markers.
5. Edit the file and select the correct final values.
6. Remove all conflict markers.
7. Stage the resolved file:

```bash
git add filename
```

8. Review the resolution:

```bash
git diff --cached
```

9. Complete the merge commit:

```bash
git commit -m "Resolve merge conflict"
```

10. Push the updated feature branch:

```bash
git push origin feature/your-task-name
```

Refer to `docs/Command_Sequences.txt` for the complete configuration conflict scenario.

## 10. Debugging and Code Quality

Developers should use IDE debugging tools to investigate application errors.

Recommended practices include:

- Setting breakpoints to pause execution.
- Inspecting local variables.
- Examining the call stack.
- Reviewing stack traces when exceptions occur.
- Identifying and correcting the root cause.

Developers should also run local linters to identify potential code-quality issues before submitting changes.

Refer to `docs/Debugging_and_Linting_Summary.md` for detailed explanations.

## 11. Documentation References

The following documents provide additional technical details:

| Document | Description |
|---|---|
| `SCM_Workflow_Diagram.md` | SCM concepts, branching strategy, and state transitions |
| `Command_Sequences.txt` | Git commands, Pull Request workflow, and merge conflict resolution |
| `Debugging_and_Linting_Summary.md` | Debugging techniques, call stacks, stack traces, and linting |

## 12. Final Contribution Checklist

Before submitting a contribution, verify that:

- [ ] The changes are developed in a separate feature branch.
- [ ] The working copy contains only intended changes.
- [ ] Changes are staged and committed correctly.
- [ ] Local Git diffs have been reviewed.
- [ ] Linting checks have been completed.
- [ ] Merge conflicts have been resolved.
- [ ] The feature branch has been pushed to GitHub.
- [ ] A Pull Request has been submitted.
- [ ] Required peer review and checks have been completed.

---

**Maintaining a consistent SCM workflow helps protect the main branch, improve collaboration, and ensure reliable software changes.**