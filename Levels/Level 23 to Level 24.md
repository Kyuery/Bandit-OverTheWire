# Bandit Level 23 → Level 24

## Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Commands you may need to solve this level

- `cron`
- `crontab`
- `crontab(5)` (use “man 5 crontab” to access this)

# Answer

To solve Bandit Level 23 → Level 24, you'll need to create a shell script and have it executed by cron. Follow these steps:

1.  Log into the server for Level 23 using SSH. The command is:

    ```bash
    ssh bandit23@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password when prompted (the password is the one you found in Level 22).

2.  Check the contents of the `/etc/cron.d/cronjob_bandit24` directory to find the configuration for the cron job:

    ```bash
    cat /etc/cron.d/cronjob_bandit24
    ```

3.  Look for the line that specifies the command being executed and examine it to see what it does.

    ```bash
    bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
    @reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
    * * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
    ```

4.  The cron configuration may use a script or directly specify a command. Identify the command that is being executed.

5.  Concatenate the script directory to identify its purpose:

    ```bash
    cat /usr/bin/cronjob_bandit24.sh

    ```

6.  Examine the output:

    ```bash
     #!/bin/bash

     myname=$(whoami)

     cd /var/spool/$myname/foo
     echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
     for i in _ ._;
     do
     if [ "$i" != "." -a "$i" != ".." ];
     then
     echo "Handling $i"
         owner="$(stat --format "%U" ./$i)"
         if [ "${owner}" = "bandit23" ]; then
     timeout -s 9 60 ./$i
             fi
             rm -f ./$i
     fi
     done
    ```

7.  Replace `myname` variable from bandit23 to bandit24:

    ```bash
    myname=bandit24
    ```

8.  Execute the script below to output the password of `bandit24` to the temporary directory.

    ```bash


    echo "cat /etc/bandit_pass/bandit24 > /tmp/password.txt" > get.sh

    ```

9.  Make the script executable:

    ```bash
    chmod 777 my_script.sh
    ```

10. Save and exit the crontab editor.

11. Wait for a minute, and then check if your script was executed. You may want to check the output. If you want to keep a copy of the output, you can redirect it to a file:

12. Now, you should be able to retrieve the password for Level 24. The password is typically stored in the `/tmp/` directory or the `/var/spool` directory.

    ```bash
    cat /tmp/password.txt
    ```

    ```bash
    VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
    ```

13. Once you have the password, use it to log in to Level 24 using SSH:

    ```bash
    ssh bandit24@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password when prompted.
