# Equivalence Classes for Authorization Form

> **⚠️ Important note:**  
> User data for `engelskeLetter` is provided for demonstration purposes only.  
> **Do not use it** when creating equivalence classes / boundary values and when running tests, because the results may be irrelevant (for example, this user may no longer be logged in). Your test results will not match the reference solution.  
> **To avoid relying on demo data, register your own user and use your own credentials** when creating equivalence classes and executing tests.

---

## Authorization Process

| Inspection group | Category KE | Class name | Test data inside a class | Explanation / optimization |
|----------------|-------------|------------|--------------------------|-----------------------------|
| Authorization process | Successful authorization | correct login and password | Username: `engelskeLetter`<br>Password: `ktokto17` (correct) | Valid credentials → successful login |
| | Failed authorization | correct login, incorrect password | Username: `engelskeLetter`<br>Password: `ktoKTo17` (incorrect) | Wrong password → login fails |
| | | correct password, incorrect login | Username: `enGelskeLetter` (incorrect)<br>Password: `ktokto17` | Wrong username → login fails |

---

## Name Field (Login)

| Category KE | Class name | Test data inside a class | Explanation / optimization |
|-------------|------------|--------------------------|-----------------------------|
| Input characters | space at the beginning | `engelskeLetter` (with leading space) | Check trimming behavior |
| | space at the end | `engelskeLetter` (with trailing space) | Check trimming behavior |
| | case matches | `engelskeLetter` | Valid for successful authorization |
| | case does not match | `enGelskeLetter` | Invalid → unsuccessful authorization |
| Mandatory | empty field | `""` (0 characters) | Required field validation |
| | field contains data | `engelskeLetter` | Valid for successful authorization |

---

## Password Field

| Category KE | Class name | Test data inside a class | Explanation / optimization |
|-------------|------------|--------------------------|-----------------------------|
| Input characters | space at the beginning | `ktokto17` (with leading space) | Check trimming behavior |
| | space at the end | `ktokto17` (with trailing space) | Check trimming behavior |
| | case matches | `ktokto17` | Valid for successful authorization |
| | case does not match | `ktoKTo17` | Invalid → unsuccessful authorization |
| Mandatory | empty field | `""` (0 characters) | Required field validation |
| | field contains data | `ktokto17` | Valid for successful authorization |

---

## Summary of Positive and Negative Classes

- **Positive classes:** correct login + correct password (case‑sensitive match, no extra spaces), both fields non‑empty.
- **Negative classes:**  
  - Correct login + incorrect password  
  - Incorrect login + correct password  
  - Any field empty  
  - Case mismatch for login or password (if system is case‑sensitive)  
  - Leading/trailing spaces (depending on trimming rules)