# BUG-001: All catalog product cards render 404 fallback images for problem_user

- **Defect ID:** BUG-001
- **Linked Test Case:** TC-AUTH-006
- **Severity:** Major (Significant UI degradation across primary product catalog)
- **Priority:** P2 (High visibility functional failure)
- **Component:** Inventory Catalog UI / Asset Routing
- **Environment:** Chrome (Latest), Windows 11
- **Tested User Account:** `problem_user`

---

### Description
When logging in under the `problem_user` session, every product item in the inventory view fails to fetch its designated image asset. The application defaults to rendering a generic placeholder image (`sl-404.168b1cce.jpg`).

---

### Preconditions
1. User is on the login page: `https://www.saucedemo.com/`.

---

### Steps to Reproduce
1. In the **Username** field, enter: `problem_user`
2. In the **Password** field, enter: `secret_sauce`
3. Click the **Login** button.
4. Inspect the product cards on `/inventory.html`.
5. Open Chrome DevTools (`F12`) and view the **Console** tab.

---

### Expected Result
Each product card displays its distinct product photo matching the catalog inventory (e.g., backpack shows backpack image, bike light shows bike light image).

---

### Actual Result
All product cards render the exact same broken placeholder image. The DevTools console reports multiple HTTP 404 errors for the requested image paths:
`GET https://www.saucedemo.com/static/media/sauce-backpack-1200x1500.0a0b85a3.jpg 404 (Not Found)`

---

### Impact
Users cannot visually verify items prior to purchase, degrading user trust and interface usability.