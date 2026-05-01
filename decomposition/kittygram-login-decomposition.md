# Decomposition of the Kittygram Login Page

## Links
- **Requirements:** [Google Docs](URL_PLACEHOLDER) *(если есть ссылка, вставьте её)*
- **Implementation:** [Kittygram](URL_PLACEHOLDER) *(если есть ссылка на сайт, вставьте)*

---

> Gray areas (unclear from mockups) have been clarified.

## Main Objects on the Authorization Page

### Page Background
- Color: white

### Cat Picture
- Image content: the cat's black face, white eye sockets, and black pupils
- Position: top of the page, horizontally centered

### "Login" Text
- Text: "Login."
- Color: black
- Font style: bold, sans-serif
- Position: below the cat picture, horizontally centered

### Login Description
- Text: "Login to Kittygram!"
- Color: gray
- Font style: normal, sans-serif
- Position: below the "Login" text

### Login Form
- Background: white
- Shape: vertically elongated rectangle with rounded corners
- Position: below the "Login" text and login description
- Border: none
- Shadow color: gray

---

## Name Field

### Field Characteristics
- Shape: horizontally elongated rectangle with rounded corners
- Position: top of the form, first field
- Field background: light gray
- Border: gray

### Placeholder
- Text: "Name."
- Text color: gray
- Font style: normal, sans-serif
- Alignment: left-aligned with indent

### Input String (when user types)
- Text matches input
- Text color: black
- Font style: normal, sans-serif
- Alignment: left-aligned with indent

### Focus State
- The frame is highlighted in green

---

## Password Field

### Field Characteristics
- Shape: horizontally elongated rectangle with rounded corners
- Position: after the Name field
- Field background: light gray
- Border: gray

### Placeholder
- Text: "Password."
- Text color: gray
- Font style: normal, sans-serif
- Alignment: left-aligned with indent

### Input String (when user types)
- Text matches input (shown as dots if hidden)
- Text color: black
- Font style: normal, sans-serif
- Alignment: left-aligned with indent

### Eye Icon (toggle password visibility)
- Image: eye socket and pupil, transparent background, black outline
- Location: near the right edge of the Password field
- When password is hidden: the image is crossed out from right to left
- When password is revealed: the strikethrough disappears

### Hiding/Revealing Password
- Clicking the eye icon hides the text (shows black dots) or reveals it

### Focus State
- The frame is highlighted in green

---

## Login Button

### Button Characteristics
- Shape: horizontally elongated rectangle with rounded corners
- Position: below the Password field, with an indent
- Background color: orange
- Border: none

### Button Text
- Text: "Login"
- Text color: white
- Font style: normal, sans-serif
- Position: centered on the button, indented to the right

### Focus State
- Background color turns light orange

---

## Text "or"

- Text: "or."
- Color: gray
- Font style: normal, sans-serif
- Position: below the Login button

---

## Registration Link

- Text: 
  - "Not registered yet?"
  - "Register."
- Color: light blue
- Font style: normal, sans-serif
- Position: below the "or" text

---

## Footer

### Footer Bar
- Position: at the bottom of the page, full width
- Background: black

### Caption
- Text: "Kittygram 2021"
- Color: white
- Font style: normal, sans-serif
- Position: centered in footer

---

## Error Messages

### Name Requirement Error (empty field)
- Text: "The name field is required."
- Color: red
- Font style: normal, sans-serif
- Position: below the Name field

### Password Requirement Error (empty field)
- Text: "The password field is required."
- Color: red
- Font style: normal, sans-serif
- Position: below the Password field

### Incorrect Username/Password Error
- Text: "Incorrect username and/or password."
- Color: red
- Font style: normal, sans-serif
- Position: below the Password field