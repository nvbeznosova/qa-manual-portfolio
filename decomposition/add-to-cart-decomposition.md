# Tariff Plan – Add‑to‑Cart Functionality

## Task
Test the implementation of the tariff plan selection (add‑to‑cart flow).

## Links
- **Requirements (mockups):** [Figma Design](https://www.figma.com/design/PjpyWANACPWaVPizTgHkeC/multi-step-form_external_link?node-id=0-1&t=UP7GuhP9sch7WlC9-0)
- **Requirements (text):** [Google Docs](https://docs.google.com/document/d/104A3Mxzm1tcWZoiJg_h5Y9dr0FsER2bnkxvBMDcAVu8/edit?usp=sharing)
- **Implementation:** [Tariff Plan Form](https://qa-faculty.github.io/tariff-plan/)

---

## Components and Prices

### 1. Personal Data
- **3 data entry fields with validation:** Name, Email, Phone

---

### 2. Plan Selection – Annual Maintenance (with 2 months free)

| Tariff | Price (annual) |
|--------|----------------|
| Standard | 9,000 rubles + 2 months free |
| Advance | 12,000 rubles + 2 months free |
| Pro | 15,000 rubles + 2 months free |

---

### 3. Plan Selection – Monthly Service

| Tariff | Price (monthly) |
|--------|-----------------|
| Standard | 900 rubles/month |
| Advance | 1,200 rubles/month |
| Pro | 1,500 rubles/month |

---

### 4. Additional Options – Annual Maintenance

| Option | Price (annual) |
|--------|----------------|
| Ability to play online | 1,000 rubles/year |
| Get 1 TB of cloud storage | 2,000 rubles/year |
| Personalize your profile | 2,000 rubles/year |

---

### 5. Additional Options – Monthly Service

| Option | Price (monthly) |
|--------|-----------------|
| Ability to play online | 100 rubles/month |
| Get 1 TB of cloud storage | 200 rubles/month |
| Personalize your profile | 200 rubles/month |

---

### 6. Confirm Button

- **Action:** When clicked, information about the selected tariff plan (for the specified account) is transmitted to the server.
- **Expected result:** Successful data submission; response handling (success/error).