# Git and GitHub notes/cheatsheet

## Table of Contents
- [Git and GitHub notes/cheatsheet](#git-and-github-notescheatsheet)
  - [Table of Contents](#table-of-contents)
  - [Git Basics](#git-basics)
    - [Setting up Git](#setting-up-git)
  - [Git Workflow](#git-workflow)
  - [GitHub Basics](#github-basics)
    - [Fork a Repository](#fork-a-repository)
    - [Create a Pull Request](#create-a-pull-request)
  - [Common Git Commands](#common-git-commands)
  - [Git Branching](#git-branching)
  - [Git Remote Operations](#git-remote-operations)

---

## Git Basics

Git is a version control system that allows you to track changes in your files and collaborate on projects.

### Setting up Git

```bash
# Set your username and email globally
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"

# Check your configuration
git config --list
```

## Git Workflow

__1. Initialise or Clone a repository__  
Use this to initialise an existing directory as a Git repository.

```bash
git init
```

Use this to create a local copy of a remote repository.

```bash
git clone https://github.com/username/repository.git
```

__2. Create a new branch__  
Always create a new branch to work on features or bug fixes.

```bash
git checkout -b new-branch-name
```

__3. Stage changes__  
Add modified files to the staging area.

```bash
git add file-name
```

To add all files:

```bash
git add .
```

__4. Commit changes__  
Commit the staged changes with a message.

```bash
git commit -m "Commit message"
```

__5. Push changes to GitHub__  
Push your changes to the remote repository on GitHub.

```bash
git push origin branch-name
```

__6. Merge changes__  
Merge your changes into a specified branch, typically main.

```bash
git merge branch-name
```

## GitHub Basics

GitHub is a hosting platform for Git repositories.

- __Forking__: Make a copy of a repository on GitHub under your account.

- __Pull Request (PR)__: A request to merge changes from your branch into another branch (typically the main branch).

- __Issues__: A way to track tasks, bugs, or enhancements in a project.

### Fork a Repository

To contribute to someone else's project, fork it to your account and then clone it.

```bash
# Fork the repo from GitHub then clone your fork
git clone https://github.com/your-username/repository.git
```

### Create a Pull Request

After pushing your changes, open a pull request to the original repository for review and merging.

## Common Git Commands

Check Git Status
  
```bash
git status
```

View Commit History
  
```bash
git log
```

Show Changes between Commits
  
```bash
git diff
```

Remove a file from Git
  
```bash
git rm file-name
```

## Git Branching

View Branches
```bash
git branch
```

Switch Branches
```bash
git checkout branch-name
```

Merge Branches
```bash
git merge branch-name
```

Delete a Branch
```bash
git branch -d branch-name
```

Create a New Branch
```bash
git checkout -b new-branch-name
```

## Git Remote Operations
Add a Remote
```bash
git remote add origin https://github.com/username/repository.git
```

View Remotes
```bash
git remote -v
```

Fetch Latest Changes from Remote
```bash
git fetch origin
```

Pull Latest Changes from Remote
```bash
# Pulls changes from the 'main' branch
git pull origin main
```

Push to Remote
```bash
git push origin branch-name
```

added change