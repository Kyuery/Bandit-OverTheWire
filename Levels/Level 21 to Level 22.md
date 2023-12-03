# Bandit Level 21 → Level 22

## Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

## Commands you may need to solve this level

- `cron`
- `crontab`
- `crontab(5)` (use “man 5 crontab” to access this)

# Answer

To solve Bandit Level 21 → Level 22, follow these steps:

1. Log into the server for Level 21 using SSH. The command is:

   ```bash
   ssh bandit21@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 20).

2. Check the contents of the `/etc/cron.d/` directory to find the configuration for the cron job:

   ```bash
   cat /etc/cron.d/
   ```

   This command will display the contents of all files in the `/etc/cron.d/` directory.

3. Look for the line that specifies the command being executed and examine it to see what it does.

   ```
   bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
   @reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
   * * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
   ```

4. The cron configuration may use a script or directly specify a command. Identify the command that is being executed.

5. Now that you know the command, execute it to retrieve the password for the next level.

6. Execute the identified command. If it's a script, use `cat` to display its content:

   ```bash
   cat /usr/bin/cronjob_bandit22.sh
   ```

7. It will output another directory which contains the password:

   ```bash
   bandit21@bandit:/tmp/cronjob22$ cat /usr/bin/cronjob_bandit22.sh
   #!/bin/bash
   chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
   cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
   ```

8. Concatenate the output directory '/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv'

   ```bash
   cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
   ```

9. The output of the command should contain the password for Level 22.

   ```bash
   WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
   ```

10. Now, you have the password for Level 22. Use it to log in to Level 22 using SSH:

    ```bash
    ssh bandit22@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password you found when prompted.
