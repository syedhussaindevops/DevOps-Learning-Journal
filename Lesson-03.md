# Lesson 3

## Linux File Management

Today we're going to learn how to create, copy, move, rename, and delete files and folders.

These are commands every DevOps engineer uses daily.

## Command 1

```bash
mkdir DevOps
```

### What happened?

A new folder called DevOps was created.

Now check:

```bash
ls
```

You should see

```text
DevOps
```

## Command 2

Move inside it.

```bash
cd DevOps
```

Check location.

```bash
pwd
```

Example

```text
/home/cloudshell-user/DevOps
```

Now you are inside the DevOps folder.

## Command 3

Create your first file.

```bash
touch linux.txt
```

Verify

```bash
ls
```

Output

```text
linux.txt
```

## Command 4

Write something into the file.

```bash
echo "Welcome to DevOps" > linux.txt
```

Read it.

```bash
cat linux.txt
```

Output

```text
Welcome to DevOps
```

## Command 5

Now copy the file.

```bash
cp linux.txt linux-copy.txt
```

Check

```bash
ls
```

Output

```text
linux.txt
linux-copy.txt
```

## Real World

Imagine your deployment configuration is very important.

Instead of editing the original, engineers often create a backup.

Example

```text
deployment.yaml
deployment-backup.yaml
```

## Command 6

Rename a file.

```bash
mv linux-copy.txt notes.txt
```

Now

```bash
ls
```

Output

```text
linux.txt
notes.txt
```

### Remember

mv has two jobs:

- Move files
- Rename files

## Command 7

Create another folder.

```bash
mkdir Practice
```

Move the file into it.

```bash
mv notes.txt Practice/
```

Go inside

```bash
cd Practice
```

Check

```bash
ls
```

Output

```text
notes.txt
```

## Command 8

Go back one folder.

```bash
cd ..
```

Think of this like going one level up.

## Command 9

Delete a file.

```bash
rm linux.txt
```

Verify

```bash
ls
```

## Command 10

Delete an empty folder.

```bash
rmdir Practice
```

If it says the directory is not empty, that's expected because notes.txt is still inside it.

In that case:

```bash
rm Practice/notes.txt
rmdir Practice
```

## Interview Questions

### Q1. What is the difference between cp and mv?

Answer

cp creates a copy.

mv moves or renames.

### Q2. Difference between rm and rmdir?

Answer

rm removes files.

rmdir removes empty directories.
