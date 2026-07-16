# StegoRSA - Cryptography (picoCTF 2026)

**Points:** 100 | **Difficulty:** Easy

## Challenge Description

<img width="823" height="696" alt="image" src="https://github.com/user-attachments/assets/c73bc234-bc3d-44b7-a01b-af1d48ef6b04" />


## Files/Info Given
- attached image file
- attached encoded file

## Recon / Initial Analysis
The image attached was a image of a key and the attached encoded file contains the flag encoded which needs to be decoded using its RSA key.

An RSA key is a pair of mathematically linked cryptographic keys (Public and Private) used in the RSA algorithm for secure data transmission, digital signatures, and authentication. While Public key are used to encode a message and private key can be used to decode it. We need to find private key.

## Approach
I looked for metadata of the image given in https://fotoforensics.com/ . Metadata revelead hex data in the jpeg comment. We can decode the hex data to its raw file using cyberchef tool(https://gchq.github.io/CyberChef/). 

<img width="1682" height="862" alt="image" src="https://github.com/user-attachments/assets/1255aefb-5db7-410f-adb1-284863b7a9ce" />

<img width="1857" height="846" alt="image" src="https://github.com/user-attachments/assets/0cb04f75-d18a-4da0-8ca2-dc3426febf8e" />

After decoding we found out that it is a RSA private key. I saved the key in 'key.rsa' file using nano command.

## Exploitation / Solution

To decrypt the encoded file using RSA private key, we can use OpenSSL. The command we used is

```bash
openssl pkeyutl -decrypt -inkey key.rsa -in flag.enc -out flag
```
Here we decrypted the encoded file(flag.enc) using private key(key.rsa) and redirected the output to a file named (flag).
Then we can read the flag using cat command.

<img width="592" height="127" alt="image" src="https://github.com/user-attachments/assets/07ec0139-6072-4fb2-b0e4-e576171986ca" />

## Flag
`picoCTF{rs4_k3y_1n_1mg_ce170c3d}`
