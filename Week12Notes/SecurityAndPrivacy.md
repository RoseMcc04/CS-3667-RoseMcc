# Security and Privacy

## Table of Contents

0. [Table of Contents](#table-of-contents)
1. [Software Security](#software-security)
2. [Types of Security Threats](#types-of-security-threats)
    1. [Injection Attacks](#injection-attacks)
    2. [SQL Injection Attacks](#sql-injection-attacks)
    3. [Cross-Site Scripting (XSS) Attacks](#cross-site-scripting-xss-attacks)
    4. [Session Hijacking Attacks](#session-hijacking-attacks)
    5. [Cookie Theft](#cookie-theft)
    6. [Actions to Reduce Likelihood of Hacking](#actions-to-reduce-likelihood-of-hacking)
    7. [Denial of Service (DOS) Attacks](#denial-of-service-dos-attacks)
    8. [Brute Force Attacks](#brute-force-attacks)
3. [Authentification](#authentification)
    1. [Authentification Approaches ("Factors")](#authentification-approaches-factors)
    2. [Authentification Methods](#authentification-methods)
    3. [Password-Only Weaknesses](#password-only-weaknesses)
    4. [Federated Identity](#federated-identity)
4. [Authorization](#authorization)
    1. [Access Control Policies](#access-control-policies)
    2. [Access Control Lists](#access-control-lists)
5. [Encryption](#encryption)
    1. [Encryption and Decryption](#encryption-and-decryption)
    2. [Symmetric Encryption](#symmetric-encryption)
    3. [Asymmetric Encryption](#asymmetric-encryption)
    4. [Encryption and Authentification](#encryption-and-authentification)
    5. [TLS and Digital Certificates](#tls-and-digital-certificates)
    6. [Parts of a Digital Certificate](#parts-of-a-digital-certificate)
    7. [TLS in Action](#tls-in-action)
    8. [Data Encryption](#data-encryption)
    9. [When/Where to Encrypt](#whenwhere-to-encrypt)
    10. [What to Encrypt](#what-to-encrypt)
6. [Privacy](#privacy)
    1. [Business Reasons for Privacy](#business-reasons-for-privacy)
    2. [Data Protection Laws](#data-protection-laws)
    3. [Data Protection Principles](#data-protection-principles)
    4. [Creating a Privacy Policy](#creating-a-privacy-policy)

## Software Security 

- Software security should always be a high priority for product developers and their users
- If you do not prioritize security, you and your customers will inevitably suffer losses from malicious attacks
- In the worst case, these attacks could/can put product providers out of business
    - If their product is unavailable or if customer data is compromised, customers are liable to cancel their subscriptions
- Even if they can recover from the attacks, this will take time and effort that would have been better spent working on their software

## Types of Security Threats

- **Availability threats**
    - An attacker attempts to deny access to the system for legitimate users
    - Software product part(s) affected: PROGRAM
    - *Example: Distributed Denial of Service attack (DDOS attack)*
- **Confidentiality threats**
    - An attacker tries to gain access to private information held by the system
    - Software product part(s) affected: DATA
    - *Example: Data theft*
- **Integrity threats**
    - An attacker attempts to damage the system or its data
    - Software product part(s) affected: DATA, PROGRAM
    - *Example(s): Ransomware, Virus*

### Injection Attacks

- A type of attack where a malicious user uses a valid input field to input malicious code or database commands
- These malicious instructions are then executed, causing some damage to the system (e.g., leaked, modified, or destroyed data)
- Common injection types: SQL injection, cross-site scripting (XSS), buffer overflow
- Core similarity: *data* is treated as *code*

### SQL Injection Attacks 

- Attacks on software products that use a SQL database
    - User input is used as part of a SQL command
    - SQL commands provided as part of user input
    - User inout added directly to SQL query, runs as part of the query instead of being treated as data
```sql
database.executeQuery("
SELECT FirstName, LastName
FROM Salesperson
WHERE State = '" + selectedState + "'
")
```
- What if my selectedState is: `'; DROP TABLE Users; --'`

### Cross-Site Scripting (XSS) Attacks 

- Attacker adds malicious JavaScript code to the web page that is returned from a server to a client
- Script is executed when the page is displayed in the user's browser, in the user's context (has access to cookies, maybe other session-related data)
- May steal customer information or direct them to another website:
    - This may try to capture personal data or display advertisements
    - Cookies may be stolen, which makes a session hijacking attack possible

### Session Hijacking Attacks 

- **Session hijacking**
    - a type of attack where an attacker gets a valid session cookie and uses this to impersonate a legitimate user
- When a user authenticates themselves with a web application, a session is created
    - A session is a time period during which the user's authentification is valid
    - During this time, they do not have to re-authenticate
    - Tracked by placing a session cookie on the user's device

### Cookie Theft 

- There are several ways that an attacker can find out the session cookie value
- Cross-site scripting (XSS): script sends cookies/session id to the attackers
- Traffic monitoring: capture session information by monitoring network traffic, either unencrypted or faulty protocols that allow replays

### Actions to Reduce Likelihood of Hacking 

| Action                  | Explanation                                                                                                                                                                                                 |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Traffic encryption      | Always encrypt the network traffic between clients and your server. This means setting up sessions using https rather than http. If traffic is encrypted, it is harder to monitor to find session cookies.    |
| Multifactor authentication | Always use multifactor authentication and require confirmation of new actions that may be damaging. For example, before a new payee request is accepted, you could ask the user to confirm their identity by inputting a code sent to their phone. You could also ask for password characters to be input before every potentially damaging action, such as transferring funds. |
| Short timeouts          | Use relatively short timeouts on sessions. If there has been no activity in a session for a few minutes, the session should be ended and future requests directed to an authentication page. This reduces the likelihood that an attacker can access an account if a legitimate user forgets to log off when they have finished work. |

### Denial of Service (DOS) Attacks 

- DOS attacks are attacks on a software system that are intended to make that system unavailable for normal user
- DDOS attacks are the most common type of DOS attacks
    - Thesr involve distributed computers, that have usually been hijacked as part of a botnet, sending hundreds of thousands of requests for service to a web application; There are so many service requests that legitimate users are denied access
- Other type of DOS attacks target application users
    - User lockout attacks take advantage of a common authentification policy that locks out a user after a number of failed authentification attempts; Their aim is to lock users out rather than gain access and so deny the service to these users
    - Users often use their email addresses as their login name so if an attacker has access to a database of email addresses, he or she can try to login using these addresses
- If you do not lock accounts after failed validation, then attackers can use brute-force attacks on your system; If you do, you may deny access to legitimate users

### Brute Force Attacks 

- **Brute force attacks**
    - attacks on a web application/login system, attacker may know login, but not password
- The attacker creates different passwords and tries to login with each until they succeed
- Simple attack: generate strings, try common passwords
- Brute force attacks rely on users setting weak passwords, so you can circumvent them by insisting that users set long passwords that are not in a dictionary and are not common words

## Authentification

### Authentification Approaches ("Factors")

### Authentification Methods 

### Password-Only Weaknesses...

### Federated Identity

## Authorization

### Access Control Policies

### Access Control Lists

## Encryption

### Encryption and Decryption

### Symmetric Encryption

### Asymmetric Encryption 

### Encryption and Authentification 

### TLS and Digital Certificates

### Parts of a Digital Certificate 

### TLS in Action 

### Data Encryption 

### When/Where to Encrypt 

### What to Encrypt 

## Privacy 

### Business Reasons for Privacy 

### Data Protection Laws 

### Data Protection Principles 

### Creating a Privacy Policy 
