# Git Branching Strategy

**Project:** Hiring Platform  
**Strategy:** GitHub Flow  
**Version:** 1.0

## 1. Purpose

This document defines the Git branching strategy and collaboration guidelines.

The goal is to maintain a clean and organized codebase, avoid conflicts between developers.

## 2. Branching Model

The project follows the **GitHub Flow** branching strategy.

We will maintain one permanent branch, `main`, and create short-lived branches for individual features, bug fixes, and other tasks.

There will be no separate `develop` branch.

#### a. Main Branch

- It must always contain stable, integrated code.
- All changes must be introduced through Pull Requests.

#### b. Supporting Branches

Supporting branches are created from `main` and merged back into `main` after completing the required review and checks.

| Type | Prefix | Example | Description |
| :--- | :--- | :--- | :--- |
| **Feature** | `feature/` | `feature/user-auth-api` | New features, enhancements, or UI components. |
| **Bugfix** | `bugfix/` | `bugfix/cart-total-calculation` | Fixing existing bugs or incorrect behavior. |
| **Chore** | `chore/` | `chore/eslint-setup` | configuratoin and maintenance task. |
| **Refactor**| `refactor/`| `refactor/db-connection-pool` | Code restructuring without altering external behavior. |


Supporting branches are temporary and should be deleted after successful merging.

## 3. Branch Naming Convention

All branches must follow this naming format:

`<type>/<short-description>`

Examples:

- `feature/recruiter-dashboard`
- `fix/resume-upload`

Branch names should be descriptive, lowercase, and use hyphens to separate words.

## 4. Development Workflow

Developers must follow these steps when working on a task:

1. Pull the latest changes from `main`.

```bash
git checkout main
git pull origin main
```

2. Create a new branch from the updated `main` branch.

```bash
git checkout -b feature/your-feature-name
```

3. Implement the assigned task.

4. Commit changes using meaningful commit messages.

```bash
git add .
git commit -m "feat: implement item filtering logic"
```

5. Push the branch to the remote GitHub repository.

```bash
git push origin feature/your-feature-name
```

6. Create a Pull Request targeting `main`.

7. Wait for code review and automated checks.

8. Merge the Pull Request after all requirements are satisfied.

9. Delete the supporting branch after successful merging.

## 5. Commit Message Convention

`For detailed information about the convention, refer`: https://www.conventionalcommits.org/en/v1.0.0-beta.2/

The project follows the **Conventional Commits** format to maintain consistent, meaningful, and readable commit messages.

#### a. Commit Message Format

All commit messages must follow this structure:

`<type>: <short description>`

`<optional body>`

#### b. Commit Types                                                 

| Type | Purpose |
| :--- | :--- |
| `feat` | Adding a new feature |
| `fix` | AFixing a bug |
| `refactor` | Restructuring code without changing its behavior |
| `chore` | Maintenance and configuration changes |                

#### c. Commit Message Guidelines

- Use lowercase for the commit type and description.
- Keep the description short and clear.
- leave a blank line before the `optional body` 
- Do not use vague messages such as `changes`, `update`, or `final commit`.
- Each commit should represent a logical unit of work.
- Avoid combining unrelated changes into a single commit.

#### d. Examples

- `feat: add recruiter dashboard`
- `fix: prevent duplicate email registration`


## 6. Pull Request Guidelines

Every change must be submitted through a Pull Request.

The following guidelines must be followed:

- PRs must have a clear title and description.
- The description should explain what was changed and why.
- Other team members must review and approve the PR.
- Take a screenshot of the PR

## 7. Main Branch Protection

The `main` branch must be protected through GitHub repository settings.

The following protections should be enabled:

- Require Pull Requests before merging.
- Require at least one approval.
- Require status checks to pass before merging.
- Require branches to be up to date before merging, if supported by the CI setup.

## 8. Branch Cleanup

After a Pull Request is successfully merged into `main`, the corresponding supporting branch should be deleted from GitHub.

Developers should also delete the corresponding local branch to keep their local repositories clean.

---

**End of Document**
