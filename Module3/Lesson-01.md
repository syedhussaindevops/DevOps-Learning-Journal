## Lesson 1 – Linux File Permissions

This is one of the most frequently used Linux topics in DevOps interviews.

Almost every DevOps engineer works with file permissions on servers.

By the end of this lesson, you'll understand:

- What are permissions?
- Read, Write, Execute
- Owner, Group, Others
- chmod
- Numeric permissions (755, 644, etc.)
- Symbolic permissions (u, g, o)

## Imagine This

Suppose you own a house.

Some people can:

- Enter the house
- Watch TV
- Cook
- Sleep

Others may only be allowed to visit.

Linux works the same way.

Every file has permissions that control who can do what.

## Linux Permissions

Every file has three permission types:

```text
r = Read
w = Write
x = Execute
```

## Three Types of Users

Every file belongs to:

```text
Owner
Group
Others
```

So Linux checks permissions like this:

```text
Owner    Group    Others
 rwx      r-x      r--
```

## Step 1 — Create a Practice Folder

In CloudShell:

```bash
mkdir permissions-lab
cd permissions-lab
touch test.sh
```

Check:

```bash
ls
```

Output:

```text
test.sh
```

## Step 2 — View Permissions

Run:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 cloudshell-user cloudshell-user 0 Sep 10 test.sh
```

Let's break this down.

```text
-rw-r--r--
```

Means:

```text
-
rw-
r--
r--
```

## First Character

```text
-
```

Means:

It's a file.

If it were:

```text
d
```

It would be a directory.

## Owner Permissions

```text
rw-
```

Meaning:

✅ Read

✅ Write

❌ Execute

## Group Permissions

```text
r--
```

Only read.

## Others

```text
r--
```

Only read.

## Step 3 — Give Execute Permission

Run:

```bash
chmod +x test.sh
```

Now check again:

```bash
ls -l
```

Example:

```text
-rwxr-xr-x
```

Now the file can be executed.

## Step 4 — Remove Write Permission

```bash
chmod -w test.sh
```

Check again:

```bash
ls -l
```

## Step 5 — Numeric Permissions

This is where interview questions usually begin.

Every permission has a number:

```text
Read = 4

Write = 2

Execute = 1
```

Add them together.

### Example

```text
rwx

4 + 2 + 1 = 7
```

```text
rw-

4 + 2 = 6
```

```text
r-x

4 + 1 = 5
```

```text
r--

4
```

## The Most Common Permission Values

### 777

```text
rwx rwx rwx
```

Everyone has full access.

❌ Never use this in production unless you fully understand the security implications.

### 755

```text
Owner   = rwx

Group   = r-x

Others  = r-x
```

Very common for executable scripts and directories.

### 644

```text
Owner = rw-

Group = r--

Others = r--
```

Very common for configuration and text files.

## Try It

Give:

```bash
chmod 755 test.sh
```

Check:

```bash
ls -l
```

Now:

```bash
chmod 644 test.sh
```

Check again:

```bash
ls -l
```

Observe how the permissions change.

## Symbolic Method

Instead of numbers:

```bash
chmod u+x test.sh
```

Means:

Give execute permission to the owner.

```bash
chmod g+w test.sh
```

Means:

Give write permission to the group.

```bash
chmod o-r test.sh
```

Means:

Remove read permission from others.

## Real DevOps Example

Imagine you create a deployment script.

```text
deploy.sh
```

If it isn't executable:

```bash
./deploy.sh
```

You'll get:

```text
Permission denied
```

Fix it:

```bash
chmod +x deploy.sh
```

Now it runs successfully.

This is something DevOps engineers encounter regularly.

## Interview Questions

### What does chmod do?

Answer:

chmod changes the permissions of files and directories.

### What does 755 mean?

Answer:

Owner: Read, Write, Execute

Group: Read, Execute

Others: Read, Execute

### What does 644 mean?

Answer:

Owner: Read, Write

Group: Read

Others: Read

### What does chmod +x file.sh do?

Answer:
Adds execute permission, allowing the file to be run as a script (assuming it has a valid interpreter line if needed).
