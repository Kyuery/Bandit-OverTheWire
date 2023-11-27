# Bandit Level 10 → Level 11

## Level Goal

The password for the next level is stored in the file `data.txt`, which contains base64 encoded data.

## Commands you may need to solve this level

- `grep`
- `sort`
- `uniq`
- `strings`
- `base64`
- `tr`
- `tar`
- `gzip`
- `bzip2`
- `xxd`

## Helpful Reading Material

- [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

# Answer

To solve Bandit Level 10 → Level 11, follow these steps:

1. Log into the server for Level 10 using SSH. The command is:

   ```bash
   ssh bandit10@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 9).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory and locate the `data.txt` file:

   ```bash
   ls
   ```

4. To decode the base64 encoded data in `data.txt`, you can use the `base64` command:

   ```bash
   base64 -d data.txt
   ```

   This command decodes the base64 encoded data and displays the original content.

5. The password for the next level will be displayed.

   ```
   The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
   ```

6. Now, you have the password for Level 11. Use it to log in to Level 11 using SSH:

   ```bash
   ssh bandit11@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the decoded data when prompted.
