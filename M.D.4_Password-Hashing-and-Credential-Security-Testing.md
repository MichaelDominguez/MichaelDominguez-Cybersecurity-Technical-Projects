# M.D.4 — Password Hashing & Credential Security Testing
## John the Ripper Hash Auditing, Password Policy Review, and Authentication Controls

## Overview

This technical cybersecurity project focused on credential security, password hash auditing, authentication weaknesses, and secure identity management practices. The primary hands-on activity used John the Ripper in a controlled lab environment to evaluate how weak passwords can be recovered from provided hash files.

The project also connected the lab results to broader cryptographic and identity concepts, including secure hashing, symmetric and asymmetric encryption, authentication, authorization, and modern identity controls such as multifactor authentication.

> **Portfolio Scope Note:** Screenshots are preserved as watermarked evidence of the hands-on lab. The written report focuses on method, timing, tool behavior, and defensive lessons instead of repeating recovered credential pairs as the main content.

---

## Evidence Screenshots

### John the Ripper Lab Setup

![John the Ripper password hashing and credential security testing setup](images/M.D.4%20Password%20Hashing%20and%20Credential%20Security%20Testing%20Part%201.png)

This screenshot documents the controlled Windows-based lab setup used to work with the John the Ripper directory, supplied hash files, and command-line testing environment. The evidence supports that the project was performed as a hands-on credential-security exercise rather than only as a written summary.

### Hash Auditing Execution

![John the Ripper hash auditing output](images/M.D.4%20Password%20Hashing%20and%20Credential%20Security%20Testing%20Part%202.png)

This screenshot supports the password-auditing workflow where provided hash files were tested through John the Ripper. The focus of the project was to understand how weak or predictable credentials are recovered during authorized testing and how defenders should respond with stronger password policy, multifactor authentication, and secure password-storage practices.

### Credential Security Review

![Password hashing and credential security testing results](images/M.D.4%20Password%20Hashing%20and%20Credential%20Security%20Testing%20Part%203.png)

This screenshot provides supporting evidence for the final testing stage, including review of generated tool artifacts and cleanup. The project emphasized proper handling of recovered credential artifacts such as `john.log`, `john.pot`, and `john.rec` so testing results do not become a security exposure.

---

## Objectives

- Demonstrate password hash auditing in a controlled lab environment
- Compare password recovery results across DES and MD5 hash files
- Evaluate the impact of dictionary-based attacks and rule-based cracking
- Review generated John the Ripper output files and cleanup procedures
- Explain why outdated hash functions such as MD5 and SHA-1 are not recommended for modern security use
- Connect password security to authentication, authorization, and multifactor authentication concepts

---

## Technologies & Tools Used

### Security Tools

- John the Ripper
- Windows Command Prompt
- Password wordlist testing
- Rule-based password auditing

### Identity & Cryptography Concepts

- Password hashing
- DES-based password hash testing
- MD5 hash testing
- SHA-256 and SHA-512 comparison
- AES symmetric encryption
- RSA asymmetric encryption
- Authentication vs. authorization
- Multifactor authentication
- OpenID Connect and OAuth 2.0 concepts

### Operating Environment

- Windows 10 Enterprise
- Administrator-level lab account
- Controlled local lab files

---

## Ethical Scope

This project was performed only in a controlled educational lab using provided password hash files. The purpose was to understand how attackers may exploit weak credentials and how defenders can improve password policy, authentication controls, and credential protection.

This project info does **not** include real user credential exposure, or instructions for attacking systems without consent.

---

## Password Hash Auditing Workflow

John the Ripper was used to test multiple provided password hash files. The activity demonstrated how password strength, hash type, dictionary selection, and cracking rules affect recovery time.

### Lab Files Used

- `passwd.des`
- `passwd.md5`
- `password.lst`

### Representative Commands

```bash
john passwd.des
```

```bash
john passwd.md5
```

```bash
john --wordlist=password.lst --rules passwd.md5
```

---

## DES Hash Testing

The first password auditing test used a DES-based password file.

### Result Summary

- Hash source tested: `passwd.des`
- Recovery duration: approximately 45 minutes
- Passwords recovered: 5
- Recovered credential values: documented in the controlled lab evidence, but not repeated in the report text

### Security Interpretation

The DES hash test showed that weak passwords can be recovered within a limited time window when they use predictable patterns. This reinforces the importance of strong password policies, password length requirements, and additional controls such as multifactor authentication.

---

## MD5 Hash Testing

The second password auditing test used an MD5-based password file.

### Result Summary

- Hash source tested: `passwd.md5`
- Recovery duration: approximately 30 minutes
- Passwords recovered: 4
- Recovered credential values: documented in the controlled lab evidence, but not repeated in the report text

### Security Interpretation

The MD5 test demonstrated that older or weaker hash formats are not appropriate for protecting credentials in modern environments. MD5 is no longer recommended for security-sensitive use because collision weaknesses and modern cracking capabilities make it unsuitable for password protection.

