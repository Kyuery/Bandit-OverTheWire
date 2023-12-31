# Bandit Level 16 → Level 17

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Commands you may need to solve this level

- `ssh`
- `telnet`
- `nc`
- `openssl`
- `s_client`
- `nmap`

## Helpful Reading Material

- [Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port_scanner)

# Answer

To solve Bandit Level 16 → Level 17, follow these steps:

1. Log into the server for Level 16 using SSH. The command is:

   ```bash
   ssh bandit16@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 15).

2. Use the `nmap` command to scan ports in the range 31000 to 32000 on localhost:

   ```bash
   nmap -v -A -T4 -p 31000-32000 localhost

   ```

3. Analyze the output to identify which ports have a server listening on them.

4. For each open port, check if it speaks SSL. You can use the `openssl` command with `s_client` for this:

   ```bash
   openssl s_client -connect localhost:<port>
   ```

   Replace `<port>` with the actual port number you want to check.

   Try typing some random characters and pressing Enter. If the server sends back a response, it may not be the correct one. If it doesn't respond or if it responds with an SSL certificate, it might be the correct server.

5. Continue checking each open port until you find the one that speaks SSL and provides the next credentials.

6. Once you find the correct port, submit the current password to that port using the `openssl` command:

   ```bash
   echo "current_password" | openssl s_client -connect localhost:<port>
   ```

   Replace `<port>` with the actual port number you found.

7. It will return a RSA private key. Copy the private key.

8. Create a temporary folder for the storage of the private key.

   ```bash
   mkdir /tmp/sshkeyb17
   ```

9. Paste the RSA private key.

   ```bash
   vim sshkeyb17.key
   ```

10. Change file permission to read and write (rw-)

    ```bash
    chmod 600 sshkeyb17.key
    ```

11. Connect to bandit17 localhost

    ```bash
    ssh -i sshkeyb17.key bandit17@localhost -p 2220
    ```

12. Locate the password at /etc/bandit_pass

    ```bash
    cat /etc/bandit_pass/bandit17
    ```

    ```
    VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
    ```

13. Now, you have the password for Level 17. Use it to log in to Level 17 using SSH:

    ```bash
    ssh bandit17@bandit.labs.overthewire.org -p 2220
    ```

    Enter the password you found when prompted.
