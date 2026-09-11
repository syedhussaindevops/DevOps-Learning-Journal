## Lesson 4 – File Searching & Text Processing

By the end of this lesson, you'll know how to:

- Find files quickly
- Search text inside files
- View log files
- Count lines and words
- Sort data
- Remove duplicates
- Extract specific columns

These commands are essential for troubleshooting applications and analyzing logs.

## Real DevOps Scenario

Imagine it's 2:00 AM.

A production application has crashed.

Your manager says:

"Find the error in the logs immediately."

The log file contains 500,000 lines.

Will you read them one by one?

❌ No.

You'll use Linux commands to locate the problem in seconds.

## Command 1 – find

Search for files or directories.

### Create a practice folder

```bash
mkdir search-lab
cd search-lab
```

```bash
touch app.log
touch server.log
touch database.log
touch notes.txt
```

### Search for a file:

```bash
find . -name "app.log"
```

Output:

```text
./app.log
```

### Find all log files:

```bash
find . -name "*.log"
```

Output:

```text
./app.log
./server.log
./database.log
```

## Command 2 – which

Find where a command is installed.

Example:

```bash
which git
```

Output:

```text
/usr/bin/git
```

Useful when checking if software is installed.

## Command 3 – whereis

Shows locations of binaries, source files, and manuals.

```bash
whereis git
```

Example:

```text
git: /usr/bin/git /usr/share/man/man1/git.1.gz
```

## Command 4 – cat

Display the contents of a file.

Create a file:

```bash
echo "Hello DevOps" > notes.txt
```

View it:

```bash
cat notes.txt
```

Output:

```text
Hello DevOps
```

## Command 5 – head

Display the first few lines.

Create a sample:

```bash
seq 20 > numbers.txt
```

View first 10 lines:

```bash
head numbers.txt
```

View first 5:

```bash
head -5 numbers.txt
```

## Command 6 – tail

Display the last few lines.

```bash
tail numbers.txt
```

Last 5 lines:

```bash
tail -5 numbers.txt
```

## One of the Most Important Commands

Follow a log file in real time:

```bash
tail -f application.log
```

This is one of the most commonly used commands by DevOps engineers during deployments and production support.

## Command 7 – grep

Search for text inside a file.

Create a sample log:

```bash
cat > app.log << EOF
INFO Application Started
INFO Database Connected
ERROR Database Timeout
INFO Request Received
ERROR Connection Failed
EOF
```

Search for errors:

```bash
grep ERROR app.log
```

Output:

```text
ERROR Database Timeout
ERROR Connection Failed
```

Case-insensitive search:

```bash
grep -i error app.log
```

## Command 8 – wc

Count lines, words, and characters.

```bash
wc app.log
```

Output:

```text
5 10 120 app.log
```

Only line count:

```bash
wc -l app.log
```

## Command 9 – sort

Sort data alphabetically.

```bash
cat > names.txt << EOF
John
Syed
Amit
Rahul
EOF
```

Sort:

```bash
sort names.txt
```

## Command 10 – uniq

Remove duplicate lines.

Create:

```bash
cat > duplicate.txt << EOF
AWS
Docker
AWS
Linux
Docker
EOF
```

Sort first:

```bash
sort duplicate.txt
```

Then remove duplicates:

```bash
sort duplicate.txt | uniq
```

Output:

```text
AWS
Docker
Linux
```

## Command 11 – cut

Extract specific columns.

Create:

```bash
cat > employees.csv << EOF
101,John,Developer
102,Syed,DevOps
103,Rahul,QA
EOF
```

Show only names:

```bash
cut -d "," -f2 employees.csv
```

Output:

```text
John
Syed
Rahul
```

## Command Combination

Linux becomes powerful when you combine commands.

### Find all errors:

```bash
grep ERROR app.log
```

### Count errors:

```bash
grep ERROR app.log | wc -l
```

### Find unique errors:

```bash
grep ERROR app.log | sort | uniq
```

## Real DevOps Examples

### Find Jenkins logs

```bash
find /var/log -name "*jenkins*"
```

### Search Kubernetes errors

```bash
grep ERROR application.log
```

### Monitor deployment logs

```bash
tail -f deployment.log
```

### Count failed requests

```bash
grep FAILED app.log | wc -l
```

## Interview Questions

### Q1. What does find do?

Answer:

Searches for files and directories based on criteria like name, type, or size.

### Q2. Difference between head and tail?

Answer:

head shows the beginning of a file.

tail shows the end of a file.

### Q3. Why is tail -f useful?

Answer:

It continuously displays new lines added to a log file, making it ideal for monitoring live applications.

### Q4. What does grep do?

Answer:

Searches for lines containing a specific pattern or text.

### Q5. What does wc -l do?

Answer:

Counts the number of lines in a file.

### Q6. Why use sort | uniq together?

Answer:

uniq only removes adjacent duplicate lines, so sorting first groups duplicates together.

## Commands Learned Today

| Command | Purpose |
|---|---|
| `find` | Search files and directories |
| `which` | Find executable path |
| `whereis` | Locate binary, source, and manual |
| `cat` | Display file contents |
| `head` | Show first lines |
| `tail` | Show last lines |
| `tail -f` | Monitor log files live |
| `grep` | Search text |
| `wc` | Count lines, words, characters |
| `sort` | Sort data |
| `uniq` | Remove duplicate lines |
| `cut` | Extract columns |
