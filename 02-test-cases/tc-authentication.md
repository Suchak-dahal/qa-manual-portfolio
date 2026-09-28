# Test Suite: User Authentication

- **Application Under Test (AUT):** https://www.saucedemo.com/
- **Module:** Login & Session Management


| Test Case ID | Test Scenario | Steps to Execute | Expected Result | Actual Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-AUTH-001** | Valid credentials login | 1. Open https://www.saucedemo.com/<br>2. Enter username `standard_user`<br>3. Enter password `secret_sauce`<br>4. Click Login | User is redirected to `/inventory.html`; product list is displayed. | Redirected to inventory page; products visible. | **PASS** |
| **TC-AUTH-002** | Login with locked-out account | 1. Open https://www.saucedemo.com/<br>2. Enter username `locked_out_user`<br>3. Enter password `secret_sauce`<br>4. Click Login | Error message appears: `Epic sadface: Sorry, this user has been locked out.` | Correct lockout error banner displayed. | **PASS** |
| **TC-AUTH-003** | Login with invalid password | 1. Open https://www.saucedemo.com/<br>2. Enter username `standard_user`<br>3. Enter password `wrong_password`<br>4. Click Login | Error message appears: `Epic sadface: Username and password do not match any user in this service` | Password mismatch error banner displayed. | **PASS** |
| **TC-AUTH-004** | Empty username submission | 1. Leave username field blank<br>2. Enter password `secret_sauce`<br>3. Click Login | Error message appears: `Epic sadface: Username is required` | Username required error displayed. | **PASS** |
| **TC-AUTH-005** | Empty password submission | 1. Enter username `standard_user`<br>2. Leave password field blank<br>3. Click Login | Error message appears: `Epic sadface: Password is required` | Password required error displayed. | **PASS** |


| **TC-AUTH-006** | Catalog asset rendering for problem_user session | 1. Enter username `problem_user`<br>2. Enter password `secret_sauce`<br>3. Click Login<br>4. Inspect product thumbnail images | Product cards display distinct, correct product graphics. | All products display placeholder error graphic (`sl-404.jpg`); console shows 404 asset errors. | **FAIL** |
| **TC-AUTH-007** | Inventory sort filter functionality | 1. Log in as `problem_user`<br>2. Click sort dropdown<br>3. Select 'Name (Z to A)' | Catalog items re-sort in descending alphabetical order. | Catalog order remains static; sort event listener fails. | **FAIL** |