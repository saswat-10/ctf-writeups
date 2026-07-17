# First Grep - General Skills (picoCTF 2019)

**Points:** 100 | **Difficulty:** Easy

## Challenge Description
<img width="825" height="636" alt="image" src="https://github.com/user-attachments/assets/2bc67f8c-d56a-4dce-a03c-e611104ac1a4" />


## Files/Info Given
- attached file

## Solution
First I right clicked on the file ,copied the link . Then I downloaded it in the webshell using wget command.

```bash
wget https://challenge-files.picoctf.net/c_fickle_tempest/b4b27010334d190b82728db534d40ba520fbcc0b90469bf7db1456c768476c17/filebash
```
Then It downloaded a file named file. Then I checked the type of file it is using file command and the output was.
```bash
file: ASCII text, with very long lines (14545)
```
So It is incredibly difficult to search for flag manually. So this is where grep command comes to rescue. We can use grep command to search for pattern in a file.
Its syntax is given as 
```bash
grep [options] pattern [file...]
```

So I need to search for the string pico or picoCTF as it is the format of flag in the file . So the command I used is
```bash
grep picoCTF file
```
Then It revealed the flag by highlighting the text.

## Flag
`picoCTF{grep_is_good_to_find_things_cEDf1591}`
