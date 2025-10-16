
# 🧍‍♂️ Test Cases – Sign-up (UI)
**Scenario:** TS_001 – Sign-up Validation  
**Prepared by:** Pedro Henrique Li (QA — Manual)  
**Language:** English (US)  
**Format:** Collapsible sections with QA icons  

---

<details id="tc_su_001">
<summary><b>TC_SU_001 – Validate successful registration with  all mandatory fields and required consents</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:** happy path
validates full field completion, consent acceptance, and successful backend registration flow.

**Pre-requisites:**  
1. Open the OBP Sandbox web application
in any supported browser (Edge/Chrome).  
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up  

**Test Steps:**  
1. Open the Sign-up page.
2. Enter all mandatory user details:
- First Name
- Last Name
- Email
- Username
- Password
- Repeat Password
3. Check Terms and Conditions and Privacy Policy checkboxes.
4. Click the Sign Up button.

**Test Data:**  
Valid User Data:
- First Name: John
- Last Name: Li
- Email: john.li@testmail.com
- Username: johnli
- Password: Abcd1234!
- Repeat Password: Abcd1234!

 **Expected Result:**  
ER-1: Registration form is submitted successfully
with no validation or error messages displayed.  
ER-2: User is automatically logged in or redirected to a confirmation page.  
ER-3: A success message confirming account creation is displayed on screen.  
ER-4: A confirmation email is sent to the registered address 
containing login details or verification link.  

</details>

---

<details id="tc_su_002">
<summary><b>TC_SU_002 – Validate submission with all fields empty</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:** Negative test validating mandatory field and consent enforcement. 
Ensures proper client-side and/or backend validation triggers before submission.

 **Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

  **Test Steps:**
1. Open the Sign-up page.
2. Leave all input fields 
(First Name, Last Name, Email, Username, Password, Repeat Password) completely blank.
3. Leave both Terms and Conditions and Privacy Policy checkboxes unchecked.
4. Click the Sign Up button.

 **Test Data:**  
All fields left empty:
- First Name: (blank)
- Last Name: (blank)
- Email: (blank)
- Username: (blank)
- Password: (blank)
- Repeat Password: (blank)
- Terms & Privacy: (unchecked)  

 **Expected Result:**  
ER-1: The system prevents form submission.  
ER-2: Inline or page-level validation error messages
are displayed for each mandatory field:  
- “First Name is required.”
- “Last Name is required.”
- “Email is required.”
- “Username is required.”
- “Password is required.”
- “Repeat Password is required.”  

ER-3: Error message at the top or near consent area: 
“You must accept the Terms and Privacy Policy before registering.”  
ER-4: No account is created in the system; user remains on the same page.

</details>

---

<details id="tc_su_003">
<summary><b>TC_SU_003 – Validate registration submission  when Terms consent is not checked</b></summary>

