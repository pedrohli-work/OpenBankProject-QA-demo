# 💳 Test Cases – Payment Initiation (SEPA)
**Scenario:** TS_002 – Payment Initiation  
**Prepared by:** Pedro Henrique Li (QA — Manual)  
**Language:** English (US)  
**Format:** Collapsible sections with QA icons  

---


<details id="tc_pi_001">
<summary><b>TC_PI_001 – Validate SEPA payment creation and initial status (no challenge)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🔴 P0  
**Comments:** Happy path – baseline SEPA 
creation without challenge.

**Pre-requisites:**  
Postman with environment variables set 
(host, 
consumer_key, 
username, password, 
DL_TOKEN, 
bank_id, 
account_id, 
view_id=owner, 
currency=EUR, 
amount=1.00, 
description). 

Valid DirectLogin token available or included in steps.

**Test Steps:**  
1. Obtain DirectLogin token if needed.
2. Send POST to Create Transaction Request (SEPA).
3. Capture transaction_request_id.
4. Send GET to retrieve transaction request status.

**Test Data:**  
Headers: Authorization: 
DirectLogin token={{DL_TOKEN}}, 
Content-Type: application/json
Body:
json<br>{ "to": {"iban": "DE91100000000123456789"}, 
"value": {"currency": "EUR","amount": "1.00"}, 
"description": "{{description}}", 
"charge_policy": "SHARED" }

**Expected Result:**  
ER-1: API returns 201/200 with a valid transaction_request_id.
ER-2: Response contains correct amount and currency.
ER-3: GET status shows INITIATED or COMPLETED.

</details>

---


<details id="tc_pi_002">
<summary><b>TC_PI_002 – Validate SEPA payment with challenge (TAN)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🔴 P0  
**Comments:** Validates SEPA Strong 
Customer Authentication simulation.

**Pre-requisites:**  
Environment supports SEPA with TAN challenge. 
Valid DirectLogin token.

**Test Steps:**  
1. Send POST SEPA create request.
2. Observe challenge field in response.
3. Submit challenge/TAN confirmation via indicated endpoint.
4. Poll GET status until final state.

**Test Data:**  
Body same as TC_PI_001. 
TAN: "123456" when requested.

**Expected Result:**  
ER-1: Response includes transaction_request_id and challenge.
ER-2: TAN submission accepted (HTTP 2xx).
ER-3: Status transitions from PENDING_CHALLENGE to COMPLETED.

</details>

---


<details id="tc_pi_003">
<summary><b>TC_PI_003 – Validate challenge error handling (missing or invalid TAN)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** Negative challenge flow and recovery test.

**Pre-requisites:**  
Sandbox returning challenge object.

**Test Steps:**  
1. POST SEPA create to trigger challenge.
2. Submit empty or invalid TAN (e.g. blank or "abc").
3. Resubmit with valid TAN.

**Test Data:**  
Invalid TAN: "", "abc". Valid TAN: "123456".

**Expected Result:**  
ER-1: Invalid TAN returns 4xx with validation error.
ER-2: Correct TAN returns 2xx.
ER-3: Status progresses to COMPLETED.

</details>

---


<details id="tc_pi_004">
<summary><b>TC_PI_004 – Validate authentication failure with invalid DirectLogin credentials</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** Negative authentication control.

**Pre-requisites:**  
Postman ready; invalid login credentials.

**Test Steps:**  
1. Attempt DirectLogin with incorrect credentials.
2. Attempt SEPA payment without valid token.

**Test Data:**  
Wrong username or password.

**Expected Result:**  
ER-1: DirectLogin fails with 401/403.
ER-2: SEPA request fails with 401 Unauthorized.
ER-3: No transaction request is created.

</details>

---


<details id="tc_pi_005">
<summary><b>TC_PI_005 – Validate expired DirectLogin token handling (renew and retry)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** Session recovery flow.

**Pre-requisites:**  
Expired or manually invalidated DL_TOKEN.

