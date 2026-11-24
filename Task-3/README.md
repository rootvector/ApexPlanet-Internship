# APEXPLANET SOFTWARE PVT. LTD.
# WEB APPLICATION SECURITY TESTING REPORT

**Internship:** Cybersecurity & Ethical Hacking Internship  
**Task:** Task 3 – Web Application Security  
**Timeline:** Days 25–36  
**Prepared by:** RootVector  
**Brand:** rootvector.sec  
**Testing Environment:** Controlled Lab Environment  
**Report Date:** [DD/MM/YYYY]

---

# 1. Executive Summary

This report documents the web application security testing activities performed as part of Task 3 of the ApexPlanet Cybersecurity & Ethical Hacking Internship.

The objective of this task was to understand, identify, and demonstrate common web application vulnerabilities in a controlled laboratory environment.

The practical activities covered SQL Injection, Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), File Inclusion vulnerabilities, advanced Burp Suite functionality, and web security header analysis.

The testing focused on understanding vulnerability behavior, identifying potential security weaknesses, observing their impact, and studying appropriate mitigation techniques.

All testing activities were intended for authorized laboratory environments.

# 2. Introduction

Web applications are widely used to provide online services, process information, and communicate with users. However, insecure application design and improper input validation can introduce security vulnerabilities.

Attackers may exploit these weaknesses to access sensitive information, execute unauthorized actions, or compromise application functionality.

Web application security testing helps identify such weaknesses before they can be exploited in real-world environments.

This task provided practical exposure to common web application vulnerabilities and the tools used to analyze and test them.

# 3. Objectives

The main objectives of Task 3 were:

- Understand common web application vulnerabilities.
- Install and configure Damn Vulnerable Web Application (DVWA) in Kali Linux.
- Study and demonstrate SQL Injection.
- Understand Stored and Reflected Cross-Site Scripting.
- Study CSRF attacks and token-based protection.
- Understand Local and Remote File Inclusion.
- Use Burp Suite to intercept and modify HTTP requests.
- Perform controlled request fuzzing using Burp Suite Intruder.
- Analyze web security headers.
- Understand mitigation techniques for identified vulnerabilities.

# 4. Lab Environment

The practical exercises were conducted in a controlled laboratory environment.

| Component | Details |
|---|---|
| Attacker machine | Kali Linux |
| Web application | DVWA |
| Testing proxy | Burp Suite |
| Browser | [Browser name] |
| Security header analyzer | SecurityHeaders.com |
| Network environment | [Host-only / isolated lab] |

**Target application:** [Local DVWA URL]

**Note:** Replace the above details with your actual environment configuration.

# 5. Tools Used

### 5.1 Kali Linux
Kali Linux was used as the primary security testing operating system. It provides various tools for web application security testing and penetration testing.

### 5.2 DVWA
Damn Vulnerable Web Application (DVWA) is an intentionally vulnerable web application designed for security education and authorized testing.

It was used to understand and demonstrate different web application vulnerabilities.

### 5.3 Burp Suite
Burp Suite is a web application security testing platform.

It was used to intercept, inspect, and modify HTTP requests and responses.

### 5.4 Burp Suite Intruder
Intruder was used for controlled request fuzzing to understand how applications respond to different input values.

### 5.5 SecurityHeaders.com
SecurityHeaders.com was used to analyze HTTP security headers and understand missing or improperly configured security protections.

# 6. Practical Implementation

## 6.1 SQL Injection

**Objective:** Understand how SQL Injection vulnerabilities occur when applications handle untrusted user input in database queries.

**Description:**

SQL Injection is a web application vulnerability that occurs when user-supplied input is incorporated into SQL queries without proper validation or parameterization.

An attacker may manipulate database queries and potentially access or modify unauthorized information.

**Practical procedure:**

1. Install and configure DVWA in the Kali Linux environment.
2. Open the DVWA web interface.
3. Configure the required security level.
4. Navigate to the SQL Injection module.
5. Submit controlled test inputs.
6. Observe the application's responses.
7. Study how insecure database query construction creates the vulnerability.
8. Examine prepared statements as a mitigation technique.



## 6.2 Cross-Site Scripting (XSS)

**Objective:** Understand how malicious scripts can execute in a user's browser through improperly handled application input.

**Description:**

Cross-Site Scripting is a vulnerability that allows attacker-controlled content to execute as script within another user's browser in the context of a vulnerable website.

The task covered two common types:

**Stored XSS:** Malicious input is stored by the application and later displayed to users.

**Reflected XSS:** User input is immediately reflected in the application's response.

**Practical procedure:**

1. Open the DVWA XSS modules.
2. Examine how the application processes user input.
3. Test controlled inputs in the Stored XSS module.
4. Observe the application's response.
5. Repeat the analysis using the Reflected XSS module.
6. Study input validation and output encoding.
7. Understand the purpose of Content Security Policy (CSP).



## 6.3 Cross-Site Request Forgery (CSRF)

**Objective:** Understand how CSRF can cause an authenticated user to perform an unintended action.

