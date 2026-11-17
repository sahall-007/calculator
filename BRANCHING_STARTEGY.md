# Git Branching Strategy

**Project:** Hiring Platform  
**Strategy:** GitHub Flow  
**Version:** 1.0

## 1. Purpose

This document defines the Git branching strategy and collaboration guidelines that all developers must follow while working on the Hiring Platform.

The goal is to maintain a clean and organized codebase, avoid conflicts between developers, and ensure that changes are reviewed and tested before being merged into the main branch.

## 2. Branching Model

The project follows the **GitHub Flow** branching strategy.

We will maintain one permanent branch, `main`, and create short-lived branches for individual features, bug fixes, and other tasks.

There will be no separate `develop` branch.

#### a. Main Branch

- `main` is the primary branch of the project.
- It must always contain stable, integrated code.
- All changes must be introduced through Pull Requests.

#### b. Supporting Branches

Supporting branches are created from `main` and merged back into `main` after completing the required review and checks.

- `Feature`: 
    Implementing new functionality
    eg:- `feature/user-registration`

- `Bug fix`: 
    Fixing existing issues
    eg:- `fix/login-validation` 

- `Documentation`:
    Updating project documentation
    eg:- `docs/api-documentation`

- `chore`: 
    configuratoin and maintenance task
    eg:- `chore/eslint-setup`



Supporting branches are temporary and should be deleted after successful merging.

## 3. Branch Naming Convention

All branches must follow this naming format:

`<type>/<short-description>`

Examples:

- `feature/recruiter-dashboard`
- `feature/job-posting`
- `fix/resume-upload`
- `docs/setup-guide`
- `chore/docker-configuration`

Branch names should be descriptive, lowercase, and use hyphens to separate words.

## 4. Development Workflow

Developers must follow these steps when working on a task:

1. Pull the latest changes from `main`.
2. Create a new branch from the updated `main` branch.
3. Implement the assigned task.
4. Commit changes using meaningful commit messages.
5. Push the branch to the remote GitHub repository.
6. Create a Pull Request targeting `main`.
7. Wait for code review and automated checks.
8. Merge the Pull Request after all requirements are satisfied.
9. Delete the supporting branch after merging.

## 5. Commit Message Convention

`For detailed information about the convention, refer`: https://www.conventionalcommits.org/en/v1.0.0-beta.2/

The project follows the **Conventional Commits** format to maintain consistent, meaningful, and readable commit messages.

#### a. Commit Message Format

All commit messages must follow this structure:

<type>: <short description>

<optional body> 

#### b. Commit Types                                                 

 `feat`     -  Adding a new feature                                    
 `fix`      -  Fixing a bug                                                
 `docs`     -  Documentation changes                                   
 `refactor` -  Restructuring code without changing its behavior         
 `test`     -  Adding or updating tests                                
 `chore`    -  Maintenance and configuration changes                  

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
- Merge conflicts must be resolved before merging.
- The developer who created the PR should address review feedback.
- Take a screenshot of the PR

## 7. Main Branch Protection

The `main` branch must be protected through GitHub repository settings.

The following protections should be enabled:

- Require Pull Requests before merging.
- Require at least one approval.
- Require status checks to pass before merging.
- Prevent direct pushes to `main`.
- Require branches to be up to date before merging, if supported by the CI setup.

## 8. Branch Cleanup

After a Pull Request is successfully merged into `main`, the corresponding supporting branch should be deleted from GitHub.

Developers should also delete the corresponding local branch to keep their local repositories clean.

## 9. General Guidelines

- Always create supporting branches from the latest `main`.
- Keep branches focused on a single task whenever practical.
- Avoid committing unfinished or unrelated changes.
- Pull the latest changes regularly to reduce merge conflicts.
- Never commit secrets, credentials, or environment files containing sensitive information.
- Follow the same branching conventions across the team.

---

**End of Document**
