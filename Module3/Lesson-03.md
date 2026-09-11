## Lesson 3 – Linux File Ownership (chown & chgrp)

By the end of this lesson, you'll understand:

- What is file ownership?
- Owner vs Group
- chown
- chgrp
- ls -l
- Real DevOps examples
- Interview questions

## First Understand the Concept

Imagine you're working in a company.

There are three employees:

Syed  
Rahul  
John

A project folder belongs to Syed.

Only Syed should be able to modify it.

Linux solves this using ownership.

Every file has:

- Owner
- Group
- Permissions

Example:

```text
-rwxr-xr--
syed devops
```

Here:

Owner = syed

Group = devops

## Step 1 – Check Ownership

Run:

```bash
mkdir ownership-lab
cd ownership-lab
```

```bash
touch app.log
```

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 cloudshell-user cloudshell-user 0 Sep 10 app.log
```

Break it down:

```text
-rw-r--r--
```

↓

Permissions

```text
cloudshell-user
```

↓

Owner

```text
cloudshell-user
```

↓

Group

## Why is Ownership Important?

Imagine Jenkins creates a file.

Later,

Tomcat needs to read it.

If ownership is wrong,

Tomcat gets:

```text
Permission denied
```

One of the first things a DevOps engineer checks is:

```text
Who owns this file?
```

## Command 1 – chown

### Change Owner

### Syntax

```bash
sudo chown username filename
```

### Example

```bash
sudo chown syed app.log
```

Now

Owner becomes:

```text
syed
```

## Change Owner and Group Together

```bash
sudo chown syed:devops app.log
```

Now

Owner

```text
syed
```

Group

```text
devops
```

## Command 2 – chgrp

### Change only the Group

Example:

```bash
sudo chgrp developers app.log
```

Owner stays the same.

Only group changes.

## Verify

Run

```bash
ls -l
```

Example

```text
-rw-r--r-- 1 syed developers
```

## Real DevOps Example 1

Imagine:

Jenkins builds:

```text
app.war
```

Owner:

```text
jenkins
```

Tomcat runs as:

```text
tomcat
```

Tomcat tries to deploy.

Error:

```text
Permission denied
```

Solution

```bash
sudo chown tomcat:tomcat app.war
```

Now deployment succeeds.

## Real DevOps Example 2

Terraform creates logs.

Owner:

```text
root
```

DevOps engineer cannot edit.

Fix:

```bash
sudo chown syed logs.txt
```

## Real DevOps Example 3

### Docker Volume

Container creates files.

Owner:

```text
root
```

Developer cannot edit them.

Fix ownership.

## Company Scenario

Developer says:

"I can't edit the deployment folder."

You check:

```bash
ls -l
```

Output

```text
root root
```

Solution

```bash
sudo chown -R syed:devops deployment/
```

Problem solved.

## Recursive Ownership

Suppose folder contains 1000 files.

Instead of changing each file:

```bash
sudo chown -R syed:devops project/
```

`-R`

means

```text
Recursive
```

Everything changes.

## Difference

### chown

Changes Owner

and optionally Group

### chgrp

Changes only Group

## Interview Questions

### Q1. What is file ownership?

Answer:

Every Linux file has an owner and a group that determine who can access or modify it.

### Q2. What does chown do?

Answer:

It changes the owner of a file or directory. It can also change the group when used in the format owner:group.

### Q3. What does chgrp do?

Answer:

It changes only the group associated with a file or directory.

### Q4. What is the purpose of -R?

Answer:

It applies the ownership change recursively to all files and subdirectories.

### Q5. Why is ownership important in DevOps?

Answer:

Incorrect ownership can prevent applications, services, or deployment tools from reading, writing, or executing files. Checking ownership is a common troubleshooting step.

## Commands Learned Today

| Command | Purpose |
|---|---|
| `ls -l` | View permissions, owner, and group |
| `chown` | Change file owner |
| `chown owner:group` | Change owner and group |
| `chgrp` | Change group only |
| `chown -R` | Recursively change ownership |
