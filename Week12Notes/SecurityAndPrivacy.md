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
3. [Authentication](#authentication)
    1. [Authentication Approaches ("Factors")](#authentication-approaches-factors)
    2. [Authentication Methods](#authentication-methods)
    3. [Password-Only Weaknesses](#password-only-weaknesses)
    4. [Federated Identity](#federated-identity)
4. [Authorization](#authorization)
    1. [Access Control Policies](#access-control-policies)
    2. [Access Control Lists](#access-control-lists)
5. [Encryption](#encryption)
    1. [Encryption and Decryption](#encryption-and-decryption)
    2. [Symmetric Encryption](#symmetric-encryption)
    3. [Asymmetric Encryption](#asymmetric-encryption)
    4. [Encryption and authentication](#encryption-and-authentication)
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
    - A session is a time period during which the user's authentication is valid
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
    - User lockout attacks take advantage of a common authentication policy that locks out a user after a number of failed authentication attempts; Their aim is to lock users out rather than gain access and so deny the service to these users
    - Users often use their email addresses as their login name so if an attacker has access to a database of email addresses, he or she can try to login using these addresses
- If you do not lock accounts after failed validation, then attackers can use brute-force attacks on your system; If you do, you may deny access to legitimate users

### Brute Force Attacks 

- **Brute force attacks**
    - attacks on a web application/login system, attacker may know login, but not password
- The attacker creates different passwords and tries to login with each until they succeed
- Simple attack: generate strings, try common passwords
- Brute force attacks rely on users setting weak passwords, so you can circumvent them by insisting that users set long passwords that are not in a dictionary and are not common words

## Authentication

- Authentication is the process of ensuring that a user of your system is who they claim to be 
- You need authentication in all software products that maintain user information, so that only the providers of that information can access and change it 
- You also use authentication to learn about your users so that you can personalize their experience of using your product 

### Authentication Approaches ("Factors")

![Authentication Approaches Example](data:image/png;base64,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)

### Authentication Methods 

- **Knowledge-based authentication**
    - user provides secret, personal information when they reguster with the system; Each time they log on, the system asks for this information 
- **Possession-based authentication**
    - relies on the user having a physical device that can generate or display information that is known to the authenticating system; The user inputs this information to confirm that they possess the authenticating device 
- **Attribute-based authentication**
    - Based on a unique biometric attribute of the user, such as a fingerprint or retinal scan, which is registered with the system 
- **Multi-factor authentication**
    - combines previous approaches and requires users to use more than one authentication method 

### Password-Only Weaknesses...

| Weakness             | Explanation                                                                                                                                               |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Insecure passwords   | Users choose passwords that are easy to remember. However, it is also easy for attackers to guess or generate these passwords, using either a dictionary or a brute force attack. |
| Phishing attacks     | Users click on an email link that points to a fake site that tries to collect their login and password details.                                               |
| Password reuse       | Users use the same password for several sites. If there is a security breach at one of these sites, attackers then have passwords that they can try on other sites. |
| Forgotten passwords  | Users regularly forget their passwords, so you need to set up a password recovery mechanism to allow these to be reset. This can be a vulnerability if users' credentials have been stolen and attackers use that mechanism to reset their passwords. |

### Federated Identity

- **Federated identity**
    - use an external "group" authentication service, not a local login 
- *Examples: login using Google, Facebook, or LinkedIn credentials*
- *Local example: using Appalachian State University credentials*
- Advantage: user has fewer passwords to remember, authentication providers can be "hardened" against attack <br>
![Federated Identity Example: Azure Architecture](https://learn.microsoft.com/en-us/azure/architecture/patterns/_images/federated-identity-overview.png)

## Authorization

- **Authorization**
    - compleentary to authentication, controls access to specific resources *(e.g., you could share a document so someone can edit, but not share or delete it)*
- Authorization rules are generally defined using an *access control policy*
- This policy is a set of rules that define what information (data and programs) is controlled, who has access to that information, and the type of access that is allowed 

### Access Control Policies

- Explicit access control policies are important for both legal and technical reasons 
    - Data protectuon rules limit the access to the personal data; This must be reflected in the defined access control policy; If this policy is incomplete or does not conform to the data protection rules, then there may be subsequent legal action in the event of a data breach 
    - Technically, an access control policy can be a starting point for setting up the access control scheme for a system 
    - *Example: If the access control policy defines the access rights of students, then when new students are registered, they all get these rights by default*

### Access Control Lists

- Access control lists (ACLs) are used in most file and database systems to implement access control policies 
- ACLs are tables that link users with resources and specify what those users are permitted to do 
- If access control lists are based on individual permissions, then thesed can become very large; However, you can deamatically cut their size by allocating users to groups ("roles"), and then assigning permissions to the group (RBAC, "role-based access group")
![Access Control List Diagram](https://www.imperva.com/learn/wp-content/uploads/sites/13/2020/02/access-control-list.jpg)

## Encryption

- Encryption is the process of making a document unreadable by applying an algorithmic transformation to it 
- Modern encryption techniques are such that you can encrypt data so that it is practically uncrackable using currently available technology 
- However, history has demonstrated that apparently strong encryption may be hackable when new technology becomes available 
- If commercial quantum systems become available, we will have to use a completely different approach to encryption on the Internet 

### Encryption and Decryption

![Encryption and Decryption Diagram](https://programmerprodigy.code.blog/wp-content/uploads/2020/04/bfafa-iu.png)

### Symmetric Encryption

- In a symmetric encryption scheme, the same encryption key is used for encoding and decoding the information that is to be kept secret 
- If Alice and Bob wish to exchange a secret message, both must have a copy of this encryption key; Alice encrypts the message with this key; When Bob receives the message, he decodes it using the same key to read its contents 
- The fundamental problem with a symmetric encryption scheme is securely sharing the encryption key 
- If Alice simply sends the key to Bob, an attacker may intercept the message and gain access to the key; The attacker can then decode all future secret communications 

### Asymmetric Encryption 

- Asymmetric encryption does not require secret keys to be shared 
- An asymmetric encryption scheme uses different keys for encrypting and decrypting messages 
- Each user has a public and a private key; Messages ma be encrypted using either key but can only be decrypted using the other key 
- Public keys may be published and shared by the key owner; Anyone can access and use a public key 
- However, messages can only be decrypted by the user's private key so it is only readable by the intended recipient  

### Encryption and Authentication 

- Asymmetric encryption can also be used to authenticate the sender of a message by encrypting it with a private key and decrypting it with the corresponding public key 
    - Say Alice wants to send a message to Bob and she has a copy of his public key 
    - However, she is not sure whether or not the public key that she has to Bob is correct and she is concerned that the message may be sent to the wrong person 
    - Private/public key encryption can be used to verify Bob;s identity -- Bob uses his private key to encrypt a message and sends this to Alice; If it can be decrypted using Bob's public key, then Alice has the correct key 
    - Generally called "signing" the message 

### TLS and Digital Certificates

- The https protocol is a standard protocol for securely exchanging texts on the web; It is the standard http protocol plus an encryption layer called TLS (Transport Layer Security); This encryption layer is used for two things: 
    - To verify the identiti of the web server 
    - To encrypt communications so that they cannot be read by an attacker who intercepts the messages between the client and the server 
- TLS encryption depends on a digital certificate that is sent from the web server to the client 
    - Digital certificates are issued by a certificate authority (CA), which is a trusted identity verification service 
    - The CA encrypts the information in the certificate using their private key to create a unique signature; This signature is included in the certificate along with the public key of the CA; To check that the certificate is valid, you can decrypt the signature using the CA's public key 
- [A good free option](https://letsencrypt.org/)
- [To check your server](https://www.ssllabs.com/ssltest/)

### Parts of a Digital Certificate 

| Certificate element         | Explanation                                                                                                                                          |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Subject information         | Information about the company or individual whose website is being visited. Applicants apply for a digital certificate from a certificate authority who checks that the applicant is a valid organization. |
| Certificate authority information | Information about the certificate authority (CA) who has issued the certificate.                                                                 |
| Certificate information     | Information about the certificate itself, including a unique serial number and a validity period, defined by start and end dates.                     |
| Digital signature           | The combination of all of the above data uniquely identifies the digital certificate. The signature data are encrypted with the CA’s private key to confirm that the data are correct. The algorithm used to generate the digital signature is also specified. |
| Public key information      | The public key of the CA is included along with the key size and the encryption algorithm used. The public key may be used to decrypt the digital signature. |

### TLS in Action 

![TLS in Action Example](https://builtin.com/sites/www.builtin.com/files/styles/ckeditor_optimize/public/inline-images/2_mutual-tls-tutorial.jpg)

### Data Encryption 

- As a product provider, you inevitably store information about your users, and, for cloud-based products, user data 
- Encryption can be used to reduce the damage that may occur from data theft; If information is encrypted, it is impossible, or very expensive, for thieves to access and use the unencrypted data 

### When/Where to Encrypt 

- Data in transit: encrypted when moving data from one computer to another - over the web, using https vs. http (now becoming default - e.g., iOS apps need special permissions to make http calls)
- Data at rest: if data is not being used, then the files where the data is stored should be encrypted so that theft of these files will not lead to disclosure of confidential information 
- Data in use: generally not done here, except for initial encryption/decryption, since this is slow 

### What to Encrypt 

- **Application**
    - The application decides what data should be encrypted and decrypts that data immediately before it is used 
- **Database**
    - The DBMS may encrypt the entire database when it is closed, with the database decrypted with it is reopened; Alternatively, individual tables or columns may be encrypted/decrypted 
- **Files**
    - The operating system encrypts individual files when they are closed and decrypts them when they are reopened 
- **Media**
    - The operating system encrypts disks when they are unmounted and decrypts these disks when they are remounted 

## Privacy 

- **Privacy**
    - a social concept that relates to the collection, dissemination, and appropriate use of personal information held by a third-party 
- Importance of privacy has changed over time and individuals have their own views on what degree of privacy is important 
- Culture and age affect peoples' views on what privacy means: 
    - Younger people were early adopters of the first social networks and many of them seem to be less inhibited about sharing personal information on these platforms than older people 
    - In some countries, the level of income earned by an individual is seen as a private matter; in others, all tax returns are openly published 

### Business Reasons for Privacy 

- If you are offering a product directly to consumers and you fail to conform to privacy regulations, then you may be subject to legal action by product buyers or by a data regulator 
- If your conformance is weaker than the protection offered by data protection regulations in some countries, you will not be able to sell your product in these countries 
- [*Example: The GDPR*](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation)
- If your product is a business product, business customers require privacy safeguards so that they are not put at risk of privacy violations and legal action by users 
- If personal information is leaked or misused, even if this is not seen as a violation of privacy regulations, this can lead to serious reputational damage that may cost you customers 

### Data Protection Laws 

- In many countries, the right to individual privacy is protected by data protection laws 
- These laws limit the collection, dissemination, and use of personal data to the purposes for which it was collected 
    - *Example: A travel insurance company may collect health information so that they can access their level of risk; This is legal and permissable*
    - *Counter-Example: It would not be legal for those companies to use this information to target online advertising of health products, unless their users had given specific permission for this*

### Data Protection Principles 

| Data protection principle | Explanation                                                                                                                                               |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Awareness and control     | Users of your product must be made aware of what data are collected when they are using your product, and must have control over the personal information that you collect from them. |
| Purpose                   | You must tell users why data are being collected and you must not use those data for other purposes.                                                        |
| Consent                   | You must always have the consent of a user before you disclose their data to other people.                                                                  |
| Data lifetime             | You must not keep data for longer than you need to. If a user deletes an account, you must delete the personal data associated with that account.            |
| Secure storage            | You must maintain data securely so that it cannot be tampered with or disclosed to unauthorized people.                                                   |
| Discovery and error correction | You must allow users to find out what personal data you store. You must provide a way for users to correct errors in their personal data.            |
| Location                  | You must not store data in countries where weaker data protection laws apply unless there is an explicit agreement that the stronger data protection rules will be upheld. |

### Creating a Privacy Policy 

- You should establish a privacy policy that defines how personal and sensitive information about users is collected, stored and managed
- Software products use data in different ways, so your privacy policy has to define the personal data that you will collect and how you will use that data
- Product users should be able to review your privacy policy and change their preferences regarding the information that you store
