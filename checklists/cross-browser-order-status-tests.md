# Cross‑Browser Test Results: Scooter Ordering Web App

**Test environment:**  
- macOS Sequoia 15.6.1  
- Yandex Browser 25.8.5.977 (64‑bit), 1920×1080  
- Google Chrome 142.0.7444.162, 1280×720  

---

## Screen Header

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 1 | Clicking on the Yandex logo takes you to the Zen page. | PASSED | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A32) |
| 2 | The Yandex logo is written in black bold font and is located in the upper left corner of the screen. | PASSED | PASSED | – |
| 3 | Clicking on the "Scooter" logo leads to the website's main page. | PASSED | PASSED | – |
| 4 | The Samokat logo is written in a thin black font and is located in the upper left part of the screen to the right of the Yandex logo. | PASSED | PASSED | – |

---

## Order Status Field

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 5 | When you click the “Order Status” button in the landing page header, the “Order Number” input field appears. | PASSED | PASSED | – |
| 6 | When you enter the order number in the "Order Number" input field and press Enter, if the order number is entered correctly, information about the order appears. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A40) |
| 7 | Verify that the order information is displayed when entering the correct order number. | PASSED | PASSED | – |
| 8 | Check that when entering a non-existent order number, the message "There is no such order. Are you sure you have the correct number?" is displayed. | PASSED | PASSED | – |
| 9 | Check if an error message appears when entering special characters in the "Order Number" field. | PASSED | PASSED | – |

---

## Order Status Window

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 10 | When displaying order information, the Name field appears. | PASSED | PASSED | – |
| 11 | When displaying order information, the Last Name field appears. | PASSED | PASSED | – |
| 12 | When displaying order information, the Address field appears. | PASSED | PASSED | – |
| 13 | When displaying order information, the Metro Station field appears. | PASSED | PASSED | – |
| 14 | When displaying order information, the Phone field appears. | PASSED | PASSED | – |
| 15 | When displaying information about an order, the field "When we deliver" appears. | PASSED | PASSED | – |
| 16 | When displaying information about an order, the Rental Period field appears. | PASSED | PASSED | – |
| 17 | When displaying order information, the Color field appears. | PASSED | PASSED | – |
| 18 | When displaying order information, a Comment field appears. | PASSED | PASSED | – |
| 19 | The "Scooter in stock" status becomes active when the user places an order. | PASSED | PASSED | – |
| 20 | The "Courier is on his way to you" status becomes active when the courier has confirmed in his app that he has accepted the order. | PASSED | PASSED | – |
| 21 | The "Courier on site" status becomes active when the courier presses the "Complete" button in their app. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A33) |
| 22 | "Okay, now it's time to ride." Becomes active when the courier confirms the order has been completed. | PASSED | PASSED | – |
| 23 | "Okay, now it's time to go." Doesn't become active until the courier confirms the order has been completed. | PASSED | PASSED | – |
| 24 | Check the order status chain display (active status is highlighted in black, completed statuses are marked with a check mark). | PASSED | PASSED | – |
| 25 | Check that the courier's name is displayed in the "Courier is on its way to you" status and is moved to the second line if the name is long. | PASSED | PASSED | – |
| 26 | Check that when the rental ends, the status changes to "Rental time has ended". | PASSED | PASSED | – |
| 27 | When the rental period ends and the status changes to "Rental period ended," the message "The courier will pick up the scooter soon" appears. | PASSED | PASSED | – |
| 28 | Check the display of an overdue order (status "Courier is delayed", highlighted in red). | PASSED | PASSED | – |
| 29 | The user can enter the number of another order and view its status. | PASSED | PASSED | – |

---

## Order Cancellation

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 30 | At the bottom of the order information there is a "Cancel order" button. | PASSED | PASSED | – |
| 31 | Clicking the "Cancel Order" button opens a pop‑up window with text "Do you want to cancel your order?" and two buttons: "Cancel" and "Back". | PASSED | PASSED | – |
| 32 | Clicking "Back" returns the user to the order status page. | PASSED | PASSED | – |
| 33 | Clicking "Cancel" opens a pop‑up with text "Order canceled. Come back, we're always waiting for you :)" and an "OK" button that takes you to the landing page's main page. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A37) |
| 34 | The user can cancel the order until the courier has started working on it. | PASSED | PASSED | – |
| 35 | Once the order is with the courier, the "Cancel order" button is not clickable and the order cannot be cancelled. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A39) |
| 36 | A canceled order is deleted from the system. The user cannot view it. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A2) |

---

## Overdue Order

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 37 | An order is considered overdue if the courier fails to complete it on time. | PASSED | PASSED | – |
| 38 | If order is overdue, "Courier is on its way" status changes to "Courier is delayed", and signature changes to "We won't deliver the scooter on time. To check the order status, call support at 0101." Status and signature are highlighted in red. | PASSED | PASSED | – |
| 39 | If the user has received an overdue order, the countdown to the end of the rental period begins from the moment the order is received. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A36) |

---

## Layout Tests

| # | Description | Yandex | Chrome | Bug Report |
|---|-------------|--------|--------|-------------|
| 40 | General design of the "Order Status" button – title placed in black on the left side of the landing page header, no outline or fill, white background. | PASSED | PASSED | – |
| 41 | General design of the "Order Status" field – after clicking, a field appears with placeholder "Order Number", gray color, gray outline, white background. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A22) |
| 42 | "Order Status" window – top has field with tracking number and "View" button; left side displays order info, right side order statuses; bottom has "Cancel Order" button (black frame, black on white). | PASSED | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A30) |
| 43 | Order Status window – field with order number has black frame, black text; "View" button white on black background, black fill. | PASSED | PASSED | – |
| 44 | Order Status window – field headers (First Name, Last Name, Address, Metro Station, Phone, Delivery Date, Rental Period, Color, Comment) – all headers standard gray, info black; "Delivery Date" and "Rental Period" outlined with black horizontal lines. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A28) |
| 45 | Order Status window – order status headers gray; active status black; error/delay status red; field content (order info) black. | PASSED | PASSED | – |
| 46 | Status 1: title "Scooter in warehouse", explanation "The courier will pick it up soon". | PASSED | PASSED | – |
| 47 | Status 2: title "The courier is on its way to you", explanation "Contact number: 0101". In case of delay, text changes to "The courier is delayed. We won't be able to deliver the scooter on time. To check the order status, call support: 0101." | PASSED | PASSED | – |
| 48 | Status 3: title "Courier on site", explanation "Pick up the scooter and pay for the rental". | PASSED | PASSED | – |
| 49 | Status 4: title "Okay, now it's time to ride.", explanation "Until the rental ends." | PASSED | PASSED | – |
| 50 | Order cancellation window – rectangular, white fill, black title "Do you want to cancel your order?" centered; buttons "Back" (white font, black fill) and "Cancel" (black font, black border, white fill). Text and buttons equally spaced. | PASSED | PASSED | – |
| 51 | Order cancellation confirmation window – rectangular, white fill, black title "Order canceled. Come back, we're always here for you :)" centered; "OK" button (white font, black fill), right‑aligned. | **FAILED** | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1z2GJ7hXzrcGRNNSyQbNAPgiRRBD5omDePHeSlxgYZK4/edit?gid=791488173#gid=791488173&range=A31) |

---

**Summary:** All tests passed except where noted with **FAILED**. See linked bug reports for details.