# Log Hunt - General Skills

**Points:** 50 | **Difficulty:** Easy

## Challenge Description
<img width="828" height="737" alt="image" src="https://github.com/user-attachments/assets/be9e9e54-6c62-4113-9ff3-218048bd2dd2" />

## Files/Info Given
- attached log file

## Approach
Initailly I inspected the log file.

<img width="578" height="602" alt="image" src="https://github.com/user-attachments/assets/88dd0d47-a7f0-44d6-9a03-b20b7b09ed9a" />

We can see that parts of flag are being revealed with "INFO FLAGPART:" in the log file. grep command is best to use in this case to filter out useful parts instead of searching throughout the file manually.

The command i used here is 
```bash
grep "INFO FLAGPART:" server.log
```
We got the following output.

<img width="471" height="472" alt="image" src="https://github.com/user-attachments/assets/057f21fe-1030-4d05-9598-6598792cd481" />

We can assemble the flag from these parts easily now.
## Flag
`picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}`
