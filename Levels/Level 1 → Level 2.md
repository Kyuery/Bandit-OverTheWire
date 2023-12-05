# Bandit Level 1 → Level 2

## Level Goal

The password for the next level is stored in a file called `-` located in the home directory.

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

## Helpful Reading Material

- Google Search for “dashed filename”
- Advanced Bash-scripting Guide - Chapter 3 - Special Characters

# Answer

To solve Bandit Level 1 → Level 2, follow these steps:

1. Log into the server for Level 1 using SSH. The command is:

   ```bash
   ssh bandit1@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 0).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory:

   ```bash
   ls
   ```

   Look for a file named `-`.

4. To read the contents of the `-` file, use the `cat` command with the relative path:

   ```bash
   cat ./-
   ```

   The password for the next level will be displayed.

   ```
   rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
   ```

5. Now, you have the password for Level 2. Use it to log in to Level 2 using SSH:

   ```bash
   ssh bandit2@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the `-` file when prompted.
