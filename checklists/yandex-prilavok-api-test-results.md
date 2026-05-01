# Yandex.Prilavok API – Test Checklist and Results

## Main.Kits – Creating a SET (POST /api/v1/kits)

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T1 | Create a set with a name of up to 15 characters. | 201 Created, response matches doc, set created. | PASSED | – |
| T2 | Create a set with a name over 15 characters. | 400 Bad request, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A2) |

---

## Main.Kits – Adding products to a set (POST /api/v1/kits/id/products)

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T3 | Pass an existing set id. | 200 OK, response structure `{"ok": true}`, products added. | PASSED | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A3) |
| T4 | Pass an ID that meets the requirements but is not in the database. | 404 Not Found. | PASSED | – |
| T5 | Add products to an existing set that already contains same‑name items. | 200 OK, quantity increases. | PASSED | – |
| T6 | Pass an existing `productsList` array. | 200 OK, response `{"ok": true}`. | PASSED | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A3) |
| T7 | Pass a non‑existent `productsList` array. | 400 Bad request. | PASSED | – |
| T8 | Pass an empty array to `productsList`. | 400 Bad request. | PASSED | – |
| T9 | Pass an array with a missing parameter. | 400 Bad request. | PASSED | – |
| T10 | Pass `productsList` that is **not** an array. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A5) |
| T11 | Pass the missing key to `productsList`. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A6) |

### productsList – `id` field

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T12 | Pass an integer (7) as `id`. | 200 OK. | PASSED | – |
| T13 | Do not pass `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A7) |
| T14 | Pass a string (`"two"`) as `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A8) |
| T15 | Pass `0` as `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A9) |
| T16 | Pass a fractional value (1.5) as `id`. | 400, error message. | PASSED | – |
| T17 | Pass an empty string (`""`) as `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A9) |
| T18 | Pass a negative value (-7) as `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A9) |
| T19 | Pass a very large number (1354112) as `id`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A9) |
| T20 | Pass `id` as text without quotes. | 400 Bad request. | PASSED | – |

### productsList – `quantity` field

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T21 | Add 28 products (allowed quantity). | 200 OK, response `{"ok": true}`, products added. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A10) |
| T22 | Add 29 products. | 200 OK, products added. | **FAILED** | – |
| T23 | Add 30 products. | 200 OK, products added. | **FAILED** | – |
| T24 | Add 31 products (unacceptable). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A11) |
| T25 | Add 32 products. | 400 Bad request. | **FAILED** | – |
| T26 | Add 31 unique products. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A6) |
| T27 | Pass a string (`"two"`) as `quantity`. | 400, error message. | PASSED | – |
| T28 | Pass `0` as `quantity`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A12) |
| T29 | Pass a missing `quantity` parameter. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A1) |
| T30 | Pass a negative value (-7) as `quantity`. | 400, error message. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A1) |
| T31 | Pass a very large number (1354112) as `quantity`. | 400, error message. | PASSED | – |
| T32 | Pass request without one of the required fields. | 404 Bad request. | PASSED | – |
| T33 | Pass request without `quantity` field. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A13) |

---

## Couriers – Check delivery availability and costs (POST /fast-delivery/v3.1.1/calculate-delivery.xml)

### productsCount tests

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T34 | Weight 5.1, quantity 2 (within max). | 200 OK, delivery calculated. | PASSED | – |
| T35 | Weight 99, quantity 100 (exceed max). | 200 OK, delivery cost 99 rub. | PASSED | – |
| T36 | Pass invalid data format – string (`abc`). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14) |
| T37 | Pass special characters (`@!#`). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14) |
| T38 | Pass negative number (-2). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14) |
| T39 | Pass `0`. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14) |
| T40 | Pass a huge number (2147483648). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14) |
| T41 | Do not pass `productsCount` at all. | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A15) |
| T42 | Weight 1 kg, quantity 1, time 10. | 200 OK, delivery possible. | PASSED | – |
| T43 | Weight 1 kg, quantity 2, time 10. | 200 OK. | PASSED | – |
| T44 | Weight 1 kg, quantity 5, time 10. | 200 OK. | PASSED | – |
| T45 | Weight 1 kg, quantity 6, time 10. | 200 OK. | PASSED | – |
| T46 | Weight 1 kg, quantity 7, time 10. | 200 OK. | PASSED | – |
| T47 | Weight 1 kg, quantity 8, time 10. | 200 OK, but cost becomes 43 rub. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A16) |

