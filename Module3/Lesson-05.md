## Lesson 5 – Linux Process Management

By the end of this lesson, you'll understand:

- What is a process?
- Foreground vs Background processes
- Process ID (PID)
- ps
- top
- kill
- killall
- jobs
- bg
- fg
- nohup
- Real DevOps troubleshooting

## What is a Process?

A process is simply a program that is currently running.

For example:

Chrome running → Process  
Jenkins running → Process  
Docker running → Process  
Java application running → Process

Think of it like this:

```text
Program (Stored on Disk)
        │
        ▼
When Executed
        │
        ▼
Process (Running in Memory)
```

## Real DevOps Scenario

A developer calls you:

"The application is down."

As a DevOps Engineer, the first thing you'll check is:

Is the application process running?

## Command 1 – ps

Shows running processes.

Run:

```bash
ps
```

Example:

```text
PID   TTY      TIME     CMD
1234  pts/0    00:00:00 bash
5678  pts/0    00:00:00 ps
```

### Show All Processes

```bash
ps -ef
```

Example:

```text
UID      PID   PPID   CMD
root       1      0   systemd
root     420      1   sshd
cloudshell 900    1   bash
```

### Important Columns

| Column | Meaning |
|---|---|
| PID | Process ID |
| PPID | Parent Process ID |
| CMD | Command running |

## Command 2 – top

Run:

```bash
top
```

You'll see live system information:

- CPU Usage
- Memory Usage
- Running Processes
- Process IDs

This is one of the most-used Linux monitoring commands.

### Exit:

Press:

```text
q
```

## Command 3 – kill

Every process has a PID.

Suppose PID is:

```text
4521
```

Stop it:

```bash
kill 4521
```

### Force Kill

Sometimes a process doesn't stop.

Use:

```bash
kill -9 4521
```

⚠️ Use kill -9 carefully, as it doesn't allow the application to shut down gracefully.

## Command 4 – killall

Instead of PID:

```bash
killall java
```

Stops all Java processes.

Another example:

```bash
killall nginx
```

## Command 5 – jobs

Start a background task:

```bash
sleep 300 &
```

Check:

```bash
jobs
```

Output:

```text
[1]+ Running sleep 300 &
```

### Background Process (&)

Normally:

```bash
sleep 300
```

Terminal waits.

Instead:

```bash
sleep 300 &
```

Runs in the background.

You can continue using the terminal.

## Command 6 – fg

Bring the background job back:

```bash
fg
```

Now it's in the foreground.

## Command 7 – bg

Suppose you started:

```bash
sleep 500
```

Press:

```text
Ctrl + Z
```

Process is suspended.

Resume it in the background:

```bash
bg
```

## Command 8 – nohup

Very important for servers.

Run:

```bash
nohup sleep 300 &
```

Output:

```text
appending output to nohup.out
```

Even if you close the terminal,

the process keeps running.

### Why nohup?

Without it:

```text
Close Terminal
      │
      ▼
Process Stops
```

With nohup:

```text
Close Terminal
      │
      ▼
Process Keeps Running
```

## Real DevOps Example 1

Developer says:

"Application isn't responding."

Check:

```bash
ps -ef | grep java
```

If nothing appears,

the Java application isn't running.

## Real DevOps Example 2

CPU usage is high.

Run:

```bash
top
```

Find the process consuming CPU.

Stop it (if appropriate):

```bash
kill PID
```

## Real DevOps Example 3

Jenkins service hangs.

Find it:

```bash
ps -ef | grep jenkins
```

Restart the service if needed:

```bash
sudo systemctl restart jenkins
```

(We'll learn systemctl later.)

## Command Combination

Find Java process:

```bash
ps -ef | grep java
```

Find Docker process:

```bash
ps -ef | grep docker
```

Find Jenkins process:

```bash
ps -ef | grep jenkins
```

## Interview Questions

### Q1. What is a process?

Answer:

A process is a program that is currently running in memory.

### Q2. What does ps -ef do?

Answer:

Displays detailed information about all running processes.

### Q3. Difference between kill and kill -9?

Answer:

kill sends a termination signal, allowing the application to shut down gracefully.

kill -9 forcefully stops the process immediately.

### Q4. What does top do?

Answer:

Displays real-time information about CPU, memory, and running processes.

### Q5. What is nohup?

Answer:

nohup allows a process to continue running even after the terminal session is closed.

### Q6. Difference between Foreground and Background Process?

| Foreground | Background |
|---|---|
| Uses the current terminal | Runs without blocking the terminal |
| Terminal waits | Terminal remains available for other commands |

## Commands Learned Today

| Command | Purpose |
|---|---|
| `ps` | Show running processes |
| `ps -ef` | Detailed process list |
| `top` | Live process monitoring |
| `kill PID` | Stop a process |
| `kill -9 PID` | Force stop a process |
| `killall` | Stop processes by name |
| `jobs` | List background jobs |
| `bg` | Resume a job in the background |
| `fg` | Bring a job to the foreground |
| `nohup` | Keep a process running after logout |