---

## Dictionary & Rule-Based Cracking

A dictionary-based password audit was performed using `password.lst` with John the Ripper rules enabled.

### Result Summary

- Hash source tested: `passwd.md5`
- Wordlist used: `password.lst`
- Rules enabled: yes
- Recovery duration: approximately 2 seconds
- Passwords recovered: 4
- Recovered credential values: documented in the controlled lab evidence, but not repeated in the report text

### Security Interpretation

This result showed how quickly weak or predictable passwords can be recovered when they appear in common wordlists or follow common user-created patterns. Rule-based cracking is especially effective because it can modify dictionary entries using predictable substitutions, capitalization, or number patterns.

---

## Tool Output & File Handling

After John the Ripper was executed, additional working files were generated in the tool directory.

### Files Generated

- `john.log`
- `john.pot`
- `john.rec`

### Purpose of Generated Files

- `john.log` records tool activity and cracking session details
- `john.pot` stores recovered password results
- `john.rec` supports session recovery if a cracking process is interrupted

These files were removed after testing to maintain a clean lab environment and avoid leaving recovered credential artifacts on the system.

---

## Endpoint Security Observations

During the lab, additional password recovery tools were evaluated in a controlled setting. Some tools were blocked by Windows Security or browser protection controls, showing how endpoint defenses can reduce exposure to potentially risky credential recovery utilities.

### Defensive Takeaway

Endpoint protections, browser security warnings, and controlled execution policies help prevent unauthorized credential dumping or password recovery activity. These controls are especially important in enterprise environments where credential theft is a common attack path.

---

## Cryptographic Security Review

The supplemental encryption and hashing material helped connect the password auditing lab to broader cryptographic security practices.

### Symmetric Encryption

AES is the preferred modern choice for symmetric encryption in .NET-based environments. Symmetric encryption uses the same key for encryption and decryption, making key protection a critical requirement.

### Asymmetric Encryption

RSA is a common asymmetric encryption option in .NET-based environments. Asymmetric encryption uses a public/private key pair and is often used for secure key exchange, digital signatures, and identity-related security workflows.

### Hashing Guidance

MD5 and SHA-1 should not be used for modern security-sensitive applications. SHA-256 and SHA-512 are stronger alternatives for many hashing use cases, although password storage should use dedicated password hashing algorithms and secure configurations rather than general-purpose hashing alone.

---

## Authentication & Authorization Concepts

This project also reviewed the difference between authentication and authorization.

### Authentication

Authentication verifies the identity of a user, device, or service. Passwords are one form of authentication, but relying only on passwords creates risk when users choose weak or reused credentials.

### Authorization

Authorization determines what an authenticated user is allowed to access or perform. Strong authentication must be paired with proper access control to limit damage if credentials are compromised.

### Modern Identity Controls

Modern identity systems commonly use:

- Multifactor authentication
- Centralized identity providers
- OpenID Connect for authentication
- OAuth 2.0 for authorization
- Token-based access control

These controls reduce reliance on standalone passwords and improve account protection.

---

## Technical Skills Demonstrated

- Password hash auditing
- John the Ripper usage in a controlled lab
- DES hash testing
- MD5 hash testing
- Dictionary-based cracking analysis
- Rule-based password auditing
- Credential artifact handling
- Password security risk review
- Authentication and authorization concepts
- Hashing algorithm comparison
- Cryptographic control review
- Multifactor authentication awareness
- Secure identity management fundamentals

---

## Key Security Lessons

- Dictionary attacks are highly effective against predictable credentials
- Rule-based cracking can recover passwords even when users slightly modify common words
- MD5 and SHA-1 should not be used for modern security-sensitive hashing
- Credential artifacts such as `john.pot` should be handled carefully and removed after authorized testing
- Passwords alone are not enough for strong account security
- Multifactor authentication and centralized identity management improve protection against credential compromise

---

## Project Outcome

This project demonstrated how password auditing tools can be used ethically to evaluate credential strength and understand password-based authentication risk. By comparing DES, MD5, and dictionary-based testing results, the project showed how weak passwords can be recovered and why organizations should enforce stronger password policies, multifactor authentication, and secure credential storage practices.

The project also strengthened my understanding of cryptographic fundamentals, including the difference between encryption and hashing, the risks of outdated algorithms, and the role of modern authentication and authorization systems in protecting user accounts.

---

## References

- Openwall. (2019). *John the Ripper password cracker*. https://www.openwall.com/john/
- Conrad, E., Misenar, S., & Feldman, J. (2016). *Domain 5: Identity and Access Management*. Syngress.
- Yıldırım, M., & Mackie, I. (2019). *Encouraging users to improve password security and memorability*. International Journal of Information Security.
- Gregg, M., & Santos, O. (2022). *CEH Certified Ethical Hacker Cert Guide*. Pearson Education.
- Microsoft. *Microsoft Identity Platform documentation*.
