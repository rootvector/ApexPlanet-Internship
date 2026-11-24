# Stored Cross-Site Scripting (XSS) – DVWA

**Project:** ApexPlanet Cybersecurity & Ethical Hacking Internship – Task 3  
**Application:** Damn Vulnerable Web Application (DVWA)  
**Vulnerability:** Stored Cross-Site Scripting (XSS)  
**Security Level:** Low  
**Testing Environment:** Authorized local lab

## 1. Overview

Stored Cross-Site Scripting occurs when an application stores malicious JavaScript input and later displays it to users without proper output encoding.

The injected script may execute whenever someone visits the affected page.

## 2. Payload

**Basic Stored XSS payload:**

```html
<script>alert('Stored XSS')</script>
```

## 3. Testing Procedure

1. Open DVWA in the local lab.
2. Set the security level to Low.
3. Navigate to the XSS (Stored) module.
4. Enter the payload into the message or guestbook input field.
5. Submit the form.
6. Observe whether the JavaScript alert executes.
7. Refresh the page and check whether the payload remains stored and executes again.

## 4. How It Works

- `<script>` starts a JavaScript block.
- `alert()` displays a browser alert.
- The application stores the submitted input.
- If the application later renders the input without proper output encoding, the browser executes the script.

## 5. Observation

_Add your actual testing result here._

- Did the alert execute after submission?
- Did it execute again after refreshing the page?
- Was the submitted content stored?

## 6. Screenshots

Save your actual screenshots in the `Screenshots/` directory.

| Screenshot | Description |
|---|---|
| `01-stored-xss-module.png` | DVWA Stored XSS module |
| `02-stored-xss-input.png` | Payload entered into the form |
| `03-stored-xss-execution.png` | JavaScript alert execution |
| `04-stored-xss-persistence.png` | Execution after refreshing the page |

## 7. Security Impact

- JavaScript execution in another user's browser.
- Potential session-related attacks.
- Unauthorized actions performed through a victim's authenticated browser.
- Manipulation of page content.

Actual impact depends on the application and browser security controls.

## 8. Mitigation

- Apply context-aware output encoding.
- Sanitize HTML when user-submitted HTML is genuinely required.
- Validate input on the server side.
- Use secure cookie attributes such as HttpOnly and SameSite.
- Implement a suitable Content Security Policy (CSP).

## 9. Conclusion

This practical demonstrates how untrusted user input can become stored executable content when an application does not properly encode output.

**Disclaimer:** Testing was performed in an authorized local DVWA lab for educational purposes.
