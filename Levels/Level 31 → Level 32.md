# Bandit Level 31 → Level 32

## Level Goal

There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port 2220. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

- `git`

To solve Bandit Level 31 → Level 32, you'll need to interact with a Git repository as before. Here's the step-by-step solution:

### Step-by-Step Solution

1. **Log into Bandit Level 31**:

   ```bash
   ssh bandit31@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password for bandit31 when prompted.

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
   git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
   ```

   When prompted, enter the password for bandit31.

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

   ```bash
   This time your task is to push a file to the remote repository.

   Details:
      File name: key.txt
      Content: 'May I come in?'
      Branch: master
   ```

7. **follow the instructions based on the README.md**:
   Create a file `key.txt` and commit it to the master branch.

   ```bash
   vim key.txt
   ```

8. **Check the `.gitignore` file**:
   The `.gitignore` is interupting our commit, delete the file.

   ```bash
   rm .gitignore
   ```

9. **Commit**:
   Commit the new file that you have created:

   ```bash
   git add key.txt
   ```

   Check status

   ```bash
   git status
   ```

10. **Look for the password**:
    Look through the files and logs to find the password for bandit32. Once found, note it down.

11. **Log into bandit32 with the found password**:
    ```bash
    ssh bandit32@bandit.labs.overthewire.org -p 2220
    ```
    Use the password you found in the repository.