**Test Steps:**  
1. Create SEPA payment with expired token → expect 401.
2. Obtain new token.
3. Retry SEPA creation → expect success.

**Test Data:**  
Invalid token replaced by valid one.

**Expected Result:**  
ER-1: First attempt 401 Unauthorized.
ER-2: Second attempt 201/200 with valid transaction_request_id.

</details>

---


<details id="tc_pi_006">
<summary><b>TC_PI_006 – Validate invalid IBAN is rejected</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** Negative input validation.

**Pre-requisites:**  
Valid token.

**Test Steps:**  
1. POST SEPA create with incorrect IBAN format.

**Test Data:**  
to.iban = "DE001234"

**Expected Result:**  
ER-1: API returns 4xx with IBAN validation message.
ER-2: No transaction request created.

</details>

---


<details id="tc_pi_007">
<summary><b>TC_PI_007 – Validate non-EUR currency is rejected</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** SEPA requires EUR-only.

**Pre-requisites:**  
Valid token.

**Test Steps:**  
1. POST SEPA create with "currency": "USD".

**Test Data:**  
currency = "USD", amount = "1.00".

**Expected Result:**  
ER-1: API returns 4xx error indicating unsupported currency.
ER-2: No transaction created.

</details>

---


<details id="tc_pi_008">
<summary><b>TC_PI_008 – Validate zero or negative amounts are rejected</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟠 P1  
**Comments:** Boundary value validation.

**Pre-requisites:**  
Valid token.

**Test Steps:**  
1. POST SEPA create with "amount": "0.00".
2. Repeat with "amount": "-1.00".

**Test Data:**  
0.00 and -1.00.

**Expected Result:**  
ER-1: API rejects with 4xx validation error.
ER-2: No transaction request ID generated.

</details>

---


<details id="tc_pi_009">
<summary><b>TC_PI_009 – Validate required headers and body fields (schema enforcement)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟢 P2  
**Comments:** Contract robustness test.

**Pre-requisites:**  
None.

**Test Steps:**  
1. POST SEPA create without Authorization header.
2. Repeat without Content-Type: application/json.
3. Repeat with missing to or value fields in body.

**Test Data:**  
Headers/bodies intentionally incomplete.

**Expected Result:**  
ER-1: Missing Authorization → 401 Unauthorized.
ER-2: Missing body fields → 4xx validation error.
ER-3: No transaction created.

</details>

---


<details id="tc_pi_010">
<summary><b>TC_PI_010 – Validate description field length limit (2000 characters)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟢 P2  
**Comments:** Field constraint validation.

**Pre-requisites:**  
Valid token.

**Test Steps:**  
1. POST SEPA create with description exceeding 2000 chars.

**Test Data:**  
String of 2001+ characters.

**Expected Result:**  
ER-1: API returns 4xx error for description length violation.
ER-2: No transaction request ID generated.

</details>

---


<details id="tc_pi_011">
<summary><b>TC_PI_011 – Validate future-dated SEPA request (optional scheduling)</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🟢 P2  
**Comments:** Optional SEPA scheduling test.

**Pre-requisites:**  
Valid token; 
sandbox supports future_date.

**Test Steps:**  
1. POST SEPA create with "future_date": "20251201".

**Test Data:**  
Future date field included.

**Expected Result:**  
ER-1: API returns 201/200 accepting request.
ER-2: Status shows scheduled initiation (INITIATED or equivalent).

</details>

---


<details id="tc_pi_012">
<summary><b>TC_PI_012 – Validate SEPA type availability for account/view</b></summary>

**Test Scenario:** (TS_002)
Payment Initiation (SEPA)  
**Priority:** 🔵 P3  
**Comments:** Defensive pre-check before payment creation.

**Pre-requisites:**  
Valid token; 
account and view accessible.

**Test Steps:**  
1. GET /transaction-request-types for the account/view.
2. Confirm SEPA listed.

**Test Data:**  
None.

**Expected Result:**  
ER-1: Response 200 lists SEPA as available type.
ER-2: If missing, execution marked blocked by environment.

</details>

---
