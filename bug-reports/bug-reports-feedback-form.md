# Bug Reports – Feedback Form

| ID | Bug Name | Priority | Status | Preconditions | Steps to Reproduce | Expected Result | Actual Result |
|----|----------|----------|--------|---------------|-------------------|-----------------|---------------|
| B1 | The text color in the form header is black, not purple. | Desirable | Open | Feedback form page is open. | View the text color in the form header. | Text color is purple. | Text color is black. |
| B2 | Email addresses end in `.ru`, not `.com`. | Critical | Open | Feedback form page is open. | Find the block with email. | Email addresses: `feedback@oursite.com`, `letter@oursite.com`. | Email addresses: `feedback@oursite.ru`, `letter@oursite.ru`. |
| B3 | The success message contains an extra block of text. | Desirable | Open | Feedback form page is open. | 1. Fill Name: Kirill.<br>2. Fill Email: rivan@yandex.ru.<br>3. Fill Phone: 89002223311.<br>4. Fill Message: "Hi, how are you!".<br>5. Click Send. | Message text: "Your message has been sent successfully!" | Message text: "Your message has been successfully sent! If you have any questions or suggestions for collaboration, please fill out the form below." |
| B4 | The Name field returns an error when entering English letters. | Standard | Open | Feedback form page is open. | 1. Enter "Alex" in Name field.<br>2. Valid email: rivan@yandex.ru.<br>3. Valid phone: 89002223311.<br>4. Valid message: "Hello everyone!".<br>5. Click Send. | Success message displayed. | Error message appears under Name field. |
| B5 | The Email field accepts Cyrillic characters. | Standard | Open | Feedback form page is open. | 1. Enter "Ivan" in Name.<br>2. Enter "ivan@yandex.ru" (Cyrillic) in Email.<br>3. Valid phone: 89002223311.<br>4. Valid message: "Hello everyone!".<br>5. Click Send. | Error message under Email field. | Success message displayed. |
| B6 | The Email field accepts an email address without the period symbol. | Standard | Open | Feedback form page is open. | 1. Enter "Ivan" in Name.<br>2. Enter "rivan@yandexru" (no dot) in Email.<br>3. Valid phone: 89002223311.<br>4. Valid message: "Hello everyone!".<br>5. Click Send. | Error message under Email field. | Success message displayed. |
| B7 | The Message field does not accept input of 499 or 500 characters. | Standard | Open | Feedback form page is open. | 1. Enter "Ivan" in Name.<br>2. Valid email: rivan@yandex.ru.<br>3. Valid phone: 89002228943.<br>4. Enter 499‑char text (or 500‑char).<br>5. Click Send. | Success message displayed. | Error message under Message field. |
| B8 | The Email field accepts email addresses with special characters. | Standard | Open | Feedback form page is open. | 1. Enter "Ivan" in Name.<br>2. Enter "rivan!№%@yandex.ru" in Email.<br>3. Valid phone: 89002223311.<br>4. Valid message: "Hello everyone!".<br>5. Click Send. | Error message under Email field. | Success message displayed. |
| B9 | The Email field accepts an email address with a space. | Standard | Open | Feedback form page is open. | 1. Enter "Ivan" in Name.<br>2. Enter `"rivan@yandex.ru"` (with leading/trailing space) in Email.<br>3. Valid phone: 89002223311.<br>4. Valid message: "Hello everyone!".<br>5. Click Send. | Error message under Email field. | Success message displayed. |

---

## Summary

- **Critical:** 1 (B2)
- **Standard:** 6 (B4, B5, B6, B7, B8, B9)
- **Desirable:** 2 (B1, B3)

All bugs are in **Open** status.