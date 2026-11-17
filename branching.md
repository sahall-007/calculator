# Git Branching Strategy: GitHub Flow

This document outlines the Git workflow, branching conventions, and code review standards for our project. We use **GitHub Flow**, a lightweight branching model designed to support continuous integration and continuous deployment (CI/CD).

---

## 1. Core Rules
1. **`main` is Always Deployable:** The `main` branch represents the stable production state. No code should ever be pushed directly to `main`.
2. **Short-Lived Branches:** All work is done on feature or fix branches that live for a short duration (ideally less than a few days) and are merged frequently.
3. **Automation is Key:** Automated tests and builds must pass before any code can be merged.

---

## 2. Branch Naming Conventions

All working branches must be branched off from `main` and use a clear, descriptive prefix followed by a hyphenated description and an optional ticket/issue ID.

| Type | Prefix | Example | Description |
| :--- | :--- | :--- | :--- |
| **Feature** | `feature/` | `feature/user-auth-api` | New features, enhancements, or UI components. |
| **Bugfix** | `bugfix/` | `bugfix/cart-total-calculation` | Fixing existing bugs or incorrect behavior. |
| **Hotfix** | `hotfix/` | `hotfix/payment-gateway-crash` | Urgent fixes for production issues. |
| **Refactor**| `refactor/`| `refactor/db-connection-pool` | Code restructuring without altering external behavior. |

---

## 3. Step-by-Step Workflow

### Step 1: Sync and Create a Branch
Ensure your local `main` branch is up to date, then create your working branch:
```bash
git checkout main
git pull origin main
git checkout -b feature/your-feature-name
