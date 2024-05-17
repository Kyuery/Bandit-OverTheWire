# Bandit Level 32 → Level 33

## Level Goal

After all this git stuff, it's time for another escape. Good luck!

## Commands you may need to solve this level

- `sh`
- `man`

To solve Bandit Level 32 → Level 33, you need to escape from the restricted shell environment using the provided commands.

### Step-by-Step Solution

1. **Log into Bandit Level 32**:

   ```bash
   ssh bandit32@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit32 when prompted.

2. **Run the provided shell command**:

   ```bash
   sh
   ```

   This will start a new shell session.

3. **Check the home directory for any files**:

   ```bash
   ls
   ```

   This will list any files in the home directory.

4. **Read the content of the README file**:

   ```bash
   cat README.txt
   ```

   The password for the next level should be in this file.

5. **Note down the password**.
6. **Log into bandit33 with the found password**:
   ```bash
   ssh bandit33@bandit.labs.overthewire.org -p 2220
   ```
   Use the password you found in the README.txt file.
