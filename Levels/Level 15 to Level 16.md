# Bandit Level 15 → Level 16

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

## Helpful note

Getting “HEARTBEATING” and “Read R BLOCK”? Use `-ign_eof` and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

## Commands you may need to solve this level

- `ssh`
- `telnet`
- `nc`
- `openssl`
- `s_client`
- `nmap`

## Helpful Reading Material

- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/books/openssl-cookbook/)

# Answer

To solve Bandit Level 15 → Level 16, follow these steps:

1. Log into the server for Level 15 using SSH. The command is:

   ```bash
   ssh bandit15@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 14).

2. Use the `openssl` command to connect to port 30001 on localhost with SSL encryption and submit the current password:

   ```bash
   openssl s_client -connect localhost:30001
   ```

3. You will see a prompt. Enter the current password when prompted.

4. Once you submit the current password, the password for the next level will be displayed in the SSL session output.

   ```
   JQttfApK4SeyHwDlI9SXGR50qclOAil1
   ```

5. Now, you have the password for Level 16. Use it to log in to Level 16 using SSH:

   ```bash
   ssh bandit16@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.
