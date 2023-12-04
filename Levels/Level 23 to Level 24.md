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

1. Log into the server for Level 23 using SSH. The command is:

   ```bash
   ssh bandit23@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 22).

2. Check the contents of the `/etc/cron.d/` directory to find the configuration for the cron job:

   ```bash
   cat /etc/cron.d/*
   ```

   This command will display the contents of all files in the `/etc/cron.d/` directory.

3. Identify the cron job that is being executed.

4. Create a shell script in your home directory. Let's call it `my_script.sh`. You can use a text editor like `nano` to create it:

   ```bash
   nano my_script.sh
   ```

5. Inside the `my_script.sh` file, write a simple command. For example, you can write a command that echoes a message:

   ```bash
   #!/bin/bash
   echo "Hello, this is my script!"
   ```

   Save and exit the text editor.

6. Make the script executable:

   ```bash
   chmod +x my_script.sh
   ```

7. Test your script to make sure it works:

   ```bash
   ./my_script.sh
   ```

   If the script prints the message, it's working.

8. Now, set up the cron job to execute your script. Open your crontab for editing:

   ```bash
   crontab -e
   ```

9. Add a line to schedule the execution of your script. For example, to run the script every minute, add:

   ```bash
   * * * * * /path/to/your/script.sh
   ```

   Make sure to replace `/path/to/your/script.sh` with the actual path to your script.

10. Save and exit the crontab editor.

11. Wait for a minute, and then check if your script was executed. You may want to check the output. If you want to keep a copy of the output, you can redirect it to a file:

```bash
* * * * * /path/to/your/script.sh > /path/to/output.txt 2>&1
```

Replace `/path/to/output.txt` with the actual path.

12. Now, you should be able to retrieve the password for Level 24. The password is typically stored in the `/tmp/` directory or the `/var/spool` directory.

13. Once you have the password, use it to log in to Level 24 using SSH:

    ```bash
    ssh bandit24@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password when prompted.