**Test Scenario:**
(TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:**
Negative test validates backend and frontend enforcement 
of Terms consent acceptance.  

 **Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

  **Test Steps:**
1. Open the Sign-up page.
2. Fill all mandatory fields with valid data:  
- First Name
- Last Name
- Email
- Username
- Password
- Repeat Password
3. Leave the Terms and Conditions checkbox unchecked.
4. Check the Privacy Policy checkbox.
5. Click the Sign Up button.

 **Test Data:**  
Valid Data:
- First Name: John
- Last Name: Li
- Email: john.li@testmail.com
- Username: johnli
- Password: Abcd1234!
- Repeat Password: Abcd1234!
- Terms: Unchecked
- Privacy: Checked

 **Expected Result:**  
ER-1: The registration form does not submit successfully.  
ER-2: A validation error message is displayed:
“You must accept the Terms and Conditions before registering.”  
ER-3: No account is created; 
user remains on the same page with form data retained.

</details>

---

<details id="tc_su_004">
<summary><b>TC_SU_004 – Validate registration submission  when Privacy Policy consent is not checked</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:**
Negative test verifying privacy consent enforcement per legal and UX requirements.  

**Pre-requisites:**  
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up  

**Test Steps:**
1. Open the Sign-up page.
2. Fill all mandatory fields with valid data.
3. Check the Terms and Conditions checkbox.
4. Leave the Privacy Policy checkbox unchecked.
5. Click the Sign Up button.

**Test Data:**  
Valid Data:
- First Name: John
- Last Name: Li
- Email: john.li@testmail.com
- Username: johnli
- Password: Abcd1234!
- Repeat Password: Abcd1234!
- Terms: Checked
- Privacy: Unchecked

**Expected Result:**  
ER-1: Form submission is blocked.  
ER-2: Validation error displayed near consent checkbox: 
“You must accept the Privacy Policy before registering.”  
ER-3: Form data remains visible after validation failure.  

</details>

---

<details id="tc_su_005">
<summary><b>TC_SU_005 – Validate registration submission  with both consents unchecked</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:**
Negative test combining both consent validations. 
Confirms dual-check enforcement before account creation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Open the Sign-up page.
2. Fill all mandatory fields with valid data.
3. Leave both Terms and Conditions and Privacy Policy checkboxes unchecked.
4. Click the Sign Up button.

**Test Data:**  
Valid Data:
- First Name: John
- Last Name: Li
- Email: john.li@testmail.com
- Username: johnli
- Password: Abcd1234!
- Repeat Password: Abcd1234!
- Terms: Unchecked
- Privacy: Unchecked

**Expected Result:**  
ER-1: Registration blocked; form does not submit.  
ER-2: Validation errors displayed for both consents:
- “You must accept the Terms and Conditions.”
- “You must accept the Privacy Policy.”  

ER-3: User remains on same page; no account created.

</details>

---

<details id="tc_su_006">
<summary><b>TC_SU_006 – Validate registration with invalid email formats</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:**
Negative validation test ensuring proper frontend and backend email format checks.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Open the Sign-up page.
2. Fill all fields with valid data except Email.
3. Enter invalid email formats (see Test Data).
4. Check both Terms and Privacy Policy checkboxes.
5. Click Sign Up.

**Test Data:**
Invalid email samples:
- user@
- user.com
- user@domain

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Field-level validation message displayed near Email field:
- “Please enter a valid email address.”  

ER-3: Other field data remains intact.

</details>

---

<details id="tc_su_007">
<summary><b>TC_SU_007 – Validate registration with mismatched  Password and Repeat Password fields</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔴 P0  
**Comments:**
Negative validation for password mismatch; ensures consistency between both password fields.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Open the Sign-up page.
2. Fill all fields with valid data.
3. Enter Abcd1234! in the Password field.
4. Enter Abcd12345! in the Repeat Password field.
5. Check both Terms and Privacy Policy checkboxes.
6. Click Sign Up.

**Test Data:**
- Password: Abcd1234!
- Repeat Password: Abcd12345!

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Validation error displayed under Repeat Password field:
- “Password confirmation does not match.”

ER-3: No account created; user remains on form.

</details>

---

<details id="tc_su_008">
<summary><b>TC_SU_008 – Validate registration attempt using  an already registered username</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Negative validation ensuring username uniqueness.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up
3. Ensure the username is already registered in the system.

**Test Steps:**
1. Fill all mandatory fields with valid data.
2. Enter an existing username.
3. Check both Terms and Privacy Policy checkboxes.
4. Click Sign Up.

**Test Data:**  
- Username: johnli
- Email: newuser@testmail.com
- Other fields: valid data

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Page-level error message displayed: “Username already exists.”  
ER-3: User remains on the same page; other field data preserved.

</details>

---

<details id="tc_su_009">
<summary><b>TC_SU_009 – Validate registration attempt with  an already registered email address</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:**
Negative duplicate validation; ensures unique constraint on email address.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up
3. Ensure the test email is already registered in the system.

**Test Steps:**
1. Fill all mandatory fields with valid data.
2. Enter a registered email address into the Email field.
3. Check both Terms and Privacy Policy checkboxes.
4. Click Sign Up.

**Test Data:**
- Email: john.li@testmail.com (already registered)
- Username: johnli2
- Other fields: valid data

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Page-level error message displayed: “Email address already registered.”  
ER-3: User remains on the same page; other field data is preserved.

</details>

---

<details id="tc_su_010">
<summary><b>TC_SU_010 – Validate minimum character length  for First and Last Name fields</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Boundary test ensuring field length validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter a single character in First and Last Name fields.
2. Fill other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- First Name: A
- Last Name: B
- Other fields: valid data

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Inline validation: 
- “First Name must be at least 2 characters.” 
- “Last Name must be at least 2 characters.”

</details>

---

<details id="tc_su_011">
<summary><b>TC_SU_011 – Validate trimming of leading and  trailing spaces from user inputs</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Data cleanup test to ensure normalization before submission.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter values with spaces before and after text in all input fields.
2. Check both consents.
3. Submit.

**Test Data:**
- First Name: “ Jan ”
- Last Name: “ Li ”
- Email: “ jan.li@testmail.com”

**Expected Result:**  
ER-1: Leading/trailing spaces are trimmed automatically.  
ER-2: Registration succeeds with cleaned input.  
ER-3: Stored data contains no extra spaces.

</details>

---

<details id="tc_su_012">
<summary><b>TC_SU_012 – Validate submission without entering First Name</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Field-level mandatory validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave First Name blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- First Name: (blank)
- Other fields: valid data

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Inline error message displayed: “First Name is required.”

</details>

---

<details id="tc_su_013">
<summary><b>TC_SU_013 – Validate submission without entering Last Name</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Basic field validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave Last Name blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- Last Name: (blank)

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Inline error message displayed: “Last Name is required.”

</details>

---

<details id="tc_su_014">
<summary><b>TC_SU_014 – Validate submission without entering Username</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Field-level validation for user ID.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave Username blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- Username: (blank)

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Error message displayed: “Username is required.”

</details>

---

<details id="tc_su_015">
<summary><b>TC_SU_015 – Validate submission without entering Email</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Basic field-level email validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave Email blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- Email: (blank)

**Expected Result:**  
ER-1: Submission blocked.  
ER-2: Error displayed: “Email is required.”

</details>

---

<details id="tc_su_016">
<summary><b>TC_SU_016 – Validate submission without entering Password</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Password mandatory validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave Password field blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- Password: (blank)

**Expected Result:**  
ER-1: Form submission blocked.  
ER-2: Error displayed: “Password is required.”

</details>

---

<details id="tc_su_017">
<summary><b>TC_SU_017 – Validate submission without  entering Repeat Password</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟠 P1  
**Comments:** Ensures password confirmation field enforcement.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Leave Repeat Password blank.
2. Fill all other fields validly.
3. Check consents.
4. Submit.

**Test Data:**
- Repeat Password: (blank)

**Expected Result:**  
ER-1: Submission blocked.  
ER-2: Error displayed: “Repeat Password is required.”

</details>

---

<details id="tc_su_018">
<summary><b>TC_SU_018 – Validate copy/paste functionality  between Password and Repeat fields</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Browser behavior check, consistency across fields.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter Password.
2. Copy and paste same into Repeat Password.
3. Fill all other fields and consents.
4. Submit.

**Test Data:**
- Password: Abcd1234!
- Repeat Password: same

**Expected Result:**  
ER-1: Form submits successfully.  
ER-2: No mismatch message shown.  
ER-3: Account successfully created.  

</details>

---

<details id="tc_su_019">
<summary><b>TC_SU_019 – Validate password and  repeat password fields are masked</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** Security-related UI validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter text in both password fields.
2. Observe input characters.

**Test Data:**
- Password: Abcd1234!

**Expected Result:**  
ER-1: Input is hidden behind dots/bullets ().  
ER-2: No plaintext visible during entry.

</details>

---

<details id="tc_su_020">
<summary><b>TC_SU_020 – Validate Terms and  Conditions hyperlink redirects correctly</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** UI navigation and link validation.

**Pre-requisites:**
1. Open the OBP Sandbox web application 
in any supported browser (Edge/Chrome).
2. Navigate to 
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Click the Terms and Conditions hyperlink.
2. Observe navigation result.

**Test Data:**  

**Expected Result:**  
ER-1: User is redirected to the Terms and Conditions page.  
ER-2: Page displays correct content and title.

</details>

---

<details id="tc_su_021">
<summary><b>TC_SU_021 – Validate Privacy Policy link opens Privacy page</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** Link validation

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Click Privacy link

**Test Data:**  

**Expected Result:**  
ER-1: Privacy Policy page opens correctly

</details>

---

<details id="tc_su_022">
<summary><b>TC_SU_022 – Validate keyboard-only navigation</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Accessibility check

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Navigate using Tab/Enter;
2. Submit

**Test Data:**
- Valid data

**Expected Result:**  
ER-1: Form fully operable via keyboard

</details>

---

<details id="tc_su_023">
<summary><b>TC_SU_023 – Validate multiple rapid submissions</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Concurrency control

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Fill valid data;
2. Double-click Sign Up quickly

**Test Data:**
- Valid data

**Expected Result:**
ER-1: Only one account created; no duplication

</details>

---

<details id="tc_su_024">
<summary><b>TC_SU_024 – Validate Username with special characters</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Character rule check

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Use dots, hyphens, underscores in username;
2. Submit

**Test Data:**
- user.name, 
- user-name, 
- user_name

**Expected Result:**  
ER-1: Accepted or rejected per rule with clear message

</details>

---

<details id="tc_su_025">
<summary><b>TC_SU_025 – Validate case-insensitive email handling</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Data normalization

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter email in uppercase;
2. Submit

**Test Data:**
- USER@MAIL.COM

**Expected Result:**  
ER-1: Treated as valid; normalized

</details>

---

<details id="tc_su_026">
<summary><b>TC_SU_026 – Validate field persistence after validation errors</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** UX consistency

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Fill all fields;
2. Submit with missing consent;
3. Observe fields

**Test Data:**
- Valid data

**Expected Result:**  
ER-1: Fields retain previous values after error

</details>

---

<details id="tc_su_027">
<summary><b>TC_SU_027 – Validate long email address handling</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** Boundary test

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter long but valid email;
2. Submit

**Test Data:**
- firstname.lastname+tag@verylongdomain.com

**Expected Result:**  
ER-1: Accepted if valid; error if exceeds limit

</details>

---

<details id="tc_su_028">
<summary><b>TC_SU_028 – Validate Username minimum and maximum length</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** Boundary test

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Test short and long usernames;
2. Submit

**Test Data:**
- u, 
- username_with_long_length

**Expected Result:**  
ER-1: Clear error or acceptance per rule

</details>

---

<details id="tc_su_029">
<summary><b>TC_SU_029 – Validate First/Last Name with diacritics</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🔵 P3  
**Comments:** Unicode check

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Enter José, Maë;
2. Submit

**Test Data:**
- José, 
- Maë

**Expected Result:**  
ER-1: Accepted; no encoding issue

</details>

---

<details id="tc_su_030">
<summary><b>TC_SU_030 – Validate successful retry after previous failure</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟢 P2  
**Comments:** Retry flow

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Trigger error (Terms off);
2. Fix;
3. Resubmit

**Test Data:**
- Valid data

**Expected Result:**  
ER-1: Form submits successfully after correction

</details>

---

<details id="tc_su_031">
<summary><b>TC_SU_031 – Validate basic label translation (EN/ES toggle)</b></summary>

**Test Scenario:** (TS_001) Sign-up  
**Priority:** 🟣 P4  
**Comments:** Localization check

**Pre-requisites:**
1. Open OBP Sandbox in the browser
https://apisandbox.openbankproject.com/user_mgt/sign_up

**Test Steps:**
1. Switch interface language;
2. Observe labels

**Test Data:**  

**Expected Result:**  
ER-1: Labels update correctly for selected language

</details>

---

