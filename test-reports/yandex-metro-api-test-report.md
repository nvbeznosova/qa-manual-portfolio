# Yandex Metro API Test Report (v 3.6)

## Test Environment and Scope

- **API testing tool:** Postman  
- **Testbed:** `https://{id}.serverhub.praktikum-services.ru/`  
- **API documentation:** `https://{id}.serverhub.praktikum-services.ru/docs/`  

### New functionality tested

1. **Working with kits** – adding products to a kit  
   – `POST /api/v1/kits/{id}/products`

2. **Working with couriers** – delivery availability and cost via "Privezhem Bystro" courier service  
   – `POST /fast-delivery/v3.1.1/calculate-delivery.xml`

3. **Working with shopping cart**  
   – `GET /api/v1/orders/id` – get list of products in cart  
   – `PUT /api/v1/orders/:id` – add products to cart  
   – `DELETE /api/v1/orders/:id` – delete cart

## Test Documentation

- **Checklist for new functionality:** [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=1132915931#gid=1132915931)
- **Full test results (bug reports):** [Link](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876)

## Test Execution Summary

- **Total tests:** 100  
- **Passed:** 68  
- **Failed:** 32  

---

## Bugs by Priority

### Blocking
- None

### Critical
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A4)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A5)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A6)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A7)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A8)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A9)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A10)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A12)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A13)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A14)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A15)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A16)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A18)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A19)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A21)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A23)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A24)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A25)

### Medium Priority
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A2)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A11)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A17)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A20)
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A22)

### Low Priority
- [Bug report](https://docs.google.com/spreadsheets/d/1t9o1UgrM871EVMJllytvVNSVd5yF8MA9R8P42kk-q1s/edit?gid=496274876#gid=496274876&range=A3)

### Minor
- None

## Recommendation

> **No blocking bugs were found, but there are many critical bugs that significantly impact the app's performance. The testing team does NOT recommend releasing the version until critical issues are fixed.**

## Additional Information

1. **Test documentation creation:** 1 day  
2. **Testing execution:** 2 days  
3. **Bugs found (as stated in source):** one blocking bug and two critical ones (note: this contradicts the "Blocking: None" statement above – likely an error in the original text).  
4. **Testing types performed:** functional  
5. **Areas to watch after fixes:**  
   - Limitations on parameters passed with the set ID  
   - All commands related to cart: requesting products, adding products, deleting cart  
   (These are not blocking but significantly affect user experience)  

## Final Recommendation

1. Fix **critical bugs** first – after that, the version may be submitted for release.  
2. Fix remaining medium/low priority bugs in the background and release them in subsequent updates.