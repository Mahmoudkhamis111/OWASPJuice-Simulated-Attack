# Web Penetration Testing Report

---

## Executive Summary

### Purpose of the Test

This report evaluates the security of the Juice Shop application. The focus is on identifying critical vulnerabilities such as Cross-Site Scripting (XSS) and SQL Injection that could lead to:

- Data theft
- Unauthorized access
- System compromise

---

## Scope and Methodology

### Scope

The security assessment was limited to:

- The search functionality in the Juice Shop application.
- Login fields and admin functionalities.

### Methodology

- **Testing Approach:**
  - Black-box testing to simulate external attacks.
  - Manual and automated techniques for vulnerability detection.
- **Tools Used:**
  - **Burp Suite** for request interception and modification.
  - **OWASP ZAP** for vulnerability scanning.
  - **Hydra** for brute-force attacks.
  - **Gobuster** and **Dirb** for URL enumeration.

---

## Vulnerability Findings

### Critical Vulnerabilities

#### 1. Enumeration to Find Admin Path

- **Description:** 
  Attackers analyzed URLs to uncover hidden admin paths.
- **Risk and Impact:**
  - Exposed admin endpoints enabled further exploitation.
- **Evidence:**
  ![Enumeration to Find Admin Path](https://github.com/Mahmoudkhamis111/OWASPJuice-Simulated-Attack/blob/main/WhatsApp%20Image%202024-12-28%20at%2002.10.33_e12adf1e.jpg?raw=true)
- **Mitigation Steps:**
  1. Hide admin paths from public access.
  2. Use access control mechanisms to secure sensitive endpoints.
  3. Monitor and log unusual requests to detect enumeration attempts.
---

#### 2. Brute Force on Admin Credentials

- **Description:**
  The admin login page lacked rate-limiting, enabling brute-force attacks.
- **Risk and Impact:**
  - Admin account compromise led to full application control.
- **Evidence:**
  ![Brute Force on Admin Credentials](https://github.com/Mahmoudkhamis111/OWASPJuice-Simulated-Attack/blob/main/WhatsApp%20Image%202024-12-28%20at%2002.18.23_aac10af9.jpg?raw=true)
- **Mitigation Steps:**
  1. Enforce account lockout policies after repeated failed attempts.
  2. Require strong, complex passwords.
  3. Implement two-factor authentication (2FA).
  4. Monitor login attempts and block IPs after excessive failures.

---

#### 3. XSS in Product Search

- **Description:**
  The search field failed to sanitize user input, allowing script injection.
- **Risk and Impact:**
  - Theft of cookies and session tokens.
  - Session hijacking and unauthorized actions.
- **Evidence:**
  ![XSS in Product Search](https://github.com/Mahmoudkhamis111/OWASPJuice-Simulated-Attack/blob/main/WhatsApp%20Image%202024-12-28%20at%2001.37.55_66c6ee85.jpg?raw=true
)
- **Mitigation Steps:**
  1. Implement input validation and output encoding.
  2. Enforce a Content Security Policy (CSP) to block unauthorized scripts.
  3. Use libraries like **DOMPurify** to sanitize inputs.
---


#### 4. BruteForce an Admin Password
# Brute Force on Admin Password Using Hydra Tool in Kali Linux

## Introduction

Brute forcing an admin password using the Hydra tool in Kali Linux involves systematically attempting various password combinations until the correct one is found. Hydra supports multiple protocols and can utilize wordlists to enhance the efficiency of the attack, making it a powerful tool for penetration testing.

## Understanding Hydra and Its Usage

### What is Hydra?
- Hydra is an open-source login cracker that supports over 50 protocols, including SSH, FTP, HTTP, and more.
- It is designed for penetration testing and ethical hacking, allowing security professionals to assess the strength of passwords.

### Why Use Hydra?
- Hydra can perform brute force attacks efficiently by trying multiple username and password combinations simultaneously.
- It is particularly useful for testing the security of systems and identifying weak passwords.

## Setting Up Hydra for Brute Force Attacks

### Installation
- Hydra comes pre-installed with Kali Linux, so no additional installation steps are required.

### Basic Command Structure
- The basic syntax for using Hydra is:
  ```
  hydra -L <userlist> -P <wordlist> <target> <protocol>
```
```
[]()




## Consequences of Vulnerabilities

1. **Data Theft:** Exposure of sensitive information like cookies and user credentials.
2. **Session Hijacking:** Unauthorized access to user accounts.
3. **Application Manipulation:** Altered interfaces and redirection of users.
4. **Reputation Damage:** Loss of trust and potential legal repercussions.

---

## Mitigation and Solutions

1. **Input Validation:**
   - Block harmful code by validating all user inputs.
2. **Output Encoding:**
   - Encode outputs to prevent scripts from executing in browsers.
3. **Content Security Policy (CSP):**
   - Enforce strict CSP rules to limit unauthorized script execution.
4. **Regular Security Testing:**
   - Perform automated and manual security audits regularly.

---

## Conclusion

### Summary of Security Posture

The assessment revealed critical vulnerabilities in the Juice Shop application that pose significant risks to security and integrity. Immediate remediation is necessary to safeguard data and comply with security standards.

### Recommendations

1. Address identified vulnerabilities, especially XSS and SQL Injection.
2. Implement strong authentication measures.
3. Regularly train developers in secure coding practices.
4. Conduct periodic penetration tests to identify and address future risks.

---

## Team Composition

- **Abdullah Nasser Najeeb  (__2305248__)** 
- **Mahmoud Khamis Ali  (__2305210__)**  

---

## Resources

- [OWASP Juice Shop Website](https://github.com/bkimminich/juice-shop)
- Tools Used: **Burp Suite**, **Hydra**, **Gobuster**, **OWASP ZAP**

---
