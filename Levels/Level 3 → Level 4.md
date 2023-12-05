# Bandit Level 3 → Level 4

## Level Goal

The password for the next level is stored in a hidden file in the `inhere` directory.

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

# Answer

To solve Bandit Level 3 → Level 4, follow these steps:

1. Log into the server for Level 3 using SSH. The command is:

   ```bash
   ssh bandit3@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 2).

2. Once you're logged in, navigate to the `inhere` directory using the `cd` command:

   ```bash
   cd inhere
   ```

3. Use the `ls` command to list the files in the `inhere` directory:

   ```bash
   ls
   ```

   Look for a hidden file. Hidden files in Linux start with a dot (`.`).

4. To list hidden files, use the `ls` command with the `-a` flag:

   ```bash
   ls -a
   ```

   This will show all files, including hidden ones.

5. Look for a hidden file and use the `cat` command to read its contents. For example:

   ```bash
   cat .hidden
   ```

   Replace `.hidden` with the actual hidden file name you find.

6. The password for the next level will be displayed.

   ```
   2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
   ```

7. Now, you have the password for Level 4. Use it to log in to Level 4 using SSH:

   ```bash
   ssh bandit4@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the hidden file when prompted.
