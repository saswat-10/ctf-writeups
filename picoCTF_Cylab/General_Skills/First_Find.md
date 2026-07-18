# First Find - General Skills

**Points:** 100 | **Difficulty:** Easy

## Challenge Description
<img width="827" height="503" alt="image" src="https://github.com/user-attachments/assets/260f0ec5-1415-4626-a224-68d5c4fe30d7" />


## Files/Info Given
- attached zip file

## Solution
Firstly, we download the zip file into our webshell using wget command
```bash
$ wget https://artifacts.picoctf.net/c/501/files.zip
```
Then Upon checking file type using file command we confirm that it is a zip file and needs to be unzipped.
```bash
$ unzip files.zip
```
Using ls command, we can see a new directory named files . Upon inspecting the files directory we can see it is a large directory with lot of subdirectories.

Our objective is to find a file named 'uber-secret.txt'

We can use find command here to make our lives easier.

Its syntax is:
```bash
$ find [path] [options] [expression]
```

The command we use to find the file 'uber-secret.txt' is:
```bash
$ find . -name 'uber-secret.txt'
```
So we are searching for file named uber-secret.txt in current directory and its sub directories so we used '.' in file path .

The output we get is
```bash
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```
We can simply copy the path and use cat command to read the flag.
```bash
$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

## Flag
`picoCTF{f1nd_15_f457_ab443fd1}`
