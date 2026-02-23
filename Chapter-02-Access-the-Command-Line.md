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
Viewing the contents of a file
```bash
[user@host ~]$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
...output omitted...
```
To view the contents of multiple files
```bash
[user@host ~]$ cat file1 file2
Hello World!!
Introduction to Linux commands.
```
Display first 10 lines of a file
```bash
[user@host ~]$ head /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
```
Display last 3 lines of a file
```bash
[user@host ~]$ tail -n 3 /etc/passwd
gdm:x:42:42::/var/lib/gdm:/sbin/nologin
gnome-initial-setup:x:977:977::/run/gnome-initial-setup/:/sbin/nologin
avahi:x:70:70:Avahi mDNS/DNS-SD Stack:/var/run/avahi-daemon:/sbin/nologin
```
**Counts lines, words, and characters** in a file. Use the -l, -w, or -c options to display only the given number of lines, words, or characters, respectively.
```bash
[user@host ~]$ wc /etc/passwd
  45  102 2480 /etc/passwd
[user@host ~]$ wc -l /etc/passwd ; wc -l /etc/group
45 /etc/passwd
70 /etc/group
[user@host ~]$ wc -c /etc/group /etc/hosts
 966 /etc/group
 516 /etc/hosts
1482 total
```
**TAB COMPLETION**  
Allows a user to quickly complete commands or file names after they have typed
enough at the prompt to make it unique. If the characters typed are not unique, pressing the Tab
key twice displays all commands that begin with the characters already typed.

- Single press completes as much of the file name as possible
- Double press list all of the files that are matched by the current pattern.

Writing long commands in multiple lines
```bash
[user@host]$ head -n 3 \
> /usr/share/dict/words \
> /usr/share/dict/linux.words
==> /usr/share/dict/words <==
1080
10-point
10th
==> /usr/share/dict/linux.words <==
1080
10-point
10th
[user@host ~]$ 
```
Display the Command History
```bash
[user@host ~]$ history
...output omitted...
   23  clear
   24  who
   25  pwd
   26  ls /etc
   27  uptime
   28  ls -l
   29  date
   30  history
[user@host ~]$ !ls
ls -l
total 0
drwxr-xr-x. 2 user user 6 Mar 29 21:16 Desktop
...output omitted...
[user@host ~]$ !26
ls /etc
abrt                     hosts                     pulse
adjtime                  hosts.allow               purple
aliases                  hosts.deny                qemu-ga
...output omitted...
```
- The **!number** command expands to the command matching the
number specified.
- The **!string** command expands to the most recent command that begins with
the string specified.

### Useful Command-line Editing Shortcuts

| SHORTCUT | DESCRIPTION |
|---|---|
| `Ctrl + A` | Jump to the beginning of the command line. |
| `Ctrl + E` | Jump to the end of the command line. |
| `Ctrl + U` | Clear from the cursor to the beginning of the command line. |
| `Ctrl + K` | Clear from the cursor to the end of the command line. |
| `Ctrl + Left Arrow` | Jump to the beginning of the previous word on the command line. |
| `Ctrl + Right Arrow` | Jump to the end of the next word on the command line. |
| `Ctrl + R` | Search the history list of commands for a pattern. |
