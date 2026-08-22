# TryHackMe — Corridor

**Platform:** TryHackMe

**Difficulty:** Very Easy

**Category:** Web / IDOR

**Room:** https://tryhackme.com/room/corridor

## Objective

The objective of this room is to investigate a web application and identify an **IDOR (Insecure Direct Object Reference)** vulnerability.

---

## Reconnaissance

I started by scanning the target machine to identify open ports and running services.

```bash
nmap -sC -sV <MACHINE_IP>
```

The scan revealed a web server running on port 80.

I accessed the web application by entering the following URL in a browser:

```text
http://<MACHINE_IP>
```

The page displayed a corridor containing multiple doors.

<img width="1915" height="772" alt="Corridor web application" src="https://github.com/user-attachments/assets/0b410461-70d6-4096-a0ea-b790642a03a4" />

While moving the mouse pointer over the doors, I noticed that they were clickable links pointing to different paths in the URL.

The paths contained values that looked like hexadecimal strings. Since the challenge description mentioned hashes, I investigated these values further.

After checking the values using an MD5 hash lookup tool, I found that the visible door paths corresponded to the MD5 hashes of consecutive numbers.

The same values can also be observed directly in the source code of the webpage.

<img width="1463" height="235" alt="Door paths in page source" src="https://github.com/user-attachments/assets/81b2592e-1046-4a08-9d2d-5067a0ec84cd" />

This indicated that the values used as URL paths were not random. They were predictable MD5 hashes derived from numeric identifiers.

---

## Exploitation

Since the room is based on an **IDOR vulnerability**, I investigated whether I could access another resource by modifying the identifier in the URL.

The application was using the MD5 hash of a number as the URL path. Therefore, I could generate the MD5 hash for other candidate numbers and test them.

The hashes can be generated using:

```bash
echo -n "<candidate>" | md5sum
```

I then tested the resulting hash as a URL path:

```text
http://<MACHINE_IP>/<generated_identifier>
```

Because the identifiers were predictable, it was possible to test values outside the range of the doors displayed on the page.

Another approach would be to generate a list of MD5 hashes for a range of numbers and use a tool such as **ffuf** to automate the requests and identify an interesting response.

The vulnerable behavior demonstrates why using a predictable or hashed identifier does not provide proper access control. The application should verify whether a user is authorized to access the requested resource instead of relying on the obscurity of the identifier.

**Flag:** Omitted from this public write-up in accordance with TryHackMe's write-up submission guidelines.

---

## Key Takeaways

* Learned how to identify potential IDOR vulnerabilities.
* Learned how URL parameters can reveal object references.
* Learned that hashing an identifier does not make it unpredictable or secure.
* Practiced inspecting webpage source code to understand application behavior.
* Practiced generating MD5 hashes and testing predictable identifiers.
* Learned the importance of proper server-side authorization checks.

---

## Conclusion

The Corridor room demonstrated how predictable object references can lead to an IDOR vulnerability.

By inspecting the webpage, identifying the MD5-based URL pattern, and generating additional identifiers, I was able to investigate resources that were not directly exposed through the normal navigation of the application.

The main takeaway is that **encoding or hashing an object identifier is not a substitute for proper access control**. Authorization must be enforced on the server for every requested resource.
