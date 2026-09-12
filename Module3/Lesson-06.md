## Lesson 6 – Linux Package Management & Services

By the end of this lesson, you'll understand:

- What is a package?
- Package managers (apt, yum, dnf)
- Install, update, remove software
- Linux Services
- systemctl
- journalctl
- Real DevOps examples

## What is a Package?

Think of a package like an app installer on Windows.

For example:

Windows:

```text
ChromeSetup.exe
```

Linux:

```text
docker
git
jenkins
nginx
java
```

Instead of downloading installers manually, Linux uses a Package Manager.

## Package Managers

Different Linux distributions use different package managers.

| Linux Distribution | Package Manager |
|---|---|
| Ubuntu | apt |
| Debian | apt |
| Amazon Linux 2 | yum |
| Amazon Linux 2023 | dnf |
| CentOS | yum |
| RHEL | yum / dnf |

## Which One Will We Use?

Since we'll later use AWS EC2 (Amazon Linux), you'll mostly work with:

```text
yum
```

and

```text
dnf
```

However, many interview questions ask about both apt and yum, so you should know all of them.

## Command 1 – Update Package Information

### Ubuntu

```bash
sudo apt update
```

### Amazon Linux

```bash
sudo yum update
```

or

```bash
sudo dnf update
```

This refreshes package information and installs available updates.

## Command 2 – Install Software

### Ubuntu

```bash
sudo apt install git
```

### Amazon Linux

```bash
sudo yum install git
```

or

```bash
sudo dnf install git
```

## Command 3 – Remove Software

### Ubuntu

```bash
sudo apt remove nginx
```

### Amazon Linux

```bash
sudo yum remove nginx
```

## Command 4 – Search Packages

### Ubuntu

```bash
apt search docker
```

### Amazon Linux

```bash
yum search docker
```

## Verify Installation

Example:

```bash
git --version
```

Output:

```text
git version 2.x.x
```

## What is a Service?

Some applications need to run continuously in the background.

Examples:

```text
Jenkins
Docker
Nginx
Apache
SSH
```

These are called services.

## Real DevOps Example

Imagine Jenkins is installed.

If Jenkins is stopped,

Nobody can trigger CI/CD pipelines.

Your first task is to check:

Is Jenkins service running?

## Command 5 – Check Service Status

```bash
sudo systemctl status docker
```

Example:

```text
Active: active (running)
```

If it says:

```text
inactive
```

The service is stopped.

## Command 6 – Start a Service

```bash
sudo systemctl start docker
```

## Command 7 – Stop a Service

```bash
sudo systemctl stop docker
```

## Command 8 – Restart a Service

```bash
sudo systemctl restart docker
```

This is one of the most frequently used commands.

## Command 9 – Reload a Service

```bash
sudo systemctl reload nginx
```

Reload applies configuration changes without fully restarting the service.

## Command 10 – Enable a Service

Start automatically when the server boots.

```bash
sudo systemctl enable docker
```

## Command 11 – Disable a Service

```bash
sudo systemctl disable docker
```

## Command 12 – Check if a Service is Enabled

```bash
systemctl is-enabled docker
```

Example:

```text
enabled
```

## Command 13 – List Running Services

```bash
systemctl list-units --type=service
```

## Viewing Logs with journalctl

Many Linux services write logs to the system journal.

View recent logs for Docker:

```bash
sudo journalctl -u docker
```

Follow logs live:

```bash
sudo journalctl -fu docker
```

This is similar to:

```bash
tail -f logfile
```

## Real DevOps Scenario 1

A developer says:

"Docker isn't working."

Check:

```bash
sudo systemctl status docker
```

If stopped:

```bash
sudo systemctl start docker
```

Verify:

```bash
sudo systemctl status docker
```

## Real DevOps Scenario 2

Jenkins UI is not opening.

Check:

```bash
sudo systemctl status jenkins
```

If failed:

```bash
sudo journalctl -u jenkins
```

Review the logs for the root cause.

## Real DevOps Scenario 3

Nginx configuration changed.

Instead of rebooting the server:

```bash
sudo systemctl reload nginx
```

## Interview Questions

### Q1. What is a package manager?

Answer:

A package manager installs, updates, removes, and manages software packages on Linux.

### Q2. Difference between apt and yum?

Answer:

apt is commonly used on Debian and Ubuntu.

yum is commonly used on CentOS, RHEL, and Amazon Linux 2.

Newer Red Hat–based systems often use dnf, which replaces yum while maintaining compatibility.

### Q3. What does systemctl do?

Answer:

systemctl is used to manage Linux services, including starting, stopping, restarting, enabling, and checking their status.

### Q4. Difference between start and enable?

| Start | Enable |
|---|---|
| Starts the service now | Starts the service automatically after reboot |

### Q5. Why use journalctl?

Answer:

journalctl displays logs collected by systemd, making it useful for troubleshooting service failures.

## Commands Learned Today

| Command | Purpose |
|---|---|
| `apt update / yum update / dnf update` | Update package information |
| `apt install / yum install` | Install software |
| `apt remove / yum remove` | Remove software |
| `systemctl status` | Check service status |
| `systemctl start` | Start a service |
| `systemctl stop` | Stop a service |
| `systemctl restart` | Restart a service |
| `systemctl reload` | Reload configuration |
| `systemctl enable` | Start service on boot |
| `systemctl disable` | Disable auto-start |
| `journalctl -u` | View service logs |
| `journalctl -fu` | Follow service logs live |
