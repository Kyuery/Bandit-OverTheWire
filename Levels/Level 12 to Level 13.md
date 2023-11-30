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

1. SSH Login to Level 12:

   ```bash
   ssh bandit12@bandit.labs.overthewire.org -p 2220
   ```

   Enter the Level 11 password when prompted.

2. Create a Temporary Working Directory:

   ```bash
   mkdir /tmp/myname123
   ```

   This directory will serve as the workspace for file manipulation.

3. Copy `data.txt` to the Temporary Directory:

   ```bash
   cp data.txt /tmp/myname123/
   ```

4. Navigate to the Temporary Directory:

   ```bash
   cd /tmp/myname123
   ```

5. Determine Compression Type:

   ```bash
   file data.txt
   ```

   Identify the compression type used (e.g., gzip, bzip2).

6. Reverse the Hexdump Using `xxd`:

   ```bash
   xxd -r data.txt > output_file
   ```

7. Decompress and Change File Extensions:
   Depending on the compression type, use appropriate commands. Repeat this process until you reach the hexdump.

   ```bash
   # For gzip
   mv output_file output_file.gz
   gzip -d output_file.gz

   # For bzip2
   mv output_file output_file.bz2
   bzip2 -d output_file.bz2

   # For tar
   mv output_file output_file.tar
   tar xvf output_file.tar

   # Clean up
   rm output_file.tar
   rm data.txt

   # For data5.bin
   mv data5.bin data5.tar
   tar xf data5.tar
   rm data5.tar

   # For data6.bin
   mv data6.bin data6.bz2
   bzip2 -d data6.bz2

   # For data6
   mv data6 data6.tar
   tar xf data6.tar
   rm data6.tar

   # For data8.bin
   mv data8.bin data8.gz
   gzip -d data8.gz
   ```

8. Determine Compression Type Again:

   ```bash
   file output_file
   ```

9. Repeat the Decompression Process:
   Continue decompressing until the password is revealed.

   ```bash
   The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
   ```

10. SSH Login to Level 13:

    ```bash
    ssh bandit13@bandit.labs.overthewire.org -p 2220
    ```

    Use the password obtained in the previous steps.
