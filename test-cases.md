# Test Cases – SauceDemo

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
