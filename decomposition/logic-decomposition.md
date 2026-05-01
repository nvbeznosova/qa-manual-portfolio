# Decomposition of the Feedback Form Page Logic

## Links
- **Requirements:** [Google Docs](https://docs.google.com/document/d/1xe1fZoU6_NTDv7z57Mfna1rqeT3Fh6v7OvFgkKbEQdI)
- **Implementation:** [Feedback Form](https://qa-faculty.github.io/feedback_form/)

---

## Main Objects and Further Decomposition

### 1. Name Field

#### Boundary / Length
- Less than 2 characters
- From 2 to 30 characters
- More than 30 characters

#### Symbols / Content
- Russian letters
- English letters
- Arabic letters
- Capital letters
- Lowercase letters
- Space
- Hyphen
- Special characters

#### State
- The field is filled
- The field is empty

#### Validation
- Error message appears (if validation fails)

---

### 2. Email Field

#### Boundary / Length
- Less than 5 characters
- From 5 to 30 characters
- More than 30 characters

#### Symbols / Content
- Symbol @
- The symbol . (dot)
- English letters
- Numbers
- Space
- Special characters
- Hyphen

#### State
- The field is filled
- The field is empty

#### Validation
- Error message appears (if validation fails)

---

### 3. Phone Field

#### Boundary / Length
- Less than 7 characters
- From 7 to 14 characters
- More than 14 characters

#### Symbols / Content
- Numbers
- Hyphen
- Letters
- Space
- Special characters

#### State
- The field is filled
- The field is empty

#### Validation
- Error message appears (if validation fails)

---

### 4. Message Field

#### Boundary / Length
- Less than 10 characters
- From 10 to 500 characters
- More than 500 characters

#### Symbols / Content
- Russian letters
- English letters
- Arabic letters
- Numbers
- Punctuation marks
- Space
- Special characters

#### State
- The field is filled
- The field is empty

#### Validation
- Error message appears (if validation fails)

---

### 5. Submit Button

#### State
- Active

#### Action
- Validation completed successfully → form submitted (or positive action)
- Validation failed → submission blocked, error messages shown