# Bandit Level 19 → Level 20

## Level Goal

To gain access to the next level, you should use the setuid binary in the home directory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Helpful Reading Material

- [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)

# Answer

To solve Bandit Level 19 → Level 20, follow these steps:

1. Log into the server for Level 19 using SSH. The command is:

   ```bash
   ssh bandit19@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 18).

2. In the home directory, you will find an executable file with setuid permissions named `bandit20-do`. Execute it without arguments to learn how to use it:

   ```bash
   ./bandit20-do
   ```

   This command will provide information on how to use the setuid binary.

3. After executing the `bandit20-do` binary, you should be able to read the password for Level 20. Check the usual location:

   ```bash
   ./bandit20-do cat /etc/bandit_pass/bandit20
   ```

   ```
   VxCazJaVykI6W36BkBU0mJTCM8rR95XT
   ```

4. Now, you have the password for Level 20. Use it to log in to Level 20 using SSH:

   ```bash
   ssh bandit20@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.
