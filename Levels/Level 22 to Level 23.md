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

6. Examine the output:

   ```bash
   #!/bin/bash

   myname=$(whoami)
   mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

   echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

   cat /etc/bandit_pass/$myname > /tmp/$mytarget
   ```

   This script will display the directory of the password of your current user (`bandit22`).

7. Copy the 4th line then modify the '$myname' to output the user 'bandit23':

   ```bash
   echo I am user bandit23 | md5sum | cut -d ' ' -f 1
   ```

   ```bash
   8ca319486bfbbc3663ea0fbe81326349
   ```

8. Concatenate the given tmp directory output:

   ```bash
    cat /tmp/8ca319486bfbbc3663ea0fbe81326349
   ```

9. The output of the command should contain the password for Level 23.

   ```bash
   QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
   ```

10. Now, you have the password for Level 23. Use it to log in to Level 23 using SSH:

    ```bash
    ssh bandit23@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password you found when prompted.
