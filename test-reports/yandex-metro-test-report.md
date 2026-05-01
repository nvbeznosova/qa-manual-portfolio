# Yandex Metro Test Report (v 3.6)

## Test Environment
- **Emulator:** Android Studio
- **OS:** Android 9.0 Pie
- **Device:** Honor 8
- **Screen resolution:** 1080×1920, 5.5″ diagonal
- **App version:** 3.6

## Test Documentation
- **Checklist (functional):** [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=899462569#gid=899462569)
- **Regression checklist:** [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=1540435533#gid=1540435533)
- **Test results (full):** [Link](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547)

## Test Execution Summary
- **Total checks:** 63
- **Passed:** 37
- **Failed:** 22
- **Skipped:** 4 (due to insufficient functionality)

---

## Bugs by Priority

### Blocking
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A5)

### Critical
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A9)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A11)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A13)

### Medium Priority
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A4)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A6)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A12)

### Low Priority
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A2)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A7)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A8)

### Minor
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A3)
- [Bug report](https://docs.google.com/spreadsheets/d/1EQZRGJU8biGVePqpNyIdKOAdVXWkcEdCPm7Vvurmcq4/edit?gid=845933547#gid=845933547&range=A10)

---

## Recommendation
> **Two blocking bugs were found. The testing team does NOT recommend publishing the new version on Google Play.**

## Additional Information
- **Test documentation creation:** 1 day
- **Testing execution:** 2 days
- **Blocking bugs found:** 1  
- **Critical bugs found:** 3  
  *These will interfere with user interaction with the app.*
- **Types of testing performed:** Functional, regression

## Post‑Fix Notes
After fixing the bugs, special attention should be paid to:
- **Geolocation detection**
- **Synchronisation of data input with device voice input functionality**  
  (These are not critical errors but significantly impact the user experience.)

## Final Recommendation
1. Fix **blocking and critical bugs** first, then publish the app version.
2. Fix the remaining bugs in the background and release them in subsequent updates.