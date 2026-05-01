# Test Design Techniques: Equivalence Partitioning & Boundary Value Analysis

## Name Field

**Requirements:**  
This field is required and cannot be empty. Russian and English letters, uppercase and lowercase, are accepted. Spaces and hyphens are also allowed. The name must be between 2 and 30 characters long.

| Class | Borders | Test data inside a class | Test data at the boundaries |
|-------|---------|--------------------------|-----------------------------|
| The field contains data (valid) | – | `Ivan` | – |
| The field is empty (invalid) | – | `""` (0 characters) | – |
| Length from 2 to 30 characters (valid) | 2 – 30 | `Ivan` (4) | `Ni` (2), `NikolayNikolayNikolayNikolayNi` (30) |
| Length less than 2 characters (invalid) | 0 – 1 | `O` (1) | `""` (0), `O` (1) |
| Length more than 30 characters (invalid) | 31 – +∞ | `AlexanderAlexanderAlexanderAlexander` (36) | `NikolayNikolayNikolayNikolayNi` (30 – valid boundary), `NikolayNikolayNikolayNikolayNik` (31), `NikolayNikolayNikolayNikolayNiko` (32) |
| Capital letters (valid) | – | `IVAN` | – |
| Lowercase letters (valid) | – | `ivan` | – |
| Space (valid) | – | `Ivan Ivanov` | – |
| Hyphen (valid) | – | `Ivan-Ivan` | – |
| Russian letters (valid) | – | `Иван` | – |
| English letters (valid) | – | `Alex` | – |
| Arabic letters (invalid) | – | `ب غوريون` | – |
| Numbers (invalid) | – | `123` | – |
| Special character (invalid) | – | `*&%` | – |

---

## Email Field

**Requirements:**  
Required field. Cannot be empty. Must contain “@” and “.” (dot). Only Latin letters, numbers, and hyphens. Length from 5 to 30 characters.

| Class | Borders | Test data inside a class | Test data at the boundaries |
|-------|---------|--------------------------|-----------------------------|
| The field contains data (valid) | – | `rivan@yandex.ru` | – |
| The field is empty (invalid) | – | `""` (0) | – |
| Length from 5 to 30 characters (valid) | 5 – 30 | `rivan@yandex.ru` (15) | `@t.k` (4 – invalid), `r@m.r` (5), `r@m.ru` (6), `krolkinaangelinaole@yandex.ru` (29), `krolkinaangelinaoleg@yandex.ru` (30), `krolkinaangelinaolega@yandex.ru` (31 – invalid) |
| Length less than 5 characters (invalid) | 0 – 4 | `@.` (2) | `""` (0), `@` (1), `@.t` (3), `k@.k` (4), `r@m.r` (5 – valid boundary) |
| Length more than 30 characters (invalid) | 31 – +∞ | `krolkinaangelinaolega1lala@yandex.ru` (36) | `krolkinaangelinaoleg@yandex.ru` (30 – valid), `krolkinaangelinaolega@yandex.ru` (31), `krolkinaangelinaolega1@yandex.ru` (32) |
| Latin characters (valid) | – | `rivan@yandex.ru` | – |
| Russian characters (invalid) | – | `иван@yandex.ru` | – |
| Numbers (valid) | – | `ivan32@yandex.ru` | – |
| Contains @ and . (valid) | – | `rivan@yandex.ru` | – |
| Special characters (invalid) | – | `rivan!№%@yandex.ru` | – |
| Space (invalid) | – | `rivan@yandex.ru` (with space) | – |
| Missing @ (invalid) | – | `rivanyandex.ru` | – |
| Missing . (invalid) | – | `rivan@yandexru` | – |
| Hyphen (valid) | – | `r-ivan@yandex.ru` | – |

---

## Telephone Field

**Requirements:**  
Required field. Must not be empty. Only numbers are allowed. Number of digits must be from 7 to 14, no spaces or hyphens.

| Class | Borders | Test data inside a class | Test data at the boundaries |
|-------|---------|--------------------------|-----------------------------|
| The field contains data (valid) | – | `89002223311` | – |
| The field is empty (invalid) | – | `""` (0) | – |
| From 7 to 14 digits (valid) | 7 – 14 | `89002223311` (11) | `890022` (6 – invalid), `8900222` (7), `89002223` (8), `8900222894343` (13), `89002228943439` (14), `890022289434337` (15 – invalid) |
| Less than 7 digits (invalid) | 0 – 6 | `9112` (4) | `""` (0), `7` (1), `91123` (5), `911282` (6), `9112373` (7 – valid boundary) |
| More than 14 digits (invalid) | 15 – +∞ | `890022233110686786` (18) | `89002228943439` (14 – valid), `890022289434337` (15), `8900222894343337` (16) |
| Letters (invalid) | – | `b900223311a` | – |
| Hyphen (invalid) | – | `8-9002223322` | – |
| Special characters (invalid) | – | `8&9002223322` | – |
| Space (invalid) | – | `8 9002223322` | – |

---

## Message Field

**Requirements:**  
Required field. Must not be empty. Message length must be from 10 to 500 characters.

| Class | Borders | Test data inside a class | Test data at the boundaries |
|-------|---------|--------------------------|-----------------------------|
| The field contains data (valid) | – | `Hello` | – |
| The field is empty (invalid) | – | `""` (0) | – |
| Length from 10 to 500 characters (valid) | 10 – 500 | `Hello, How are you?` (16) | `Hello Ya` (9 – invalid), `Hello Yam` (10), `Hello Yama` (11), `[499 chars]`, `[500 chars]`, `[501 chars – invalid]` |
| Length less than 10 characters (invalid) | 0 – 9 | `Hello` (6) | `Hello` (6), `""` (0) |
| Length more than 500 characters (invalid) | 501 – +∞ | `[512 chars]` | `[500 chars]` (valid), `[501 chars]`, `[502 chars]` |
| Latin characters (valid) | – | `Hello, what's up?` | – |
| Russian symbols (valid) | – | `Привет, как дела` | – |
| Arabic characters (invalid) | – | `مرحبا ما الأمر معك` | – |
| Numbers (valid) | – | `12345678900` | – |
| Special characters (valid) | – | `!"№;%:?*()()` | – |
| Punctuation marks (valid) | – | `So, maybe we should continue our activity?` | – |
| Space (valid) | – | `Hi, how are you` | – |