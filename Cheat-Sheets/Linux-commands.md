# Linux Commands Notes

These are Linux commands I practiced while learning terminal basics and solving some security labs. I wrote down what each command does, the syntax, and examples that I actually used while navigating the system.

Many of these commands were practiced while working inside the Linux terminal and while solving beginner challenges like OverTheWire Bandit.

---

## Command: ls
What it does: Lists files and directories in the current folder  
Syntax: `ls [options] [path]`  
Example: `ls -la ~/Downloads`  
Useful flags:
- `-l` → long format  
- `-a` → show hidden files  
- `-h` → human readable sizes  

What I learned: Hidden files starting with `.` only appear if `-a` is used.

---

## Command: cd
What it does: Changes the current directory  
Syntax: `cd [directory]`  
Example: `cd /var/log`  
Useful flags:
- `cd ..` → move one directory up  
- `cd ~` → go to home directory  

What I learned: Using `cd -` quickly switches back to the previous directory.

---

## Command: pwd
What it does: Prints the current working directory  
Syntax: `pwd`  
Example: `pwd`  

What I learned: Helpful when navigating deep directory structures during labs.

---

## Command: mkdir
What it does: Creates a new directory  
Syntax: `mkdir [directory_name]`  
Example: `mkdir practice_files`  

Useful flags:
- `-p` → creates parent directories if needed  

---

## Command: rmdir
What it does: Removes an empty directory  
Syntax: `rmdir [directory]`  
Example: `rmdir old_folder`

What I learned: It only works if the folder is empty.

---

## Command: rm
What it does: Deletes files or directories  
Syntax: `rm [options] file`  
Example: `rm notes.txt`

Useful flags:
- `-r` → delete directories recursively  
- `-f` → force delete  

What I learned: `rm -rf` is powerful and dangerous because it deletes without confirmation.

---

## Command: cp
What it does: Copies files or directories  
Syntax: `cp [options] source destination`  
Example: `cp notes.txt backup_notes.txt`

Useful flags:
- `-r` → copy directories  
- `-v` → verbose output

---

## Command: mv
What it does: Moves or renames files  
Syntax: `mv source destination`  
Example: `mv notes.txt study_notes.txt`

What I learned: `mv` is also commonly used just to rename files.

---

## Command: touch
What it does: Creates an empty file  
Syntax: `touch filename`  
Example: `touch test.txt`

What I learned: Useful when creating files for practice or scripts.

---

## Command: cat
What it does: Displays the contents of a file  
Syntax: `cat file`  
Example: `cat passwords.txt`

Useful flags:
- `-n` → show line numbers

What I learned: Often used together with pipes.

Example:

`cat log.txt | grep error`

---

## Command: less
What it does: Views large files one page at a time  
Syntax: `less file`  
Example: `less /var/log/syslog`

What I learned: Press `q` to exit.

---

## Command: head
What it does: Shows the first lines of a file  
Syntax: `head [options] file`  
Example: `head -n 10 rockyou.txt`

Useful flags:
- `-n` → number of lines

---

## Command: tail
What it does: Shows the last lines of a file  
Syntax: `tail [options] file`  
Example: `tail -n 20 log.txt`

Useful flags:
- `-f` → follow updates in real time

What I learned: `tail -f` is useful when monitoring logs.

---

## Command: grep
What it does: Searches for specific text patterns  
Syntax: `grep [options] pattern file`  
Example: `grep password notes.txt`

Useful flags:
- `-i` → ignore case  
- `-r` → recursive search  
- `-n` → show line numbers  

What I learned: `grep` becomes very powerful when combined with pipes.

Example:

`cat access.log | grep 404`

---

## Command: find
What it does: Searches for files or directories  
Syntax: `find [path] [options]`  
Example: `find . -name "*.txt"`

Useful flags:
- `-name` → search by filename  
- `-type` → specify file type  
- `-size` → search by file size  

What I learned: Useful when files are buried deep in directories.

---

## Command: chmod
What it does: Changes file permissions  
Syntax: `chmod permissions file`  
Example: `chmod 755 script.sh`

What I learned: `755` allows owner full access but only read/execute for others.

---

## Command: chown
What it does: Changes file ownership  
Syntax: `chown user:group file`  
Example: `sudo chown root:root config.txt`

Useful flags:
- `-R` → recursive ownership change

---

## Command: whoami
What it does: Displays the current logged-in user  
Syntax: `whoami`  
Example: `whoami`

What I learned: Helpful to confirm privilege levels during labs.

---

## Command: id
What it does: Displays user and group IDs  
Syntax: `id`  
Example: `id`

What I learned: Shows UID and groups associated with the user.

---

## Command: uname
What it does: Shows system information  
Syntax: `uname [options]`  
Example: `uname -a`

Useful flags:
- `-a` → shows all system information

---

## Command: df
What it does: Shows disk space usage  
Syntax: `df [options]`  
Example: `df -h`

Useful flags:
- `-h` → human readable output

---

## Command: du
What it does: Displays disk usage of files or directories  
Syntax: `du [options] path`  
Example: `du -sh downloads`

Useful flags:
- `-s` → summary  
- `-h` → human readable

---

## Command: ps
What it does: Displays running processes  
Syntax: `ps [options]`  
Example: `ps aux`

What I learned: Helpful for checking processes consuming resources.

---

## Command: top
What it does: Displays real-time system processes and CPU usage  
Syntax: `top`  
Example: `top`

What I learned: Press `q` to exit the interface.

---

## Command: kill
What it does: Terminates a process  
Syntax: `kill PID`  
Example: `kill 1452`

Useful flags:
- `-9` → force kill

---

## Command: ping
What it does: Tests connectivity to another machine  
Syntax: `ping host`  
Example: `ping google.com`

Useful flags:
- `-c` → limit number of packets

Example:

`ping -c 4 google.com`

---

## Command: wget
What it does: Downloads files from the internet  
Syntax: `wget URL`  
Example: `wget https://example.com/file.zip`

Useful flags:
- `-c` → resume interrupted downloads

---

## Command: curl
What it does: Transfers data to or from servers  
Syntax: `curl URL`  
Example: `curl https://api.github.com`

Useful flags:
- `-O` → save output as file  
- `-I` → fetch headers only

---

## Command: history
What it does: Shows previously executed commands  
Syntax: `history`  
Example: `history`

What I learned: Useful for repeating previous commands quickly.

---

## Command: clear
What it does: Clears the terminal screen  
Syntax: `clear`  
Example: `clear`

---

## Conclusion

Practicing these commands helped me become more comfortable navigating the Linux terminal, managing files, and inspecting system processes. Many of these commands are frequently used in cybersecurity environments, especially when working through labs or analyzing system logs.
