AWS DevOps Learning — Day 01
Lesson 1: Understanding the AWS Console

Before creating anything, I first learned about the AWS Management Console and some of the AWS services commonly used by DevOps engineers.

Think of AWS like a huge city where every service has a specific purpose.

AWS Service	What It Is
EC2	Virtual Computers
S3	Cloud Storage
IAM	Users and Permissions
VPC	Private Network
RDS	Databases
CloudWatch	Monitoring
CloudShell	Linux Terminal in the Browser

These services are frequently used in real-world DevOps environments.

Step 1 — Check Your AWS Region

The first thing to check when working with AWS is the Region.

The AWS Region can be found in the top-right corner of the AWS Console.

Some examples of AWS Regions are:

Asia Pacific (Mumbai)
Asia Pacific (Hyderabad)
US East (N. Virginia)
Europe (Frankfurt)
Why is the AWS Region important?

AWS resources are created inside a specific geographical region.

The selected Region can affect:

Resource availability
Latency
Pricing
Data location
Service availability

Important: Don't change the Region yet. First understand which Region is currently selected.

My Current AWS Region
Region: __________________________

Step 2 — Open AWS CloudShell

AWS CloudShell will be my first Linux environment.

There are two ways to open CloudShell.

Option 1 — From the AWS Console

Look at the bottom-left area of the AWS Console and click:

CloudShell

Option 2 — Using the AWS Search Bar

Use the AWS search bar at the top and search for:

CloudShell


Then open AWS CloudShell.

The first time CloudShell is opened, AWS may take a minute or two to prepare the environment.

What is AWS CloudShell?

AWS CloudShell is a browser-based Linux terminal provided by AWS.

It allows us to use a Linux shell directly from the AWS Console without installing Linux on our local computer.

A simple way to understand it:

My Browser
     |
     v
AWS Console
     |
     v
AWS CloudShell
     |
     v
Linux Terminal

AWS CloudShell + Linux

Learning Linux through CloudShell will help me later when working with various DevOps tools and technologies.

The Linux skills learned here will be useful for:

Jenkins
Docker
Kubernetes
Terraform
Ansible
EC2
DevOps automation
DevOps interviews
Rule for My Learning

Don't just copy commands. Understand what every command does.

For every command, I should understand:

What does it do?
Why do we use it?
When do we use it in real-world projects?

The goal is to build understanding, not just memorize commands.

Basic Linux Commands

Today I learned five basic Linux commands.

1. pwd
Meaning

Print Working Directory

Purpose

Shows the directory/location where I am currently working.

Example
pwd


Possible output:

/home/cloudshell-user


Think of it as asking Linux:

"Where am I?"

2. ls
Meaning

List

Purpose

Shows the files and folders inside the current directory.

Example
ls


Possible output:

file1.txt
projects
scripts


Think of it as asking Linux:

"What is inside this folder?"

3. whoami
Meaning

Who am I?

Purpose

Shows the current Linux user.

Example
whoami


Possible output:

cloudshell-user


This helps us understand which user account is currently executing commands.

4. date
Meaning

Displays the current system date and time.

Example
date


Possible output:

Fri Sep 11 12:51:00 UTC 2026


The exact output may be different depending on the environment and system configuration.

5. clear
Meaning

Clears the terminal screen.

Example
clear


This does not delete files or remove anything from the system.

It simply clears the visible terminal output.

Linux Commands — Quick Reference
Command	Meaning	Purpose
pwd	Print Working Directory	Shows the current location
ls	List	Shows files and folders
whoami	Current User	Shows the logged-in Linux user
date	Date/Time	Displays the current system date and time
clear	Clear Terminal	Clears the terminal screen
Practice

I ran the following commands in AWS CloudShell:

pwd
ls
whoami
date
clear


Instead of just copying the commands, I focused on understanding what each command does and why it is useful.

Key Takeaways

Today I learned:

What the AWS Management Console is.
What an AWS Region is.
Why the AWS Region is important.
What AWS CloudShell is.
How CloudShell provides a Linux terminal in the browser.
Basic Linux commands.
The importance of understanding commands instead of blindly copying them.
Commands Learned
pwd      → Where am I?
ls       → What is here?
whoami   → Who am I?
date     → What is the current date/time?
clear    → Clear the terminal screen

Day 01 Progress
 Checked AWS Region
 Opened AWS CloudShell
 Ran pwd
 Ran ls
 Ran whoami
 Ran date
 Ran clear
 Understood what each command does
Next Step

Continue learning Linux fundamentals and gradually connect these Linux concepts with AWS and DevOps tools.

Goal: Understand first. Automate later. 🚀
