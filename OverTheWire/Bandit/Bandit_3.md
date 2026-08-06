# Bandit Level 3 → 4

**Difficulty:** ⭐1 (rate 1–5)
**Tools used:** ssh, cat, ls ,cd

<img width="687" height="310" alt="image" src="https://github.com/user-attachments/assets/4f113d30-083d-42d8-9192-2201c64dee54" />

---

## Objective
The password for the next level is stored in a hidden file in the inhere directory.

---

## Solution

We logged in using credentials

username: bandit3

password: 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

In this level, we have to find a hidden file inside inhere directory. When we normally use ls command it lists the content of the directory but do not list hidden files and directory inside it.

We can add -a flag in ls command to show all files/directories (hidden + non-hidden).

After moving inside inhere directory using cd(change directory) command -> ```cd inhere``` . We can list all files by using the command.

```bash
ls -a
```
We can now see a hidden file named `...Hiding-From-You` .

We can use cat command to get the flag .

<img width="387" height="125" alt="image" src="https://github.com/user-attachments/assets/b199c9a9-a523-4f33-b6ca-f77f0b51fb43" />


---

## Flag / Password

```
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
```

---

