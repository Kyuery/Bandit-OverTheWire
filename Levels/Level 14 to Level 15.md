# Bandit Level 14 → Level 15

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Commands you may need to solve this level

- `ssh`
- `telnet`
- `nc`
- `openssl`
- `s_client`
- `nmap`

## Helpful Reading Material

- [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (Not completely accurate, but good enough for beginners)
- [IP Addresses](https://en.wikipedia.org/wiki/IP_address)
- [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
- [Ports](<https://en.wikipedia.org/wiki/Port_(computer_networking)>)

# Answer

To solve Bandit Level 14 → Level 15, follow these steps:

1. Log into the server for Level 14 using SSH. The command is:

   ```bash
   ssh bandit14@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 13).

2. Use the `telnet` command to connect to port 30000 on localhost and submit the current password:

   ```bash
   telnet localhost 30000
   ```

   If you don't have `telnet` installed, you can use `nc` (netcat) instead:

   ```bash
   echo "current_password" | nc localhost 30000
   ```

   Replace `current_password` with the password you found in Level 14.

3. Submit the current password through either `telnet` or `nc`, and the password for the next level will be displayed.

   ```
   jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
   ```

4. Now, you have the password for Level 15. Use it to log in to Level 15 using SSH:

   ```bash
   ssh bandit15@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password you found when prompted.
