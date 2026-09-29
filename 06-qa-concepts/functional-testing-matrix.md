# Functional Testing Types & Practical Application

This document maps core functional testing methodologies directly to practical workflows executed on the SauceDemo e-commerce platform.

---

## 1. Functional Testing Overview Matrix

| Testing Type | Primary Objective | Scope Level | When Executed in STLC | Practical SauceDemo Scenario |
| :--- | :--- | :--- | :--- | :--- |
| **Smoke Testing** | Verify basic system stability before accepting build | Broad / Shallow | Immediately after new build deployment | Check login, load catalog, and place dummy order to ensure critical path works. |
| **Sanity Testing** | Verify targeted bug fixes or minor code changes | Narrow / Deep | After bug fix deployment | Re-test only sorting dropdown behavior after developers submit a patch for BUG-002. |
| **Regression Testing** | Ensure new changes have not broken existing features | Complete Suite | Prior to major release milestone | Re-execute all 12 test cases across Auth, Inventory, Cart, and Checkout modules. |
| **Exploratory Testing** | Unscripted test execution based on tester intuition | Ad-hoc / Deep | Throughout active test execution | Input special characters, large strings, and manipulate browser history during checkout. |
| **Integration Testing** | Verify data accuracy across interconnected components | Sub-system interfaces | After unit validation | Verify that product price from inventory matches cart line item, tax calculation, and order total. |
| **UAT (User Acceptance)** | Validate software against end-user business requirements | End-to-end user journeys | Final pre-production validation phase | Evaluate ease of order cancellation, item retention in cart, and invoice transparency. |
| **Unit Testing** | Validate individual functions and isolated logic | Component / Function | During software implementation (Dev-owned) | Verify automated logic calculating sales tax percentage on cart items. |
| **Mocking** | Simulate third-party dependencies during testing | External service layer | When third-party APIs are unavailable | Simulating payment gateway responses (e.g., credit card approval/declined signals). |

---

## 2. Practical Test Scenarios

### Scenario A: Smoke Test Suite (Pass/Fail Gatekeeper)
- **Goal:** Determine if application is stable for detailed testing within 60 seconds.
- **Steps:**
  1. Navigate to `https://www.saucedemo.com/`.
  2. Authenticate as `standard_user` / `secret_sauce`.
  3. Add the first available item to cart.
  4. Complete checkout with valid mock data.
- **Criteria:** If order confirmation appears, build is accepted for testing. If any step fails, build is rejected immediately.

### Scenario B: Integration Testing (Data Consistency Audit)
- **Goal:** Confirm integrity of state and calculation between separate UI views.
- **Steps:**
  1. Add **Sauce Labs Backpack** (`$29.99`) and **Sauce Labs Bike Light** (`$9.99`) to cart.
  2. Navigate to `/cart.html` and verify item names and individual prices.
  3. Proceed to `/checkout-step-two.html` (Summary Overview).
- **Verification Formula:**
  - **Item Total:** `$29.99 + $9.99 = $39.98`
  - **Tax (8%):** `$3.20`
  - **Total:** `$43.18`
- **Criteria:** Calculated total rendered on screen must equal mathematical sum of parts.

### Scenario C: Exploratory Testing Log (Edge Case Discovery)
- **Observation:** Checkout input boundary evaluation on `/checkout-step-one.html`.
- **Actions Taken:**
  - Inputted emojis (`🔥🛒`) into First Name $\to$ System accepted without sanitization warning.
  - Inputted negative numerical strings (`-99999`) into Postal Code $\to$ System allowed order progression.
- **Recommendation:** Implement client-side regex format checking for postal code inputs.