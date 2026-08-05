# Bandit Level 0 → 1

**Difficulty:** ⭐1 (rate 1–5)

**Tools used:** ssh, cat, ls

<img width="1597" height="500" alt="image" src="https://github.com/user-attachments/assets/da920287-9d8f-46dc-850c-828186134ebb" />

---

## Objective

 The password for the next level is stored in a file called `readme`. We need the password for entering next level.

---

## Solution
In previous level, we understood how to use ssh command to connect to remote server. On the previous level we were able to obtain the password for this level.

We can login into this level as user bandit1 by the following command.

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
And entering the pass(obtained from previous level) : `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR`

We are now inside the server. We can use ls command to view contents in present directory

We cannot see a "-" named file using cat command as terminal get confused with '-' as flag/options.

To view or open a file that starts with a dash (-) in Linux, prefix the filename with a double dash (--) or a relative path (./) so the terminal does not mistake the dash for a command option.

As the file name is only dash, we must use `./`. So we can type this command to read content of the file.

```
cat ./-
```

This file contains password for next level.

<img width="326" height="93" alt="image" src="https://github.com/user-attachments/assets/0e6a0810-f90f-4c8c-8a91-cec5f4203b2f" />

## Password

```
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
```

