# SQL-Exercise-4
UNION &amp; UNION ALL Exercise

# BrightLearn Exercise 04: SQL UNION & UNION ALL (Handwritten Solutions)

This repository contains handwritten solutions and query outputs for the NexBank dataset exercise covering `UNION` and `UNION ALL` set operators[cite: 1, 2].

---

## Overview

* **Dataset**: Fictional African retail bank (NexBank)[cite: 2].
* **Format**: Handwritten queries and result sets, digitized and uploaded for review.
* **Topics**:
  * **Questions 01–05 (`UNION`)**: Combining overlapping datasets with automatic deduplication[cite: 2, 4].
  * **Questions 06–10 (`UNION ALL`)**: Appending datasets while retaining all records and duplicates[cite: 2, 9].
  * **Bonus 01–03**: Operator rationale and query syntax troubleshooting[cite: 14, 15].

---

## Key SQL Rules

1. **Equal Column Count**: Both `SELECT` queries must return the same number of columns[cite: 2].
2. **Compatible Data Types**: Corresponding columns in each query must share compatible data types[cite: 2].
3. **Column Headers**: Result headers inherit names and aliases directly from the first `SELECT` statement[cite: 2].

---

## Query Summary & Expected Counts

| Question | Tables Combined | Operator | Deduplication | Output Rows |
| :--- | :--- | :--- | :--- | :--- |
| **Q01** | `branch_sandton_accounts`, `branch_rosebank_accounts`[cite: 4] | `UNION`[cite: 4] | Yes (`A003`, `A004`)[cite: 4] | 6 rows[cite: 4] |
| **Q02** | `savings_products`, `current_products`[cite: 4, 5] | `UNION`[cite: 5] | Yes (`SV03`)[cite: 5] | 7 rows[cite: 5] |
| **Q03** | `retail_banking_staff`, `corporate_banking_staff`[cite: 5] | `UNION`[cite: 6] | Yes (`5003`, `5004`)[cite: 5] | 6 rows[cite: 5] |
| **Q04** | `mobile_branch_cities`, `digital_branch_cities`[cite: 6] | `UNION`[cite: 6] | Yes (`C01`, `C03`)[cite: 6] | 6 rows[cite: 6] |
| **Q05** | `push_notification_targets`, `inapp_banner_targets`[cite: 7] | `UNION`[cite: 7] | Yes (`C1002`, `C1003`)[cite: 7] | 6 rows[cite: 7] |
| **Q06** | `atm01_transactions`, `atm02_transactions`[cite: 9] | `UNION ALL`[cite: 9] | No (keeps duplicate `T1003`)[cite: 2, 9] | 8 rows[cite: 9] |
| **Q07** | `gauteng_loan_applications`, `western_cape_loan_applications`[cite: 10] | `UNION ALL`[cite: 10] | No (keeps duplicate `LA003`)[cite: 2, 10] | 8 rows[cite: 10] |
| **Q08** | `email_complaints`, `app_complaints`[cite: 10] | `UNION ALL`[cite: 11] | No (preserves all records)[cite: 2, 11] | 8 rows[cite: 10] |
| **Q09** | `april_payments`, `may_payments`[cite: 11] | `UNION ALL`[cite: 11] | No (preserves all records)[cite: 2, 11] | 8 rows[cite: 11] |
| **Q10** | `debit_entries`, `credit_entries`[cite: 12] | `UNION ALL`[cite: 12] | No (preserves all records)[cite: 2, 12] | 8 rows[cite: 12] |

---

## Bonus Questions Summary

* **Bonus 01**: Use `UNION` because it eliminates duplicate customer records across the two monthly watch lists[cite: 2, 14].
* **Bonus 02**: Use `UNION ALL` because an audit count requires every transaction record, including cross-system duplicates[cite: 2, 14].
* **Bonus 03**: The original query fails due to mismatched column counts (2 columns vs. 3 columns); fix by aligning the column lists in both `SELECT` clauses[cite: 2, 15].
