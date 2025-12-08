Password Cracking Report – Booking System Phase 2
Introduction

In this phase, we analyzed the password security of the Booking System by extracting MD5 password hashes from the system database and attempting to crack them. Since MD5 is an outdated and insecure hashing algorithm, unsalted MD5 hashes can often be cracked instantly using public wordlists and online MD5 cracking tools.

We cracked five different user password hashes using an online MD5 decryption tool. The results demonstrate how weak and predictable passwords expose the system to credential theft.

Cracked Passwords

Below are the five hashes, their cracked passwords, explanations, and the required screenshots (saved as SS_1–SS_5).

1. Hash:
a0e8402fe185455606a2ae870dcbc4cd


Cracked password: carrots123
Explanation:
This password is weak because it is based on a common dictionary word (“carrots”) with predictable numbers (“123”). Such passwords are commonly found in public password dumps.

Screenshot: <img width="1344" height="503" alt="SS_1" src="https://github.com/user-attachments/assets/f4657b12-480a-462d-bb5f-5f656a233a52" />


2. Hash:
d730fc82effd704296b5bbcff45f323e


Cracked password: donuts4life
Explanation:
Although longer, the password is still based on a predictable phrase. Attackers easily crack such passwords using themed dictionaries (e.g., food-related wordlists).

Screenshot: <img width="1349" height="577" alt="SS_2" src="https://github.com/user-attachments/assets/dcb1cf5e-6a69-4e02-a897-15318a5fc54e" />


3. Hash:
735f7f5e652d7697723893e1a5c04d90


Cracked password: iamvengeance
Explanation:
This password is based on a pop-culture reference. Pop-culture terms appear frequently in wordlists, making them easy to crack even if they look complex.

Screenshot: <img width="1466" height="576" alt="SS_3" src="https://github.com/user-attachments/assets/a74c19c2-0e75-466b-964a-62a8516435d2" />


4. Hash:
7cb56c2b86150b797cff32eaef97f338


Cracked password: breaking4thwall
Explanation:
Attempts at creativity (like replacing "fourth" with "4th") do not significantly improve security if the base phrase is well-known.

Screenshot: <img width="1372" height="603" alt="SS_4" src="https://github.com/user-attachments/assets/60c64a5a-72e1-4353-9487-fc5578146a95" />


5. Hash:
706ab9fc256efabf4cb4cf9d31ddc8eb


Cracked password: darkside42
Explanation:
Even though this password includes a number, it is predictable and tied to well-known themes (Star Wars, villain words). Attackers often test themed wordlists first.

Screenshot: <img width="1411" height="581" alt="SS_5" src="https://github.com/user-attachments/assets/834d39be-2a28-4ca1-bd9e-9a00c7ce202e" />


Required Questions
1. What is the main difference between Dictionary and Non-Dictionary attacks?

Dictionary attack:
Uses a predefined list of likely passwords (wordlists). Very fast. Works well against weak or commonly used passwords.

Non-dictionary attack:
Tries every possible combination (bruteforce) or uses rules to mutate characters. Much slower but can eventually crack even strong passwords.

2. What advantage does an attacker gain by having access to the system’s database that reveals the users and password hashes?

The attacker can perform offline cracking, which:

avoids rate limits

avoids account lockouts

avoids alerts

They can try billions of guesses per second.

They immediately get all users and all password hashes at once.

Even one cracked password can often allow privilege escalation.

3. What security benefits do longer passwords provide?

Longer passwords increase the number of possible combinations exponentially.

Brute-force attacks become extremely slow or impossible.

They make dictionary and hybrid attacks less effective because the password space becomes too large.

Even a simple long passphrase is more secure than a short complex password.
