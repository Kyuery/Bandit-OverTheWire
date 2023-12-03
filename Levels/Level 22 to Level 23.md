# Bandit Level 22 → Level 23

## Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Commands you may need to solve this level

- `cron`
- `crontab`
- `crontab(5)` (use “man 5 crontab” to access this)

# Answer

To solve Bandit Level 22 → Level 23, follow these steps:

1. Log into the server for Level 22 using SSH. The command is:

   ```bash
   ssh bandit22@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 21).

2. Check the contents of the `/etc/cron.d/cronjob_bandit23` directory to find the configuration for the cron job:

   ```bash
   cat /etc/cron.d/cronjob_bandit23
   ```

   This command will display the contents of all files in the `cronjob_bandit23` directory.

3. Look for the line that specifies the command being executed and examine it to see what it does.

   ```bash
   bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
   @reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
   * * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
   ```

4. The cron configuration may use a script or directly specify a command. Identify the command that is being executed.

5. Concatenate the script directory to identify its purpose:

   ```bash
   cat /usr/bin/cronjob_bandit23.sh
   ```

6. Now that you know the command, execute it to retrieve the password for the next level.

7. Execute the identified command. If it's a script, use `cat` to display its content:

   ```bash
   cat /path/to/script.sh
   ```

   If it's a direct command, execute it:

   ```bash
   /path/to/command
   ```

8. The output of the command should contain the password for Level 23.

9. Now, you have the password for Level 23. Use it to log in to Level 23 using SSH:

   ```bash
   ssh bandit23@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.

Congratulations! You've completed Bandit Level 22 → Level 23. Continue with the challenges, and feel free to ask if you have any questions!
