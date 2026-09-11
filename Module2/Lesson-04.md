## Lesson 4 – GitHub Integration

By the end of this lesson, you'll know:

What is a remote repository?  
What is GitHub?  
How to connect your local repository to GitHub  
git remote  
git push  
git pull  
git fetch  
git clone  

## First Understand the Concept

Until now, you've been working only on your local machine (CloudShell).

```text
CloudShell
    │
    ▼
Git Repository
```

Nobody else can see your work.

Now we want to upload it to GitHub.

```text
CloudShell
      │
      ▼
Git Repository
      │
      ▼
GitHub Repository
```

GitHub becomes your online backup and collaboration platform.

## Real Company Workflow

```text
Developer
      │
      ▼
Git (Laptop)
      │
      ▼
GitHub
      │
      ▼
Jenkins
      │
      ▼
Build
      │
      ▼
Docker
      │
      ▼
Kubernetes
```

This is the same workflow we'll build during our DevOps projects.

## Step 1 – Create a Repository on GitHub

Go to:

https://github.com

Click:

**New Repository**

Repository Name:

```text
git-fundamentals
```

Choose:

✅ Public

❌ Don't add README

❌ Don't add .gitignore

❌ Don't add License

Click:

**Create Repository**

GitHub will show commands similar to:

```bash
git remote add origin https://github.com/USERNAME/git-fundamentals.git
git branch -M main
git push -u origin main
```

Don't worry—we'll understand every command.

## Step 2 – Add a Remote

A remote is simply the GitHub repository.

Run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/git-fundamentals.git
```

Example:

```bash
git remote add origin https://github.com/syedhussaindevops/git-fundamentals.git
```

### Check the Remote

```bash
git remote -v
```

Example:

```text
origin https://github.com/syedhussaindevops/git-fundamentals.git
origin https://github.com/syedhussaindevops/git-fundamentals.git
```

## Step 3 – Push Your Code

Rename the branch (if needed):

```bash
git branch -M main
```

Now upload:

```bash
git push -u origin main
```

The first time, GitHub may ask you to authenticate.

Follow the prompts.

### What is Push?

Think of it as:

```text
Laptop
     │
     ▼
GitHub
```

You're uploading your work.

## Step 4 – Pull

Suppose another developer updates the project.

You want the latest version.

Run:

```bash
git pull
```

It downloads the newest changes.

## Step 5 – Fetch

```bash
git fetch
```

Fetch checks for updates but doesn't merge them into your working branch.

## Step 6 – Clone

Suppose tomorrow you buy a new laptop.

Instead of downloading ZIP files...

Run:

```bash
git clone https://github.com/syedhussaindevops/git-fundamentals.git
```

Git downloads the complete project.

## Difference

### Clone

Downloads an entire repository.

Used once.

### Pull

Downloads the latest changes.

Used daily.

### Push

Uploads your work.

Used daily.

### Fetch

Checks for new updates.

Doesn't merge automatically.

## Real DevOps Workflow

```text
Developer
      │
      ▼
git add
      │
      ▼
git commit
      │
      ▼
git push
      │
      ▼
GitHub
      │
      ▼
Jenkins detects new code
      │
      ▼
CI/CD Pipeline starts
```

This is why GitHub is so important in DevOps.

## Interview Questions

### Q1. What is GitHub?

Answer:

GitHub is a cloud-based platform for hosting Git repositories and enabling collaboration, version control, and code sharing.

### Q2. What is a remote repository?

Answer:

A remote repository is a Git repository hosted on a server (such as GitHub) that allows collaboration and backup of source code.

### Q3. Difference between git fetch and git pull?

Answer:

git fetch downloads the latest changes but does not merge them.

git pull downloads and merges the changes into the current branch.

### Q4. Difference between git clone and git pull?

Answer:

git clone copies a repository for the first time.

git pull updates an existing local repository.

## Git Commands Learned So Far

| Command | Purpose |
|---|---|
| `git init` | Initialize a repository |
| `git status` | Check repository status |
| `git add` | Stage changes |
| `git commit` | Save a snapshot |
| `git log` | View commit history |
| `git branch` | List or create branches |
| `git switch` | Switch branches |
| `git merge` | Merge branches |
| `git remote` | Manage remote repositories |
| `git push` | Upload changes |
| `git pull` | Download and merge changes |
| `git fetch` | Download changes without merging |
| `git clone` | Copy a remote repository |
