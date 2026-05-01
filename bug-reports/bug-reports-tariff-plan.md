# Bug Reports – Tariff Plan (Multi‑step Form)

**Common Environment:** Win10, Chrome 119, Yandex 23.11, Firefox 120.

---

| ID | Bug Name | Priority | Status | Preconditions | Steps to Reproduce | Expected Result | Actual Result |
|----|----------|----------|--------|---------------|-------------------|-----------------|---------------|
| tariff_plan-3 | No error message for the 'Name' field. | Desirable | Open | Open the form at https://qa-faculty.github.io/tariff-plan/ | 1. Fill "Personal Data":<br>Name = `12345`<br>Email = `123@ru`<br>Phone = `123456`<br>2. Click "Next". | Error message "Error in Name field" appears. | No error message shown. |
| tariff_plan-4 | Price changes to dollars when toggling payment period. | Standard | Open | Same as above. | 1. Switch toggle to "Once a year".<br>2. Switch back to "Every month". | Price remains in rubles. | Price becomes dollars. |
| tariff_plan-6 | Option names and "More Space" price differ from requirements (Step 3). | Standard | Open | 1. Open the form.<br>2. Proceed to Step 3. | View option names, descriptions, and prices. | Options named: "Multiplayer", "More Space", "Custom Theme".<br>"More Space" price = 200 rubles/month. | Actual names:<br>- "Access to multiplayer games"<br>- "More storage"<br>- "Custom theme in your profile".<br>Price for "More storage" = +200 rubles/month (text mismatch). |
| tariff_plan-7 | Dollar sign appears before the tariff price (Step 4). | Critical | Open | 1. Open the form.<br>2. Proceed to Step 4. | 1. In Step 2, select "Once a year".<br>2. Proceed to Step 4, review prices. | No dollar sign in tariff price. | Dollar sign is displayed. |
| tariff_plan-8 | Gray background of the tariff block (Step 4). | Desirable | Open | 1. Open the form.<br>2. Proceed to Step 4. | View the background of the tariff block. | Background should not be gray (e.g., white or as per design). | Background is gray. |
| tariff_plan-9 | Incorrect error message text for the "Phone" field. | Desirable | Open | Open the form at the first step. | 1. Fill "Personal Data":<br>Name = `12345`<br>Email = `123@ru`<br>Phone = `123456`<br>2. Click "Next". | Error message "Error in the Phone field" appears. | Message "Error in the number field" appears instead. |

---

## Summary

- **Critical:** 1 (tariff_plan-7)
- **Standard:** 2 (tariff_plan-4, tariff_plan-6)
- **Desirable:** 3 (tariff_plan-3, tariff_plan-8, tariff_plan-9)

All bugs are in **Open** status.