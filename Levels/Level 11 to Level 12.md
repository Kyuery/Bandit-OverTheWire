# Bandit Level 11 → Level 12

## Level Goal

The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

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

- [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/ROT13)

# Answer

To solve Bandit Level 11 → Level 12, follow these steps:

1. Log into the server for Level 11 using SSH. The command is:

   ```bash
   ssh bandit11@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 10).

2. Once you're logged in, navigate to the home directory using the `cd` command:

   ```bash
   cd
   ```

3. Use the `ls` command to list the files in the home directory and locate the `data.txt` file:

   ```bash
   ls
   ```

4. To decode the content of `data.txt` where all letters have been rotated by 13 positions (Rot13), you can use the `tr` command:

   ```bash
   cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   ```

   This command performs the Rot13 transformation on the content of `data.txt`.

5. The password for the next level will be displayed.

   ```
   The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
   ```

6. Now, you have the password for Level 12. Use it to log in to Level 12 using SSH:

   ```bash
   ssh bandit12@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found in the Rot13-transformed data when prompted.
