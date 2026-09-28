# Master Test Plan: SauceDemo Web Application

## 1. Objective & Scope
The objective is to validate the functional stability, form validation, session handling, and catalog features of the SauceDemo platform (`https://www.saucedemo.com/`).

### In-Scope
- User authentication and authorization states (Standard, Locked-out, Problem user).
- Inventory catalog display and sorting filters.
- Shopping cart actions (add, remove, counter validation).
- Checkout workflow inputs and form validations.

### Out-of-Scope
- Payment processor backend integration (simulated interface).
- Performance/Load stress testing.
- Automated API regression suites.

## 2. Test Environment
- **Target Application:** `https://www.saucedemo.com/`
- **Browsers:** Google Chrome, Mozilla Firefox
- **Operating System:** Windows 11
- **Inspection Tools:** Chrome DevTools (Console, Elements, Network)

## 3. Severity & Priority Standards
- **Critical (P1):** System crash, blocker bug preventing login or order completion.
- **Major (P2):** Core feature failure without workaround (e.g., broken images, non-functional sort filter).
- **Medium (P3):** Feature failure with an available workaround.
- **Low (P4):** Minor visual misalignment, typo, or cosmetic issue.

## 4. Entry & Exit Criteria
- **Entry Criteria:** AUT is accessible online; test data credentials provided.
- **Exit Criteria:** 100% of planned test cases executed; all discovered defects logged with reproduction steps; test summary sign-off completed.