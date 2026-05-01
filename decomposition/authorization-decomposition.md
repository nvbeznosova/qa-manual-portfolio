# Decomposition of the Authorization Process (Kittygram)

> **Note:** Clarified requirements are highlighted in grey (the ambiguous parts have been resolved).

## Main Objects / Test Coverage

### Authorization Process

#### Successful Authorization
- **Existing login and password pair** – user can log in
- **Successful authorization after unsuccessful authorization** – after a failed attempt, the next valid attempt works

#### Failed Authorization

##### Non‑existent login, existing password
- **Login typed in different register** (e.g., uppercase vs lowercase) → should fail
- **Spaces before and after an existing login** → should be trimmed? (expect failure)
- **Login is empty** → error message

##### Existing login, incorrect password
- **Password typed in different case** → should fail
- **Spaces before and after the existing password** → should fail
- **Password is empty** → error message

---

### Error Messages

- **Empty login** – appropriate error shown
- **Empty password** – appropriate error shown
- **Incorrect login and/or password** – error message displayed

---

### Toggle Password Visibility

- **Password is visible** (eye icon toggled)
- **Password is hidden** (dots shown)

---

### Re‑login

- User can log in again after logging out (or after session expires)

---

### Entering Text into the Password Field by Pasting

- Copy‑paste works as expected

---

### Follow the Registration Link

- Clicking "Register" redirects to registration page

---

### Opening the Authorization Page

- **Direct link** – page opens correctly
- **From the registration page** – navigation works

---

### Placeholder Visibility

#### Name Field
- **Visible** – placeholder shown when field empty
- **Hidden** – disappears when user starts typing

#### Password Field
- **Visible** – placeholder shown when field empty
- **Hidden** – disappears when user starts typing