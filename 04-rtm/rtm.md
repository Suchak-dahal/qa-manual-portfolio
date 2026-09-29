# Requirements Traceability Matrix (RTM)

- **Application Under Test:** SauceDemo Platform
- **Scope:** Authentication, Catalog, Cart & Checkout Sprint 1

| Requirement ID | Requirement Description | Test Case ID | Test Status | Defect ID | Defect Severity |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **REQ-AUTH-001** | Authenticate valid users and redirect to catalog | TC-AUTH-001 | PASS | None | N/A |
| **REQ-AUTH-002** | Prevent login for locked-out accounts with clear feedback | TC-AUTH-002 | PASS | None | N/A |
| **REQ-AUTH-003** | Reject unauthorized credentials with mismatch notification | TC-AUTH-003 | PASS | None | N/A |
| **REQ-AUTH-004** | Enforce required fields on username and password inputs | TC-AUTH-004<br>TC-AUTH-005 | PASS | None | N/A |
| **REQ-CAT-001** | Render distinct, valid imagery for all catalog items | TC-AUTH-006 | FAIL | BUG-001 | Major (P2) |
| **REQ-CAT-002** | Re-order catalog items dynamically based on sort selection | TC-AUTH-007 | FAIL | BUG-002 | Major (P2) |
| **REQ-CART-001** | Increment cart badge counter on item addition | TC-CART-001 | PASS | None | N/A |
| **REQ-CART-002** | Decrement counter and remove item from cart view | TC-CART-002 | PASS | None | N/A |
| **REQ-CHK-001** | Support end-to-end checkout completion for valid input | TC-CHECKOUT-001 | PASS | None | N/A |
| **REQ-CHK-002** | Enforce client-side validation on empty checkout inputs | TC-CHECKOUT-002 | PASS | None | N/A |
| **REQ-CHK-003** | Accept valid text input for Last Name during checkout | TC-CHECKOUT-003 | FAIL | BUG-003 | Blocker (P1) |