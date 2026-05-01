# Bug Reports – Kittygram Authorization

| ID | Bug Name | Priority | Status | Preconditions | Steps to Reproduce | Expected Result | Actual Result |
|----|----------|----------|--------|---------------|-------------------|-----------------|---------------|
| B4 | Upon successful authorization, the main page opens instead of the "add cat" page. | Standard | Open | 1. Registration completed (valid login/password).<br>2. User not logged in.<br>3. Login page open. | 1. Enter valid login.<br>2. Enter valid password.<br>3. Click Login. | "Add cat" page opens. | Main page opens. |
| B7 | Can log in with login containing surrounding spaces. | Critical | Open | Same as B4. | 1. Enter login with spaces before and after.<br>2. Enter valid password.<br>3. Click Login. | User stays on login page (error). | Page accessible to unauthorized user opens. |
| B8 | Can log in with password containing surrounding spaces. | Critical | Open | Same as B4. | 1. Enter valid login.<br>2. Enter password with spaces before and after.<br>3. Click Login. | User stays on login page (error). | Page accessible to unauthorized user opens. |
| B9 | Authorized user is not redirected from login page to main page. | Critical | Open | User is already authorized. | 1. Go directly to login page (`/signin`). | User should be redirected to main page. | User stays on login page (or sees inaccessible page?). |

---

## Summary

- **Critical:** 3 (B7, B8, B9)
- **Standard:** 1 (B4)

All bugs are in **Open** status.