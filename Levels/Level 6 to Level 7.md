# Bandit Level 6 → Level 7

## Level Goal

The password for the next level is stored somewhere on the server and has all of the following properties:

- Owned by user `bandit7`
- Owned by group `bandit6`
- 33 bytes in size

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`
- `grep`

# Answer

To solve Bandit Level 6 → Level 7, follow these steps:

1. Log into the server for Level 6 using SSH. The command is:

   ```bash
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 5).

2. Once you're logged in, use the `find` command to search for a file that meets the specified criteria (owned by user `bandit7`, owned by group `bandit6`, and 33 bytes in size):

   ```bash
   find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
   ```

   This command searches the entire file system (`/`) for a file owned by user `bandit7`, owned by group `bandit6`, and 33 bytes in size. `2>/dev/null` redirects any error messages to /dev/null to avoid cluttering the output.

3. The `find` command should return the path to the file that meets these criteria.

4. Use the `cat` command to read the contents of the file:

   ```bash
   cat /var/lib/dpkg/info/bandit7.password
   ```

5. The password for the next level will be displayed.

   ```
   z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
   ```

6. Now, you have the password for Level 7. Use it to log in to Level 7 using SSH:

   ```bash
   ssh bandit7@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the specified file when prompted.
