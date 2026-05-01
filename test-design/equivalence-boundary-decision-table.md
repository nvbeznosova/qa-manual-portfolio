# Equivalence Partitioning, Boundary Value Analysis & Decision Table

## 1. Name Field

**Requirements:**  
Required, cannot be empty. Allowed: Russian/English letters (upper/lower case), spaces, hyphens. Length 2–30 characters.

| Class | Borders | Inside class example | Boundary values |
|-------|---------|----------------------|------------------|
| Valid data | – | `Ivan` | – |
| Empty (invalid) | – | `""` (0) | – |
| Length 2–30 (valid) | 2 – 30 | `Ivan` (4) | `O` (1 – invalid), `Yang` (2), `Yana` (3), `...29`, `...30`, `...31` (invalid) |
| Length <2 (invalid) | 0 – 1 | – | `""` (0), `O` (1) |
| Length >30 (invalid) | 31 – +∞ | `AlexanderAlexanderAlexanderAlexander` (36) | `...30` (valid), `...31`, `...32` |
| Capital letters (valid) | – | `IVAN` | – |
| Lowercase letters (valid) | – | `ivan` | – |
| Space (valid) | – | `Ivan Ivanov` | – |
| Hyphen (valid) | – | `Ivan-Roman` | – |
| Russian letters (valid) | – | `Иван` | – |
| English letters (valid) | – | `Alex` | – |
| Arabic letters (invalid) | – | `ب غوريون` | – |
| Numbers (invalid) | – | `1 van` | – |
| Special char (invalid) | – | `@van` | – |

---

## 2. Email Field

**Requirements:**  
Required, cannot be empty. Must contain `@` and `.`. Latin letters, numbers, hyphens only. Length 5–30 characters.

| Class | Borders | Inside class example | Boundary values |
|-------|---------|----------------------|------------------|
| Valid data | – | `rivan@yandex.ru` | – |
| Empty (invalid) | – | `""` (0) | – |
| Length 5–30 (valid) | 5 – 30 | `rivan@yandex.ru` (15) | `@t.k` (4 – invalid), `r@m.r` (5), `r@m.ru` (6), `...29`, `...30`, `...31` (invalid) |
| Length <5 (invalid) | 2 – 4 | `@.t` (3) | `@.` (2), `@.t` (3), `k@.k` (4), `r@m.r` (5 – valid boundary) |
| Length >30 (invalid) | 31 – +∞ | long@example.com (36) | `...30` (valid), `...31`, `...32` |
| Latin letters (valid) | – | `rivan@yandex.ru` | – |
| Russian letters (invalid) | – | `иван@yandex.ru` | – |
| Numbers (valid) | – | `rivan94@yandex.ru` | – |
| Contains @ and . (valid) | – | `rivan@yandex.ru` | – |
| Missing @ (invalid) | – | `rivanyandex.ru` | – |
| Missing . (invalid) | – | `rivan@yandexru` | – |
| Hyphen (valid) | – | `r-ivan@yandex.ru` | – |

---

## 3. Telephone Field

**Requirements:**  
Required, cannot be empty. Only numbers and `+` sign allowed. Digits count 7–14, no spaces or hyphens.

| Class | Borders | Inside class example | Boundary values |
|-------|---------|----------------------|------------------|
| Valid data | – | `89002223311` | – |
| Empty (invalid) | – | `""` (0) | – |
| Digits 7–14 (valid) | 7 – 14 | `89002223311` (11) | `890022` (6 – invalid), `8900222` (7), `89002223` (8), `...13`, `...14`, `...15` (invalid) |
| `+` sign (valid) | – | `+79998886655` | – |
| Digits <7 (invalid) | 0 – 6 | `9112` (4) | `""` (0), `7` (1), ... `911282` (6), `9112373` (7 – valid) |
| Digits >14 (invalid) | 15 – +∞ | `890022233110686786` (18) | `...14` (valid), `...15`, `...16` |
| Letters (invalid) | – | `b900223311a` | – |
| Hyphen (invalid) | – | `8-9002223322` | – |
| Space (invalid) | – | `8 9002223322` | – |

---

## 4. Decision Table for Tariff Parameter Selection (Positive Checks)

**Service types:** Monthly / Annual · Standard / Advanced / Pro  
**Options:** Play online, More space, Custom profile (1 = selected, 0 = not selected)  
**Result:** Final price (rubles/month or rubles/year + 2 months free for annual plans)

