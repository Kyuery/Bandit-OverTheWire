# Bandit Level 20 → Level 21

## Level Goal

There is a setuid binary in the home directory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think.

## Commands you may need to solve this level

- `ssh`
- `nc`
- `cat`
- `bash`
- `screen`
- `tmux`
- Unix ‘job control’ (`bg`, `fg`, `jobs`, `&`, `CTRL-Z`, …)

# Answer

To solve Bandit Level 20 → Level 21, follow these steps:

1. Log into the server for Level 20 using SSH. The command is:

   ```bash
   ssh bandit20@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 19).

2. In the home directory, you will find an executable file named `suconnect`. Execute it without arguments to understand its functionality:

   ```bash
   ./suconnect
   ```

   This will provide information about the `suconnect` program.

3. It's mentioned that `suconnect` makes a connection to `localhost` on a specified port. You need to set up a listener on a port and have `suconnect` connect to it.

4. Open a new terminal window (you can use a tool like `tmux` or `screen` for this, or simply open a new terminal).

5. Start a listener on a port of your choice using the `nc` (netcat) command:

   ```bash
   nc -l -v -p 12345
   ```

   Replace `12345` with the port number of your choice.

6. Back in the original terminal where you have `suconnect`, run it with the specified port:

   ```bash
   ./suconnect 12345
   ```

   ```
   bandit20@bandit:~$ ./suconnect 12345
   Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
   Password matches, sending next password
   ```

   You should see a connection being made to `localhost`.

7. In the terminal where you started the `nc` listener, type the password for Level 20 and press Enter.

8. The `suconnect` program will read the password and transmit the password for Level 21.

9. Check the output in the `suconnect` terminal to see the transmitted password for Level 21.

   ```
   bandit20@bandit:~$ nc -l -v -p 12345
   Listening on 0.0.0.0 12345
   Connection received on localhost 52332
   VxCazJaVykI6W36BkBU0mJTCM8rR95XT
   NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
   ```

10. Now, you have the password for Level 21. Use it to log in to Level 21 using SSH:

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```

Enter the password you found when prompted.
