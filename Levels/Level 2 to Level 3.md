# Bandit Level 2 → Level 3

## Level Goal

The password for the next level is stored in a file called `spaces in this filename` located in the home directory.

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

## Helpful Reading Material

- Google Search for “spaces in filename”

# Answer

To solve Bandit Level 2 → Level 3, follow these steps:

1. Log into the server for Level 2 using SSH. The command is:

   ```bash
   ssh bandit2@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 1).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory:

   ```bash
   ls
   ```

   Look for a file named `spaces in this filename`.

4. To read the contents of the file with spaces in its name, use the `cat` command with quotes around the filename:

   ```bash
   cat "spaces in this filename"
   ```

   The password for the next level will be displayed.

   ```
   aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
   ```

5. Now, you have the password for Level 3. Use it to log in to Level 3 using SSH:

   ```bash
   ssh bandit3@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the file with spaces in its name when prompted.
