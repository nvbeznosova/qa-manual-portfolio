# Test Results: Tariff Plan – Field Validation & Tariff Selection Logic

**Environment:** Windows 10, Chrome 119  

---

## Field Validation (Step 1) – All Passed

| ID | Test Description | Result |
|----|-----------------|--------|
| 1 | Transition to Step 2 – Name field length = 2 characters | Passed |
| 2 | Transition to Step 2 – Name length = 3 | Passed |
| 3 | Transition to Step 2 – Name length = 4 | Passed |
| 4 | Transition to Step 2 – Name length = 29 | Passed |
| 5 | Transition to Step 2 – Name length = 30 | Passed |
| 6 | Transition to Step 2 – Name = capital letters | Passed |
| 7 | Transition to Step 2 – Name = lowercase letters | Passed |
| 8 | Transition to Step 2 – Name contains space | Passed |
| 9 | Transition to Step 2 – Name contains hyphen | Passed |
| 10 | Transition to Step 2 – Name = English letters | Passed |
| 11 | Name field – empty (0 chars) → error message | Passed |
| 12 | Name field – 1 char → error | Passed |
| 13 | Name field – 31 chars → error | Passed |
| 14 | Name field – 32 chars → error | Passed |
| 15 | Name field – 36 chars → error | Passed |
| 16 | Name field – numbers → error | Passed |
| 17 | Name field – special characters → error | Passed |
| 18 | Name field – Arabic letters → error | Passed |
| 19 | Transition to Step 2 – Email length = 5 | Passed |
| 20 | Transition to Step 2 – Email length = 6 | Passed |
| 21 | Transition to Step 2 – Email length = 15 | Passed |
| 22 | Transition to Step 2 – Email length = 29 | Passed |
| 23 | Transition to Step 2 – Email length = 30 | Passed |
| 24 | Transition to Step 2 – Email with hyphen | Passed |
| 25 | Transition to Step 2 – Email with numbers | Passed |
| 26 | Email field – 2 chars → error | Passed |
| 27 | Email field – 3 chars → error | Passed |
| 28 | Email field – 4 chars → error | Passed |
| 29 | Email field – 31 chars → error | Passed |
| 30 | Email field – 32 chars → error | Passed |
| 31 | Email field – 36 chars → error | Passed |
| 32 | Email field – empty → error | Passed |
| 33 | Email field – Cyrillic characters → error | Passed |
| 34 | Email field – missing "@" → error | Passed |
| 35 | Email field – missing dot → error | Passed |
| 36 | Transition to Step 2 – Phone length = 11 | Passed |
| 37 | Transition to Step 2 – Phone length = 7 | Passed |
| 38 | Transition to Step 2 – Phone length = 8 | Passed |
| 39 | Transition to Step 2 – Phone length = 13 | Passed |
| 40 | Transition to Step 2 – Phone length = 14 | Passed |
| 41 | Phone field – empty → error | Passed |
| 42 | Phone field – 1 char → error | Passed |
| 43 | Phone field – 4 chars → error | Passed |
| 44 | Phone field – 5 chars → error | Passed |
| 45 | Phone field – 6 chars → error | Passed |
| 46 | Phone field – 15 chars → error | Passed |
| 47 | Phone field – 16 chars → error | Passed |
| 48 | Phone field – 18 chars → error | Passed |
| 49 | Phone field – letters → error | Passed |
| 50 | Phone field – hyphen → error | Passed |
| 51 | Phone field – space → error | Passed |

---

## Tariff Selection Logic (Steps 2–4)

| ID | Test Description | Result | Bug Report |
|----|-----------------|--------|-------------|
| 52 | Standard tariff – 1 month, no options | **Failed** | tariff_plan-1 |
| 53 | Standard tariff – 1 month + Play Online | Passed | – |
| 54 | Standard tariff – 1 month + Play Online + More Space | Passed | – |
| 64 | Standard tariff – 1 year + More Space + Custom Profile | Passed | – |
| 65 | Standard tariff – 1 year + Custom Profile | Passed | – |
| 66 | Standard tariff – 1 year + More Space | Passed | – |
| 67 | Standard tariff – 1 year + Play Online + Custom Profile | Passed | – |
| 68 | Advanced tariff – 1 month, no options | **Failed** | tariff_plan-1 |
| 69 | Advanced tariff – 1 month + Play Online | Passed | – |
| 70 | Advanced tariff – 1 month + Play Online + More Space | Passed | – |
| 71 | Advanced tariff – 1 month + Play Online + More Space + Custom Profile | Passed | – |
| 72 | Advanced tariff – 1 month + More Space + Custom Profile | Passed | – |
| 73 | Advanced tariff – 1 month + Custom Profile | Passed | – |
| 74 | Advanced tariff – 1 month + More Space | Passed | – |
| 75 | Advanced tariff – 1 month + Play Online + Custom Profile | Passed | – |
| 76 | Advanced tariff – 1 year, no options | **Failed** | tariff_plan-1 |
| 77 | Advanced tariff – 1 year + Play Online | Passed | – |
| 78 | Advanced tariff – 1 year + Play Online + More Space | Passed | – |
| 79 | Advanced tariff – 1 year + Play Online + More Space + Custom Profile | Passed | – |
| 80 | Advanced tariff – 1 year + More Space + Custom Profile | Passed | – |
| 85 | Pro tariff – 1 month + Play Online | Passed | – |
| 86 | Pro tariff – 1 month + Play Online + More Space | Passed | – |
| 87 | Pro tariff – 1 month + Play Online + More Space + Custom Profile | Passed | – |
| 88 | Pro tariff – 1 month + More Space + Custom Profile | Passed | – |
| 89 | Pro tariff – 1 month + Custom Profile | Passed | – |
| 90 | Pro tariff – 1 month + More Space | Passed | – |
| 94 | Pro tariff – 1 year + Play Online + More Space | Passed | – |
| 95 | Pro tariff – 1 year + Play Online + More Space + Custom Profile | Passed | – |
| 96 | Pro tariff – 1 year + More Space + Custom Profile | Passed | – |
| 97 | Pro tariff – 1 year + Custom Profile | Passed | – |
| 98 | Pro tariff – 1 year + More Space | Passed | – |
| 99 | Pro tariff – 1 year + Play Online + Custom Profile | Passed | – |

---

## Summary of Failures

- **tariff_plan-1** – affects tests 52, 68, 76 (basic tariff without options fails for Standard/Advanced tariffs, and possibly Pro? Pro basic not listed).