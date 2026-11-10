# ForgeLine DevOps Metrics Dashboard

## Why This Matters

Software Configuration Management (SCM) ensures that all software
changes are tracked, controlled, and reviewed before integration.
It protects the stability of the main branch.

## Core Idea

Our strategy is based on Feature Branch Isolation.
Developers must work on separate branches instead of modifying
the main branch directly.

## Key Terms

- Version Control: A system that tracks changes over time.
- Repository: A database containing project files and commit history.
- Configuration Item (CI): A trackable set of related changes.
- Working Copy: The local files where developers make changes.
- Staging Area: A temporary area that holds selected changes.
- Local Repository: The local Git database containing commits.
- Upstream Repository: The centralized GitHub repository.
- Feature Branch: An isolated branch for developing new changes.

## Part 1: Feature Branch Isolation Strategy

```text
Upstream: main
       |
       A (Initial Commit)
       |
       +---------------------------> D (Merge Pull Request)
       |
       |
Local: feature/metrics
       |
       +----> B (Commit)
       |
       +----> C (Commit)
                    |
                    +--------------> D# ForgeLine DevOps Metrics Dashboard

## Why This Matters

Software Configuration Management (SCM) ensures that all software
changes are tracked, controlled, and reviewed before integration.
It protects the stability of the main branch.

## Core Idea

Our strategy is based on Feature Branch Isolation.
Developers must work on separate branches instead of modifying
the main branch directly.

## Key Terms

- Version Control: A system that tracks changes over time.
- Repository: A database containing project files and commit history.
- Configuration Item (CI): A trackable set of related changes.
- Working Copy: The local files where developers make changes.
- Staging Area: A temporary area that holds selected changes.
- Local Repository: The local Git database containing commits.
- Upstream Repository: The centralized GitHub repository.
- Feature Branch: An isolated branch for developing new changes.

## Part 1: Feature Branch Isolation Strategy

```text
Upstream: main
       |
       A (Initial Commit)
       |
       +---------------------------> D (Merge Pull Request)
       |
       |
Local: feature/metrics
       |
       +----> B (Commit)
       |
       +----> C (Commit)
                    |
                    +--------------> D

+--------------------+
|    WORKING COPY    |
|   Modified Files   |
+--------------------+
          |
          | git add
          v
+--------------------+
|    STAGING AREA    |
|  Selected Changes  |
+--------------------+
          |
          | git commit
          v
+--------------------+
|   LOCAL REPOSITORY |
|   Commit History   |
+--------------------+
          |
          | git push
          v
+--------------------+
| UPSTREAM REPOSITORY|
|      GitHub        |
+--------------------+