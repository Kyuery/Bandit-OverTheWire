# Bandit Level 26 → Level 27

## Level Goal

Good job getting a shell! Now hurry and grab the password for bandit27!

## Commands you may need to solve this level

- `ls`

To solve Bandit Level 26 → Level 27, follow these steps:

### Step-by-Step Solution

1. **Log into Bandit Level 26**:

   ```bash
   ssh bandit26@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit26 when prompted.

2. **Get a shell if needed**:
   If you are in a restricted shell, you may need to break out of it as you did in the previous level. However, since you should already have a shell, you can proceed to the next steps directly.

3. **List the files in the home directory**:

   ```bash
   ls
   ```

   Look for any files that might contain the password.

4. **Read the password file**:
   The password for bandit27 is typically stored in a file named something obvious. It's often a good idea to check files in the home directory:

   ```bash
   cat /home/bandit26/your-password-file
   ```

   Alternatively, look for hidden files or directories:

   ```bash
   ls -a
   ```

5. **Find the password file**:
   In the context of OverTheWire Bandit, the password files are usually stored in `/etc/bandit_pass`. You can read the password for bandit27 directly from there:

   ```bash
   cat /etc/bandit_pass/bandit27
   ```

   Note down the password displayed.

6. **Log into bandit27 with the found password**:
   ```bash
   ssh bandit27@bandit.labs.overthewire.org -p 2220
   ```
   Use the password you found in the previous step.
