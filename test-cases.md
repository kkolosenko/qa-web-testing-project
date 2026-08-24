# Test Cases – SauceDemo

## Test Environment

- **Test User:** `standard_user`
- **Password:** `secret_sauce`
- **Browser:** Google Chrome
- **Platform:** Desktop

> Unless otherwise specified, all test cases are executed using `standard_user`.

## Login Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-001 | Login with valid credentials | User is on the Login page | 1. Enter `standard_user` <br> 2. Enter `secret_sauce` <br> 3. Click **Login** | User should successfully log in and be redirected to the Products page | User successfully logged in and Products page was displayed | PASS |
| TC-002 | Login with invalid password | User is on the Login page | 1. Enter `standard_user` <br> 2. Enter invalid password <br> 3. Click **Login** | Login should be denied and an error message should be displayed | Login denied and error message displayed | PASS |
| TC-003 | Login with invalid username | User is on the Login page | 1. Enter invalid username <br> 2. Enter `secret_sauce` <br> 3. Click **Login** | Login should be denied and an error message should be displayed | Login denied and error message displayed | PASS |
| TC-004 | Login with empty fields | User is on the Login page | 1. Leave Username empty <br> 2. Leave Password empty <br> 3. Click **Login** | Login should be denied and a required-field error should be displayed | Login denied and required-field error displayed | PASS |
| TC-005 | Login with empty password | User is on the Login page | 1. Enter `standard_user` <br> 2. Leave Password empty <br> 3. Click **Login** | Login should be denied and a password-required error should be displayed | Login denied and password-required error displayed | PASS |
| TC-006 | Login with empty username | User is on the Login page | 1. Leave Username empty <br> 2. Enter `secret_sauce` <br> 3. Click **Login** | Login should be denied and a username-required error should be displayed | Login denied and username-required error displayed | PASS |
| TC-007 | Login with locked-out account | User is on the Login page | 1. Enter `locked_out_user` <br> 2. Enter `secret_sauce` <br> 3. Click **Login** | Login behavior should follow the account status defined in requirements | Login denied and locked-out message displayed | Requires clarification |

## Products Page Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-008 | Verify Products page with standard user | User is on the Login page | 1. Login as `standard_user` <br> 2. Review product images, names, descriptions and prices <br> 3. Review UI elements | Correct product information and UI should be displayed | Products page displayed correctly | PASS |
| TC-009 | Verify Products page with problem user | User is on the Login page | 1. Login as `problem_user` <br> 2. Open Products page <br> 3. Review product images | Each product should display the correct product image | Some products display dog images instead of the correct product images | FAIL |
| TC-010 | Verify product details with error user | User is logged in as `error_user` | 1. Open Products page <br> 2. Click on a product <br> 3. Review name, image, description and price | Complete and correct product information should be displayed | Product description is missing when opening some products | FAIL |
| TC-011 | Verify Products page UI with visual user | User is on the Login page | 1. Login as `visual_user` <br> 2. Review product images <br> 3. Review positions of UI elements <br> 4. Navigate through the page | Correct images should be displayed and UI elements should remain properly positioned | Incorrect product image displayed and some UI elements are misplaced or unstable | FAIL |

## Performance Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-012 | Verify page loading performance | User is on the Login page | 1. Login as `performance_glitch_user` <br> 2. Open Products page <br> 3. Open different products <br> 4. Navigate between pages <br> 5. Observe loading behavior | Pages should load consistently within an acceptable response time | Pages load noticeably slower and inconsistently | FAIL |

