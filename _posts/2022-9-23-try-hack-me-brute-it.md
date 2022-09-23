---
layout: post
title: Try Hack Me Room Brute It
---

# Et Tu, Brute It?

## Task 1 About this box

Try Hack Me breaks down our rooms into tasks. Our Task 1 in this room is mostly an introduction to the room and what we hope to learn about while we're here.
We should be learning about **-Brute-force -Hash cracking -Privilege escalation**
I find it useful to write these things down and refer back to it as sometimes we start to think our goal is to fill in all the answers in this room when really our goals should be to better our understanding of the concepts listed above

We also start the machine in Task 1 and then we're on our way

## Task 2 Reconnaissance

Our tasks are further broken down into separate questions and our first question for task 2 is How many ports are open?

### How many ports are open?

We actually get a straightforward instruction here to use nmap. I followed an example I found on the internet without knowing what the flags are doing. The first command I used was: **nmap -A -T4 [TARGET_IP_HERE]**

The hint for this question suggest using **nmap -sS -sV [TARGET_IP_HERE]**. I got the answer I needed and noted down that I should circle back around to understand what the nmap flags are doing on these commands.

The **-A** flag combines two flags, **-O** and **-sV** which gives us operating system information and tries to tell us what services are running on the machine. The **-T4** is a timing template, which I understand to mean that T0 is the slowest but most accurate setting and T5 would be the fastest least accurate setting.

![_config.yml]({{ site.baseurl }}/images/blog/brute/task2.jpg)

To compare this is what we get with only the **-T4** flag

![_config.yml]({{ site.baseurl }}/images/blog/brute/task2_2.jpg)

### What version of SSH is running?

Our nmap scan shows this to be Open SSH 7.6p1

### What version of Apache is running?

This is part of why we needed those flags, in the first picture above we can see Apache on port 80 running version 2.4.29

### Which Linux distribution is running?

Again something we get from the flags used, it shows Ubuntu as part of the server header and again is referenced in the OpenSSH version name. I assumed I didn't have this information already so this was a good reminder to note down information in case we need it for later.

### Search for hidden directories on the web server. What is the hidden directory?

I used dirbuster to search for hidden file directories. The hint on this suggested using the command **gobuster dir -u [TARGET_IP_HERE] -w common.txt**, I should do more research but I believe this is just a preference for one tool or the other.

## Task 3 Getting a shell

Coming soon

### What is the user:password of the admin panel?

### Crack the RSA key you found. What is John's RSA Private Key passphrase?

### user.txt

### Web flag

## Task 4 Privilege Escalation

Coming soon

### Find a form to escalate your privileges. What is the root's password?

### root.txt

