GitHub Merge & Release Process

## Overview

This document describes the standard development, review, merge, and release workflow followed by the team using GitHub Pull Requests (PRs).

---

# Development Workflow

## 1. Technical Discussion & Design Approval

Before implementation begins:

* The developer discusses the feature, enhancement, or fix with the Technical Lead.
* The architecture, implementation approach, and code design are reviewed and agreed upon.
* Once approved, development work starts.

---

## 2. Development & Pull Request Creation

After completing the implementation:

* The developer commits the changes to their feature branch.
* A Pull Request (PR) is created in GitHub targeting the `development` branch.

---

## 3. Code Review Process

The Pull Request is reviewed by the Development Team Lead.

### Review Process

* The reviewer checks:

  * Code quality
  * Architecture compliance
  * Performance considerations
  * Security and best practices
  * Coding standards

### Feedback & Fixes

* The reviewer may add comments or request changes.
* The developer addresses all review comments and pushes the required fixes.
* The reviewer re-verifies the updates.

### Approval

* Once all review comments are resolved and the code meets quality standards, the PR is approved.

---

## 4. Automated GitHub Checks

After the Pull Request is approved, customized GitHub CI/CD checks run automatically.

These checks verify:

* UI application builds successfully
* Backend services build successfully
* No compilation or build errors exist
* Additional automated validations configured in the pipeline

The PR can only proceed if all required checks pass successfully.

---

## 5. Merge to Development Environment

After approval and successful checks:

* The Pull Request is merged into the `development` branch.
* The latest changes are automatically deployed/published to the QA environments for testing and validation.

---

# Release Workflow

## 6. Release Preparation

When it is time for a production release:

* The Development Team Lead creates a Pull Request from:

  * `development` → `main`

---

## 7. Release Approval Process

The release PR requires:

* Approval from **two approvers**
* Verification that:

  * QA testing is completed
  * Release scope is validated
  * No blocking issues remain

Only after receiving the required approvals can the PR be merged into the `main` branch.

---

## 8. Production Release

After the release PR is merged into `main`:

* A new production release is published.
* The production environment is updated with the approved release version.

---

# Summary Flow

```text
Technical Discussion & Design Approval
                ↓
        Development Work
                ↓
      Create Pull Request
                ↓
        Team Lead Review
                ↓
      Developer Fixes Comments
                ↓
        Review Re-Verification
                ↓
     GitHub Automated Checks
                ↓
     Merge into Development
                ↓
      Deploy to QA Environment
                ↓
      Release PR to Main Branch
                ↓
      Two Approvals Required
                ↓
        Merge into Main
                ↓
       Publish to Production
```
