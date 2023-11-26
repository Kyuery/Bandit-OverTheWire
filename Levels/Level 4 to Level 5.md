# Bandit Level 4 → Level 5

## Level Goal

The password for the next level is stored in the only human-readable file in the `inhere` directory. Tip: if your terminal is messed up, try the “reset” command.

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

# Answer

To solve Bandit Level 4 → Level 5, follow these steps:

1. Log into the server for Level 4 using SSH. The command is:

   ```bash
   ssh bandit4@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 3).

2. Once you're logged in, navigate to the `inhere` directory using the `cd` command:

   ```bash
   cd inhere
   ```

3. Use the `file` command to determine the type of each file in the directory:

   ```bash
   file ./*
   ```

   **Note:** Because the file starts at `-`, we will use `./`.
   This will provide information about the type of content each file contains.

4. Look for the only human-readable file in the output. It might say something like ASCII text. Use the `cat` command to read the contents of that file:

   ```bash
   cat `./-file07`
   ```

5. The password for the next level will be displayed.

   ```
   lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
   ```

6. Now, you have the password for Level 5. Use it to log in to Level 5 using SSH:

   ```bash
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the human-readable file when prompted.
