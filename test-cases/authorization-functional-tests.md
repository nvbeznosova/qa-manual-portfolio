# Functional Test Cases: Kittygram Authorization

## Preconditions (for all tests unless overridden)
- Registration completed, valid login and password obtained.
- User is not logged in.
- Authorization page (`/signin`) is open.

---

## Successful Authorization

| ID | Test case name | Steps | Expected result | Status | Bug ID |
|----|----------------|-------|-----------------|--------|--------|
| T1 | Successful authorization | 1. Enter valid login.<br>2. Enter valid password.<br>3. Click Login. | "Add new cat" page opens. | **Failed** | B4 |
| T2 | Successful authorization after unsuccessful attempt | 1. Click Login with empty fields.<br>2. Then enter valid credentials.<br>3. Click Login again. | "Add new cat" page opens. | **Failed** | B4 |
| T11 | Re‑login (logout then login again) | 1. Login successfully.<br>2. Logout.<br>3. Login again with same credentials. | "Add new cat" page opens. | **Failed** | B4 |

---

## Failed Authorization – Non‑existent Login / Existing Password

| ID | Test case name | Steps | Expected result | Status | Bug ID |
|----|----------------|-------|-----------------|--------|--------|
| T3 | Existing login in different case | Enter login in wrong case, correct password. | Stay on login page, error "Incorrect login or password". | Passed | – |
| T4 | One space before existing login | Enter `" login"` (space then valid login). | Stay on login page, error message. | **Failed** | B7 |
| T5 | One space after existing login | Enter `"login "` (valid login + space). | Stay on login page, error message. | **Failed** | B7 |
| T6 | Empty login | Leave Name blank, enter valid password. | Error about empty login. | Passed | – |

---

## Failed Authorization – Existing Login / Non‑existent Password

| ID | Test case name | Steps | Expected result | Status | Bug ID |
|----|----------------|-------|-----------------|--------|--------|
| T7 | Existing password in different case | Valid login, password in wrong case. | Stay on login page, error message. | Passed | – |
| T8 | One space before existing password | Valid login, `" password"` (space then valid password). | Stay on login page, error message. | **Failed** | – |
| T9 | One space after existing password | Valid login, `"password "` (valid password + space). | Stay on login page, error message. | **Failed** | B8 |
| T10 | Empty password | Valid login, leave Password blank. | Error: "The password field is required." | Passed | – |

---

## Password Visibility Toggle

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T12 | Switch eye from closed to open (filled field) | Password field filled, eye crossed out. | Click eye icon. | Entered text becomes visible. | Passed |
| T13 | Switch eye from open to closed (filled field) | Password field filled, eye open. | Click eye icon. | Entered text hidden (dots). | Passed |
| T14 | Paste text into Password field | Valid password in clipboard, eye hidden. | Paste into Password field, then click eye. | Copied text displayed. | Passed |

---

## Registration Link

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T15 | Follow registration link | Click "Not registered yet? Register". | Registration page opens. | Passed |

---

## Redirects (Unauthorized User)

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T16 | Direct link to main page | Go to `/` (main page). | Authorization page opens. | Passed |
| T17 | Direct link to secondary page (e.g., `/cats/add`) | Go to page not accessible without login. | Authorization page opens. | Passed |

---

## Redirects (Authorized User)

| ID | Test case name | Preconditions | Steps | Expected result | Status | Bug ID |
|----|----------------|---------------|-------|-----------------|--------|--------|
| T18 | Authorized user tries to open login page | User already logged in. | Go to `/signin` directly. | Main page opens (redirect). | **Failed** | B9 |

---

## Opening Authorization Page (without redirects)

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T19 | Direct link (not logged in) | User not logged in. | Go to `/signin`. | Authorization page opens. | Passed |
| T20 | From registration page | User on registration page. | Click "Already registered? Login". | Authorization page opens. | Passed |

---

## Placeholder Visibility – Name Field

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T21 | Initially visible | – | Open login page. | Placeholder "Name" shown. | Passed |
| T22 | Disappears after typing | Field empty. | Enter 1+ characters. | Placeholder gone. | Passed |
| T23 | Reappears after clearing | Field has text. | Clear the field. | Placeholder shown again. | Passed |

---

## Placeholder Visibility – Password Field

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T24 | Initially visible | – | Open login page. | Placeholder "Password" shown. | Passed |
| T25 | Disappears after typing | Field empty. | Enter 1+ characters. | Placeholder gone. | Passed |
| T26 | Reappears after clearing | Field has text. | Clear the field. | Placeholder shown again. | Passed |

---

## Summary of Found Bugs

| Bug ID | Description | Affected Tests |
|--------|-------------|----------------|
| B4 | Successful authorization fails (page does not open correctly) | T1, T2, T11 |
| B7 | Leading/trailing spaces in login not handled (should be trimmed) | T4, T5 |
| B8 | Trailing space in password not handled | T9 |
| B9 | Authorized user is not redirected from login page | T18 |

---

## Notes
- All other tests passed.
- For layout and field appearance, refer to `authorization-page-test-cases.md`.
- Tests T8 (space before password) failed but no bug ID assigned – investigate if same as B8?.