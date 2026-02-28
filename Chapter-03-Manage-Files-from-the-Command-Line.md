# Chapter 3: Managing Files from the Command Line

## Goals
Copy, move, create, delete, and organize files while
working from the Bash shell.

## Objectives

- Describe how Linux organizes files, and the
purposes of various directories in the file
system hierarchy.
- Specify the location of files relative to the
current working directory and by absolute
location, determine and change your working
directory, and list the contents of directories.
- Create, copy, move, and remove files and
directories.
- Make multiple file names reference the same
file using hard links and symbolic (or "soft")
links.
- Efficiently run commands affecting many files
by using pattern matching features of the Bash
shell.

## The File System Hierarchy
<img width="573" height="219" alt="image" src="https://github.com/user-attachments/assets/583891d2-612f-4502-95cf-2b48369793d8" />  

File-system hierarchy is a single inverted tree of directories🌳  
This tree is inverted because the root of the
tree is said to be at the top of the hierarchy, and the branches of directories and subdirectories
stretch below the root.  

## Important Red Hat Enterprise Linux Directories
## Key Commands
| **Main commands** | Purpose |
|---|---|
| [`/usr`](#) | Installed software, shared libraries, include files, and read-only program data.<br><br>Important subdirectories include:<br>• `/usr/bin`: User commands<br>• `/usr/sbin`: System administration commands<br>• `/usr/local`: Locally customized software |
| [/etc](#) | Configuration files specific to this system. |
| [/var](#) | Variable data specific to this system that should persist between boots. Files that dynamically change, such as databases, cache directories, log files, printer-spooled documents, and website content may be found under **/var**.|
| [/run](#) | Runtime data for processes started since the last boot. This includes process ID files and lock files, among other things. The contents of this directory are recreated on reboot. This directory consolidates **/var/run** and **/var/lock** from earlier versions of Red Hat Enterprise Linux. |
| [/home](#) | Home directories are where regular users store their personal data and configuration files. |
| [/root](#) | Home directory for the administrative superuser, root. |
| [/tmp](#) | A world-writable space for temporary files. Files which have not been accessed, changed, or modified for 10 days are deleted from this directory automatically. Another temporary directory exists, **/var/tmp**, in which files that have not been accessed, changed, or modified in more than 30 days are deleted automatically. |
| [/boot](#) | Files needed in order to start the boot process. |
| [/dev](#) | Contains special device files that are used by the system to access hardware. |  

## ABSOLUTE PATHS
**Absolute Path** is the files exact location in the file system hierarchy. It begins at the root (/) directory and specifies each subdirectory that must be traversed to reach the specific file.

## Current Working Directory and Relative Paths
When a user logs in and opens a command window, the initial location is usually the user's home directory.  
Current working directory is the current location.  

Like an absolute path, a relative path identifies a unique file, specifying only the path necessary to
reach the file from the working directory. Recognizing relative path names follows a simple rule: A
path name with anything other than a forward slash as the first character is a relative path name.  

**linux File Systems are case-sensitive**
