# Bandit

The Bandit wargame is designed for absolute beginners and aims to teach the basics needed to play other wargames. If you notice something essential is missing or have ideas for new levels, please let us know!

## Note for Beginners

This game, like most others, is organized into levels. You start at Level 0 and try to "beat" or "finish" it. Completing a level provides information on how to start the next level. The pages on this website for "Level <X>" contain information on how to progress from the previous level to Level X. For example, the page for Level 1 has information on how to gain access from Level 0 to Level 1. All levels in this game have a dedicated page on this website, accessible from the sidemenu on the left of this page.

You may encounter situations where you have no idea what to do. Don’t panic! Don’t give up! The purpose of this game is for you to learn the basics, and part of learning is reading new information. If you've never used the command line before, start with this [introduction to user commands](insert_link_here).

Here are several things you can try when you're unsure how to proceed:

1. If you know a command but don’t know how to use it, try the manual (man page) by entering `man <command>`. For example, `man ls` to learn about the “ls” command. The “man” command also has a manual; try it! When using `man`, press `q` to quit (you can also use `/` and `n` and `N` to search).
2. If there is no man page, the command might be a shell built-in. In that case, use the `help <X>` command. For example, `help cd`.
3. Your favorite search engine is your friend. Learn how to use it! Google is recommended.
4. If you are still stuck, you can join us via [chat](insert_chat_link_here).

You’re ready to start! Begin with Level 0, linked on the left of this page. Good luck!

## Note for VMs

If you are using a virtual machine (VM), you may encounter a "broken pipe error" when attempting to connect to overthewire.org via SSH if the network adapter for the VM is configured to use NAT mode. Adding the setting `IPQoS throughput` to `/etc/ssh/ssh_config` should resolve the issue. If this does not solve your problem, the only option then is to change the adapter to Bridged mode.

