# Requirements Traceability Matrix (RTM)

- **Application Under Test:** SauceDemo Platform
- **Scope:** Authentication & Catalog Sprint 1

| Requirement ID | Requirement Description | Test Case ID | Test Status | Defect ID | Defect Severity |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **REQ-AUTH-001** | System must authenticate valid users and redirect to catalog | TC-AUTH-001 | PASS | None | N/A |
| **REQ-AUTH-002** | System must prevent login for locked-out accounts with clear feedback | TC-AUTH-002 | PASS | None | N/A |
| **REQ-AUTH-003** | System must reject unauthorized passwords with mismatch notification | TC-AUTH-003 | PASS | None | N/A |
| **REQ-AUTH-004** | System must enforce required fields on username and password inputs | TC-AUTH-004<br>TC-AUTH-005 | PASS | None | N/A |
| **REQ-CAT-001** | System must render distinct, valid imagery for all catalog items | TC-AUTH-006 | FAIL | BUG-001 | Major (P2) |
| **REQ-CAT-002** | System must re-order catalog items dynamically based on sort selection | TC-AUTH-007 | FAIL | BUG-002 | Major (P2) |


