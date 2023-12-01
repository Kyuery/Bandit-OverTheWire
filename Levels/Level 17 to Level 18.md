# Bandit Level 17 → Level 18

## Level Goal

There are 2 files in the home directory: `passwords.old` and `passwords.new`. The password for the next level is in `passwords.new` and is the only line that has been changed between `passwords.old` and `passwords.new`.

**NOTE:** If you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19.

## Commands you may need to solve this level

- `cat`
- `grep`
- `ls`
- `diff`

# Answer

To solve Bandit Level 17 → Level 18, follow these steps:

1. Log into the server for Level 17 using SSH. The command is:

   ```bash
   ssh bandit17@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 16).

2. Use the `ls` command to list the files in the home directory and identify the two files: `passwords.old` and `passwords.new`:

   ```bash
   ls
   ```

3. Use the `diff` command to find the line that has been changed between `passwords.old` and `passwords.new`:

   ```bash
   diff passwords.old passwords.new
   ```

   The output will show the lines that are different between the two files.

4. The password for the next level will be displayed in the output.

   ```
   < hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
   ---
   > p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
   ```

5. Now, you have the password for Level 18. Use it to log in to Level 18 using SSH:

   ```bash
   ssh bandit18@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.
