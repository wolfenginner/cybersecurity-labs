# Lab 01: Linux Environment Setup & CLI Navigation

**Date:** July 2026  
**Level:** Junior / Beginner  
**Objective:** Set up Linux-based operating systems and implement basic file and directory management using the Command Line Interface (CLI).

## 1. Environment Setup
To begin my cybersecurity journey, I installed and configured two essential distributions in virtual environments:
* **Ubuntu:** To familiarize myself with a standard user/server environment.
* **Kali Linux:** The industry-standard distribution for security auditing and penetration testing (pentesting).

## 2. Command Practice & File Management
Instead of using the Graphical User Interface (GUI), I used the terminal to create and manage an organized directory structure.

### Navigation & Location
* `pwd` (Print Working Directory): Used to know my exact location in the system.
* `ls` (List): Used to list files and folders in the current directory.
* `cd` & `cd ..` (Change Directory): Used to navigate between folders and move back to the previous directory.

### File & Directory Manipulation
I practiced these commands by performing the following workflow:
1. Created a secure working directory using `mkdir Security_Lab`.
2. Switched to the folder using `cd Security_Lab` and created an empty text file using `touch report.txt`.
3. Moved the file to a new location to simulate archiving a final report: `mv report.txt /destination/path`.

### Safe Deletion
I practiced the difference between deleting empty directories and directories with content:
* `rmdir`: Applied to remove completely empty folders.
* `rm -r`: Used the recursive flag (`-r`) to delete directories containing files, understanding the risk and power of this command in production environments3.

```text
# ---- STEP 1: ENVIRONMENT SETUP ----
# Checking current user and system hostname
lobito@kali:~$ whoami
lobito@kali:~$ hostname
lobito@kali:~$ pwd

# Checking current network configuration and IP address
lobito@kali:~$ ip a


# ---- STEP 2: FILE MANIPULATION ----
# Creating a new lab folder and moving inside
lobito@kali:~$ mkdir Security_Lab
lobito@kali:~$ cd Security_Lab
lobito@kali~/Security_Lab$ pwd

# Creating a text report and verifying it exists
lobito@kali~/Security_Lab$ touch report.txt
lobito@kali~/Security_Lab$ ls
report.txt

# Moving the report to Documents and verifying the lab folder is now empty
lobito@kali~/Security_Lab$ mv report.txt /home/lobito/Documents/
lobito@kali~/Security_Lab$ ls


# ---- STEP 3: CLEANING UP & SAFE DELETION ----
# Going back to home directory and deleting the empty lab folder
lobito@kali~/Security_Lab$ cd ..
lobito@kali:~$ rmdir Security_Lab

# TESTING ERROR: Trying to use rmdir on a folder that is NOT empty
lobito@kali:~$ mkdir -p Practice/Nested_Folder
lobito@kali:~$ rmdir Practice
rmdir: failed to remove 'Practice': Directory not empty

# CORRECT COMMAND: Using recursive delete to remove the folder and its content safely
lobito@kali:~$ rm -r Practice
lobito@kali:~$
