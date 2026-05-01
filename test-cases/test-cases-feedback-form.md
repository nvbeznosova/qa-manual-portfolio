# Test Cases: Feedback Form

## Preconditions (for all test cases)
- The feedback form page is open.
- All fields are initially empty unless specified otherwise.

---

## 1. Name Field

### 1.1 Valid Lengths (2–30 characters)
| ID | Name | Steps | Expected Result | Status |
|----|------|-------|-----------------|--------|
| T1 | Length = 2 | Enter `Ni` in Name field, valid email `rivan@yandex.ru`, phone `89002223311`, message `Hello everyone!`. Click Send. | Success message displayed. | Passed |
| T2 | Length = 3 | Enter `Yana` in Name field. (Other fields same as T1) | Success message displayed. | Passed |
| T3 | Length = 4 | Enter `Ivan` in Name field. | Success message displayed. | Passed |
| T4 | Length = 29 | Enter `KocherginaNikitskayaKocherginaNi` (29 chars). | Success message displayed. | Passed |
| T5 | Length = 30 | Enter `KocherginaNikitskayaKocherginaNick` (30 chars). | Success message displayed. | Passed |

### 1.2 Valid Characters (letters, space, hyphen, case)
| ID | Name | Steps (Name field input) | Expected Result | Status |
|----|------|--------------------------|-----------------|--------|
| T6 | Capital letters | `IVAN` | Success | Passed |
| T7 | Lowercase letters | `ivan` | Success | Passed |
| T8 | Space | `Ivan Ivanov` | Success | Passed |
| T9 | Hyphen | `Ivan-Roman` | Success | Passed |
| T10 | English letters | `Alex` | Success | **Failed** (bug B4) |

> ℹ️ *Other valid character tests (Russian letters – implicit) passed.*

### 1.3 Invalid Lengths (<2 or >30)
| ID | Name | Steps (Name field input) | Expected Result | Status |
|----|------|--------------------------|-----------------|--------|
| T11 | Empty (0 chars) | `""` | Error message under Name field | Passed |
| T12 | 1 character | `O` | Error message | Passed |
| T13 | 31 characters | `NikolayNikolayNikolayNikolayNik` | Error message | Passed |
| T14 | 32 characters | `NikolayNikolayNikolayNikolayNiko` | Error message | Passed |
| T15 | 36 characters | `AlexanderAlexanderAlexanderAlexander` | Error message | Passed |

### 1.4 Invalid Characters (digits, special, Arabic)
| ID | Name | Steps (Name field input) | Expected Result | Status |
|----|------|--------------------------|-----------------|--------|
| T16 | Digits | `1van` | Error message | Passed |
| T17 | Special characters | `@van` | Error message | Passed |
| T18 | Arabic letters | `ب غوريون` | Error message | Passed |

---

## 2. Email Field

### 2.1 Valid Lengths (5–30 characters)
| ID | Name | Steps (Email field input) | Expected | Status |
|----|------|---------------------------|----------|--------|
| T20 | Length = 5 | `r@m.r` | Success | Passed |
| T21 | Length = 6 | `r@m.ru` | Success | Passed |
| T22 | Length = 15 | `rivan@yandex.ru` | Success | Passed |
| T23 | Length = 29 | `krolkinaangelinaole@yandex.ru` | Success | Passed |
| T24 | Length = 30 | `krolkinaangelinaoleg@yandex.ru` | Success | Passed |

