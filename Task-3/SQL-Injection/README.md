# SQL Injection – DVWA (Low Security)

**Project:** ApexPlanet Cybersecurity & Ethical Hacking Internship – Task 3  
**Application:** Damn Vulnerable Web Application (DVWA)  
**Vulnerability:** SQL Injection (SQLi)  
**Security Level:** Low  
**Testing Environment:** Authorized local lab

---

## 1. Overview

SQL Injection is a web application vulnerability that occurs when an application inserts user-supplied input directly into an SQL query without properly validating or parameterizing it.

An attacker may be able to alter the intended SQL query and access database records that should not be exposed.

For this practical, SQL Injection was studied and tested using DVWA at the Low security level.

## 2. Reference

The following article was used as a reference for understanding the vulnerability and the example payloads:

- **Title:** SQL Injection Vulnerability in DVWA
- **Author:** Esosa Okonedo
- **Published:** March 29, 2025
- **Link:** https://medium.com/@esosaokonedo1999/sql-injection-vulnerability-in-dvwa-da3d9e26db9f

The payload examples below are based on the article's *Low Security Level* section.

## 3. Vulnerability Analysis

The article shows this SQL query in the DVWA Low implementation:

```sql
SELECT first_name, last_name
FROM users
WHERE user_id = '$id';
```

The application inserts the supplied `$id` value directly into the SQL query.

The main security weaknesses are:

- User input is directly concatenated into the SQL query.
- Input is not properly validated or sanitized.
- Prepared statements are not used.
- An attacker can modify the intended SQL query through crafted input.

## 4. SQL Injection Payloads

### 4.1 Classic SQL Injection

**Payload from the reference article:**

```sql
1' OR '1'='1
```

**How it works:**

The payload modifies the original SQL condition:

```sql
SELECT first_name, last_name
FROM users
WHERE user_id = '1' OR '1'='1';
```

The expression `'1'='1'` is always TRUE.

As a result, the database may return multiple records instead of only the record associated with the supplied user ID.

**Testing procedure:**

1. Open DVWA in the local lab.
2. Navigate to the SQL Injection module.
3. Set the security level to Low.
4. Enter the payload in the User ID input field.
5. Submit the request.
6. Observe the application response.

**Observation:**

_Add your actual observation here._

### 4.2 UNION-Based SQL Injection

**Payload from the reference article:**

```sql
1 UNION SELECT user, password FROM users#
```

**How it works:**

The `UNION` operator combines the results of two SELECT queries.

The original query retrieves:

```sql
SELECT first_name, last_name
FROM users
WHERE user_id = '1';
```

The injected query attempts to retrieve:

```sql
SELECT user, password
FROM users;
```

The `#` character is used as a MySQL comment marker, which can comment out the remaining part of the SQL statement.

The original and injected SELECT statements must return compatible numbers of columns and compatible data types for the UNION operation to work.

**Testing procedure:**

1. Keep DVWA at Low security.
2. Open the SQL Injection module.
3. Enter the UNION-based payload in the User ID input field.
4. Submit the request.
5. Observe the returned application output.

**Observation:**

_Add your actual observation here. Do not claim that usernames or password hashes were displayed unless you verified this in your test._

## 5. Results and Evidence

Add screenshots captured from your own DVWA testing.

| Screenshot | Description |
|---|---|
| `01-dvwa-sqli-module.png` | DVWA SQL Injection module |
| `02-normal-input.png` | Normal User ID input and response |
| `03-classic-sqli.png` | Classic SQL Injection test |
| `04-union-sqli.png` | UNION-Based SQL Injection test |

## 6. Security Impact

If a web application is vulnerable to SQL Injection, possible impacts include:

- Unauthorized access to database records.
- Exposure of sensitive information.
- Authentication bypass, depending on the vulnerable query.
- Potential modification or deletion of database data, depending on database permissions and the injection point.

## 7. Mitigation Techniques

The following practices help prevent SQL Injection:

1. **Prepared Statements:** Use parameterized queries with `mysqli_prepare()` or PDO.
2. **Input Validation:** Validate input according to its expected type. For numeric IDs, enforce integer validation.
3. **Least Privilege:** Give the database account only the permissions it requires.
4. **Error Handling:** Avoid exposing detailed database errors to application users.
5. **Secure Coding:** Never build SQL queries by directly concatenating untrusted input.

## 8. Conclusion

This practical demonstrates how unsafe handling of user input can make a web application vulnerable to SQL Injection.

Using DVWA at Low security provides a controlled environment to understand Classic and UNION-Based SQL Injection techniques.

The exercise highlights why prepared statements, proper input validation, and secure database access are important for web application security.

---

**Disclaimer:** All testing was performed in an authorized local DVWA lab for educational purposes.

**Reference:**  
Esosa Okonedo, *SQL Injection Vulnerability in DVWA* (March 29, 2025).  
https://medium.com/@esosaokonedo1999/sql-injection-vulnerability-in-dvwa-da3d9e26db9f
