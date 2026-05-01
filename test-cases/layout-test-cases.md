# Layout & Functional Test Cases – Feedback Form

## Preconditions
- The feedback form page is open.

---

## Layout Test Cases

| ID | Test case name | Steps | Expected result | Status | Bug ID |
|----|----------------|-------|-----------------|--------|--------|
| T1 | Page background gradient | Determine the background color of the page. | Background color is a gradient. | Passed | – |
| T2 | Form window display | Find the form window on the page. | Form is located in the center of the page. White background. A vertical gray line between contact block and form fields. | Passed | – |
| T3 | Form title display | Find the form title on the page. | Title located in the center of the page (right block). Text: "Send us a message". Color: purple. Left-aligned. | **Failed** | B1 |
| T4 | Form subtitle display | Find the website subtitle on the page. | Subtitle below title (right block). Text: "If you have any questions or collaboration suggestions, please fill out the form below." Color: black. Left-aligned. | Passed | – |
| T5 | Contact block display | Find the area of the block with contacts. | Block is on the left. Contains address, phone, email. Elements centered. | Passed | – |
| T6 | Address block | Find the address block. | Contains geolocation icon (purple); heading "Address" (black, bold); "Moscow" (gray); "Kravchenko St., 7" (gray). | Passed | – |
| T7 | Phone numbers block | Find the phone numbers block. | Contains handset icon (purple); heading "Telephone" (black, bold); "8-499-131-88-09" (gray); "8-495-939-33-25" (gray). | Passed | – |
| T8 | Email block | Find the email block. | Contains envelope icon (purple); heading "Email" (black, bold); "feedback@oursite.com" (gray); "letter@oursite.com" (gray). | **Failed** | B2 |
| T9 | Name field | Find the Name field in the form. | Placeholder "Your name". Located at the beginning. Border gray, background gray. Centered field, text left-aligned. | Passed | – |
| T10 | Email field | Find the Email field in the form. | Placeholder "Enter Email". Between Name and Phone. Border gray, background gray. Centered field, text left-aligned. | Passed | – |
| T11 | Message field | Find the Message field in the form. | Placeholder "Message". Below Phone field. Border gray, background gray. Centered field, text left-aligned. | Passed | – |
| T12 | Phone field | Find the Phone field in the form. | Placeholder "Enter Phone". Between Email and Message. Border gray, background gray. Centered field, text left-aligned. | Passed | – |
| T13 | Submit button | Find the Send button. | Button color purple. Text "Submit", white. Located at bottom of form. Left-aligned, button text centered. | Passed | – |

---

## Functional Test Case

| ID | Test case name | Preconditions | Steps | Expected result | Status | Bug ID |
|----|----------------|---------------|-------|-----------------|--------|--------|
| T14 | Successful message sending | Form page open | 1. Fill Name (e.g., Kirill).<br>2. Fill Email (rivan@yandex.ru).<br>3. Fill Phone (89002223311).<br>4. Fill Message (Hi, how are you!).<br>5. Click Send. | Message text: "Your message has been successfully sent!" – black, below "Send us a message" heading, right of contact info. | **Failed** | B3 |

---

## Summary of Bugs

| Bug ID | Test ID | Issue |
|--------|---------|-------|
| B1 | T3 | Form title styling/location mismatch |
| B2 | T8 | Email block content or color mismatch |
| B3 | T14 | Success message not displayed as expected |

---

## Notes
- All other layout tests passed.
- For detailed validation of error messages and field content, refer to separate test case files (e.g., `test-cases-feedback-form.md`).