### 2.2 Valid Characters (hyphen, Latin, numbers)
| ID | Name | Steps (Email input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T25 | Hyphen allowed | `r-ivan@yandex.ru` | Success | Passed |

### 2.3 Invalid Lengths (<5 or >30)
| ID | Name | Steps (Email input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T27 | 2 chars | `@@` | Error | Passed |
| T28 | 1 char | `@` | Error | Passed |
| T29 | 3 chars | `@@@` | Error | Passed |
| T30 | 4 chars | `k@.k` | Error | Passed |
| T31 | 31 chars | `krolkinaangelinaolega@yandex.ru` | Error | Passed |
| T32 | 32 chars | `krolkinaangelinaolega1@yandex.ru` | Error | Passed |
| T33 | 36 chars | `krolkinaangelinaolega1lala@yandex.ru` | Error | Passed |

### 2.4 Required Field (empty)
| ID | Name | Steps | Expected | Status |
|----|------|-------|----------|--------|
| T34 | Empty Email | Leave Email blank | Error message under Email | Passed |

### 2.5 Invalid Characters / Format
| ID | Name | Steps (Email input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T36 | Missing `@` | `rivanyandex.ru` | Error | Passed |
| T37 | Missing `.` | `rivan@yandexru` | Error | **Failed** (bug B6) |
| T38 | Special character | `rivan!№%@yandex.ru` | Error | **Failed** (bug B8) |
| T39 | Contains space | `rivan@yandex.ru` (with space) | Error | **Failed** (bug B9) |

---

## 3. Telephone Field

### 3.1 Valid Lengths (7–14 digits)
| ID | Name | Steps (Phone input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T40 | 11 digits | `89002223311` | Success | Passed |
| T41 | 7 digits | `8900222` | Success | Passed |
| T42 | 8 digits | `89002223` | Success | Passed |
| T43 | 13 digits | `8900222894343` | Success | Passed |
| T44 | 14 digits | `89002228943439` | Success | Passed |

### 3.2 Invalid Lengths (<7 or >14)
| ID | Name | Steps (Phone input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T45 | Empty | `""` | Error | Passed |
| T46 | 1 digit | `7` | Error | Passed |
| T47 | 4 digits | `9112` | Error | Passed |
| T48 | 5 digits | `91123` | Error | Passed |
| T49 | 6 digits | `911282` | Error | Passed |
| T50 | 15 digits | `890022289434337` | Error | Passed |
| T51 | 16 digits | `8900222894343337` | Error | Passed |
| T52 | 18 digits | `890022233110686786` | Error | Passed |

### 3.3 Invalid Characters (letters, hyphen, space, special)
| ID | Name | Steps (Phone input) | Expected | Status |
|----|------|---------------------|----------|--------|
| T53 | Letters | `b900223311a` | Error | Passed |
| T54 | Hyphen | `8-9002223322` | Error | Passed |
| T55 | Space | `8 9002223322` | Error | Passed |
| T56 | Special char | `8&9002223322` | Error | Passed |

---

## 4. Message Field

### 4.1 Valid Lengths (10–500 characters)
| ID | Name | Steps (Message input) | Expected | Status |
|----|------|-----------------------|----------|--------|
| T57 | Length = 10 | `Hello, Yam` | Success | Passed |
| T58 | Length = 11 | `Hello, Yama` | Success | Passed |
| T59 | Length = 16 | `Hello, How are you?` | Success | Passed |
| T60 | Length = 499 | (499‑char text) | Success | **Failed** (bug B7) |
| T61 | Length = 500 | (500‑char text) | Success | **Failed** (bug B7) |

### 4.2 Valid Characters (special, Latin, numbers, punctuation)
| ID | Name | Steps (Message input) | Expected | Status |
|----|------|-----------------------|----------|--------|
| T62 | Special chars | `!"№;%:?*()()` | Success | Passed |
| T63 | Latin letters | `Hello what's up` | Success | Passed |
| T64 | Numbers | `12345678900` | Success | Passed |
| T65 | Punctuation | `So, maybe we should continue our lesson?` | Success | Passed |

### 4.3 Invalid Lengths (<10 or >500)
| ID | Name | Steps (Message input) | Expected | Status |
|----|------|-----------------------|----------|--------|
| T66 | Empty | `""` | Error | Passed |
| T67 | 1 char | `P` | Error | Passed |
| T68 | 6 chars | `Hello` | Error | Passed |
| T69 | 8 chars | `Hello, I` | Error | Passed |
| T70 | 9 chars | `Hello, Yam` | Error | Passed |
| T71 | 501 chars | (501‑char text) | Error | Passed |
| T72 | 502 chars | (502‑char text) | Error | Passed |
| T73 | 512 chars | (512‑char text) | Error | Passed |

---

## Summary of Failed Tests (Bugs)

| Test ID | Field | Issue | Bug ID |
|---------|-------|-------|--------|
| T10 | Name | English letters not accepted (should be valid) | B4 |
| T37 | Email | Missing dot allowed (should fail) | B6 |
| T38 | Email | Special characters not rejected | B8 |
| T39 | Email | Space not rejected | B9 |
| T60, T61 | Message | Messages of 499/500 characters fail (should succeed) | B7 |

---

## Notes
- All other tests passed.
- For reproducibility, use valid inputs for other fields unless testing specific field.
- Preconditions include open form; for negative tests, other fields must be valid.