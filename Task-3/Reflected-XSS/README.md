# Reflected Cross-Site Scripting (XSS) – DVWA

**Project:** ApexPlanet Cybersecurity & Ethical Hacking Internship – Task 3  
**Application:** Damn Vulnerable Web Application (DVWA)  
**Vulnerability:** Reflected Cross-Site Scripting (XSS)  
**Security Level:** Low  
**Testing Environment:** Authorized local lab

## 1. Overview

Reflected Cross-Site Scripting occurs when an application immediately includes untrusted user input in its response without proper output encoding.

Unlike Stored XSS, the injected input is generally not saved permanently by the application.

## 2. Payload

**Basic Reflected XSS payload:**

```html
<script>alert('Reflected XSS')</script>
```

## 3. Testing Procedure

1. Open DVWA in the local lab.
2. Set the security level to Low.
3. Navigate to the XSS (Reflected) module.
4. Enter the payload into the input field.
5. Submit the request.
6. Observe whether the JavaScript alert executes.
7. Check whether the input is reflected in the application response.

## 4. How It Works

- The payload contains a JavaScript script element.
- The application receives the submitted input.
- If the application inserts that input into the response without proper output encoding, the browser may execute the script.
- The execution occurs as part of the immediate response rather than through persistent storage.

## 5. Observation

_Add your actual testing result here._

- Did the alert execute immediately after submission?
- Was the input reflected in the response?
- Did the payload remain after refreshing the page?

## 6. Screenshots

Save your actual screenshots in the `Screenshots/` directory.

| Screenshot | Description |
|---|---|
| `01-reflected-xss-module.png` | DVWA Reflected XSS module |
| `02-reflected-xss-input.png` | Payload entered into the form |
| `03-reflected-xss-execution.png` | JavaScript alert execution |
| `04-reflected-xss-response.png` | Application response showing reflected input |

## 7. Security Impact

- JavaScript execution in a victim's browser.
- Potential phishing or page-content manipulation.
- Potential session-related attacks.
- Actions performed in the context of the vulnerable website.

Actual impact depends on the application and its security controls.

## 8. Mitigation

- Apply context-aware output encoding.
- Validate untrusted input.
- Avoid inserting untrusted data into HTML using unsafe DOM operations.
- Use a suitable Content Security Policy (CSP).
- Use secure cookie attributes.

## 9. Conclusion

This practical demonstrates how reflected user input can cause JavaScript execution when a web application fails to encode untrusted data before displaying it.

**Disclaimer:** Testing was performed in an authorized local DVWA lab for educational purposes.
