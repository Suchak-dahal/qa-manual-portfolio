# BUG-002: Product sorting dropdown does not re-order items for problem_user session

- **Defect ID:** BUG-002
- **Linked Test Case:** TC-AUTH-007
- **Severity:** Major (Loss of key catalog filtering functionality)
- **Priority:** P2 (High visibility functional failure)
- **Component:** Inventory Filter / Sorting Component
- **Environment:** Chrome (Latest), Windows 11
- **Tested User Account:** `problem_user`

---

### Description
When logged in under the `problem_user` account, selecting any alternate sorting option (such as "Name (Z to A)", "Price (low to high)", or "Price (high to low)") fails to re-order the displayed products. The catalog list remains locked in the default "Name (A to Z)" sequence.

---

### Preconditions
1. User is authenticated on `https://www.saucedemo.com/` as `problem_user`.
2. User is on the catalog page (`/inventory.html`).

---

### Steps to Reproduce
1. Navigate to the top-right corner of the product catalog.
2. Click on the product sort container (currently displaying `Name (A to Z)`).
3. Select `Name (Z to A)` from the dropdown options.
4. Observe the order of products in the inventory grid.

---

### Expected Result
The catalog refreshes and re-orders items in descending alphabetical order, beginning with "Test.allTheThings() T-Shirt (Red)" and ending with "Sauce Labs Backpack".

---

### Actual Result
The product grid does not change order. The items remain listed in their default ascending order (`Sauce Labs Backpack` remains first).

---

### Impact
Users cannot sort or filter products by price or name, creating friction in catalog navigation and item selection.