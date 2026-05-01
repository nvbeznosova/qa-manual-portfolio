# Field Validation: Equivalence Partitioning & Boundary Value Analysis

**Testing technique:** Equivalence Partitioning (EP) and Boundary Value Analysis (BVA)  
**Application:** Scooter ordering web form  

---

## Address Field

| Test focus | Class / Border | Test data | Expected | Status | Bug link |
|-----------|----------------|-----------|----------|--------|----------|
| Length validity (5–50 chars) | 5 – 50 | "Moscow, Miklukho-Maklaya St., 10" (30) | Valid | PASSED | – |
| Length boundaries (5–50) | min=5, max=50 | "Moscow" (5), "...49", "...50", "...51" (invalid) | Valid | PASSED | – |
| Length <5 | 0 – 4 | "" (0), "M" (1), "Mos" (3), "Mosk" (4), "Moskv" (5 – valid) | Invalid (error) | PASSED | – |
| Length >50 | 51 – +∞ | Very long address (76) | Invalid (error) | PASSED | – |
| Only Russian letters | – | "Moscow, Miklukho-Maklaya Street" | Valid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A4) |
| Only numbers | – | "12345678" | Invalid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A5) |
| Required (empty) | – | Empty field | Error | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A6) |
| Special characters (., dash, comma) | – | Various | Valid | PASSED | – |
| Leading/trailing spaces | – | Spaces before/after | Should trim | PASSED | – |

---

## Delivery Date

| Test focus | Class / Border | Test data | Expected | Status | Bug link |
|-----------|----------------|-----------|----------|--------|----------|
| Calendar – only from tomorrow | tomorrow – +∞ | Tomorrow, day after tomorrow, +5 days | Valid | PASSED | – |
| Past dates | –∞ – today | Yesterday, today | Invalid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A7) |
| Required | – | Empty | Error expected (probably) | PASSED? (not clear) | – |

---

## Name Field

| Test focus | Class / Border | Test data | Expected | Status | Bug link |
|-----------|----------------|-----------|----------|--------|----------|
| Length 2–15 chars | 2 – 15 | "Nina" (4), "Ni" (2), "Nin" (3), "Nina Anna Nina" (14), "Nina Anna Ninaa" (15) | Valid | PASSED | – |
| Length <2 | 0 – 1 | "" (0), "N" (1) | Invalid | PASSED | – |
| Length >15 | 16 – +∞ | "Very long name..." (65) | Invalid | PASSED | – |
| Dash / hyphen | – | "Nina Anna-Maria" | Valid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A9) |
| Numbers only | – | "1234567890" | Invalid? (but PASSED – maybe field allows numbers?) | PASSED | – |
| English letters | – | "Nina Anna-Maria" | Valid | PASSED | – |
| Special characters | – | "Nina Anna-Maria@" | Should reject? (PASSED – maybe allowed?) | PASSED | – |
| Required (empty) | – | Empty | Error | PASSED | – |

---

## Comment Field

| Test focus | Class / Border | Test data | Expected | Status | Bug link |
|-----------|----------------|-----------|----------|--------|----------|
| Length ≤24 chars | 0 – 24 | "Call in 30 minutes" (19), 0,1,23,24 chars | Valid | PASSED | – |
| Length >24 | 25 – +∞ | Very long comment (62) | Invalid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A11) |
| Numbers only | – | "1234567890" | Should be valid? but **FAILED** (maybe field should accept numbers) | **FAILED** | (no link) |
| English letters only | – | "Comments" | Valid? but **FAILED** | **FAILED** | (no link) |
| Special characters | – | "Call in 30 minutes @" | Should be valid? but **FAILED** | **FAILED** | (no link) |

---

## Telephone Field

| Test focus | Class / Border | Test data | Expected | Status | Bug link |
|-----------|----------------|-----------|----------|--------|----------|
| 11 digits (no "+") | exactly 11 | "89991234567" | Valid | PASSED | – |
| 12 digits (with "+") | exactly 12 | "+74991234567" | Valid | PASSED | – |
| Length <11 (no "+") | 0 – 10 | "99912345" (8), "", "9", etc. | Invalid | PASSED | – |
| Length >11 (no "+") | 12 – +∞ | "999123457899" (12) | Invalid | PASSED | – |
| Length >12 (with "+") | 13 – +∞ | "+999123457899" (13) | Invalid | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A10) |
| Letters, special chars | – | "Hello", "+7(999)1234567" | Invalid (should be numbers only) | PASSED | – |

---

## Surname Field (similar to Name) – All PASSED

| Test focus | Status |
|-----------|--------|
| Length 2–15, <2, >15 | PASSED |
| Numbers, Russian, English, special chars, required | PASSED |
| Space within surname | PASSED |

---

## Color Field – All PASSED

| Test focus | Status |
|-----------|--------|
| "Black Pearl", "Gray Hopelessness" | PASSED |
| Not in list (e.g., "Red") | PASSED |
| Two values at once | PASSED |
| Required (empty) | PASSED |

---

## Rental Period – All PASSED (options from "Day" to "Seven days")

---

## Metro Station – All PASSED (Moscow stations, London station, empty)

---

## Summary

- **Total checks:** ~70  
- **Failed checks:** ~10 (highlighted above)  
- **Main issues:** address validation (Russian letters, numbers only, empty), delivery date (past dates allowed), name (dash/hyphen), comment (length >24, numbers/English letters/special chars wrongly rejected), telephone (length with "+" sign).

This document demonstrates systematic application of equivalence partitioning and boundary value analysis for form field validation.