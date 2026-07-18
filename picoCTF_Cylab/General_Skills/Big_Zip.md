# Big Zip - General Skills

**Points:** 100 | **Difficulty:** Easy

## Challenge Description
<img width="816" height="608" alt="image" src="https://github.com/user-attachments/assets/95b213c3-0ceb-41de-8c0c-ba04cbb6b206" />


## Files/Info Given
- attached zip file

## Solution
Firstly, lets download the zip file into the webshell using wget command.
```bash
$ wget https://artifacts.picoctf.net/c/505/big-zip-files.zip
```
Using file command we found that it is indeed a zip file and needs to be unzipped.
We can unzip it by simply
```bash
$ unzip big-zip-files.zip
```
It loads the screen with lot of files containing large .txt files.
Then use cd command to move inside big-zip-files directory now unzipped.

We found very large amount of text files and subdirectories with text files.
So It is not possible to go through every single file and directory and search for flag by reading.

But dont worry, to make our lives easier there is grep command.
We can simply use the command to get the flag(as flag format is picoCTF{})
```bash
$ grep "picoCTF" . -r
```
The ouput we got is :
```bash
./folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```
## Flag
`picoCTF{gr3p_15_m4g1c_ef8790dc}`
