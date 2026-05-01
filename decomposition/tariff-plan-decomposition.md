# Decomposition of Tariff Plan Selection

## Links
- **Requirements (mockups):** [Figma Design](https://www.figma.com/design/PjpyWANACPWaVPizTgHkeC/multi-step-form_external_link?node-id=0-1&t=UP7GuhP9sch7WlC9-0)
- **Requirements (text):** [Google Docs](https://docs.google.com/document/d/104A3Mxzm1tcWZoiJg_h5Y9dr0FsER2bnkxvBMDcAVu8/edit?usp=sharing)
- **Implementation:** [Tariff Plan Form](https://qa-faculty.github.io/tariff-plan/)

---

## Page Layout Overview

- **Left side:** design element spanning full height, contains four steps (each corresponding to an open form).
- **Right side:** form for entering data and selecting tariff parameters.

---

## Form Step 1 – Your Data

### Left Side – Step 1
- Number `1` highlighted in light blue circle with fill; other text white on light blue background.
- Text: `"Step 1 YOUR DATA"`

### Right Side – Step 1

#### Header
- `"Personal Data"`
- Color: black, centered on the left edge of the data entry area

#### Form Description
- Position: below header
- Color: gray
- Text: `"Please enter your name, email address, and phone number."`

#### Fields: Name, Email, Phone
- Location: below description
- Borders: light gray, rounded corners
- Field names: above each field, black font
- When active (focus): borders become blue

#### Placeholders
- Color: gray
- Content:
  - Name: `"Alexander Pushkin"`
  - Email: `"poet@mail.ru"`
  - Phone: `"+7 999 888 77 66"`

#### Validation Errors
- Error text: aligned with field name, centered on the right, red color
- Field borders: red
- Empty field error: `"Required field."`
- Invalid data errors:
  - Name field: `"Error in Name field"`
  - Email field: `"Error in Email field"`
  - Phone field: `"Error in Phone field"`

#### "Next" Button
- White letters on dark blue background
- Rounded corners

---

## Form Step 2 – Choose a Plan

### Left Side – Step 2
- Number `2` highlighted in light blue circle with fill; other text white on light blue background.
- Text: `"Step 2 CHOOSE A PLAN"`

### Right Side – Step 2

#### Default State
- Standard plan selected, monthly payment
- Selected plan indicated by blue frame, element filled with transparent blue

#### Header
- `"Select a plan"`
- Color: black, centered on left edge

#### Form Description
- Position: below header
- Color: gray
- Text: `"Can be caulked monthly or annually"`

#### Tariff Plan Buttons (3 rectangles)
- Contain plan description and price
- Focused button: blue border
- Pressed button: blue border + light blue background

#### Button Texts
- Plan names: black font, prices: gray
  - `Standard` – 900 rubles/month
  - `Advanced` – 1200 rubles/month
  - `Pro` – 1500 rubles/month

#### Subscription Method Toggle
- Design: white circle in blue oval on light gray rectangular field
- Options: `"Every month"` (default) / `"Once a year"`
- Selected option text: blue
- Unselected option text: gray

#### "Back" and "Next" Buttons
- **Back:** no border, gray text, centered on left edge
- **Next:** white text on dark blue background, rounded corners, centered on right edge

---

## Form Step 3 – Add Options

### Left Side – Step 3
- Number `3` highlighted in light blue circle with fill; other text white on light blue background.
- Text: `"Step 3 ADD OPTIONS"`

### Right Side – Step 3

#### Default State
- `"Play online"` option selected
- Selected field: blue border + white checkmark in blue square + transparent blue fill

#### Header
- `"Add options"`
- Color: black, centered on left edge

#### Form Description
- Position: below header
- Color: gray
- Text: `"Additional options help improve the digital experience"`

#### Option Buttons (with checkbox)
- Each option: name (black), explanatory text (gray), checkbox, price (blue)
- Focused button: blue border
- Pressed button: blue border + light blue background

#### Options and Prices
| Option | Description | Price (monthly) | Price (yearly) |
|--------|-------------|----------------|----------------|
| Play online | Multiplayer | 100 rubles | 1000 rubles |
| More space | Additional 1 TB in the cloud | 200 rubles | 2000 rubles |
| Custom profile | Custom theme | 200 rubles | 2000 rubles |

#### "Back" and "Next" Buttons (same as Step 2)
- **Back:** no border, gray text, left edge
- **Next:** white on dark blue, rounded corners, right edge

---

## Form Step 4 – Confirmation

### Left Side – Step 4
- Number `4` highlighted in light blue circle with fill; other text white on light blue background.
- Text: `"Step 4 CONFIRMATION"`

### Right Side – Step 4

#### Header
- `"At the Finish Line"`
- Color: black, left edge

#### Form Description
- Text: `"Please check that everything is correct before confirming."`
- Color: gray, below header

#### Plan Block
- Plan name (black, bold) – aligned to right edge
- Plan price (black, bold) – to the right of name
- `"Edit"` button (gray, underlined) below name

#### Additional Options Block
- Option name (gray, normal font) – aligned to right, below separator line
- Price (black, normal font) – to the right of name

#### Total (per month) Line
- Label: gray, normal font, aligned right
- Price: purple, normal font, to the right

#### "Back" and "Confirm" Buttons
- **Back:** no border, gray text, left edge
- **Confirm:** white text on dark blue background, rounded corners, right edge

---

## Tariff Plan Confirmation Window (after submission)

> Same left side as Step 4.

### Right Side – Confirmation Content

#### Illustration
- Pink checkmark in white circle inside a larger pink circle

#### Heading
- `"Thank You"`
- Dark blue, centered in form area, bold font

#### Description
- Color: gray, centered, normal font
- Text: `"Thank you for choosing a plan! If you have any questions about plans, please contact us at support@loremgaming.com."`