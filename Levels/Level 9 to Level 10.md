# Bandit Level 9 → Level 10

## Level Goal

The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several ‘=’ characters.

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

# Answer

To solve Bandit Level 9 → Level 10, follow these steps:

1. Log into the server for Level 9 using SSH. The command is:

   ```bash
   ssh bandit9@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 8).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory and locate the `data.txt` file:

   ```bash
   ls
   ```

4. To find the password in `data.txt` preceded by several '=' characters, you can use the `strings` command along with `grep`:

   ```bash
   strings data.txt | grep "====="
   ```

   This command searches for human-readable strings in `data.txt` and filters out lines containing several '=' characters.

5. The password for the next level will be displayed.

   ```
   G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
   ```

6. Now, you have the password for Level 10. Use it to log in to Level 10 using SSH:

   ```bash
   ssh bandit10@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the line with several '=' characters when prompted.
