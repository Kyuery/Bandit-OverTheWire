# Bandit Level 25 → Level 26

## Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not `/bin/bash`, but something else. Find out what it is, how it works, and how to break out of it.

## Commands you may need to solve this level

- `ssh`
- `cat`
- `more`
- `vi`
- `ls`
- `id`
- `pwd`

To solve Bandit Level 25 → Level 26, follow these steps:

### Step-by-Step Solution

1. **Log into Bandit Level 25**:

   ```bash
   ssh bandit25@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit25 when prompted.

2. **Check the shell for user bandit26**:

   ```bash
   cat /etc/passwd | grep bandit26
   ```

   This command will show the entry for bandit26, which includes the shell being used. You should see something like:

   ```
   bandit26:x:11026:11026:Bandit level 26:/home/bandit26:/usr/bin/showtext
   ```

3. **Understand the shell**:

   The shell is `/usr/bin/showtext`. Let's examine what this shell does:

   ```bash
   cat /usr/bin/showtext
   ```

   It might be a script or a binary. If it's a script, you can view its contents directly. If it's a binary, you'll need to find another way to understand it.

4. **Log into bandit26**:

   ```bash
   ssh bandit26@localhost -p 2220 -i bandit26.sshkey
   ```

   Use the password for bandit25 when prompted. This will log you into bandit26, but you'll be dropped into the custom shell `/usr/bin/showtext`.

5. **Break out of the custom shell**:

   The `/usr/bin/showtext` script is designed to show text files but may have vulnerabilities or escape sequences. Try exiting the script or interrupting it. One common technique is to check if it allows you to spawn a new shell:

   If it uses `more` or `less` to display text, you might be able to escape to a shell by:

   - Pressing `v` to open the current file in the default text editor (usually `vi` or `vim`).
   - Once in `vi` or `vim`, you can open a shell by typing:

     ```bash
     :set shell=/usr/bin/bash
     ```

     ```bash
     :set shell?
     ```

     ```bash
     :!bash
     ```

   If it uses `more`, you can try to escape by pressing `!` to execute a shell command.

6. **Find the password for bandit26**:

   Once you have access to a shell, you can navigate and find the password:

   ```bash
   cat /etc/bandit_pass/bandit26
   ```

   ```bash
   c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
   ```

7. **Log into bandit26 with the found password**:
   ```bash
   ssh bandit26@bandit.labs.overthewire.org -p 2220
   ```
   Use the password you found in the previous step.
