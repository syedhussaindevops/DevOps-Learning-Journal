# 📚 Lesson 2: Linux Directories & Files

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

Real-world use
You create folders to organize projects:

Projects
├── Jenkins
├── Docker
├── Kubernetes
└── Terraform

cd
What does it mean?
cd = Change Directory

It lets you move into another folder.

cd DevOps

touch
What does it mean?
Creates an empty file.

touch notes.txt

Real-world use
DevOps engineers create files such as:

README.md
Dockerfile
Jenkinsfile
deployment.yaml
terraform.tf

cat
What does it mean?
cat = Concatenate

For now, think of it as:

"Show me what's inside a file."

Example
cat notes.txt

Since the file is empty, nothing will be displayed.

echo
echo prints text.

Example
echo "Hello DevOps"

Command Reference
Command	Purpose
mkdir	Create a folder
cd	Move into a folder
touch	Create a file
echo	Print or write text
cat	Display file contents

Q: What is the difference between mkdir and touch?
Answer:

mkdir creates a directory (folder).

touch creates an empty file
