# Bandit Level 18 → Level 19

## Level Goal

The password for the next level is stored in a file `readme` in the home directory. Unfortunately, someone has modified `.bashrc` to log you out when you log in with SSH.

## Commands you may need to solve this level

- `ssh`
- `ls`
- `cat`

# Answer

To solve Bandit Level 18 → Level 19, follow these steps:

1. Log into the server for Level 18 using SSH. The command is:

   ```bash
   ssh bandit18@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 17).

2. Since the `.bashrc` file has been modified to log you out, you need to specify the command to run immediately after logging in. Use the `-t` option to force pseudo-tty allocation and provide the command:

   ```bash
   ssh -t bandit18@bandit.labs.overthewire.org -p 2220 cat readme
   ```

   This command will log you in and immediately execute the `cat readme` command, displaying the content of the `readme` file.

3. The password for the next level will be displayed.

   ```
   awhqfNnAbc1naukrpqDYcF95h7HoMTrC
   ```

4. Now, you have the password for Level 19. Use it to log in to Level 19 using SSH:

   ```bash
   ssh bandit19@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.

Congratulations! You've completed Bandit Level 18 → Level 19. Keep going, and feel free to ask if you have any questions!
