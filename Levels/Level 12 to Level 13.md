# Bandit Level 12 → Level 13

## Level Goal

The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed. For this level, it may be useful to create a directory under `/tmp` in which you can work using `mkdir`. For example: `mkdir /tmp/myname123`. Then copy the data file using `cp`, and rename it using `mv` (read the manpages!).

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
- `mkdir`
- `cp`
- `mv`
- `file`

## Helpful Reading Material

- [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)

# Answer

To solve Bandit Level 12 → Level 13, follow these steps:

1. Log into the server for Level 12 using SSH. The command is:

   ```bash
   ssh bandit12@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 11).

2. Create a temporary directory under `/tmp`. You can use the `mkdir` command:

   ```bash
   mkdir /tmp/myname123
   ```

   This directory will be used to work on the files.

3. Copy the `data.txt` file to the temporary directory using the `cp` command:

   ```bash
   cp data.txt /tmp/myname123/
   ```

4. Navigate to the temporary directory:

   ```bash
   cd /tmp/myname123
   ```

5. Use the `file` command to determine the type of the file:

   ```bash
   file data.txt
   ```

   The output will tell you the type of compression used. You may see references to gzip, bzip2, etc.

6. Decompress the file accordingly. Depending on the compression type, you can use commands like `gunzip`, `bunzip2`, or `tar`:

   ```bash
   gunzip data.txt  # If it's gzip compressed
   ```

   Or

   ```bash
   tar xvf data.txt  # If it's a tar archive
   ```

   If it's bzip2 compressed, use `bunzip2`, and so on.

7. Repeat the process of checking the file type and decompressing until you get the hexdump of the file.

8. Once you have the hexdump of the file, you can use a command like `xxd` to reverse the hexdump:

   ```bash
   xxd -r data.txt > output_file
   ```

   This command will reverse the hexdump and save the result in `output_file`.

9. Use the `file` command again on the output file to determine the compression type, and decompress if necessary.

10. Repeat the process until you get the password for the next level.

11. Now, you have the password for Level 13. Use it to log in to Level 13 using SSH:

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

Enter the password you found when prompted.

Congratulations! You've completed Bandit Level 12 → Level 13. Keep going, and feel free to ask if you have any questions!
