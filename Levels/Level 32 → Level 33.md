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

2. **Utilize Positional Parameters**:

   Notice that you can't enter commands due to it being always in uppercase, utilize positional parameters.

   To run sh command:

   ```bash
   $0
   ```

   This will start a new shell session.

3. **Read the content of the `bandit_pass` file**:

   ```bash
   cat /etc/bandit_pass/bandit33
   ```

   The password for the next level should be in this file.

   ```bash
   odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
   ```

4. **Note down the password**.
5. **Log into bandit33 with the found password**:
   ```bash
   ssh bandit33@bandit.labs.overthewire.org -p 2220
   ```
   Use the password you found in the README.txt file.