| Test | Service type | Play online | More space | Custom profile | Result |
|------|--------------|-------------|------------|----------------|--------|
| 1 | Monthly Stand | 0 | 0 | 0 | 900 ₽/m |
| 2 | Monthly Stand | 1 | 0 | 0 | 1000 ₽/m |
| 3 | Monthly Stand | 1 | 1 | 0 | 1200 ₽/m |
| 4 | Monthly Stand | 1 | 0 | 1 | 1200 ₽/m |
| 5 | Monthly Stand | 1 | 1 | 1 | 1400 ₽/m |
| 6 | Monthly Stand | 0 | 1 | 1 | 1300 ₽/m |
| 7 | Monthly Stand | 0 | 0 | 1 | 1100 ₽/m |
| 8 | Monthly Stand | 0 | 1 | 0 | 1100 ₽/m |
| 9 | Annual Stand | 1 | 1 | 0 | 12,000 ₽/year + 2m free |
| 10 | Annual Stand | 1 | 0 | 0 | 10,000 ₽/year + 2m free |
| 11 | Annual Stand | 0 | 0 | 0 | 9000 ₽/year + 2m free |
| 12 | Annual Stand | 1 | 1 | 1 | 14,000 ₽/year + 2m free |
| 13 | Annual Stand | 0 | 1 | 1 | 13,000 ₽/year + 2m free |
| 14 | Annual Stand | 0 | 0 | 1 | 11,000 ₽/year + 2m free |
| 15 | Annual Stand | 0 | 1 | 0 | 11,000 ₽/year + 2m free |
| 16 | Annual Stand | 1 | 0 | 1 | 12,000 ₽/year + 2m free |
| 17 | Monthly Adv | 0 | 0 | 0 | 1200 ₽/m |
| 18 | Monthly Adv | 1 | 0 | 0 | 1300 ₽/m |
| 19 | Monthly Adv | 1 | 1 | 0 | 1500 ₽/m |
| 20 | Monthly Adv | 1 | 0 | 1 | 1500 ₽/m |
| 21 | Monthly Adv | 1 | 1 | 1 | 7500 ₽/m |
| 22 | Monthly Adv | 0 | 1 | 1 | 1600 ₽/m |
| 23 | Monthly Adv | 0 | 0 | 1 | 1400 ₽/m |
| 24 | Monthly Adv | 0 | 1 | 0 | 1400 ₽/m |
| 25 | Annual Adv | 1 | 1 | 0 | 15,000 ₽/year + 2m free |
| 26 | Annual Adv | 1 | 0 | 0 | 13,000 ₽/year + 2m free |
| 27 | Annual Adv | 0 | 0 | 0 | 12,000 ₽/year + 2m free |
| 28 | Annual Adv | 1 | 1 | 1 | 17,000 ₽/year + 2m free |
| 29 | Annual Adv | 0 | 1 | 1 | 16,000 ₽/year + 2m free |
| 30 | Annual Adv | 0 | 0 | 1 | 14,000 ₽/year + 2m free |
| 31 | Annual Adv | 0 | 1 | 0 | 14,000 ₽/year + 2m free |
| 32 | Annual Adv | 1 | 0 | 1 | 15,000 ₽/year + 2m free |
| 33 | Monthly Pro | 0 | 0 | 0 | 1500 ₽/m |
| 34 | Monthly Pro | 1 | 0 | 0 | 1600 ₽/m |
| 35 | Monthly Pro | 1 | 1 | 0 | 1800 ₽/m |
| 36 | Monthly Pro | 1 | 0 | 1 | 1800 ₽/m |
| 37 | Monthly Pro | 1 | 1 | 1 | 2000 ₽/m |
| 38 | Monthly Pro | 0 | 1 | 1 | 1900 ₽/m |
| 39 | Monthly Pro | 0 | 0 | 1 | 1700 ₽/m |
| 40 | Monthly Pro | 0 | 1 | 0 | 1700 ₽/m |
| 41 | Annual Pro | 0 | 0 | 0 | 15,000 ₽/year + 2m free |
| 42 | Annual Pro | 1 | 0 | 0 | 16,000 ₽/year + 2m free |
| 43 | Annual Pro | 1 | 1 | 0 | 18,000 ₽/year + 2m free |
| 44 | Annual Pro | 1 | 1 | 1 | 20,000 ₽/year + 2m free |
| 45 | Annual Pro | 0 | 1 | 1 | 19,000 ₽/year + 2m free |
| 46 | Annual Pro | 0 | 0 | 1 | 17,000 ₽/year + 2m free |
| 47 | Annual Pro | 0 | 1 | 0 | 17,000 ₽/year + 2m free |
| 48 | Annual Pro | 1 | 0 | 1 | 18,000 ₽/year + 2m free |