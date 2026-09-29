# SauceDemo E-Commerce Manual QA Portfolio

![QA Status](https://img.shields.io/badge/Status-Complete-success)
![STLC Phases](https://img.shields.io/badge/STLC-End--to--End-blue)
![Bugs Logged](https://img.shields.io/badge/Defects-3%20Reported-critical)
![Pass Rate](https://img.shields.io/badge/Pass%20Rate-75%25-yellow)

A comprehensive manual quality assurance test suite and defect audit for the [SauceDemo](https://www.saucedemo.com/) web platform, executed under standard Software Testing Life Cycle (STLC) procedures.

---

## Executive Summary

- **Application Under Test:** SauceDemo Web App
- **Scope Tested:** Authentication, Session Handling, Catalog Sorting, Image Asset Rendering, Shopping Cart, and Checkout Flow.
- **Total Test Cases Executed:** 12
- **Pass Rate:** 75% (9 Passed, 3 Failed)
- **Defects Identified:** 3 (1 Blocker, 2 Major)
- **Deployment Decision:** **REJECTED (NO-GO)** due to critical path failure on checkout completion.

---

## Repository Structure

| Directory | Deliverable | Description |
| :--- | :--- | :--- |
| [`01-test-plan/`](01-test-plan/test-plan.md) | **Test Plan** | Defines scope, testing types, environments, severity rubric, and entry/exit criteria. |
| [`02-test-cases/`](02-test-cases/) | **Test Suites** | Executed test cases for Auth (`tc-authentication.md`) and Cart/Checkout (`tc-cart-checkout.md`). |
| [`03-bug-reports/`](03-bug-reports/) | **Defect Reports** | Actionable bug reports with preconditions, reproduction steps, console logs, and visual evidence. |
| [`04-rtm/`](04-rtm/rtm.md) | **Traceability Matrix** | Bi-directional mapping between business requirements, test cases, and logged defects. |
| [`05-test-summary/`](05-test-summary/test-summary.md) | **Summary & Sign-Off** | Quantitative test execution metrics and release deployment verdict. |

---

## Logged Defects Summary

| Defect ID | Summary | Severity | Priority | Linked Case | Visual Evidence |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[BUG-001](03-bug-reports/BUG-001-broken-catalog-images.md)** | Product catalog thumbnail assets fail with 404 errors | Major | P2 | TC-AUTH-006 | [Screenshot](03-bug-reports/assets/bug-001-broken-images.png) |
| **[BUG-002](03-bug-reports/BUG-002-inventory-sort-unresponsive.md)** | Inventory sort filter fails to re-order products | Major | P2 | TC-AUTH-007 | Documented |
| **[BUG-003](03-bug-reports/BUG-003-checkout-lastname-blocked.md)** | Checkout form progression blocked by Last Name input validation | Blocker | P1 | TC-CHECKOUT-003 | Documented |

---

## Test Environment & Tools
- **Platform:** Google Chrome (Latest), Mozilla Firefox
- **OS:** Windows 11
- **Developer Tools:** Chrome DevTools (Console, Elements, Network)
- **Documentation & Tracking:** VS Code, Git, GitHub Markdown