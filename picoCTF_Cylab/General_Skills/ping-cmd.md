# ping-cmd - General Skills (picoCTF 2026)
**Points:** 100 | **Difficulty:** Easy
## Challenge Description

<img width="825" height="731" alt="image" src="https://github.com/user-attachments/assets/a682e522-c62c-47f8-b688-4f82e7dc2a45" />

## Files/Info Given
-nc mysterious-sea.picoctf.net 62511

## Recon / Initial Analysis
I opened webshell and connected to the service by the command given above.

It asked for an ip to ping and only 8.8.8.8 was allowed by service for us to ping. I pinged 8.8.8.8 and it successfully pinged the IP and stopped.  

## Approach

We can pass more than one command by using | (pipe operator). So, I passed 
```bash
8.8.8.8 | ls
```

The server listed two files, named flag.txt and script.sh and stopped.
Then I terminated current process using (Ctrl + C) and reconnected to the service and typed the command to read content of flag.txt.

```bash
8.8.8.8 | cat flag.txt
```

The server revealed the flag.
<img width="898" height="172" alt="image" src="https://github.com/user-attachments/assets/31a40f99-03a3-48e1-bbe3-197336bca6d3" />
## Flag
picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_b75fc848}

## Key Takeaways
Any time user input reaches a system shell, treat pipe (|), semicolon (;), backtick, and &&/|| characters as potential injection vectors.
