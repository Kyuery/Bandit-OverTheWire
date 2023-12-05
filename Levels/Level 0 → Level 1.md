# Bandit Level 0 → Level 1

## Level Goal

The password for the next level is stored in a file called `readme` located in the home directory. Use this password to log into `bandit1` using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Commands you may need to solve this level

- `ls`
- `cd`
- `cat`
- `file`
- `du`
- `find`

# Answer

To solve Bandit Level 0 → Level 1, follow these steps:

1. Log into the server for Level 0 using SSH. The command is:

   ```bash
   ssh bandit0@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is also `bandit0`).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory:

   ```bash
   ls
   ```

   Look for a file named `readme`.

4. To read the contents of the `readme` file, use the `cat` command:

   ```bash
   cat readme
   ```

   The password for the next level will be displayed.

   ```
   NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
   ```

5. Now, you have the password for Level 1. Use it to log in to Level 1 using SSH:

   ```bash
   ssh bandit1@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the `readme` file when prompted.

Congratulations! You've completed Bandit Level 0 → Level 1. Continue exploring and solving the challenges in the game. If you have any questions or get stuck, feel free to ask!
