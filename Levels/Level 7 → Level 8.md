# Bandit Level 7 → Level 8

## Level Goal

The password for the next level is stored in the file `data.txt` next to the word `millionth`.

## Commands you may need to solve this level

- `man`
- `grep`
- `sort`
- `uniq`
- `strings`
- `base64`
- `tr`
- `tar`
- `gzip`
- `bzip2`
- `xxd`

# Answer

To solve Bandit Level 7 → Level 8, follow these steps:

1. Log into the server for Level 7 using SSH. The command is:

   ```bash
   ssh bandit7@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 6).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory and locate the `data.txt` file:

   ```bash
   ls
   ```

4. Now, you need to search for the password in `data.txt` next to the word "millionth." You can use the `grep` command:

   ```bash
   grep millionth data.txt
   ```

   This command will display the line containing the word "millionth" in the `data.txt` file.

5. The password for the next level will be displayed.

   ```
   TESKZC0XvTetK0S9xNwm25STk5iWrBvP
   ```

6. Now, you have the password for Level 8. Use it to log in to Level 8 using SSH:

   ```bash
   ssh bandit8@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found next to the word "millionth" when prompted.
