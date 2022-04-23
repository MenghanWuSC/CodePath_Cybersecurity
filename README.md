# Project 9 - Pentesting Live Targets

Time spent: **4** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: **blue**, **green**, and **red**.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection (SQLi)

Description: To start the SQL Injection attack, be sure to try on some particular symbols `'` `"` to see whether the website sanitizes the inputs.
It seems that the Blue site fails to do so, which is subject to possible SQL Injection attacks.

Symptom indicates:
> Database query failed.

<img src="blue-vuln1.gif">

Vulnerability #2: Session Hijacking/Fixation

Description: With the help of `public/hacktools/change_session_id.php` you may arbitrarily change the **session ID**. That is, if the website does not properly implement the authentication mechanism, just as the Blue site, the attacker may simultaneously log-in in multiple browsers with the same session ID.

<img src="blue-vuln1.gif">

## Green

Vulnerability #1: Username Enumeration

Description: As the developer of the website, you had better not leak additional information in case of **the oracle attack**. In this case, take a careful look at the Green site's signal messages when using the Username `jmonroe99`.

Symptom indicates:
> Log in was unsuccessful.

<img src="green-vuln1.gif">

Vulnerability #2: Cross-Site Scripting (XSS)

Description: When it comes to the feature: **form input**, a adequate sanitizing of inputs is required. It seems that the Green site fails to do so, which is subject to possible Cross-Site Scripting attacks when logging-in to the backend.

<img src="green-vuln1.gif">

## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)

Description:

<img src="red-vuln1.gif">

Vulnerability #2: Cross-Site Request Forgery (CSRF)

Description:

<img src="red-vuln1.gif">

## Notes

Describe any challenges encountered while doing the work