### productsWeight tests

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T48 | Pass invalid data – string (`abc`). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A17) |
| T49 | Pass special characters (`@!#`). | 400 Bad request. | **FAILED** | – |
| T50 | Pass negative number (-2). | 400 Bad request. | **FAILED** | – |
| T51 | Pass `0`. | 400 Bad request. | **FAILED** | – |
| T52 | Pass huge number (2147483648). | 400 Bad request. | **FAILED** | – |
| T53 | Do not pass `productsWeight`. | 400 Bad request. | **FAILED** | – |
| T54 | Skip `productsWeight` parameter in request. | 400 Bad request. | PASSED | – |
| T55 | Quantity 1, weight 0.1, time 10. | 200 OK. | PASSED | – |
| T56 | Quantity 1, weight 1.0, time 10. | 200 OK. | PASSED | – |
| T57 | Quantity 1, weight 2.5, time 10. | 200 OK. | PASSED | – |
| T58 | Quantity 1, weight 2.6, time 10. | 500 Internal Server Error. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A18) |
| T59 | Quantity 1, weight 6.0, time 10. | 500 Internal Server Error. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A19) |

### deliveryTime tests

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T60 | Pass invalid string (`abc`). | 400 Bad request. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A20) |
| T61 | Pass special characters (`@!#`). | 400 Bad request. | **FAILED** | – |
| T62 | Pass negative number (-2). | 400 Bad request. | **FAILED** | – |
| T63 | Pass `0`. | 400 Bad request. | **FAILED** | – |
| T64 | Pass huge number (2147483648). | 400 Bad request. | **FAILED** | – |
| T65 | Do not pass `deliveryTime`. | 400 Bad request. | **FAILED** | – |
| T66 | Skip `deliveryTime` parameter in request. | 500 Internal Server Error. | PASSED | – |
| T67 | Quantity 1, weight 1, time 7. | 200 OK. | PASSED | – |
| T68 | Quantity 1, weight 1, time 10. | 200 OK. | PASSED | – |
| T69 | Quantity 1, weight 1, time 21. | 200 OK. | PASSED | – |
| T70 | Quantity 1, weight 1, time 6. | 500 Internal Server Error. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A21) |
| T71 | Quantity 1, weight 1, time 22. | 500 but `isItPossibleToDeliver="true"`. | PASSED | – |

---

## Main.Basket – Get list of products in cart (GET /api/v1/orders/id)

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T72 | Pass existing cart ID. | 200 OK, response with product list. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A7) |
| T73 | Pass non‑existent cart ID (100). | 400 error message. | PASSED | – |

---

## Main.Basket – Add products to cart (PUT /api/v1/orders/id)

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T74 | Pass existing cart ID. | 200 OK, products added. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A23) |
| T75 | Pass non‑existent cart ID. | 400 error. | PASSED | – |
| T76 | Pass invalid ID (string `"two"`). | 400 error. | PASSED | – |
| T77 | Pass negative ID (-7). | 400 error. | PASSED | – |
| T78 | Pass huge ID (1354112). | 400 error. | PASSED | – |
| T79 | Pass `0` as ID. | 400 error. | PASSED | – |
| T80 | Pass empty string `""` as ID. | 400 error. | PASSED | – |
| T81 | Request must contain `id` and `quantity`. | 200 OK, products added. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A8) |
| T82 | No quotes in cart ID data. | 400 Not found. | PASSED | – |
| T83 | Missing key for cart ID. | 400 Not found. | PASSED | – |

### Basket – quantity field

| ID | Test Description | Expected Result | Status |
|----|-----------------|-----------------|--------|
| T84 | Pass invalid data format (`*^%`). | 400 error. | PASSED |
| T86 | Pass negative value (-7). | 400 error. | PASSED |
| T87 | Pass huge number (1354112). | 400 error. | PASSED |
| T88 | Pass `0`. | 400 error. | PASSED |
| T89 | Pass empty string `""`. | 400 error. | PASSED |
| T90 | No `quantity` in the basket. | 400 error. | PASSED |

### Basket – productsList array

| ID | Test Description | Expected Result | Status |
|----|-----------------|-----------------|--------|
| T91 | Pass an empty array. | 400 error. | PASSED |
| T92 | Pass an empty string instead of array. | 400 error. | PASSED |
| T93 | Pass array with missing parameter. | 400 error. | PASSED |
| T94 | Pass array without `id`. | 400 error. | PASSED |
| T95 | Pass array with wrong data type in `id` (`% :,.`). | 400 error. | PASSED |
| T96 | Re‑add items already in cart. | 400 error. | PASSED |
| T97 | Add items to non‑existent cart. | 400 error. | PASSED |
| T98 | Add more items than in stock. | 400 error. | PASSED |

---

## Main.Basket – Delete cart (DELETE /api/v1/orders/:id)

| ID | Test Description | Expected Result | Status | Bug Report |
|----|-----------------|-----------------|--------|-------------|
| T99 | Delete existing cart ID. | 200 OK, response `{"ok": true}`, cart removed. | **FAILED** | [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A25) |
| T100 | Delete non‑existent cart ID (100). | 400 error message. | PASSED | – |