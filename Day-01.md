AWS DevOps Learning — Day 01
Lesson 1: Understanding the AWS Console

Before creating any AWS resources, it's important to understand the AWS Management Console and the services that DevOps engineers use frequently.

AWS Services — Simple Explanation

Think of AWS like a huge city, where each service has a specific purpose:

AWS Service	What It Is
EC2	Virtual Computers
S3	Cloud Storage
IAM	Users and Permissions
VPC	Private Network
RDS	Managed Databases
CloudWatch	Monitoring and Logging
CloudShell	Linux Terminal in the Browser

These services are commonly used in real-world DevOps environments.

Step 1 — Check Your AWS Region

The first thing to check when working with AWS is the Region.

Look at the top-right corner of the AWS Console.

You may see regions such as:

Asia Pacific (Mumbai)
Asia Pacific (Hyderabad)
US East (N. Virginia)
Europe (Frankfurt)
Why is the AWS Region important?

AWS resources are created inside a specific geographical region.

For example:

EC2 Instance
      ↓
AWS Region
      ↓
Asia Pacific (Mumbai)


The region you select can affect:

Resource availability
Latency
Pricing
Data location
Service availability

Learning rule: Don't change the region yet. First understand which region is currently selected.

My Current AWS Region
Region: __________________________

Step 2 — Open AWS CloudShell

AWS CloudShell will be our first Linux environment.

There are two ways to open it.

Option 1 — From the AWS Console

Look at the bottom-left area of the AWS Console and click:

CloudShell

Option 2 — Using AWS Search

Use the AWS search bar at the top and search for:

CloudShell


Then open AWS CloudShell.

The first time you open CloudShell, AWS may take a minute or two to prepare the environment.

What is AWS CloudShell?

AWS CloudShell is a browser-based terminal provided by AWS.

It gives us a Linux shell directly inside the AWS Console.

Instead of installing Linux on our local computer, we can use CloudShell to practice Linux commands and interact with AWS.

A simple way to think about it:

Your Browser
     │
     ▼
AWS Console
     │
     ▼
AWS CloudShell
     │
     ▼
Linux Terminal

AWS CloudShell + Linux

Learning Linux through CloudShell will be useful later when working with many DevOps tools and technologies.

The Linux skills we learn here will help with:

Jenkins
Docker
Kubernetes
Terraform
Ansible
EC2
DevOps automation
DevOps interviews

Linux is one of the fundamental skills for a DevOps engineer.

Rule for Our Learning

Don't just copy commands. Understand what every command does.

For every command, ask three questions:

What does it do?
Why do we use it?
When would we use it in a real project?

This will help us build actual understanding instead of simply memorizing commands.

Basic Linux Commands

We will start with five simple Linux commands.

1. pwd
Meaning

Print Working Directory

Purpose

Shows the directory/location where you are currently working.

Example:

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

Example:

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

Example:

whoami


Possible output:

cloudshell-user


This is useful for understanding which user account is currently executing commands.

4. date
Meaning

Displays the current system date and time.

Example:

date


Possible output:

Fri Sep 11 12:51:00 UTC 2026


The exact output will depend on the environment and system configuration.

5. clear
Meaning

Clears the terminal screen.

Example:

clear


This does not delete your files or commands. It simply clears the visible terminal output.

Linux Commands — Quick Reference
Command	Meaning	Purpose
pwd	Print Working Directory	Shows the current location
ls	List	Shows files and folders
whoami	Current User	Shows the logged-in Linux user
date	Date/Time	Displays the current system date and time
clear	Clear Terminal	Clears the terminal screen
Practice

Run the following commands one by one in AWS CloudShell:

pwd
ls
whoami
date
clear


Try to understand the output of each command rather than simply copying it.

Key Takeaways

Today I learned:

What the AWS Management Console is.
What an AWS Region is.
Why the AWS Region matters.
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

Continue building Linux fundamentals and gradually connect these Linux concepts with AWS and DevOps tools.

Goal: Understand first. Automate later. 🚀
