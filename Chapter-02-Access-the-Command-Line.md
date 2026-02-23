# Chapter 2: Access the Command Line

## Goals
- 

## Key Commands
| **Main commands** |
|---|
| [whoami](#whoami) |
| [date](#date) |
| [passwd](#passwd) |
| [file](#file) |
| [cat](#cat) |
| [head](#head) |
| [tail](#tail) |
| [wc](#wc) |
| [history](#history) |
| [Shortcuts](#shortcuts) |

Print the username of current user
```bash
[user@host ~]$ whoami
user
```
How to combine more than one command in a single line
```bash
[user@host ~]$ command1; command2
```
Display current date and time
```bash
[user@host ~]$ date
Sun 22 Feb 2026 05:21:42 PM +08
[user@host ~]$ date +%R
17:24
[user@host ~]$ date +%x
22/02/2026
```
Changing password for user user.
```bash
[user@host ~]$ passwd
Changing password for user user.
Current password: old_password
New password: new_password
Retype new password: new_password
passwd: all authentication tokens updated successfully.
```
Display file type and its name
```bash
[user@host ~]$ file /bin/passwd
/bin/passwd: setuid ELF 64-bit LSB shared object, x86-64, version 1 
(SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, 
for GNU/Linux 3.2.0, BuildID[sha1]=a3637110e27e9a48dced9f38b4ae43388d32d0e4,
 stripped
[user@host ~]$ file /home
/home: directory
```
