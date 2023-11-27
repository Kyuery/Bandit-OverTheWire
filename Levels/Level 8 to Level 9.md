# Bandit Level 8 → Level 9

## Level Goal

The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.

## Commands you may need to solve this level

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

## Helpful Reading Material

- Piping and Redirection

# Answer

To solve Bandit Level 8 → Level 9, follow these steps:

1. Log into the server for Level 8 using SSH. The command is:

   ```bash
   ssh bandit8@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 7).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory and locate the `data.txt` file:

   ```bash
   ls
   ```

4. Now, you need to find the line of text in `data.txt` that occurs only once. You can use a combination of commands to achieve this. One possible way is to use `sort` and `uniq`:

   ```bash
   sort data.txt | uniq -u
   ```

   This command sorts the lines in `data.txt` and then filters out the unique lines, showing only the lines that occur more than once.

5. The password for the next level will be displayed.

   ```
   EN632PlfYiZbn3PhVK3XOGSlNInNE00t
   ```

6. Now, you have the password for Level 9. Use it to log in to Level 9 using SSH:

   ```bash
   ssh bandit9@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the unique line when prompted.
