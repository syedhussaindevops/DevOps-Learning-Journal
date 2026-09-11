## Lesson 3 – Git Branching & Merging

By the end of this lesson, you'll understand:

- What is a branch?
- Why do we need branches?
- How to create a branch
- How to switch branches
- How to merge branches
- How teams collaborate using Git

## 🤔 Imagine This Situation

You have a Java application.

It is working perfectly.

Your manager says:

"Add a login feature."

Should you directly change the working application?

❌ No.

What if your new code has bugs?

The whole application could stop working.

## The Solution: Branches

A branch is simply your own workspace.

Think of it like this:

```text
Main Road (main branch)
        │
        │
        ├──────── Login Feature Branch
        │
        ├──────── Payment Feature Branch
        │
        └──────── Bug Fix Branch
```

Each developer works on a separate branch.

Only after testing are the changes merged into the main branch.

## 🌳 What is the main Branch?

When you create a Git repository, Git creates a default branch called main.

This is the stable version of your project.

## Step 1 — Check Your Branch

Run:

```bash
git branch
```

Output:

```text
* main
```

The * shows your current branch.

## Step 2 — Create a New Branch

Let's create a branch called feature-login.

```bash
git branch feature-login
```

Check again:

```bash
git branch
```

Output:

```text
* main
  feature-login
```

The branch exists, but you're still on main.

## Step 3 — Switch to the New Branch

Run:

```bash
git switch feature-login
```

Or (older command):

```bash
git checkout feature-login
```

Output:

```text
Switched to branch 'feature-login'
```

Verify:

```bash
git branch
```

Now:

```text
  main
* feature-login
```

## Step 4 — Make Changes

Add a new file:

```bash
touch login.txt
```

Write some content:

```bash
echo "Login Feature Started" > login.txt
```

Commit the changes:

```bash
git add login.txt
```

```bash
git commit -m "Added login feature"
```

## Step 5 — Return to Main

```bash
git switch main
```

Now check:

```bash
ls
```

You may notice login.txt is not there.

Why?

Because it only exists in the feature-login branch.

This is one of the biggest advantages of Git branches.

## Step 6 — Merge the Branch

Merge the completed feature into main.

```bash
git merge feature-login
```

Now check:

```bash
ls
```

You'll see:

```text
README.md
login.txt
```

The feature has been merged successfully.

## 📊 Real Company Workflow

Imagine a team of four developers.

```text
                 main
                  │
      ┌───────────┼───────────┐
      │           │           │
      ▼           ▼           ▼
 login-feature  payment   bug-fix
```

Each developer works independently.

After testing:

```text
login-feature
        │
        ▼
      Merge
        │
        ▼
       main
```

This allows teams to work in parallel without affecting the stable version.

## Common Branch Names

| Branch | Purpose |
|---|---|
| main | Stable production code |
| develop | Integration branch |
| feature/login | New feature |
| bugfix/header | Bug fixes |
| hotfix/security | Urgent production fixes |

## Real DevOps Example

Suppose you have Terraform code that creates AWS infrastructure.

The production branch is working.

Your manager asks you to add an Application Load Balancer.

Instead of editing production directly:

```text
main
    │
    └── terraform-alb-feature
```

You make changes, test them, and then merge them into main.

This reduces risk and keeps production stable.

## Interview Questions

### Q1. What is a Git branch?

Answer:

A Git branch is an independent line of development that allows developers to work on new features or fixes without affecting the main codebase.

### Q2. Why do we use branches?

Answer:

- Develop features safely
- Fix bugs independently
- Enable multiple developers to work simultaneously
- Protect the stable code in the main branch

### Q3. Difference between git switch and git checkout?

Answer:

git switch is the newer, simpler command for changing branches.

git checkout is an older command that can both switch branches and restore files.
