# Checklist and Test Results: Functional Testing (Yandex Metro v3.6)

**Application version:** Yandex Metro (v 3.6)
**Test device:** Honor 8, Android 9.0 Pie, 1080x1920 screen resolution, 5.5" diagonal

---

## Route Planning

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T1 | Successful route creation with station names entered in the "From" (Arbatskaya) and "To" (Tverskaya) fields | PASSED | – |
| T2 | Unsuccessful route creation with the station name entered in the "From" field (Arbatskaya) and the "To" field empty | PASSED | – |
| T3 | With the "Tap to select a station" option enabled in the settings, the user can tap to select a route station on the map | PASSED | – |
| T4 | When creating a new route, you can select a previously created route or a station in the route history | PASSED | – |
| T5 | When adding stations to build a route, the search history is saved | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A2) |
| T6 | Route history is available by tapping in the "From" or "To" fields | PASSED | – |
| T7 | You can clear your search history by clicking the "Clear Search History" button in the main menu | PASSED | – |

---

## Selecting a Station

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T8 | If the station has not been selected before, then when selected, this station is highlighted and its card pops up | PASSED | – |
| T9 | If the station has already been selected before, a card will pop up immediately | PASSED | – |

---

## Route History

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T10 | Each route created is remembered and placed at the top of the list in the route history | PASSED | – |
| T11 | When adding a new route to the history, the station that was previously the first in the list becomes the last | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A3) |
| T12 | Route history should be saved in future versions of the application | SKIPPED | – |

---

## Route Information

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T13 | If the current time is greater than the time interval specified in the route, the interval is updated | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A4) |

---

## Route Details / Changing Screen Orientation

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T14 | When changing orientation from portrait to landscape, route details are displayed on the left side of the screen | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A5) |
| T15 | When changing the screen orientation, the scale of the constructed route is maintained in the state selected by the user | **FAILED** | – |
| T16 | When switching from portrait to landscape orientation and back, collapsed route cards retain their position | **FAILED** | – |
| T17 | When switching from portrait to landscape orientation and back, open route cards retain their position | **FAILED** | – |
| T18 | When switching from portrait to landscape orientation and back, route cards in the middle position move to the middle position | **FAILED** | – |
| T19 | When switching from portrait to landscape orientation and back, collapsed stations retain their position | **FAILED** | – |
| T20 | When switching from portrait to landscape orientation and back, open stations retain their position | **FAILED** | – |
| T21 | When switching from portrait to landscape orientation and back, the stations in the middle position move to the middle position | **FAILED** | – |
| T22 | When switching from portrait to landscape orientation and back, collapsed settings retain their position | **FAILED** | – |
| T23 | When switching from portrait to landscape orientation and back, open settings retain their position | **FAILED** | – |
| T24 | When switching from portrait to landscape orientation and back, the settings in the middle position move to the middle position | **FAILED** | – |

---

## Long Tap at a Metro Station

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T25 | When long-tapping on a station and the station card window with the "From here" and "To here" buttons is open, the map remains in the same position selected by the user | PASSED | – |
| T26 | You can select a station on the map by tapping it if the "Select a station by tapping" option is enabled in the settings | PASSED | – |
| T27 | If a station has not been selected before, then when you tap it, the station is highlighted and its card appears | PASSED | – |
| T28 | If a station has already been selected before, a card will immediately pop up when you tap it | PASSED | – |
| T29 | If the "Select a station by tapping" option is enabled, then when you long-tap on a metro station, it will immediately appear in the "From" or "To" field | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A6) |
| T30 | If the "Select a station by tapping" option is disabled, then when you long-tap on a station, it will not immediately appear in the "From" or "To" field | PASSED | – |
| T31 | If the user releases the long tap while the focus is in an empty area of the map, the station card window will close | PASSED | – |

---

## Airplane Mode or No Connection

| No. | Description of the test | Status | Link to bug report |
|-----|------------------------|--------|--------------------|
| T32 | If there is no internet connection, an error message appears | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A7) |