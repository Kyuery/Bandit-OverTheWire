# Bandit Level 28 → Level 29

## Level Goal

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via port 2220. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

- `git`

To solve Bandit Level 28 → Level 29, you need to interact with a Git repository. Here’s how you can do it:

### Step-by-Step Solution

1. **Log into Bandit Level 28**:

   ```bash
   ssh bandit28@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit28 when prompted.

2. **Clone the Git repository**:
   Use Git to clone the repository provided in the level goal. Since the repository is on the same server but requires a different username, you’ll need to specify the correct username and port.

   ```bash
   git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
   ```

   When prompted, enter the password for bandit28.

3. **Navigate to the cloned repository**:

   ```bash
   cd repo
   ```

4. **List the files in the repository**:

   ```bash
   ls
   ```

   Look for files that might contain the password for the next level.

5. **Read the contents of the files**:
   Check the files within the repository to find the password. Typically, it might be stored in a README file or another text file.

   ```bash
   cat README.md
   ```

6. **Explore Git logs and commits**:
   The password might be stored in the Git commit history. Check the logs to see the commit messages.

   ```bash
   git log
   ```

7. **Check the content of specific commits**:
   If a commit looks promising, check its content:

   ```bash
   git show <commit-hash>
   ```

8. **Look for the password**:
   Look through the files and logs to find the password for bandit29. Once found, note it down.

9. **Log into bandit29 with the found password**:
   ```bash
   ssh bandit29@bandit.labs.overthewire.org -p 2220
   ```
   Use the password you found in the repository.

### Detailed Steps and Explanation

1. **Log into Bandit Level 28**:

   ```bash
   ssh bandit28@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit28 when prompted.

2. **Clone the Git repository**:

   ```bash
   git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
   ```

   When prompted, enter the password for bandit28.

3. **Navigate to the cloned repository**:

   ```bash
   cd repo
   ```

4. **List the files in the repository**:

   ```bash
   ls
   ```

   This will show you the files available in the repository.

5. **Check for README files or similar**:

   ```bash
   cat README.md
   ```

   Look for files that might contain the password. README.md is a common file where information might be stored.

6. **Check the Git logs for hints**:

   ```bash
   git log
   ```

   This will show the commit history. Look for commit messages that might indicate where the password is stored.

7. **Check specific commits if needed**:
   ```bash
   git show <commit-hash>
   ```
   Replace `<commit-hash>` with the actual hash of a commit that looks interesting.
