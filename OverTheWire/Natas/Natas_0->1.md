
# Natas Level 0 → 1

## Challenge Info
- **Level:** natas1
- **URL:** http://natas1.natas.labs.overthewire.org
- **Category:** Web Exploitation
- **Difficulty:** ⭐1 (1–5 scale)

<img width="605" height="177" alt="image" src="https://github.com/user-attachments/assets/78d4bec5-7b9b-4f26-bf65-647ec83b938a" />


## Objective
To obtain next level's password.

## Recon
I logged in with username 'bandit1' and pass "scfWG6qNEIdzqVyfRwEGXyNUfFZkZeQ7" from previous level. Then, this page loads with following content

<img width="1857" height="877" alt="image" src="https://github.com/user-attachments/assets/fca93349-24a4-4829-a534-20dc0b9d82f7" />

It states that right clicking has been blocked. But upon checking we found out that it is only blocked on the banner where text is written. Right clicking works fine on entire space except the banner.

We can simply right click anywhere on the space and select view page source to view html code of the page.

The html code reveals the password for the next level.

<img width="1337" height="425" alt="image" src="https://github.com/user-attachments/assets/fffa918a-7496-4ea9-bf9d-f44e8b6bffb2" />

## Result
```
password for natas(2): vsDOxoXyq3wckCP1ZmTZ71ngIA606odB
```
