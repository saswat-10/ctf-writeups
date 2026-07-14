# Binary Digits - Forencics (picoCTF 2026)

**Points:** 100 | **Difficulty:** Easy

## Challenge Description
<img width="827" height="520" alt="image" src="https://github.com/user-attachments/assets/7ba5d098-39b4-4f38-9598-dfe0e79719e1" />


## Files/Info Given
- attached binary file named (digits.bin)

## Recon / Initial Analysis
I opened the file and it contained raw binary data containing sequences of 1s and 0s assigned to a variable named text

<img width="658" height="586" alt="image" src="https://github.com/user-attachments/assets/59ebb02c-c236-4f5f-98bf-f18dae67e8cc" />

## Approach
I used cyberchef tool(https://gchq.github.io/CyberChef/) for this challenge.
I copied the binary code enclosed inside "" , then pasted it in input of cyberchef. I used 'from binary' filter to decode it back to its raw file data.

<img width="1917" height="843" alt="image" src="https://github.com/user-attachments/assets/fff547c9-9e83-4173-8f59-ea1b35499413" />

The raw file data has header of `ÿØÿà...JFIF` which is header for jpg/jpeg image files. I saved the file to my computer with .jpg extension. 


## Solution
Finally, opening the jpg image revealed the flag.

<img width="800" height="496" alt="image" src="https://github.com/user-attachments/assets/cb574fa7-37e1-4198-b0c8-7952ad885ec1" />


## Flag
`picoCTF{h1dd3n_1n_th3_b1n4ry_2607862b}`
