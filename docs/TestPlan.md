# 🧪 Test Plan – Open Bank Project (OBP) Sandbox (Reduced Scope)

**Product:** OBP Sandbox (UI + API)  
**Focus:** Three demo tasks  
**Prepared by:** Pedro Henrique Li (QA — Manual)  
**Date:** 2025-10-14  

---

## 1. 🎯 Overview

This plan defines the test scope, approach, environments, and deliverables for a reduced demonstration of the **Open Bank Project (OBP) Sandbox**.

**Goal:** validate one UI flow and two API flows, executed live during the interview using Postman:
- 🧍‍♂️ **Sign-up (UI):** validate mandatory fields and consent  
- 💳 **Initiate payment (SEPA):** create and track payment status  
- 💰 **Verify balance & transactions:** confirm post-payment reconciliation  

---

## 2. 📦 Scope

Testing focuses on a minimal, functional subset of OBP Sandbox:  
🔗 [https://apisandbox.openbankproject.com](https://apisandbox.openbankproject.com)

### 2.1 ✅ Inclusions
- Register / Sign-up (UI): required field validation, email format, password confirmation, consent acceptance  
- Payments (API): authentication (DirectLogin), create transaction (SEPA/SANDBOX_TAN), retrieve status  
- Reconciliation (API): account balance and transactions verification using Postman assertions (HTTP 200, currency, amount)

### 2.2 🚫 Exclusions
- Non-covered endpoints (cards, KYC, dynamic entities)
- Security, performance, or penetration tests
- Multi-browser or mobile compatibility checks
- Email delivery or external provider integrations

---

## 3. 🧩 Test Environments

| Environment | Description |
|--------------|-------------|
| **OBP Sandbox** | Base URL in Postman Environment |
| **Browser (Edge/Chrome)** | Sign-up UI testing |
| **Postman** | Variables: host, consumer_key, username, password, DL_TOKEN, bank_id, account_id, view_id, to_account_id |

---

## 4. 🧠 Test Strategy

### Step 1 – Test Design
Formal techniques applied:  
- **Equivalence Partition (EP):** valid/invalid emails, positive/negative payment amounts  
- **Boundary Value Analysis (BVA):** amount = 0.00, min/max  
- **Decision Table:** combinations (valid/invalid email × password match × consent)  
- **State Transition:** INITIATED → PENDING_CHALLENGE → COMPLETED  
- **Use Case Testing:** End-to-End flow: Sign-up → Token → Payment → Balance check  
- **Error Guessing:** invalid TAN, malformed JSON, missing headers  

### Step 2 – Execution
- **Smoke:** verify sandbox reachability & token retrieval  
- **Functional:** run key positive and negative cases  
- **Reconciliation:** validate balance/transaction updates  
- **Defect Reporting:** log with evidence (JSON/screenshot)  

### Step 3 – Best Practices
- **Context-driven:** focus on demo tasks  
- **Shift-left:** prepare environment early  
- **Exploratory:** complement scripted cases  
- **End-to-End Validation:** ensure payment reflected in balance  

---

## 5. 🐞 Defect Reporting Procedure

| Field | Description |
|--------|--------------|
| **Defect ID** | Auto or manual |
| **Title** | Short descriptive summary |
| **Steps to Reproduce** | Sequential steps to failure |
| **Actual Result** | Observed behavior |
| **Expected Result** | Intended behavior |
| **Severity** | Blocker / Major / Minor |
| **Status** | New → In Progress → Fixed → Retested → Closed |
| **Evidence** | Screenshot or JSON |
| **Linked Test Case** | Test Case ID |

---

## 6. 👥 Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| **QA (Pedro)** | Test design, execution, evidence, summary |
| **Reviewer (Tech Lead)** | Clarifications, acceptance of demo results |
| **OBP Sandbox Support** | Maintain environment, assist with tokens |

---

## 7. ⏰ Test Schedule

| Phase | Task | Duration | Owner |
|--------|------|-----------|--------|
| Design & Setup | Prepare environment & test cases | Before interview | QA |
| Execution | Run UI & API tests live | 15–25 min | QA |
| Reporting | Summarize results | 2–3 min | QA |
| Review | Validation & feedback | End of demo | Reviewer |

---

## 8. 📦 Deliverables

| Deliverable | Description |
|--------------|-------------|
| **Postman Collection** | Auth → Payment → Status → Balance → Transactions |
| **Postman Environment** | Config vars |
| **UI Evidence** | 3–4 screenshots |
| **Execution Log** | Pass/Fail summary |
| **Defect Sheet** | Defects linked to test cases |

---

## 9. 🚀 Entry & Exit Criteria

**Entry**
- OBP Sandbox reachable  
- Valid credentials and setup  

**Exit**
- ≥ 90% executed  
- No open blockers  
- Results documented  

---

## 10. ⏸ Suspension / Resumption

**Suspend if:**
- Sandbox/API down  
- Token/auth failures unrelated to test data  

**Resume when:**
- Environment stable  
- Tokens renewed  

---

## 11. 🧰 Tools

| Tool | Purpose |
|------|----------|
| **Postman** | API tests & assertions |
| **Browser** | UI testing |
| **Snipping Tool** | Capture evidence |
| **Spreadsheet / Jira** | Track defects |

---

## 12. ⚠️ Risks & Mitigations

| ID | Risk | Impact | Mitigation |
|----|------|---------|-------------|
| R1 | Sandbox data reset | High | Create data on-the-fly |
| R2 | Token expiration | Medium | Refresh token |
| R3 | Network instability | Medium | Retry |
| R4 | Time constraint | High | Prioritize happy path |

---

## 13. ✅ Approvals

| Reviewer | Role | Signature | Date |
|-----------|------|------------|------|
| Tech Lead / Interviewer | QA Reviewer | — | — |

---

📘 [Test Plan](docs/Test_Plan_OpenBankProject.md)  
📋 [Test Scenarios](docs/Test_Scenarios_OpenBankProject.md)  
🧪 [Test Cases](docs/Test_Cases_OpenBankProject.xlsx)

**Prepared by:**  
**Pedro Henrique Li – QA Engineer**  
📅 14 Oct 2025  

