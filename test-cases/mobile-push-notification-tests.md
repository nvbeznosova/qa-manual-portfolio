# Mobile App Test Cases: Push Notifications & Offline Handling

**Environment:** Android Studio Ladybug Feature Drop emulator, version 2024.2.2 Patch 1, OS: Android 9.  
*(Applies to all test cases unless otherwise stated.)*

---

## Push Notifications

### Order end reminder (2 hours before)

| ID | Test case name | Preconditions | Steps | Expected result |
|----|----------------|---------------|-------|-----------------|
| T1 | Notification 2 hours before order end | 1. Order placed for current day.<br>2. Courier hasn't delivered by 21:59. | 1. Place order.<br>2. Set system time to 21:59. | Courier receives a push notification. |
| T2 | No notification before 2 hours | Same as T1. | 1. Place order.<br>2. Set system time to 19:59. | Courier does **not** receive notification. |
| T3 | No notification after 2 hours | Same as T1. | 1. Place order.<br>2. Set system time to 23:59. | Courier does **not** receive notification. |

### App state variations

| ID | Test case name | Preconditions | Steps | Expected result |
|----|----------------|---------------|-------|-----------------|
| T4 | App in background | Same as T1. | 1. Place order.<br>2. Set time to 23:59.<br>3. Collapse app. | Courier receives notification. |
| T5 | Notifications blocked on device | 1. Enable notification blocking.<br>2. Then same as T1. | 1. Place order.<br>2. Set time to 23:59. | Courier receives **no** notification. |
| T6 | Device offline | Same as T1. | 1. Place order.<br>2. Disable internet.<br>3. Set time to 23:59. | Courier receives notification (delivered when online). |
| T7 | App closed | Same as T1. | 1. Place order.<br>2. Set time to 23:59.<br>3. Close app. | Courier does **not** receive notification. |
| T8 | Screen locked | Same as T1. | 1. Place order.<br>2. Set time to 23:59.<br>3. Lock screen. | Courier receives notification. |

### Notification interaction & UI

| ID | Test case name | Preconditions | Steps | Expected result |
|----|----------------|---------------|-------|-----------------|
| T9 | Tap on notification | 1. Courier has unaccepted order.<br>2. Notification arrives at 21:59. | 1. Place order.<br>2. Set time to 21:59.<br>3. Tap notification. | App opens on **"My"** tab. |
| T10 | Notification content | Same as T1. | 1. Place order.<br>2. Set time to 21:59. | Text: "2 hours left until the end of the order. The order for 'Komnatnaya St. 12-14' must be completed by time N. If you don't make it, notify support: 0101." |
| T11 | Notification background | Same as T1. | 1. Place order.<br>2. Set time to 21:59. | White background. |
| T12 | Notification sender | Same as T1. | 1. Place order.<br>2. Set time to 21:59. | Logo (scooter wheel) and company name "Fndex scooter". |
| T13 | Notification text styling | Same as T1. | 1. Place order.<br>2. Set time to 21:59. | Title "2 hours left on order" in bold, rest regular font, left-aligned. |

### "My" tab after tapping notification

| ID | Test case name | Preconditions | Steps | Expected result |
|----|----------------|---------------|-------|-----------------|
| T14 | "My" tab content | Same as T1. | 1. Set time to 21:59.<br>2. Tap notification. | Tab title at top; below: address, delivery date, metro station name, "Finish" button. |
| T15 | Text styling in "My" tab | Same as T1. | 1. Place order.<br>2. Set time to 21:59.<br>3. Tap notification. | Active tab title underlined; section titles bold, content regular font. |
| T16 | "My" tab design details | Same as T1. | 1. Place order.<br>2. Set time to 21:59.<br>3. Tap notification. | Next to metro station: circle in the color of the metro line. "Complete" button: black frame, white fill. |

---

## No Internet Connection Window

| ID | Test case name | Preconditions | Steps | Expected result |
|----|----------------|---------------|-------|-----------------|
| T17 | Window appears | 1. Disable internet.<br>2. Open app. | Click any active button (e.g., "Accept order"). | Pop‑up window appears. |
| T18 | Window content | Same as T17. | Click any active button. | Text: "No Internet access. Check your connection or wait for a notification that it's restored". Button "OK". |
| T19 | Close via OK | 1. Internet disconnected.<br>2. Pop‑up shown. | Click "OK". | Window closes. |
| T20 | Cannot close by tapping outside | Same as T19. | Click any other area/button. | Window stays open. |
| T21 | Reappears if still offline | 1. Internet disconnected.<br>2. User closed the window. | Press any active button again. | Pop‑up appears again. |
| T22 | Does not appear if internet restored | 1. Internet disconnected, window closed.<br>2. Internet restored after closure. | Press any active button again. | No pop‑up appears. |

---

## Notes
- All test cases assume same emulator environment unless stated otherwise.
- No explicit pass/fail status recorded – document as designed test coverage.
- For bug tracking, add a separate column if needed.