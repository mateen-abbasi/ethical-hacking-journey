TryHackMe — Offensive Security Intro

Date: 2025-10-06

Room: Offensive Security Intro — https://tryhackme.com/room/offensive-security-intro

Completed: Yes (AttackBox machine was used)

Summary

Intro to offensive security and web reconnaissance. In this lab I used gobuster to discover hidden directories on the FakeBank web app, found /bank-transfer, accessed the page in the browser and submitted a simulated transfer to credit account 8881 with $2000 (lab task).

Environment

Platform: TryHackMe AttackBox (in-browser Kali)

Target: fakebank.thm (TryHackMe lab domain shown in room)

Tools used: gobuster, web browser, browser devtools (form inspection), optional curl

Commands / Steps (exact)

Directory discovery with gobuster: gobuster dir -u http://fakebank.thm -w wordlist.txt

Observed output included /bank-transfer with HTTP 200.

Open discovered path in browser: http://fakebank.thm/bank-transfer

Observed a simple transfer form with fields from, to, amount.

Submit the simulated transfer (in-browser): filled the form and clicked Submit to transfer $2000 from account 2276 to account 8881.

Optional example using curl: curl -X POST "http://fakebank.thm/bank-transfer" -d "from=2276&to=8881&amount=2000"

Result: success page / updated balance visible on account page.
