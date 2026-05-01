# Cross‑Browser Test Results: Tariff Plan Form

**Test environment:**  
- OS: Windows 10 (*)  
- Browsers: Chrome 119, Yandex 23.11, Firefox 120  

**Note:** All tests passed except where marked "Failed". Bug report IDs are referenced where applicable.

| ID | Test Description | Chrome 119 | Yandex 23.11 | Firefox 120 | Bug Report(s) |
|----|-----------------|------------|--------------|-------------|----------------|
| 1 | General Form Design Step 1 – left design element with four steps, right form for data entry | Passed | Passed | Passed | – |
| 2 | Left side Step 1 – number 1 in light blue circle, text "Step 1 YOUR DATA" | Passed | Passed | Passed | – |
| 3 | Right side Step 1 – header "Personal Data", black, left‑aligned | Passed | Passed | Passed | – |
| 4 | Right side Step 1 – description: "Please enter your name, email address, and phone number." gray | Passed | Passed | Passed | – |
| 5 | Right side Step 1 – Name/Email/Phone fields: light gray rounded borders, black field names above, blue border on focus | Passed | Passed | Passed | – |
| 6 | Right side Step 1 – placeholders: Name "Alexander Pushkin", Email "poet@mail.ru", Phone "+7 999 888 77 66" (gray) | Passed | Passed | Passed | – |
| 7 | Right side Step 1 – validation errors: red text right‑aligned, red borders. Empty field: "Required field." Invalid data: "Error in Name/Email/Phone field". | **Failed** | **Failed** | **Failed** | tariff_plan-3, tariff_plan-9 |
| 8 | Right side Step 1 – "Next" button: white text on dark blue, rounded corners | Passed | Passed | Passed | – |
| 9 | Left side Step 2 – number 2 in light blue circle, text "Step 2 CHOOSE A PLAN" | Passed | Passed | Passed | – |
| 10 | Right side Step 2 – default state: Standard plan selected, monthly payment, blue frame + transparent blue fill | Passed | Passed | Passed | – |
| 11 | Right side Step 2 – header "Select a plan", black, left‑aligned | Passed | Passed | Passed | – |
| 12 | Right side Step 2 – description: "Can be caulked monthly or annually", gray | Passed | Passed | Passed | – |
| 13 | Right side Step 2 – design of tariff plan buttons: three rectangles, focused – blue border, pressed – blue border + light blue background | **Failed** | **Failed** | **Failed** | tariff_plan-5 |
| 14 | Right side Step 2 – button texts: Standard 900₽/m, Advanced 1200₽/m, Pro 1500₽/m (names black, prices gray) | Passed | Passed | Passed | – |
| 15 | Right side Step 2 – subscription toggle: white circle in blue oval on light gray rectangle | Passed | Passed | Passed | – |
| 16 | Right side Step 2 – toggle text: "Every month" (default, blue) and "Once a year" (gray unselected) | Passed | Passed | Passed | – |
| 17 | Right side Step 2 – "Back" (gray text, no border, left) and "Next" (white on dark blue, right) buttons | **Failed** | **Failed** | **Failed** | tariff_plan-5 |
| 18 | Left side Step 3 – number 3 in light blue circle, text "Step 3 ADD OPTIONS" | Passed | Passed | Passed | – |
| 19 | Right side Step 3 – header "Add options", black, left‑aligned | Passed | Passed | Passed | – |
| 20 | Right side Step 3 – description: "Additional options help improve the digital experience", gray | Passed | Passed | Passed | – |
| 21 | Right side Step 3 – default state: "Play online" selected, blue border + white checkmark in blue square + transparent blue fill | Passed | Passed | Passed | – |
| 22 | Right side Step 3 – design of option buttons: option name black, explanatory text gray, checkbox white check in blue square when active, price in blue; focused – blue border, pressed – blue border + light blue background | Passed | Passed | Passed | – |
| 23 | Right side Step 3 – option texts and prices: Play online / Multiplayer (100₽/m, 1000₽/y), More space / Additional 1TB (200₽/m, 2000₽/y), Custom profile / Custom theme (200₽/m, 2000₽/y) | **Failed** | **Failed** | **Failed** | tariff_plan-6 |
| 24 | Right side Step 3 – "Back" (gray, left) and "Next" (white on dark blue, right) | Passed | Passed | Passed | – |
| 25 | Left side Step 4 – number 4 in light blue circle, text "Step 4 CONFIRMATION" | Passed | Passed | Passed | – |
| 26 | Right side Step 4 – header "At the Finish Line", black, left‑aligned | Passed | Passed | Passed | – |
| 27 | Right side Step 4 – description: "Please check that everything is correct before confirming.", gray | Passed | Passed | Passed | – |
| 28 | Right side Step 4 – rate block: name (black, bold) right‑aligned, price (black, bold) to the right, "Edit" button (gray, underlined) below | **Failed** | **Failed** | **Failed** | tariff_plan-7 |
| 29 | Right side Step 4 – additional options block: option name (gray, normal) right‑aligned below separator, price (black, normal) to the right | **Failed** | **Failed** | **Failed** | tariff_plan-8 |