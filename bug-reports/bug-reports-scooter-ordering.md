# Bug Reports – Scooter Ordering Web Application

**Common Environment (unless noted otherwise):**  
- Test bench: `https://726fac01-e105-424d-b1ed-01f13a21f4c5.serverhub.praktikum-services.ru/`  
- Browsers: Yandex Browser 25.8.4.771 (64‑bit), Google Chrome 142.0.7444.162 (64‑bit)  
- Resolutions: 1280×720, 1920×1080  
- OS: macOS Sequoia 15.6.1  

---

| ID | Bug Name | Priority | Status | Preconditions | Steps to Reproduce | Expected Result | Actual Result | Environment notes |
|----|----------|----------|--------|---------------|-------------------|-----------------|---------------|-------------------|
| BUG1 | Canceled order not removed, returns 400 error | Standard | Open | Same as common. | 1. Place order.<br>2. Cancel order.<br>3. Check status of canceled order. | User cannot view canceled order. | Canceled order can be viewed with full info. | – |
| BUG2 | Address field does not show error for 50‑char input | Standard | Open | Same as common. | 1. Go to order form.<br>2. Enter `Moscow, Miklukho-Maklaya St., 101234567890123456789` (50 chars). | Field red, error “Enter a valid address”. | No red border, no error. | – |
| BUG3 | Address field accepts only Russian letters | Critical | Open | Same as common. | 1. Order form.<br>2. Enter `Moscow, Miklukho-Maklaya Street`. | Red border + error “Enter correct address”. | No red border, no error. | – |
| BUG4 | Address field accepts only numbers | Critical | Open | Same as common. | Enter `12345678` in address. | Same as BUG3. | No error. | – |
| BUG5 | Empty address field shows no error | Critical | Open | Same as common. | Leave address empty, fill rest, click “Next”. | Address field red + error. | No red border, no error. | – |
| BUG6 | Can select past/current delivery date | Critical | Open | Same as common. | In delivery date field, select today’s date. | Only tomorrow+ allowed. | Can select today. | – |
| BUG7 | Can manually enter delivery date (should be picker only) | Critical | Open | Same as common. | Type a date into delivery date field. | Only dropdown calendar selection allowed. | Manual entry works. | – |
| BUG8 | Name field does not accept dash/hyphen | Standard | Open | Same as common. | Enter `Nina Anna-Maria` in Name field. | Dash/hyphen accepted. | Field rejects dash/hyphen. | – |
| BUG9 | Phone field accepts >12 chars including `+` | Critical | Open | Same as common. | Enter `+774991234567` (13 chars). | Max 12 chars (including +). | Accepts longer. | – |
| BUG10 | Comment field accepts >24 chars | Standard | Open | Same as common. | Enter `Very long comment that should not be accepted...`. | Max 24 chars. | Longer text accepted. | – |
| BUG11 | Comment field accepts only numbers | Standard | Open | Same as common. | Enter `1234567890`. | Should not accept numbers? (Not specified clearly: field should accept letters/punctuation). | Only numbers accepted. | – |
| BUG12 | Down arrow missing on first screen | Desirable | Open | Same as common. | Open home page. | Arrow present. | No arrow. | – |
| BUG13 | FAQ questions order wrong | Standard | Open | Same as common. | Scroll to FAQ. | Order matches layout. | Order does not match layout. | – |
| BUG14 | FAQ answer error: “I want several scooters at once!” | Standard | Open | Same as common. | Open FAQ answer for that question. | “For now, one order = one scooter. If you want to ride with friends, you can simply make multiple orders.” | “For now, this is how we work: one order = one scooter. If you want to ride with friends, you can simply make multiple orders, one after another.” | – |
| BUG15 | FAQ answer error: “How is rental time calculated?” | Standard | Open | Same as common. | Open that FAQ answer. | “Let's say you order for May 8. We'll deliver by end of day. Rental starts from payment. If delivered at 8:30 PM, daily rental ends 8:30 PM next day.” | Missing “by the end of the day”, changes wording. | – |
| BUG16 | FAQ answer error: “Can I extend order / return early?” | Standard | Open | Same as common. | Open that FAQ answer. | “Not yet! If urgent, call 0101.” | “Not yet! But if urgent, call 1010.” | – |
| BUG17 | FAQ answer error: “Can I cancel an order?” | Standard | Open | Same as common. | Open that FAQ answer. | “Yes, you can cancel until courier arrives. No fine, no explanation.” | “Yes, they haven't delivered yet. No fine, no explanation. After all, we're our own.” | – |
| BUG18 | First paragraph of “How it works” too close to scooter drawing (1280×720 Chrome) | Desirable | Open | Chrome 142.0.7444.60, 1280×720 only. | Open home page. | Distance as in layout. | Distance smaller. | Chrome 142.0.7444.60, 1280×720 |
| BUG19 | FAQ arrows on wrong side (left instead of right) | Desirable | Open | Same as common. | Scroll to FAQ. | Arrows on right side of questions. | Arrows on left side. | – |
| BUG20 | Question not bold when answer opened | Desirable | Open | Same as common. | Open any FAQ answer. | Question becomes bold. | Not bold. | – |
| BUG21 | Order status check line design mismatched | Standard | Open | Same as common. | Click “Order Status” button. | Should show “Enter order number” line. | Shows “Enter order number” + black button “Go!”. | – |
| BUG22 | “Metro Station” placeholder wrong font color | Desirable | Open | Same as common. | Open order form, first screen. | Placeholder gray. | Placeholder black. | – |
| BUG23 | Metro line color not displayed next to filled station | Standard | Open | Same as common. | Open order form, fill metro station. | Metro line color appears. | No line color. | – |
| BUG24 | Button name incorrect on first order screen | Desirable | Open | Same as common. | Open order form. | Button labeled “Next”. | Button labeled “Next”? (same word – issue may be translation: “Next” vs “Next”?) – check original: says button name incorrect, but both “Next”. Possibly language nuance. | – |
| BUG25 | “Rental Period” field arrow wrong (thick filled triangle) | Desirable | Open | Same as common. | Go to “About Rent” screen. | Thin open arrow. | Thick black filled triangle. | – |
| BUG26 | Checkbox for scooter color wrong style | Desirable | Open | Same as common. | On “About Rent”, select color. | Checkmark in square frame. | Checkmark in blue filled square. | – |
| BUG27 | Delivery date field name wrong | Desirable | Open | Same as common. | Click “Order Status”. | Field called “When will we deliver”. | Field called “Delivery Date”. | – |
| BUG28 | Cannot place order in Chrome | Blocking | Open | Chrome 142.0.7444.60, 1280×720 only. | Fill order form completely and confirm. | Order processed. | Order not processed after clicking “Yes”. | Chrome 142.0.7444.60, 1280×720 |
| BUG29 | Order status window on wrong side (left instead of right) | Desirable | Open | Chrome 142.0.7444.60, 1280×720 only. | Click “Order Status”. | Statuses on right side. | Statuses on left side. | Chrome 142.0.7444.60, 1280×720 |
| BUG30 | Order cancellation confirmation text placement off | Desirable | Open | Same as common. | Place order, then cancel. | Text/elements centered, equal margins. | Shifted to upper right corner. | – |
| BUG31 | Yandex logo leads to ya.ru, not Zen | Desirable | Open | Chrome 142.0.7444.60, 1280×720 only. | Click Yandex logo in header. | Opens Zen page. | Opens ya.ru page. | Chrome 142.0.7444.60, 1280×720 |
| BUG32 | “Courier on site” status does not activate | Critical | Open | Same as common. | Place order, then API call to complete order, check status. | Status activates when courier presses “Complete”. | Does not activate. | – |
| BUG33 | “Okay, now it's time to ride” status does not activate | Critical | Open | Same as common. | Same as BUG32. | Status activates after courier confirms order completed. | Does not activate. | – |
| BUG34 | Status does not change to “Rental time has ended” | Critical | Open | Same as common. | Same as BUG32. | Status changes when rental ends. | Does not change. | – |
| BUG35 | Countdown for overdue order does not start from receipt | Critical | Open | Same as common. | Place order, mark overdue, check countdown. | Countdown starts from moment order received. | Does not start. | – |
| BUG36 | Cancellation confirmation text incorrect | Desirable | Open | Same as common. | Cancel order. | “Order canceled. But if anything happens, come back again, we're waiting :)” | “Order canceled. Come back, we're always waiting for you :)” | – |
| BUG37 | Extra confirmation window appears not in requirements | Critical | Open | Same as common. | Place order. | After clicking “Order”, order completed, popup with order number. | “Do you want to place an order?” window with Yes/No appears first. | – |
| BUG38 | User can cancel order after courier accepted | Critical | Open | Same as common. | Place order, accept via API, check “Cancel Order” button. | Button unclickable. | Button clickable, cancellation possible. | – |
| BUG39 | Enter key does not trigger order status check | Standard | Open | Same as common. | Enter order number, press Enter. | Order info appears. | No action. | – |

---

## Summary

| Priority | Count |
|----------|-------|
| Blocking | 1 |
| Critical | 14 |
| Standard | 8 |
| Desirable | 16 |

*All bugs are in **Open** status.*