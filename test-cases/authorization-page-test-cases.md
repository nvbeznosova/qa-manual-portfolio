# Test Cases: Kittygram Authorization Page

## Preconditions
- The authorization page is open.
- User is not logged in (unless specified otherwise).

---

## Page Background

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T1 | Authorization page background | Determine the page background color. | White. | Passed |

---

## Cat Picture

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T2 | Cat image display | Determine location and appearance of the cat picture. | Cat face: black, eye sockets white, pupils black. Located at the top, above "Login" text, horizontally centered. | Passed |

---

## Login Information

| ID | Test case name | Steps | Expected result | Status | Bug ID |
|----|----------------|-------|-----------------|--------|--------|
| T3 | "Login" text | Find the word "Login". | Text: "Login". Color: black. Font: bold. Position: between cat picture and login description. | Passed | – |
| T4 | "Login to Kittygram" text | Find the inscription below "Login". | Text: "Login to Kittygram". Color: gray. Font: slightly bold. | **Failed** | – |

---

## Authorization Form

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T5 | Authorization form | Find the form on the page. | Background white. Shape: rectangular with rounded corners. Position: centered, between login description and footer. Border: none. Shadow color: gray. | Passed |

---

## Name Field

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T6 | Name field appearance | Find the Name field. | Shape: rounded rectangle. Position: top of form. Background: gray. Border: dark gray, thin. Placeholder: "Name", dark gray, normal, left-aligned. | Passed |
| T7 | Text entered in Name field | Enter any text (e.g., "lala"). | Text matches input. Does not touch edges. Color: black. Font: normal. Alignment: left. | Passed |
| T8 | Name field focus | Place cursor in Name field. | Border color turns green. | Passed |

---

## Password Field

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T9 | Password field appearance | Field empty. | Find the Password field. | Shape: rounded rectangle. Between Name field and Login button. Background: gray. Border: dark gray, thin. Placeholder: "Password", dark gray, normal, left-aligned. | Passed |
| T10 | Password field focus | – | Place cursor in Password field. | Border color turns green. | Passed |
| T11 | Text entered with hidden visibility | Eye icon crossed out, field empty. | Enter any text (e.g., "lala"). | Text hidden by black dots. Dots left-aligned, do not touch edges. | Passed |
| T12 | Focus (already covered) | – | – | – | – |
| T13 | Open eye icon | Open eye icon displayed. | Find eye icon near field. | Icon: eye socket + pupil, transparent background, black outline. Location: right edge of Password field. | Passed |
| T14 | Crossed-out eye icon | Crossed-out eye icon displayed. | Find eye icon. | Eye crossed out from right to left. | Passed |

---

## Login Button

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T15 | Login button appearance | Find the button. | Shape: rounded rectangle. Position: below Password field (large gap). Color: dark orange. Border: none. Text: "Login", white, bold, centered (indented right). | Passed |
| T16 | Login button hover | Hover over the button. | Background becomes paler. | Passed |

---

## Text "Or"

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T17 | "Or" text | Find the word "Or" in the form. | Text: "Or". Color: gray. Font: normal. Position: between Login button and registration link, centered. | Passed |

---

## Registration Link

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T18 | Registration link | Find link to registration page. | Text: "Not registered yet? Register". Color: blue. Font: normal. Position: between "Or" and bottom of form. | Passed |
| T19 | Registration link hover | Hover cursor over the link. | Color remains blue, font normal. | Passed |

---

## Page Footer

| ID | Test case name | Steps | Expected result | Status |
|----|----------------|-------|-----------------|--------|
| T20 | Footer caption | Scroll to footer, find app name. | Text: "Kittygram 2024". Color: gray. Font: slightly bold. Centered. | Passed |

---

## Error Messages (Layout)

| ID | Test case name | Preconditions | Steps | Expected result | Status |
|----|----------------|---------------|-------|-----------------|--------|
| T21 | Name required error | – | Leave Name blank, click Login. | Text: "The name field is required." Red, normal font, below Name field. | Passed |
| T22 | Password required error | Valid login exists. | Enter valid login, leave Password blank, click Login. | Text: "The password field is required." Red, normal font, below Password field. | Passed |
| T23 | Incorrect login/password error | User registered. | Enter non‑existent login and password, click Login. | Text: "Incorrect login or password." Red, normal font, below Password field. | Passed |

---

## Summary

- **Total tests:** 23 (including subtests for eye icon, focus, etc.)
- **Passed:** 22
- **Failed:** 1 (T4 – "Login to Kittygram" text style/color mismatch)

**Note:** All layout, field behaviour, and error message tests passed except the subtitle styling. No blocking issues.