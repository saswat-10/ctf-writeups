# Bandit Level 0

**Category:** Linux Fundamentals
**Difficulty:** ⭐1 (rate 1–5 stars)
**Tools used:** ssh,ls,cat

---

<img width="1568" height="346" alt="image" src="https://github.com/user-attachments/assets/bbb7cea2-ad92-4d75-a155-bdfd6388051f" />

## Solution
It is basic level and a stepping stone for beginners learning Linux commands. It teaches how to use the ssh command to connect to a remote server.

The syntax of ssh command is usually given as:
```
ssh -flag username@hostname
```

Flags—also called options or switches—are short modifiers that you add to a Linux command to change how it behaves.
Ex:- -p is a flag used to specify port number and is used when the service runs on a custom port different than usual port.

In this level we are given the info about

hostname: bandit.labs.overthewire.org

username: bandit0

password: bandit0

port : 2220

We can assemble the parts to get the command

```
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```
After entering the command to our Linux terminal, it will prompt us for a password. We can type the password as bandit0 (Disclaimer: Password may not be visible while typing , which is a security feature called shoulder surfing protection) and press enter.

We are now successfully inside the bandit server with bandit0 username.

We can use ls command to list the content

```ls```

It will list a file named 'readme'.
We can read the content of readme by using cat command.

``` cat readme ```

This file contains the password for the next level.

<img width="680" height="180" alt="image" src="https://github.com/user-attachments/assets/56762724-1132-4a8f-860a-2ab10a980519" />

## Flag / Password

```
6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
```