## Shopping Cart Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-013 | Add one product to the cart | User is logged in and is on the Products page | 1. Choose a product <br> 2. Click **Add to cart** <br> 3. Open the cart | Selected product should be displayed in the cart | Selected product is displayed in the cart | PASS |
| TC-014 | Remove a product from the Products page | User is logged in and a product has been added to the cart | 1. Add a product to the cart <br> 2. Verify the **Add to cart** button changes to **Remove** <br> 3. Click **Remove** | Product should be removed from the cart and the button should change back to **Add to cart** | Product is removed form the cart and button changes to **Add to cart** | PASS |
| TC-015 | Verify cart badge after adding one product | User is logged in and the cart is empty | 1. Add one product to the cart <br> 2. Observe the cart badge | Cart badge should display `1` | Cart badge displays `1` | PASS |
| TC-016 | Add multiple different products to the cart | User is logged in and the cart is empty | 1. Add three different products to the cart <br> 2. Open the cart | All three selected products should be displayed in the cart | All selected products are displayed in the cart  | PASS |
| TC-017 | Verify cart badge after adding multiple products | User is logged in and the cart is empty | 1. Add three different products to the cart <br> 2. Observe the cart badge | Cart badge should display `3` | `3` is displayed on the cart badge | PASS |
| TC-018 | Verify added products are displayed in the cart | User is logged in and multiple products have been added to the cart | 1. Open the cart <br> 2. Review the products in the cart | All products previously added should be displayed in the cart | All added product are displayed in the cart | PASS |
| TC-019 | Remove one product from the cart | User is logged in and at least one product is in the cart | 1. Open the cart <br> 2. Choose a product <br> 3. Click **Remove** | Selected product should be removed from the cart | The product is removed from the cart | PASS |
| TC-020 | Verify removing one product does not remove other products | User is logged in and multiple products are in the cart | 1. Open the cart <br> 2. Remove one product <br> 3. Review the remaining products | Only the selected product should be removed; other products should remain in the cart | Selected product removed, other remain in the cart | PASS |
| TC-021 | Verify product names and prices match between Products page and Cart | User is logged in and is on the Products page | 1. Note the name and price of a product <br> 2. Add the product to the cart <br> 3. Open the cart <br> 4. Compare the product name and price | Product name and price in the cart should match the information displayed on the Products page | Product name and price match | PASS |
| TC-022 | Continue shopping from the Cart page | User is logged in and is on the Cart page | 1. Click **Continue Shopping** | User should be redirected to the Products page | Redirected to the Product page | PASS |
| TC-023 | Proceed to Checkout with products in the cart | User is logged in and at least one product is in the cart | 1. Open the cart <br> 2. Click **Checkout** | User should be redirected to the Checkout information page | Redirected to Checout | PASS |
| TC-024 | Attempt to proceed to Checkout with an empty cart | User is logged in and the cart is empty | 1. Open the empty cart <br> 2. Click **Checkout** | Expected behavior is not specified in the requirements and requires clarification | Redirected to Checkout with empty cart | FAIL |

## Sorting Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-025 | Sort products by Name (A to Z) | User is logged in and is on the Products page | 1. Open the sorting dropdown <br> 2. Select **Name (A to Z)** <br> 3. Review the product order | Products should be displayed in alphabetical order from A to Z | Products are displayed in A-Z order | PASS |
| TC-026 | Sort products by Name (Z to A) | User is logged in and is on the Products page | 1. Open the sorting dropdown <br> 2. Select **Name (Z to A)** <br> 3. Review the product order | Products should be displayed in reverse alphabetical order from Z to A | Products are displayed in Z-A order | PASS |
| TC-027 | Sort products by Price (low to high) | User is logged in and is on the Products page | 1. Open the sorting dropdown <br> 2. Select **Price (low to high)** <br> 3. Review product prices | Products should be ordered from the lowest price to the highest price | Products are ordered from the lowest price to the highest price | PASS |
| TC-028 | Sort products by Price (high to low) | User is logged in and is on the Products page | 1. Open the sorting dropdown <br> 2. Select **Price (high to low)** <br> 3. Review product prices | Products should be ordered from the highest price to the lowest price | Products are ordered from the highest price to the lowest price | PASS |
| TC-029 | Verify sorting changes the product order correctly | User is logged in and is on the Products page | 1. Note the original product order <br> 2. Select a different sorting option <br> 3. Compare the new product order | Product order should change according to the selected sorting option | Product order changes according to the selected sorting option | PASS |
| TC-030 | Verify product information remains correct after sorting | User is logged in and is on the Products page | 1. Note product names, images and prices <br> 2. Apply a sorting option <br> 3. Review the same products after sorting | Product names, images and prices should remain associated with the correct products | Product names, images and prices remain associated with the correct products | PASS |

