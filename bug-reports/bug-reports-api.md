# Bug Reports – API Testing (Kits, Delivery, Orders)

**Common server address (unless overridden):** `https://{id}.serverhub.praktikum-services.ru`  
(actual ID varies per test; see individual environment notes).

---

## Kits & Products

| ID | Bug Name | Priority | Preconditions | Steps to Reproduce | Expected Result | Actual Result | Environment (server) |
|----|----------|----------|---------------|-------------------|-----------------|---------------|----------------------|
| T2 | POST `/api/v1/kits` – kit with name >15 chars is created (should return 400) | Medium | API docs open, request to add kit. | 1. Log in to Postman.<br>2. Request: `{"name": "Set for Sprint 5 Project", "cardId": 2}`. | 400 Bad request, kit not created. | 201 Created, kit created. | (common) |
| T3/T6 | POST `/api/v1/kits/id/products` – invalid response structure when adding products to existing kit | Low | API docs open, request to add products. | 1. Postman.<br>2. Request body with `productsList`. | 200 OK with product list. | 200 OK with `{"ok": true, "_time_spent": ...}` (no product list). | (common) |
| T7 | POST `/api/v1/kits/id/products` – non‑existent kit returns wrong code | Critical | Same as above. | Request with non‑existent product IDs (e.g., id=329). | 400 Bad request. | 404 Not Found. | `https://278c9002-56b5-4b9d-a2b1-53cf6d3bb877.serverhub.praktikum-services.ru` |
| T10 | `productsList` not an array → 500 instead of 400 | Critical | Same as above. | `productsList: "no-no-no"`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T11 | Missing `productsList` → 500 instead of 400 | Critical | Same as above. | Send empty JSON `{}`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T13 | Product missing `id` → 500 instead of 400 | Critical | Same as above. | `{ "productsList": [ { "quantity": 2 } ] }`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T14 | String instead of number in `id` → 500 instead of 400 | Critical | Same as above. | `"id": "two"`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T15,T17,T18,T19 | Invalid `id` values (0, "", -7, huge number) → 200 instead of error | Critical | Same as above. | Send request with `id`=0 / "" / -7 / 1354112. | Error message (4xx). | 200 OK, ID accepted. | (common) |
| T21‑T23 | Products in allowed quantity (28/29/30) → 200 but products not added | Critical | Same as above. | Send 28/29/30 products. | Products added. | 200 OK, but products not actually added. | (common) |
| T24‑T25 | 31 products → 405 Method Not Allowed (should be 400) | Medium | Same as above. | Send 31 products. | 400 Bad request. | 405 Method Not Allowed. | (common) |
| T28‑T30 | Invalid `quantity` values (0, "", -7) → 500 instead of 400 | Critical | Same as above. | `quantity` = 0 / "" / -7. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T33 | Missing `quantity` → 500 instead of 400 | Critical | Same as above. | `{ "productsList": [ { "id": 1 } ] }`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |

---

## Delivery Calculation (`/fast-delivery/v3.1.1/calculate-delivery.xml`)

| ID | Bug Name | Priority | Steps to Reproduce | Expected Result | Actual Result | Environment |
|----|----------|----------|-------------------|-----------------|---------------|--------------|
| T36‑T40 | Invalid values in `productsCount`, `productsWeight`, `deliveryTime` → 200 (should error) | Critical | POST with invalid data in those fields. | Delivery not calculated (4xx). | 200 OK, delivery calculated. | same as T7 |
| T41 | Missing `productsCount` → 500 instead of 400 | Critical | POST without `productsCount`. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T47 | Quantity = 8 → 200 (should be invalid) | Critical | POST with `productsCount=8`. | Delivery not calculated. | 200 OK, delivery calculated. | same as T7 |
| T48‑T53 | Invalid `productsWeight` (abc, @#, -2, 0, 2147483648, empty) → 500 instead of 400 | Medium | Test each invalid weight. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T58 | Weight = 2.6 → 200 (should error) | Critical | POST with weight=2.6. | Delivery not calculated. | 200 OK, delivery calculated. | same as T7 |
| T59 | Weight = 6.0 → 200 (should error) | Critical | POST with weight=6.0. | Delivery not calculated. | 200 OK, delivery calculated. | same as T7 |
| T60‑T65 | Invalid `deliveryTime` values (abc, @#, -2, 0, 2147483648, empty) → 500 instead of 400 | Medium | Test each invalid deliveryTime. | 400 Bad request. | 500 Internal Server Error. | same as T7 |
| T70 | Invalid time value (6) → 200 (should error) | Critical | POST with `deliveryTime=6`. | Delivery not calculated. | 200 OK, delivery calculated. | same as T7 |

---

## Orders & Cart

| ID | Bug Name | Priority | Steps to Reproduce | Expected Result | Actual Result | Environment |
|----|----------|----------|-------------------|-----------------|---------------|--------------|
| T72 | GET `/api/v1/orders/id` – wrong response for cart ID | Medium | Request with cart ID. | Show products in cart. | 400 error, HTML page "Cannot GET ...". | (common) |
| T74 | Existing cart ID → 400 Not Found (should return cart) | Critical | Request with existing cart ID (e.g., id=7). | Show products in cart. | 400 error, HTML page. | `https://8f8ef389-ef21-4c3f-b931-fa29daf411d8.serverhub.praktikum-services.ru` |
| T97 | PUT `/api/v1/orders/id` – products cannot be added | Critical | Request to add products to cart. | Products added. | 400 error, HTML "Cannot PUT ...". | (common) |
| T99 | DELETE `/api/v1/orders/:id` – cannot delete existing cart | Critical | DELETE request with existing cart ID. | Cart deleted. | 404 Not Found, `{"code":404,"message":"Cart with id=NaN not found"}`. | (common) |

---

## Summary by Priority

| Priority | Count |
|----------|-------|
| Critical | 18 |
| Medium | 4 |
| Low | 1 |

*All bugs are in **Open** status (not fixed).*