# 🧩 Test Scenarios – Open Bank Project (OBP)

**Project Name:** Open Bank Project  
**Client:** OBP  
**Prepared by:** Pedro Henrique Li (QA — Manual)  
**Creation Date:** 2025-10-14  
**Approval Date:** —  

---

## 🧭 Overview

This document defines the **high-level Test Scenarios** designed for the Open Bank Project Sandbox (UI + API).  
Each scenario corresponds to a functional area and maps to a set of detailed Test Cases (referenced by `TC_` IDs in the respective sheets).

---

## 📋 Scenario Summary

| **Scenario ID** | **Reference** | **Description** | **Priority** | **# of Test Cases** |
|:----------------:|:--------------|:----------------|:-------------:|:-------------------:|
| 🧍‍♂️ **TS_001** | OBP Sandbox | Validate the working of **Sign-up (UI)**: ensure all mandatory fields, email format, password confirmation, and consent acceptance are properly validated. | 🔴 P0 | **31** |
| 💳 **TS_002** | OBP Sandbox | Validate the working of **Payment Initiation (SEPA)**: authenticate via DirectLogin, create transaction request, and verify payment status transitions. | 🔴 P0 | **12** |
| 💰 **TS_003** | OBP Sandbox | Validate **Reconciliation (Balance & Transactions)**: confirm account balance update and transaction entry after a successful payment. | 🟠 P1 | **6** |

---

## 🧠 Priority Legend

| Symbol | Priority | Meaning |
|:-------:|-----------|----------|
| 🔴 | **P0 – Critical / Smoke** | Must-pass flows, mandatory for demo |
| 🟠 | **P1 – High / Regression** | Important functional paths |
| 🟢 | **P2 – Medium / UI or exploratory** | Optional / extended coverage |

---

## 🗂️ Mapping to Test Cases

| **Scenario ID** | **Example Test Cases** |
|-----------------|------------------------|
| TS_001 | TC_UI_001 – Mandatory fields validation<br>TC_UI_002 – Invalid email format<br>TC_UI_003 – Password mismatch |
| TS_002 | TC_PI_001 – SEPA (No Challenge)<br>TC_PI_002 – SEPA with Challenge (TAN) |
| TS_003 | TC_RC_001 – Reconciliation after payment<br>TC_RC_002 – Balance verification |

---

## 🧾 Notes

- The total scope covers **3 key functional areas**, aligned with the **demo objectives**:  
  1️⃣ UI validation (Sign-up)  
  2️⃣ API transaction (Payment Initiation)  
  3️⃣ Post-transaction reconciliation  
- Each scenario contains both **positive and negative** paths.  
- All executions are designed to be **demonstrated live in Postman or browser**.

---

**Document version:** 1.0  
📅 **Last updated:** 14 Oct 2025  
✍️ **Author:** Pedro Henrique Li – QA Engineer