## Checkout Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-031 | Checkout with valid customer information | User is on the Checkout information page with at least one product in the cart | 1. Enter a valid First Name <br> 2. Enter a valid Last Name <br> 3. Enter a valid Postal Code <br> 4. Click **Continue** | User should be redirected to the Checkout Overview page | Redirected to Checkout Page | PASS |
| TC-032 | Checkout with empty First Name | User is on the Checkout information page | 1. Leave First Name empty <br> 2. Enter valid Last Name <br> 3. Enter valid Postal Code <br> 4. Click **Continue** | User should remain on the page and a First Name required error should be displayed | Error displayed, user didn't go further | PASS |
| TC-033 | Checkout with empty Last Name | User is on the Checkout information page | 1. Enter valid First Name <br> 2. Leave Last Name empty <br> 3. Enter valid Postal Code <br> 4. Click **Continue** | User should remain on the page and a Last Name required error should be displayed | Error displayed, user didn't go further | PASS |
| TC-034 | Checkout with empty Postal Code | User is on the Checkout information page | 1. Enter valid First Name <br> 2. Enter valid Last Name <br> 3. Leave Postal Code empty <br> 4. Click **Continue** | User should remain on the page and a Postal Code required error should be displayed | Error displayed, user didn't go further | PASS |
| TC-035 | Checkout with all information fields empty | User is on the Checkout information page | 1. Leave all fields empty <br> 2. Click **Continue** | Checkout should not continue and a required-field error should be displayed | Error displayed, user didn't go further | PASS |
| TC-036 | Verify correct products on Checkout Overview | User is on the Checkout Overview page | 1. Review products <br> 2. Compare them with products previously added to the cart | Checkout Overview should display the same products that were added to the cart | Checkout Overview displays the same product that were added | PASS |
| TC-037 | Verify product prices on Checkout Overview | User is on the Checkout Overview page | 1. Review product prices <br> 2. Compare them with the prices displayed on the Products page | Product prices should remain correct and unchanged | Product prices correct | PASS |
| TC-038 | Verify Item Total calculation | User is on the Checkout Overview page with multiple products | 1. Add the displayed product prices <br> 2. Compare the result with **Item total** | Item total should equal the sum of all product prices before tax | Item total is right | PASS |
| TC-039 | Verify Tax is displayed | User is on the Checkout Overview page | 1. Locate the Tax value | A Tax amount should be displayed | A tax amount is displayed | PASS |
| TC-040 | Verify final Total calculation | User is on the Checkout Overview page | 1. Note Item total <br> 2. Note Tax <br> 3. Add Item total and Tax <br> 4. Compare the result with Total | Total should equal Item total plus Tax | Total shows the right amount | PASS |
| TC-041 | Cancel Checkout from customer information page | User is on the Checkout information page | 1. Click **Cancel** | User should return to the Cart page |  |  |
| TC-042 | Cancel Checkout from Checkout Overview page | User is on the Checkout Overview page | 1. Click **Cancel** | User should return to the Products page |  |  |
| TC-043 | Complete an order | User is on the Checkout Overview page with valid order information | 1. Click **Finish** | Order should be completed successfully |  |  |
| TC-044 | Verify order confirmation | User has completed an order | 1. Review the confirmation page | Successful order confirmation should be displayed |  |  |
| TC-045 | Return to Products page after completing an order | User is on the order confirmation page | 1. Click **Back Home** | User should be redirected to the Products page |  |  |

## Logout Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-046 | Open navigation menu after login | User is logged in | 1. Click the menu icon | Navigation menu should open and available options should be displayed |  |  |
| TC-047 | Logout from the application | User is logged in and navigation menu is open | 1. Click **Logout** | User should be logged out |  |  |
| TC-048 | Verify redirect after logout | User has logged out | 1. Observe the page after logout | User should be redirected to the Login page |  |  |
| TC-049 | Verify protected page cannot be accessed after logout | User has logged out | 1. Click the browser **Back** button or try to access the Products page directly | User should not be able to access protected pages without logging in again |  |  |

## Additional UI and Content Testing

| ID | Test Case | Preconditions | Steps | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-050 | Verify product names and descriptions | User is logged in as `standard_user` and is on the Products page | 1. Review all product names <br> 2. Review all product descriptions <br> 3. Check for unexpected words, codes or formatting issues | Product names and descriptions should contain clear, correct and relevant content without unexpected text or codes |  |  |
| TC-051 | Verify product images on Products page | User is logged in as `standard_user` and is on the Products page | 1. Review all product images <br> 2. Verify each image corresponds to the correct product | Each product should display the correct image |  |  |
| TC-052 | Verify cart item presentation | User is logged in and at least one product is in the cart | 1. Open the Cart page <br> 2. Review product name, description, price, quantity and visual presentation | Cart items should display complete and consistent product information according to the design requirements |  |  |
| TC-053 | Verify general UI layout on Products page | User is logged in as `standard_user` | 1. Review header, menu, cart icon, sorting control, product cards and buttons <br> 2. Resize or navigate through the page <br> 3. Check alignment and overlapping elements | UI elements should be correctly aligned, readable and stable without overlapping or misplaced elements |  |  |
| TC-054 | Verify browser console for frontend errors | User is logged in and browser DevTools Console is open | 1. Navigate through Products page <br> 2. Open the Cart page <br> 3. Open product details <br> 4. Observe Console messages | No unexpected frontend errors related to normal user actions should appear in the Console |  |  |
| TC-055 | Enter unrealistic customer information during Checkout | User is on the Checkout information page | 1. Enter unrealistic values in First Name, Last Name and Postal Code <br> 2. Click **Continue** | Expected validation behavior requires clarification from requirements |  |  |
