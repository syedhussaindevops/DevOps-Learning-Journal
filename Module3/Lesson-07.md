Module 3 – Linux Advanced
Lesson 7 – Linux Networking for DevOps
🎯 Goal

By the end of this lesson, you'll understand:

What is Networking?
IP Address
Hostname
DNS
Ports
Network troubleshooting
Essential networking commands used by DevOps engineers
🧠 Why Should a DevOps Engineer Learn Networking?

Imagine this situation:

Developer:

"My application is not working."

Manager:

"Can you check why?"

You:

Starts troubleshooting...

The problem might not be the application.

It could be:

Wrong IP
DNS issue
Closed port
Firewall
Network connectivity
Server down

This is why networking is one of the most important DevOps skills.

Networking Basics

Imagine your home.

House Number

↓

10-2-15

Every house has a unique address.

Similarly,

Every computer has an address called an

IP Address
IP Address

Example

192.168.1.10


Just like your house number identifies your home,

an IP address identifies a computer on a network.

Hostname

Instead of remembering

192.168.1.10


we use

server01


or

jenkins-server


This is called the Hostname.

Command 1 – hostname

Check your system name.

hostname


Example:

ip-172-31-10-25

Command 2 – hostname -I

Show your IP address.

hostname -I


Example:

172.31.20.101

Command 3 – ip addr

Shows complete network information.

ip addr


You'll see:

Network interfaces
IP addresses
MAC address
Interface status

This command is widely used in Linux troubleshooting.

Command 4 – ping

Checks whether another server is reachable.

Example:

ping google.com


Output:

64 bytes from...


Stop:

Ctrl + C

What Does ping Tell You?

It answers a simple question:

Can I reach this server?

Real DevOps Example

Developer says:

"Application cannot connect to Database."

First check:

ping database-server


If ping fails,

the issue may be:

Network
Firewall
DNS
Server down
Command 5 – curl

One of the most used DevOps commands.

Example:

curl https://www.google.com


Returns the webpage HTML.

Instead,

check only headers:

curl -I https://www.google.com


Example output:

HTTP/2 200 OK

Why curl?

Suppose Jenkins is running on

http://server:8080


Check:

curl http://server:8080


If you receive a response,

the application is reachable.

Command 6 – wget

Download files.

Example:

wget https://example.com/file.zip


Useful for:

Downloading software
Scripts
Packages
Command 7 – ssh

Connect to another Linux server.

Example:

ssh ec2-user@10.0.0.20


or

ssh ubuntu@server-ip


This is one of the most frequently used commands by DevOps engineers.

Command 8 – scp

Copy files securely.

Copy local file to server:

scp app.jar ec2-user@10.0.0.20:/home/ec2-user/


Copy from server:

scp ec2-user@10.0.0.20:/home/ec2-user/app.log .

Command 9 – ss

Shows listening ports.

ss -tuln


Example:

LISTEN
22
80
443
8080

Why is ss Important?

Suppose Jenkins runs on

8080


Check:

ss -tuln


If 8080 isn't listening,

Jenkins isn't accepting connections.

Command 10 – netstat

Older alternative to ss.

netstat -tuln


Many companies still use it.

Command 11 – nslookup

Checks DNS resolution.

Example:

nslookup google.com


Returns:

IP Address
Command 12 – dig

More detailed DNS lookup.

dig google.com


Shows:

DNS Server
Response
TTL
Records
Command 13 – traceroute

Shows every network hop between your computer and the destination.

traceroute google.com


Useful for diagnosing routing issues.

Real DevOps Scenario 1

Developer:

"Website isn't opening."

Steps:

ping website.com

curl website.com

ss -tuln

Real DevOps Scenario 2

Jenkins not opening.

Check:

systemctl status jenkins

ss -tuln

curl localhost:8080

Real DevOps Scenario 3

Cannot SSH into EC2.

Check:

Is EC2 running?
Is port 22 open?
Is the Security Group allowing SSH?
Is the key pair correct?
Is the SSH service running?
Real DevOps Scenario 4

Application cannot connect to MySQL.

Check:

ping mysql-server

nslookup mysql-server

ss -tuln


Verify that MySQL is listening on port 3306.

Interview Questions
Q1. What is an IP address?

Answer:

An IP address uniquely identifies a device on a network.

Q2. What does ping do?

Answer:

It checks whether a remote host is reachable over the network and measures response time.

Q3. What is curl used for?

Answer:

curl sends HTTP requests to web servers or APIs and is commonly used to verify application availability.

Q4. Difference between SSH and SCP?
SSH	SCP
Remote login	Secure file transfer
Q5. Difference between ss and netstat?

Answer:

Both display network connections and listening ports. ss is faster and is the recommended modern replacement for netstat.

Q6. What is DNS?

Answer:

DNS (Domain Name System) translates human-readable names like google.com into IP addresses.

Commands Learned Today
Command	Purpose
hostname	Show system name
hostname -I	Show IP address
ip addr	Show network configuration
ping	Test connectivity
curl	Test web servers and APIs
wget	Download files
ssh	Connect to remote servers
scp	Securely copy files
ss -tuln	Show listening ports
netstat -tuln	Show network connections
nslookup	Check DNS resolution
dig	Detailed DNS lookup
traceroute	Trace the network path
