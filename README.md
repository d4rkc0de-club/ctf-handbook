# CTF Resources
This repository consists information and resources to get started and excel in CTFs.

---

## Table of Contents
- [Introduction](#introduction)
- [Resources](#general-resources)
  - [Basics](#basics)
  - [Web Exploitation](#web-exploitation)
  - [Binary Exploitation](#binary-exploitation)
  - [Reverse Engineering](#reverse-engineering)
  - [Cryptography](#cryptography)
  - [Forensics](#forensics)
  - [OSINT](#osint)
  - [Miscellaneous](#miscellaneous)
- [Most Important Note](#most-important-note)

---

# Introduction

---

## What actually are CTFs ?
A CTF is like a puzzle game for hackers. In simple words, we are given a machine or program which is hackeable and we get a string that we submit and we get points. The flags are usually in the form of `FLAG{y0u-h4v3-f0und-4-fl4g}`.

--- 

## How do CTFs work ?
CTFs are of different kinds but the kind that we have to focus on are **Jeopardy-style** which is solving standalone challenges from various categories to earn points. The categories include [web](#web-exploitation), [pwn](#binary-exploitation), [rev](#reverse-engineering), [cryto](#cryptography), [forensics](#forensics), [osint](#osint), and [misc](#miscellaneous).

### Scoring In CTF
The scoring can be of two types
#### 1. **Static Scoring**
Every challenge has a fixed value based on their defined difficulty. Ex - 100 for easy, 300 for medium and 500 for hard.

#### 2. **Dynamic Scoring**
This is the most common type of scoring. Points decrease as more teams solve the challenge. 

### CTFtime
It is the central hub for competitive CTFs. It tracks
- Upcoming & ongoing CTF events
- Team rankings
- CTF writeups and archives
- Links to scoreboards and challenges

CTF players use this to
- Plan which competitions to join
- Track performance
- View writeups and results

#### CTFtime Points
- CTFtime assigns rating point to teams based on their performance in rated CTFs.
- Only top 10 performances of a team are rated on CTFtime
- Each CTF is worth up to 100 CTFtime points
- The rankings reset ever calendar year

--- 

# Resources

---

## Basics
These are the basic things that you need to do if you are going to start cybersecurity. It is important to keep the basics clear if you want be be good. These basics include :
### Linux
In cybersecurity, linux is the go-to OS. It gives you control, power and tools that the cybersecurity relies on. Most of the servers in the world run on linux. You can get started with it in 3 ways.
- You can use the **windows subsystem for linux (WSL)** if you are on Windows.
- You can use virtual machines using softwares like VMware or VirtualBox.
- If like to take risks, you can just run it bare metal on your device.
#### Practice
- [pwn.college Linux Luminarium](https://pwn.college/linux-luminarium/)

### Basic Programming
You need to learn basic programming for cybersec but you are not expected to know everything in every language. The best way is to just learn python and then learn others if they align with your domain.
- **Python** - used for scripting, automation and exploit devlopment. You can learn this from 
    - [CSE 101 (Introduction to Programming) in IIITD](https://techtree.iiitd.edu.in/viewDescription/filename?=CSE101)
    - [Automate the Boring Stuff with Python](https://edu.anarcho-copy.org/Programming%20Languages/Python/Automate%20the%20Boring%20Stuff%20with%20Python.pdf)
    - [Hindi Course (Code with Harry)](https://www.youtube.com/watch?v=UrsmFxEIp5k)
    - [English Course (Programming with Mosh)](https://www.youtube.com/watch?v=_uQrJ0TkZlc)
- **C** - used for understanding low level bugs. 
    - [FreeCodeCamp](https://www.youtube.com/watch?v=KJgsSFOSQv0)
- **JS** - used for web-based CTFs.
    - [Eloquent Javascript](https://eloquentjavascript.net/)
- **Assembly** - used for reverse engineering. Both of these resources need to be followed.
    - [pwn.college Intro](https://pwn.college/computing-101/your-first-program/)
    - [pwn.college Assembly Crash Course](https://pwn.college/computing-101/assembly-crash-course/)

### Basic Cybersecurity Concepts
- [Pre Security Path Tryhackme](https://tryhackme.com/path/outline/presecurity)
- [Cyber Security 101 Tryhackme](https://tryhackme.com/path/outline/cybersecurity101)

### Basics Practice
- [picoCTF](https://picoctf.org/)

---

## Web Exploitation

### Overview
Web exploitation is a category of CTF challenges focused on finding and exploiting **vulnerabilities in web applications**. These simulate real-world attacks like breaking into websites, bypassing logins, stealing data, or executing unauthorized code.
You interact with a target web server through a browser or proxy tools, trying to **find flaws in logic, security controls, or code behavior**.
In a CTF challenge, you're typically given a live web app hosted at a URL. Your goal is to inspect and manipulate how the site functions until you can trigger a bug and retrieve a flag.

### Tools
- Burpsuite
- Owasp ZAP
- ffuf
- nmap
- nuclei
- gobuster
- CyberChef

### Learning and Practice
- [Penetration Tester Route Tryhackme](https://tryhackme.com/hacktivities?tab=roadmap) (only follow the web based stuff)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) — Interactive labs with theory for every major web vuln (XSS, SQLi, CSRF, etc.).
- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — Industry-standard list of the most critical web vulnerabilities.
- [picoCTF Web Challenges](https://play.picoctf.org/practice?category=3) — Beginner-level challenges with guided hints.
- [HackTheBox: Web Challenges](https://app.hackthebox.com/challenges/web) — Realistic CTF-style problems, including hosted services.

---

## Binary Exploitation

### Overview
Binary Exploitation (often shortened to Binex or pwn) is a category in CTFs that focuses on analyzing and exploiting compiled programs (binaries) to gain unintended behavior — like leaking information, hijacking control flow, or executing arbitrary code. The goal is to understand how the program works at a low level (assembly/memory) and take advantage of flaws in how it handles input, memory, or permissions.
This is one of the most technically deep categories in CTFs, often requiring knowledge of:
- Assembly language
- Memory layout (stack, heap, etc.)
- Calling conventions
- C/C++ programming
- Operating system internals
You typically receive a binary file (a.out, chall, vuln, etc.) and are told to find a way to make it do something it shouldn’t — like read the flag, spawn a shell, or overwrite memory.

### Learning and Practice
#### [pwn.college](https://pwn.college/)
  - [Introduction](https://pwn.college/intro-to-cybersecurity/binary-exploitation/) - Gets into basic buffer overflows, shell-coding and return oriented programming. (must do)
  - [Memory Errors](https://pwn.college/program-security/memory-errors/) - Gets into popular safety checks (ASLR, Canaries) and how to bypass them.
#### [ROP](https://ropemporium.com/index.html)
Teaches Return Oriented Programming, techniques like ret2win, ret2libc, ret2csu, stack pivoting etc.
#### [Heap Exploitation](https://github.com/shellphish/how2heap)
Teaches heap exploitation strategies with libc. Make use of the ret2 wargames that are linked in the repo.
#### [pwnable.kr](https://pwnable.kr/)
Skip baby's bottle if you know the basics (not recommended). Rookiss has some very good challenges that will teach you a lot, try solving those as you learn topics required for them.

#### pwntools
- It is a python library used to automate binary exploitation.
- [Tutorial](https://github.com/Gallopsled/pwntools-tutorial)

---

## Reverse Engineering

### Overview
It is the process of recovering, understanding and reconstructing the design, data structures and algorithms that were used to build software.
In CTFs, generally the objective will be to understand the given material (with a certain objective in mind) and recover information about the internal workings (often involving a bit of cryptography too) to eventually find a flag.
One example is password verification, you may be presented with a binary containing an algorithm to check if your password is right, your task would then be to understand what is being checked, how its being checked, and most probably implement a program to reverse the procedure to get a suitable solution.
The field itself is vast and has many sub-fields that you may focus on, for example : Game Hacking, Android Hacking, Malware Analysis, Hardware / Firmware Hacking etc.

### Tools
- [Ghidra](https://github.com/NationalSecurityAgency/ghidra) 
- [IDA](https://hex-rays.com/ida-free)
- [GDB](https://github.com/pwndbg/pwndbg)

### Learning and Practice
- [pwn.college Debugging Refresher](https://pwn.college/computing-101/debugging-refresher/) - Debugging (dynamic analysis) is something you will spend a lot of time doing, GDB is taught in this module however the knowledge is transferable to other debuggers too.
- [pwn.college Reverse Engineering](https://pwn.college/program-security/reverse-engineering/) - Here you will start actually reverse engineering binaries, it also gets a bit into Virtual Machine obfuscations (which is common in CTFs)
- [z3 Python CTF](https://github.com/ViRb3/z3-python-ctf) - Z3 the state-of-the-art SMT solver, it can be used to find inputs to satisfy complex algorithms. (very important)
- Angr - is a powerful symbolic execution engine that will help automate and speedup the process of finding inputs.
    - [Angr Practice](https://github.com/Hustcw/Angr_Tutorial_For_CTF/tree/master/problems)
    - [Angr Walkthrough](https://www.youtube.com/watch?v=QkVzjn3z0iw)
- [crackmes.one](https://crackmes.one/)
- Android
    - [Raging Rock](https://www.ragingrock.com/AndroidAppRE/)
    - [Frida-Labs](https://github.com/DERE-ad2001/Frida-Labs)
- Game Hacking
    - [Game Hacking Academy](https://gamehacking.academy/)
    - [Game-Reversing Github](https://github.com/kovidomi/game-reversing)

---

## Cryptography

### Overview
Cryptography challenges in CTFs focus on breaking or analyzing encrypted data. Unlike academic cryptography, which deals with designing secure systems, CTF crypto challenges usually involve breaking weak implementations, reversing custom schemes, or recognizing misuse of standard algorithms.
You are typically given some encrypted or encoded data and must figure out a way to decrypt it or extract useful information like a flag.

### Learning and Practice
- [Cryptohack](https://cryptohack.org/)
- [Sagemath](https://www.sagemath.org/)
- [dCode](https://www.dcode.fr/)

---

## Forensics

### Overview
Forensics in CTFs is all about analyzing digital artifacts to uncover hidden information, recover deleted content, or trace suspicious activity. The challenges simulate real-world digital investigations, like digging through disk images, network traffic, memory dumps, or suspicious files.
Unlike other CTF categories that may involve breaking code or exploiting vulnerabilities, forensics focuses more on extracting and interpreting data that’s already present, sometimes hidden, obfuscated, or buried in metadata.

### Tools
- strings
- binwalk
- exiftool
- steghide
- Wireshark
- CyberChef

### Learning and Practice
- Hack the Box
- TryHackMe
- picoCTF
- CTFlearn
- Root Me 

---

## Miscellaneous

### Overview
Miscellaneous (misc) is a catch-all category in Capture The Flag competitions. It includes challenges that don’t clearly fit into other categories like pwn, web, crypto, or forensics. These problems often test creativity, outside-the-box thinking, real-world knowledge, or specialized tools.
Because it’s broad, misc challenges vary a lot, but they're often among the most fun and diverse problems in a CTF.

### Tools
- Cyberchef
- sherlock
- archive.org
- LLMs (especially ChatGPT)
- Social Media Sites
- Search Engines (google dorking)

### Learning and Practice
- For OSINT , you can practice on [GeoGuessr](https://www.geoguessr.com/)
- Learning and practice of this type is usually done by just participating in CTFs.

---

# **Most Important Note**
The real learning begins when you get your hands dirty.
Don’t wait until you feel “ready”. Just jump into CTFs and start solving! Even if you struggle or don’t score well at first, every challenge teaches you something valuable. The best way to grow in cybersecurity is to keep showing up, keep practicing, and never stop learning. Progress might feel slow at times, but if you stay consistent, you'll be amazed at how far you go. 
Also try to read writeups of challenges in your free time.
Everyone starts somewhere. JUST START.

---

