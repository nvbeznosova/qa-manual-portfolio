# Bug Reports – Yandex.Metro Mobile App

**Common Environment (unless specified otherwise):**  
- Device: Honor 8 (screen 1080x1920, 5.5″)  
- OS: Android 9.0 Pie  
- App version: 3.6  

---

| ID | Bug Name | Priority | Preconditions | Steps to Reproduce | Expected Result | Actual Result |
|----|----------|----------|---------------|-------------------|-----------------|---------------|
| T5 | Route search history stores only 2 routes. | Low priority | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya" (Arbatsko-Pokrovskaya).<br>3. To: "Tverskaya" (Zamoskvoretskaya).<br>4. Create route.<br>5. Clear stations.<br>6. Enter new stations (different route). | History of all routes is preserved. | History saved only for the first two routes. |
| T11 | Station order is not maintained when adding new route to history. | Minor | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya".<br>3. To: "Tverskaya".<br>4. Create route.<br>5. View route history. | Previously first station becomes last when new route added. | Station appears as first (order unchanged). |
| T13 | Route time interval not updated after end time exceeded. | Medium | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya".<br>3. To: "Tverskaya".<br>4. Build route. | If current time > route end time, interval updates. | Interval does not update. |
| T14‑T24 | App crashes when changing screen orientation. | Blocking | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya".<br>3. To: "Tverskaya".<br>4. Create route.<br>5. Change screen orientation (portrait ↔ landscape). | Route details displayed correctly on left, scale preserved, card states retained. | App terminates (crashes). |
| t22 | App updates but crashes after minimization. | Medium | **App version: 2.13** (other same). | 1. Open app (v2.13).<br>2. Update to v3.6 while app active. | App updates in active state without issues. | App updates, then crashes and terminates. |
| T29 | Station name not added to From/To fields on long tap. | Low | As per common environment. | 1. Open app.<br>2. Enable "Select station by tap" in settings.<br>3. Long‑tap any station. | Station name appears in "From" or "To" field. | Station card opens, but name not added. |
| T32 | No error message when internet is disconnected. | Low | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya".<br>3. To: "Tverskaya".<br>4. Create route.<br>5. Enable airplane mode. | Error message appears (no connection). | No error message shown. |
| t2 | App does not open metro map of current location / nearest station (geolocation enabled). | Critical | As per common environment. | 1. Open app.<br>2. Allow location access. | Nearest metro station indicated. | Location not determined, no nearest station. |
| t3 | Voice input not supported for station name. | Minor | As per common environment. | 1. Open app.<br>2. From: "Arbatskaya" (typed).<br>3. Use voice input for "To": "Tverskaya". | Station input works via voice. | Unable to enter station name by voice. |
| t4 | Location not determined even though app has permission. | Critical | As per common environment. | 1. Open app.<br>2. Allow location access. | Device determines user location. | Location not determined. |
| t27 | "Feedback" button does not open support window (opens Gmail instead). | Medium | As per common environment. | 1. Open app.<br>2. Go to Settings → tap "Feedback". | Support window opens (Webview). | Gmail app home page opens. |
| t31 | App crashes when switching between dark/light theme. | Critical | As per common environment. | 1. Open app.<br>2. Go to Settings → change theme (dark ↔ light). | Theme changes without affecting app stability. | App terminates (crashes). |

---

## Summary by Priority

| Priority | Count |
|----------|-------|
| Blocking | 1 |
| Critical | 4 |
| Medium | 3 |
| Minor | 2 |
| Low | 3 |

*All bugs are in **Open** status (no fix verification yet).*