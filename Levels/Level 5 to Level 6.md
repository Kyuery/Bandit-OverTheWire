# Bandit Level 5 → Level 6

## Level Goal

The password for the next level is stored in a file somewhere under the `inhere` directory and has all of the following properties:

- Human-readable
- 1033 bytes in size
- Not executable

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

# Answer

To solve Bandit Level 5 → Level 6, follow these steps:

1. Log into the server for Level 5 using SSH. The command is:

   ```bash
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```

2. Once you're logged in, navigate to the `inhere` directory using the `cd` command:

   ```bash
   cd inhere
   ```

3. Use the `find` command to search for a file that meets the specified criteria (human-readable, 1033 bytes, not executable). The command might look like this:

   ```bash
   find . -type f -readable -size 1033c ! -executable
   ```

   This command searches for a regular file (`-type f`), readable (`-readable`), with a size of 1033 bytes (`-size 1033c`), and not executable (`! -executable`).

4. The `find` command should return the path to the file that meets these criteria.

5. Use the `cat` command to read the contents of the file:

   ```bash
   cat ./maybehere07/.file2
   ```

   Replace `path/to/found/file` with the actual path you obtained from the `find` command.

6. The password for the next level will be displayed.

   ```
   P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
   ```

7. Now, you have the password for Level 6. Use it to log in to Level 6 using SSH:

   ```bash
   ssh bandit6@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the specified file when prompted.
