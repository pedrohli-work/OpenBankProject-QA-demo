# 🔁 Test Cases – Reconciliation (Balance & Transactions)
**Scenario:** TS_003 – Reconciliation (Balance & Transactions)  
**Prepared by:** Pedro Henrique Li (QA — Manual)  
**Language:** English (US)  
**Format:** Collapsible sections with QA icons  

---


<details id="tc_rc_001">
<summary><b>TC_RC_001 – Validate source account balance reflects debit after completed payment</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🔴 P0  
**Comments:** Happy path
debit must be reflected in source balance.

**Pre-requisites:**  
A SEPA (or SIMPLE) payment completed successfully. 
Postman environment set: 
- host, 
- DL_TOKEN, 
- bank_id, 
- account_id, 
- view_id=owner, 
- amount, 
- currency.

**Test Steps:**  
1. Call GET Balance for the source account 
after the successful payment.
2. Compare the returned balance with the balance 
prior to payment (if stored) or verify that the debit equals amount.

**Test Data:**  
- amount="{{amount}}", 
- currency="{{currency}}"

**Expected Result:**  
ER-1: Response 200 with a valid balance object.  
ER-2: Balance decreased by the payment amount in the same currency.  
ER-3: No sign/currency inconsistencies.

</details>

---


<details id="tc_rc_002">
<summary><b>TC_RC_002 – Validate transactions list contains the new payment entry (source)</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🔴 P0  
**Comments:** End-to-end confirmation via transaction listing.

**Pre-requisites:**  
A successful payment; 
transaction_request_id (if available) 
and description used when creating the payment.

**Test Steps:**  
1. Call GET Transactions for the source account.
2. Search for a transaction whose amount, 
currency, and description match the created payment.

**Test Data:**  
- amount="{{amount}}", 
- currency="{{currency}}", 
- description contains your payment note.

**Expected Result:**  
ER-1: Response 200 with a transactions list.  
ER-2: One entry matches the payment with correct amount, 
currency, and description.  
ER-3: If provided by API, linkage to transaction_request_id is present.

</details>

---


<details id="tc_rc_003">
<summary><b>TC_RC_003 – Validate destination account reflects credit (balance & transactions)</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🟠 P1  
**Comments:** Executable only if destination 
account/view is accessible.

**Pre-requisites:**  
Payment completed to a destination account you can query; 
proper view_id/permissions for destination.

**Test Steps:**  
1. Call GET Balance of destination account.
2. Call GET Transactions of destination account.
3. Verify credit amount and presence of the new transaction.

**Test Data:**  
- Same amount/currency as payment; 
- destination account identifiers.

**Expected Result:**  
ER-1: Destination balance increased by amount.  
ER-2: A corresponding credit transaction appears 
with correct currency and description.  
ER-3: No currency mismatch.

</details>

---


<details id="tc_rc_004">
<summary><b>TC_RC_004 – Validate transaction appears when filtering by a date range that contains the payment</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🟠 P1  
**Comments:** Validates server-side filtering by time window.

**Pre-requisites:**  
Payment timestamp known (store creation time).

**Test Steps:**  
1. Call GET Transactions with from_date and to_date 
that include the payment timestamp 
(from = payment-time − 1h; to = payment-time + 1h).

**Test Data:**  
- Date range enclosing the payment time.

**Expected Result:**  
ER-1: Response 200 with a filtered list.  
ER-2: The payment transaction is returned within the range.  
ER-3: No transactions outside the range are included.

</details>

---


<details id="tc_rc_005">
<summary><b>TC_RC_005 – Validate currency consistency between payment, balance, and transactions</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🟢 P2  
**Comments:** Data integrity check (currency alignment).

**Pre-requisites:**  
Successful payment completed.

**Test Steps:**  
1. Retrieve GET Balance and GET 
Transactions for the source account.
2. Verify ISO currency codes match the payment’s currency.

**Test Data:**  
- currency="{{currency}}"

**Expected Result:**  
ER-1: Transaction currency equals the payment currency.  
ER-2: Balance currency uses the same 
ISO code and does not conflict with transaction currency.

</details>

---


<details id="tc_rc_006">
<summary><b>TC_RC_006 – Validate balance and transactions remain unchanged after FAILED payment</b></summary>

**Test Scenario:** (TS_003) Reconciliation
Balance & Transactions  
**Priority:** 🟠 P1  
**Comments:** Negative reconciliation
failures must not impact ledger.

**Pre-requisites:**  
A payment that resulted in FAILED 
(invalid amount/currency or rejected challenge).

**Test Steps:**  
1. After the failed payment, call GET Balance and 
GET Transactions for the source account.
2. Compare with pre-failure state (or confirm absence of new related entries).

**Test Data:**  
- Reference the failed transaction_request_id if available.

**Expected Result:**  
ER-1: No balance change attributable to the failed request.  
ER-2: No new transaction records created for the failed request.  
ER-3: Status endpoint of the failed request provides informative error.

</details>

---
