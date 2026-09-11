# Module 2 – Git Fundamentals

## Lesson 2 – git status, git add, git commit, git log

Today you'll understand the 4 most important Git commands.

Every DevOps engineer uses these daily.

## Before We Start

Go to your Git repository.

```bash
cd ~/git-fundamentals
```

If it doesn't exist:

```bash
mkdir git-fundamentals
cd git-fundamentals
git init
```

## Step 1 — Create a file

```bash
touch README.md
```

Check:

```bash
ls
```

Output:

```text
README.md
```

## Step 2 — Check Git Status

Run:

```bash
git status
```

Example:

```text
On branch main

No commits yet

Untracked files:
README.md
```

### What does "Untracked" mean?

Imagine Git is your teacher.

You create a notebook.

Until you show it to the teacher...

The teacher doesn't know it exists.

That is called:

**Untracked File**

Git has noticed a new file exists, but it is not yet being tracked.

## Step 3 — Add the file

Run:

```bash
git add README.md
```

Now check:

```bash
git status
```

Now you'll see:

```text
Changes to be committed
```

### What happened?

The file has moved to the Staging Area.

Think of the staging area like a shopping cart.

You haven't bought the items yet.

You've just selected them.

## Step 4 — Commit

Run:

```bash
git commit -m "Initial commit"
```

If Git asks for your name and email, configure them first:

```bash
git config --global user.name "Syed Hussain"

git config --global user.email "your-email@example.com"
```

Replace the email with the same one you use for GitHub.

Then run the commit again.

### What is a Commit?

Think of it as:

Save Game

Git creates a permanent checkpoint.

## Step 5 — View History

Run:

```bash
git log
```

Example:

```text
commit 65af....

Author:
Date:

Initial commit
```

Every commit has a unique ID.

## Real Workflow

```text
Create file
        │
        ▼
git status
        │
        ▼
git add
        │
        ▼
git commit
        │
        ▼
git log
```

This is the basic Git workflow you'll repeat throughout your career.

## Think Like a DevOps Engineer

Don't memorize commands.

Instead, understand the flow:

```text
Work
    ↓
Check
    ↓
Stage
    ↓
Save
```

Which translates to:

```text
Modify files
      ↓
git status
      ↓
git add
      ↓
git commit
```

## Interview Questions

### What is git status?

Shows the current state of the repository, including untracked, modified, and staged files.

### What is git add?

Moves changes to the staging area before committing.

### What is a commit?

A commit is a saved snapshot (checkpoint) of your project.

### What is git log?

Displays the commit history of the repository.
