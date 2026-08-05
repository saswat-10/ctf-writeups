# Bandit Level 1 → 2

**Difficulty:** ⭐1 (rate 1–5)

**Tools used:** ssh, cat ,ls

---

<img width="762" height="476" alt="image" src="https://github.com/user-attachments/assets/adae7ffd-b82e-4150-bb56-cfc4b9389b32" />


## Objective
The password for the next level is stored in a file called - located in the home directory

---

## Solution
We can ssh into this level using the credentials.

username:bandit2
password:PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
After entering the remote server we can list content using ls command. We can see a file named " --spaces in this filename-- ".

We saw in the previous level that we can cat dashed files by using " -- "(double dash) or " ./ ".

But this file also has spaces so we cant directly read content by typing in the exact file name.

We can read it by :

1.) We can enclose filename within quotes (single or double)

2.) We can escape spaces by adding backslash before space

For this level , we will use the 1st one

So the command we used is

```bash
cat ./"--spaces in this filename--"
```

---

## Flag / Password

```
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
```
