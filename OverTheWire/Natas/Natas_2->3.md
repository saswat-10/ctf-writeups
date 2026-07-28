# Natas Level 2 → Level 3

## Challenge Info
- **Level:** natas3
- **URL:** http://natas3.natas.labs.overthewire.org
- **Category:** Web Exploitation
- **Difficulty:** ⭐1.3 (1–5 scale)

<img width="638" height="176" alt="image" src="https://github.com/user-attachments/assets/7c478dac-88ad-4a88-88cb-3a0f01aaad4e" />

## Objective
To get the next level's password.

## Solution
We logged in using credentials ("username": "natas3", "pass": "K30JrSRHzjxq3paUQuwozY4MNvmNFyhI"). 

Opening the website and looking at the source code, we can find a comment, which gives us a hint

<img width="1338" height="347" alt="image" src="https://github.com/user-attachments/assets/4afdc649-5143-4769-9ca5-9f2bd05f5214" />

This hint suggests about a file which cannot be found be google, means Google's bot cannot crawl its content. It can be done by a file named robots.txt which gives the crawler information which things to visit and which to not.

So we could find what path or files crawlers are disallowed to index by visiting robots.txt.

So , we type the following url `http://natas3.natas.labs.overthewire.org/robots.txt`

<img width="215" height="62" alt="image" src="https://github.com/user-attachments/assets/c131b916-a1e2-47ea-9c5a-08c38408446d" />

We can clearly see all search engine bots are not allowed to crawl through /s3cr3t/ and index it.

We can move to this subdirectory by following url `http://natas3.natas.labs.overthewire.org/s3cr3t/`. After navigating to the path we can see a public directory with a file named users.txt.

<img width="713" height="292" alt="image" src="https://github.com/user-attachments/assets/ceeb1a2e-7168-449c-9341-34184a6721ea" />

Opening users.txt reveals the password for the next level.

## Result
```
password for natas(4): JDrPnuZAKyl6MkiqQGFIddrqpvgOASth
```

