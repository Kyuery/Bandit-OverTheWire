# Bandit Level 0

## Level Goal

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is `bandit.labs.overthewire.org`, on port `2220`. The username is `bandit0`, and the password is `bandit0`. Once logged in, go to the Level 1 page to find out how to beat Level 1.

## Commands You May Need to Solve This Level

```bash
ssh
```

## Helpful Reading Material

- [Secure Shell (SSH) on Wikipedia](<https://en.wikipedia.org/wiki/Secure_Shell_(SSH)>)
- [How to use SSH on wikiHow](https://www.wikihow.com/Use-SSH)

# Answer

For Bandit Level 0, you need to use the `ssh` command to connect to the specified host, port, username, and password. Here's the general format:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

This command connects to the server with the username `bandit0` at the specified host and port. You'll be prompted to enter the password, which, in this case, is also `bandit0`. After successfully logging in, you can proceed to the Level 1 page to find out how to beat the next level.