**Description:**

Cross-Site Request Forgery is an attack in which a malicious website or request attempts to make a user's authenticated browser perform an unwanted action on another website.

**Practical procedure:**

1. Open the DVWA CSRF module.
2. Examine the password-change functionality.
3. Study how the application handles submitted requests.
4. Demonstrate the CSRF scenario within the authorized lab.
5. Examine how token-based protection prevents unauthorized requests.
6. Compare the behavior before and after protection.



## 6.4 File Inclusion Attacks

**Objective:** Understand how insecure file-handling mechanisms can expose sensitive files or create security risks.

**Description:**

File Inclusion vulnerabilities occur when an application dynamically loads files based on user-controlled input without sufficient validation.

Two types were covered:

**Local File Inclusion (LFI):** Attempts to access files available on the local server.

**Remote File Inclusion (RFI):** Attempts to include files hosted on an external system when the application configuration permits it.

**Practical procedure:**

1. Open the DVWA File Inclusion module.
2. Examine how the application loads requested files.
3. Study controlled Local File Inclusion behavior.
4. Analyze the security risks associated with Remote File Inclusion.
5. Examine safe file-handling practices and server configuration.



## 6.5 Burp Suite Advanced

**Objective:** Learn to intercept and modify HTTP requests and understand controlled request fuzzing.

**Description:**

Burp Suite acts as an intercepting proxy between a browser and a web application. It allows testers to inspect and modify HTTP requests and responses.

**Activities performed:**

- Configure the browser to use Burp Suite Proxy.
- Intercept HTTP requests.
- Inspect request parameters and headers.
- Modify login request parameters in the authorized lab.
- Forward modified requests.
- Use Burp Suite Intruder for controlled input fuzzing.
- Observe application responses.



## 6.6 Web Security Headers

**Objective:** Understand HTTP security headers and analyze a test website's security configuration.

**Description:**

HTTP security headers provide browser-level security controls that help reduce certain web application attacks.

**Practical procedure:**

1. Open SecurityHeaders.com.
2. Enter an authorized test website.
3. Analyze the available HTTP security headers.
4. Record missing or improperly configured headers.
5. Study how security headers can improve browser-side protection.
6. Examine how HTTP response headers can be configured in the application or web server.

**Headers studied:**

- Content-Security-Policy (CSP)
- Strict-Transport-Security (HSTS)
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy



# 7. Summary of Testing Activities

| Vulnerability / Activity | Status |
|---|---|
| SQL Injection | [Completed / Pending] |
| Stored XSS | [Completed / Pending] |
| Reflected XSS | [Completed / Pending] |
| CSRF | [Completed / Pending] |
| LFI | [Completed / Pending] |
| RFI | [Completed / Studied / Pending] |
| Burp Suite Proxy | [Completed / Pending] |
| Intruder Fuzzing | [Completed / Pending] |
| Security Headers | [Completed / Pending] |

# 8. Security Findings and Recommendations

The practical exercises demonstrated how insufficient input validation, insecure request handling, and improper web server configuration can introduce security weaknesses.

The following general recommendations were identified:

1. Use parameterized SQL queries to prevent SQL Injection.
2. Implement context-aware output encoding to reduce XSS risks.
3. Use CSRF tokens to protect state-changing requests.
4. Restrict file access using secure allowlists.
5. Apply secure authentication and session management.
6. Configure appropriate HTTP security headers.
7. Regularly test and update web applications.
8. Follow secure coding practices throughout application development.

**Important:** The recommendations above describe general security controls. Specific findings should be added only after testing and evidence collection.

# 9. Learning Outcomes

Through this task, I developed practical understanding of:

- Common web application security vulnerabilities.
- SQL Injection and secure database query handling.
- Stored and Reflected XSS.
- CSRF attacks and token-based protection.
- Local and Remote File Inclusion risks.
- HTTP request interception using Burp Suite.
- Controlled fuzzing using Intruder.
- HTTP security headers and browser protections.
- Vulnerability mitigation and secure application development.

# 10. Conclusion

Task 3 provided practical exposure to web application security testing and common vulnerabilities.

The exercises helped develop an understanding of how insecure input handling, request validation, file inclusion, and server configuration can affect application security.

The task also provided experience with tools such as DVWA, Burp Suite, and SecurityHeaders.com.

Understanding both vulnerability behavior and mitigation techniques is an important part of developing responsible penetration-testing skills.

# 11. References

1. OWASP Foundation – https://owasp.org/
2. OWASP Top 10 – https://owasp.org/www-project-top-ten/
3. DVWA – https://github.com/digininja/DVWA
4. PortSwigger Web Security Academy – https://portswigger.net/web-security
5. Burp Suite Documentation – https://portswigger.net/burp/documentation
6. Security Headers – https://securityheaders.com/

---

**Prepared by:** RootVector  
**Cybersecurity Identity:** rootvector.sec  
**Internship:** ApexPlanet Cybersecurity & Ethical Hacking Internship  
**Task:** Task 3 – Web Application Security