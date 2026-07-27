# Natas Level 1 → Level 2

## Challenge Info
- **Level:** natas2
- **URL:** http://natas2.natas.labs.overthewire.org
- **Category:** Web Exploitation
- **Difficulty:** ⭐ 1.2 (Scale 1-5)

<img width="682" height="193" alt="image" src="https://github.com/user-attachments/assets/a5274600-da8a-4944-8ba1-571066c8adce" />

## Objective
To get the next level's password.

## Solution
After entering the credentials ("username": "natas2", "pass": "vsDOxoXyq3wckCP1ZmTZ71ngIA606odB"). We landed on this page where it stated that "There is nothing on this page".So It may be hint that, pass may be on a subdirectory or other page.

<img width="1917" height="530" alt="image" src="https://github.com/user-attachments/assets/dbae1d5b-5b33-415e-aa81-4e2f2bd97455" />

We checked the html source code

<img width="1361" height="363" alt="image" src="https://github.com/user-attachments/assets/b25ae38a-fd21-476b-b909-fde50a56f106" />

On line 15 , we can see that the image has source of "files/pixel.png"

We can check for possible "files" subdirectory by appending it to our original url and pressing enter. 
`
http://natas2.natas.labs.overthewire.org/files
`
After entering the url , we get the following page

<img width="706" height="332" alt="image" src="https://github.com/user-attachments/assets/aaa20c31-ef89-4b92-a0ee-594d30625b26" />

Upon clicking on users.txt. We can see that it contains username and password of various users including natas3 password.

<img width="371" height="153" alt="image" src="https://github.com/user-attachments/assets/6cd4c119-73c8-4098-80e8-162335cb0642" />


## Result
```
password for natas(3): K30JrSRHzjxq3paUQuwozY4MNvmNFyhI
```

