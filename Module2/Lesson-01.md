# Lesson 1 – Git Fundamentals

## 🤔 Imagine This Scenario

You're writing a resume in Microsoft Word.

### Day 1:

```text
resume.docx
```

### Day 2:

You make changes but don't like them.

You save:

```text
resume_final.docx
resume_final_new.docx
resume_final_latest.docx
resume_final_latest2.docx
resume_final_latest_final.docx
```

😂 We've all done this.

This becomes confusing.

## 💡 Git Solves This Problem

Git keeps track of every change you make.

Instead of creating many files, Git stores the history.

```text
Version 1
     ↓
Version 2
     ↓
Version 3
     ↓
Version 4
```

You can go back to any previous version whenever you want.

## 📖 What is Git?

Git is a Version Control System (VCS).

In simple English:

Git keeps track of every change made to your files.

Think of it as an unlimited Undo button.

## 🏢 Real-World Example

Imagine five developers working on one project.

### Without Git:

- Person A overwrites Person B's code.
- Nobody knows who changed what.
- The project becomes messy.

### With Git:

- Every change is recorded.
- Everyone works safely.
- Changes can be reviewed.
- Problems can be rolled back.

## Git vs GitHub

Many beginners think they are the same.

They are not.

### Git

- Software installed on your computer (or available in CloudShell)
- Tracks file changes

### GitHub

- Website where Git repositories are stored online
- Makes collaboration and backup easy

Think of it like this:

```text
Git = Notebook

GitHub = Cloud storage for your notebook
```

## The Git Workflow

Every Git project follows this cycle:

```text
Create File
      │
      ▼
Modify File
      │
      ▼
Git notices changes
      │
      ▼
Save the changes (Commit)
      │
      ▼
Push to GitHub
```

This cycle is repeated throughout a project's life.

## Important Git Terms

### Repository (Repo)

A project folder managed by Git.

Example:

```text
jenkins-project
docker-lab
terraform-aws
```

### Commit

A checkpoint.

Think of it as:

"Save Game"

Every commit records the state of your project.

Example:

```text
Commit 1
Initial Project

Commit 2
Added Dockerfile

Commit 3
Configured Jenkins Pipeline
```

### Branch

A separate line of development.

Instead of changing the main project directly, you work in your own branch.

Later, your changes are merged.

### Clone

Download a repository from GitHub to your computer.

### Push

Upload your changes to GitHub.

### Pull

Download the latest changes from GitHub.

## DevOps Example

Suppose you're working on Terraform.

```text
terraform/
```

Today you write infrastructure.

Tomorrow you accidentally delete everything.

### Without Git:

😢 Everything is gone.

### With Git:

```bash
git checkout
```

or restore a previous version.

Problem solved.

## Interview Questions

### Q1. What is Git?

Answer:

Git is a distributed version control system used to track changes in files and enable collaboration among developers.

### Q2. What is GitHub?

Answer:

GitHub is a cloud-based platform used to host Git repositories and collaborate on software projects.

### Q3. Difference between Git and GitHub?

| Git | GitHub |
|---|---|
| Version control tool | Cloud hosting platform |
| Works locally | Works online |
| Tracks changes | Stores repositories |

## Today's Exercise

In AWS CloudShell, run:

```bash
git --version
```

Then create a practice folder:

```bash
mkdir git-fundamentals
cd git-fundamentals
```

Finally, initialize your first Git repository:

```bash
git init
```

You'll see a message similar to:

```text
Initialized empty Git repository...
```

🎉 Congratulations! That will be your first Git repository.
