# Lesson 2: Linux Directories & Files

Imagine Linux is like your house.

🏠 Home = Your home directory  
📁 Directory = A folder  
📄 File = A document

Today we'll learn how to create folders, move between them, create files, and read file contents.

## Command

mkdir

### What does it mean?

mkdir = Make Directory

It creates a new folder.

```bash
mkdir DevOps
```

## Real-world use

You create folders to organize projects:

```text
Projects
├── Jenkins
├── Docker
├── Kubernetes
└── Terraform
```

## cd

### What does it mean?

cd = Change Directory

It lets you move into another folder.

```bash
cd DevOps
```

## touch

### What does it mean?

Creates an empty file.

```bash
touch notes.txt
```

## Real-world use

DevOps engineers create files such as:

```text
README.md
Dockerfile
Jenkinsfile
deployment.yaml
terraform.tf
```

## cat

### What does it mean?

cat = Concatenate

For now, think of it as:

"Show me what's inside a file."

```bash
cat notes.txt
```

Since the file is empty, nothing will be displayed.

## echo

echo prints text.

```bash
echo "Hello DevOps"
```

## Command Reference

| Command | Purpose |
|---|---|
| mkdir | Create a folder |
| cd | Move into a folder |
| touch | Create a file |
| echo | Print or write text |
| cat | Display file contents |

## Q: What is the difference between mkdir and touch?

### Answer:

mkdir creates a directory (folder).

touch creates an empty file.
