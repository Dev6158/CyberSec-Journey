# Bandit Writeup (Level 0 → 10)

## Level 0 → 1
Command used: ssh bandit0@bandit.labs.overthewire.org -p 2220  
Password found: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If  
What I learned: How to connect to a remote server using SSH and retrieve file contents using basic commands like `ls` and `cat`.

---

## Level 1 → 2
Command used: cat ./-  
Password found: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx  
What I learned: Files starting with `-` are treated as options by commands. Using `./-` prevents it from being interpreted as a flag.

---

## Level 2 → 3
Command used: cat "spaces in this filename"  
Password found: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx  
What I learned: Filenames containing spaces must be quoted or escaped with backslashes.

---

## Level 3 → 4
Command used: ls -a inhere/  
Then: cat inhere/.hidden  
Password found: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ  
What I learned: Hidden files (starting with `.`) require `ls -a` to be visible.

---

## Level 4 → 5
Command used: file inhere/*  
Then: cat inhere/-file07  
Password found: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw  
What I learned: The `file` command helps identify file types. It is useful for distinguishing readable files among binary ones.

---

## Level 5 → 6
Command used: find inhere/ -type f -size 1033c ! -executable  
Then: cat <filename>  
Password found: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG  
What I learned: The `find` command can filter files based on size, type, and permissions.

---

## Level 6 → 7
Command used: find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null  
Then: cat /var/lib/dpkg/info/bandit7.password  
Password found: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj  
What I learned: How to search system-wide using `find` and suppress permission errors with `2>/dev/null`.

---

## Level 7 → 8
Command used: cat data.txt | grep millionth  
Password found: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc  
What I learned: The `grep` command is used to search for specific strings within files.

---

## Level 8 → 9
Command used: sort data.txt | uniq -u  
Password found: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM  
What I learned: Sorting is required before using `uniq`. `uniq -u` finds lines that appear only once.

---

## Level 9 → 10
Command used: strings data.txt | grep =  
Password found: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey  
What I learned: The `strings` command extracts readable text from binary files.

---

## Level 10 → 11
Command used: cat data.txt | base64 -d  
Password found: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR  
What I learned: Base64 encoding can be decoded using `base64 -d`.
