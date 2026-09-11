## Lesson 2 – Linux Users & Groups

By the end of this lesson, you'll understand:

- What is a user?
- What is a group?
- Root user
- Sudo
- whoami
- id
- groups
- sudo
- useradd
- passwd
- su
- who

## Imagine This

Suppose you work in a company.

There are different people:

👨‍💼 Employee

👨‍💻 Developer

👨‍🔧 DevOps Engineer

👨‍💼 Manager

Everyone doesn't have the same permissions.

Linux works exactly the same way.

Every person who logs into Linux is called a User.

## Types of Users

### 1. Root User

The most powerful user.

```text
root
```

Root can:

- Create users
- Delete users
- Install software
- Delete files
- Change permissions
- Stop servers

Think of Root as the Administrator of the operating system.

### 2. Normal User

Example:

```text
syed
```

A normal user has limited permissions.

This is the account you usually use for daily work.

## What is a Group?

A group is simply a collection of users.

Example:

```text
developers

devops

admins

qa
```

Instead of giving permissions to each person individually, Linux allows you to assign permissions to an entire group.

## Real DevOps Example

Imagine your company has:

### DevOps Team

Members:

Syed

Rahul

Amit

John

All of them belong to:

```text
devops
```

Now if the company gives permission to the devops group,

everyone automatically gets access.

No need to configure each user one by one.

## Command 1 — whoami

Run:

```bash
whoami
```

Output:

```text
cloudshell-user
```

This tells you the current logged-in user.

## Command 2 — id

Run:

```bash
id
```

Example:

```text
uid=1000(cloudshell-user)
gid=1000(cloudshell-user)
groups=1000(cloudshell-user)
```

### Explanation:

#### uid

User ID

#### gid

Group ID

#### groups

Groups the user belongs to.

## Command 3 — groups

Run:

```bash
groups
```

Example:

```text
cloudshell-user sudo docker
```

This shows all the groups the current user belongs to.

## Command 4 — who

Run:

```bash
who
```

Shows who is currently logged into the Linux machine.

## Command 5 — sudo

Suppose you install software.

Instead of logging in as Root,

Linux allows temporary administrator access.

Example:

```bash
sudo apt update
```

or

```bash
sudo yum update
```

Meaning:

"Run this command as Administrator."

### What is sudo?

```text
sudo
```

means

```text
Super User DO
```

It temporarily gives administrator privileges to a normal user.

## Command 6 — useradd

Creates a new user.

Example:

```bash
sudo useradd devops
```

## Command 7 — passwd

Sets a password.

```bash
sudo passwd devops
```

Linux asks:

```text
New Password:
```

Enter a password.

## Command 8 — su

Switch user.

Example:

```bash
su devops
```

Now you're logged in as:

```text
devops
```

Return to the previous user:

```bash
exit
```

### Verify

Run:

```bash
whoami
```

Output:

```text
devops
```

Exit:

```bash
exit
```

## Complete Workflow

```text
Create User
      │
      ▼
useradd
      │
      ▼
passwd
      │
      ▼
su
      │
      ▼
whoami
```

## Real Company Scenario

A new employee joins.

HR creates an account.

DevOps Engineer runs:

```bash
sudo useradd syed
```

Assign password:

```bash
sudo passwd syed
```

Add to DevOps group:

```bash
sudo usermod -aG devops syed
```

Now Syed can access DevOps resources.

## Practice Lab

Run these commands in AWS CloudShell:

```bash
whoami
```

```bash
id
```

```bash
groups
```

```bash
who
```

Now try:

```bash
sudo useradd devopsuser
```

If CloudShell allows it:

```bash
sudo passwd devopsuser
```

```bash
su devopsuser
```

```bash
whoami
```

```bash
exit
```

**Note:** AWS CloudShell is a managed environment. Some commands like useradd or passwd may be restricted. If you get a permission or environment error, that's expected. The important part is understanding the commands. Later, when we launch our own EC2 Linux server, you'll perform all these tasks with full control.

## Interview Questions

### Q1. What is Root?

Answer:

The Root user is the Linux administrator with unrestricted access to the entire operating system.

### Q2. What is sudo?

Answer:

sudo allows a user to execute commands with administrator (superuser) privileges.

### Q3. Difference between Root and sudo?

Answer:

Root is the actual administrator account.

sudo lets an authorized user temporarily perform administrator tasks without logging in as Root.

### Q4. What does whoami do?

Answer:

Displays the username of the currently logged-in user.

### Q5. What does id show?

Answer:

It displays the user's UID, GID, and group memberships.

### Q6. What is the purpose of groups?

Answer:

Groups make permission management easier by assigning access rights to multiple users at once instead of configuring each user individually.

## Commands Learned Today

| Command | Purpose |
|---|---|
| `whoami` | Display current user |
| `id` | Show user and group IDs |
| `groups` | List user's groups |
| `who` | Show logged-in users |
| `sudo` | Run a command with administrator privileges |
| `useradd` | Create a new user |
| `passwd` | Set or change a user's password |
| `su` | Switch to another user |
| `exit` | Return to the previous shell/user |
