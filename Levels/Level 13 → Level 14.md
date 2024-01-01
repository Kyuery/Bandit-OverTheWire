# Bandit Level 13 → Level 14

## Level Goal

The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: `localhost` is a hostname that refers to the machine you are working on.

## Commands you may need to solve this level

- `ssh`
- `telnet`
- `nc`
- `openssl`
- `s_client`
- `nmap`

## Helpful Reading Material

- [SSH/OpenSSH/Keys](https://en.wikibooks.org/wiki/OpenSSH/Keys)

This Markdown format maintains the structure and includes sections for the level goal, commands, and additional reading material with a hyperlink.

# Answer

To solve Bandit Level 13 → Level 14, follow these steps:

1. Log into the server for Level 13 using SSH. The command is:

   ```bash
   ssh bandit13@bandit.labs.overthewire.org -p 2220
   ```

   Enter the password when prompted (the password is the one you found in Level 12).

2. Once you're logged in, you will find a file named `sshkey.private`. Use the `cat` command to display the content of this file:

   ```bash
   cat sshkey.private
   ```

   Copy the content of the file. This is a private SSH key that you'll use to log in to the next level.

3. Use the private key to log in to the next level. The username is `bandit14`:

   ```bash
   ssh -i sshkey.private bandit14@localhost -p 2220
   ```

4. You should now be logged in as `bandit14`. Once logged in, you can read the password for the next level in the file `/etc/bandit_pass/bandit14`:
   ```bash
   cat /etc/bandit_pass/bandit14
   ```
   ```
   fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
   ```
