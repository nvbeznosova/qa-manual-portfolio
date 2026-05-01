# Mobile Regression Test Results: Yandex Metro (v3.6)

**Application version:** Yandex Metro (v 3.6)  
**Test device:** Honor 8, Android 9.0 Pie, 1080x1920 screen resolution, 5.5" diagonal  

---

## Permission to Access the Device

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t1 | When you open an app on your device, it asks for permission to access location data. | PASSED | – |
| t2 | When geolocation access is allowed, the application determines the location and opens a metro map of the city where the device is located. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A5) |
| t3 | You can enter the station name in the "From" and "To" fields using voice input. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A6) |
| t4 | After the app is granted access to geolocation, the device determines the user's location and transmits data about it to the app. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A7) |
| t5 | In your device settings, you can configure whether to allow or block notifications from the app. | PASSED | – |
| t6 | Notifications from the app do not interrupt other apps. | SKIPPED | – |

---

## Work Offline

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t7 | Previously entered data (route history) is saved on the device; the application can replay it the next time it is opened without network access (airplane mode). | PASSED | – |
| t8 | After closing the application and opening it again, the history of previously entered data is saved. | PASSED | – |

---

## Running in the Background (Interrupt Testing)

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t9 | The application works correctly when the battery charge is 5% and the device is in power saving mode. | PASSED | – |
| t10 | When you press the Home button, the application is minimized; entered data and search results are saved. | PASSED | – |
| t11 | When you launch the application after it has been completely stopped, it starts with the start page of the metro map and empty "From" and "To" fields. | PASSED | – |
| t12 | When you minimize the application and switch between tabs on the device, entered data and search results are saved. | PASSED | – |
| t13 | When the screen is locked, the application saves the user's operating state and settings. | PASSED | – |
| t14 | When a call comes in while using the app, a notification appears at the top; entered data and search results are saved during and after the call ends. | PASSED | – |
| t15 | When you receive a text message while using the app, a notification appears; entered data and search results are saved when you reply and return to the app. | PASSED | – |
| t16 | Calling the settings menu from the top panel of the device does not interrupt the application and saves the entered data and search results. | PASSED | – |

---

## Updating the Application

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t17 | After the update, the application version is updated (current version shown in settings). | PASSED | – |
| t18 | The user remained logged in after the update. | SKIPPED | – |
| t19 | After the update, access to geolocation and notification permissions (if configured) were retained. | PASSED | – |
| t20 | User data and search history are retained after updating the app version. | PASSED | – |
| t21 | The application was updated in a minimized state. | PASSED | – |
| t22 | The application was updated in an active state. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A6) |

---

## Performance

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t23 | CPU usage when running the application is at an acceptable level (13%). | PASSED | – |

---

## Testing the Connection

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t24 | The application works correctly on LTE networks. | PASSED | – |
| t25 | The application works correctly on a 5G network. | PASSED | – |
| t26 | The application works correctly on the EDGE network. | PASSED | – |

---

## Sending Feedback

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t27 | Clicking the "Feedback" button takes you to the support window using Webview. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A12) |

---

## Using the App's Dark Theme

| ID | Description of the test | Status | Bug Report Link |
|----|------------------------|--------|-----------------|
| t28 | If the dark theme is disabled, the light theme is displayed. | PASSED | – |
| t29 | If the dark theme is enabled, the user interface is displayed in a dark color. | PASSED | – |
| t30 | If the "Automatic" mode is set, the theme changes automatically: light → dark at 6:00 PM, dark → light at 6:00 AM (Moscow time). | SKIPPED | – |
| t31 | You can change the dark theme to light while using the app. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A13) |