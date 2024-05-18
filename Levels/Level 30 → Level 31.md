# Bandit Level 30 → Level 31

## Level Goal

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port 2220. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

- `git`

To solve Bandit Level 30 → Level 31, you'll again be interacting with a Git repository. Here's how you can do it:

### Step-by-Step Solution

1. **Log into Bandit Level 30**:

   ```bash
   ssh bandit30@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit30 when prompted.

2. **Craete a temporary directory for saving of cloned repo:**

   ```bash
   mkdir /tmp/your_folder
   ```

   ```bash
   cd /tmp/your_folder
   ```

3. **Clone the Git repository**:

   Use Git to clone the repository provided in the level goal. Since the repository is on the same server but requires a different username, you'll need to specify the correct username and port.

   ```bash
   git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
   ```

   When prompted, enter the password for bandit30.

4. **Navigate to the cloned repository**:

   ```bash
   cd repo
   ```

5. **List the files in the repository**:

   ```bash
   ls
   ```

   Look for files that might contain the password for the next level.

6. **Read the contents of the files**:

   Check the files within the repository to find the password. Typically, it might be stored in a README file or another text file.

   ```bash
   cat README.md
   ```

7. **Explore Git logs and commits**:

   The password might be stored in the Git tags. Check the logs to see the commit messages.

   ```bash
   git tag
   ```

8. **Check the content of specific commits**:

   Check the contents of the tag:

   ```bash
   git show secret
   ```

   ```bash
   OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
   ```

9. **Look for the password**:

   Look through the files and logs to find the password for bandit31. Once found, note it down.

10. **Log into bandit31 with the found password**:
    ```bash
    ssh bandit31@bandit.labs.overthewire.org -p 2220
    ```
    Use the password you found in the repository.
