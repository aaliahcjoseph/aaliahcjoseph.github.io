---
title: "Invoice Validation & Reconciliation Tool"
layout: single
permalink: /projects/invoice-validation/ 
classes: project-detail
---

<div class="project-page-skills">
  <span>Excel</span>
  <span>Data Validation</span>
  <span>Process Improvement</span>
  <span>Reconciliation</span>
</div>

<p class="project-page-hook">
  Two systems can agree and still both be wrong.
</p>

I developed an Excel-based validation tool designed to improve the accuracy and efficiency of invoice preparation by independently calculating expected charge quantities from actual passenger counts and menu specifications, then reconciling those quantities against internal SACS data and customer-provided IFX data.

---

# The Business Problem

Customer billing is based on the information reported through IFX. SACS and IFX can be compared directly to identify differences, but agreement between the two systems does not necessarily mean that the quantity is correct.

For example, if SACS and IFX both report the same quantity, a direct comparison would show no discrepancy — even if the quantity does not align with the actual passenger counts or applicable menu specifications.

The challenge was therefore to create a validation process that could establish an independent expected quantity before the invoice was finalized.

---

# The Solution

I developed a linked Excel validation tool that uses actual passenger counts and applicable menu specifications to calculate the expected quantity for each charge.

The expected quantity is then compared against both SACS and IFX, creating a third point of reference rather than relying solely on whether the two source systems agree.


---

# How It Works

### 01 — Bring in the source data

Actual passenger counts are entered into the **COUNTS** sheet. Corresponding SACS and IFX data are downloaded and entered into their respective sheets, with the appropriate categories assigned.

### 02 — Calculate the expectation

The **REGULAR** and **SPML** sheets use the passenger counts and applicable menu specifications to calculate expected quantities for each charge.

### 03 — Apply reference logic

The **LOOKUP** and **CODES** sheets support the validation process by mapping IFX codes to SACS codes, descriptions, and other reference information used in the calculations.

### 04 — Reconcile

The **CALCULATION** sheet brings the information together and compares the expected quantities against both SACS and IFX.

<div class="reconciliation-flow">
  <div class="reconciliation-row">
    <span class="reconciliation-source">Expected</span>
    <span class="reconciliation-arrow">→</span>
    <span class="reconciliation-target">SACS</span>
  </div>

  <div class="reconciliation-row">
    <span class="reconciliation-source">Expected</span>
    <span class="reconciliation-arrow">→</span>
    <span class="reconciliation-target">IFX</span>
  </div>
</div>

<p>
  A variance of <strong>0</strong> indicates that the reported quantity agrees with the independently calculated expectation. Non-zero variances are flagged for review.
</p>

---

# Workbook Structure

The workbook is organized into layers, moving from source data through calculation and reference logic to final validation.

| Layer | Components | Purpose |
|---|---|---|
| **Inputs** | COUNTS, SACS, IFX | Bring source data into the tool |
| **Calculations** | REGULAR, SPML | Calculate expected quantities |
| **Reference** | LOOKUP, CODES | Map codes and apply reference logic |
| **Validation** | CALCULATION | Reconcile expected vs. source quantities |
| **Output** | GROSS TOTALS | Summarize validated results |

---

# Why the Independent Calculation Matters

A direct SACS vs. IFX comparison only tells us whether the two systems match.

> **Do the two systems agree?**

The validation tool goes one step further by establishing what the quantity should be based on the underlying operational information.

> **Do the reported quantities make sense based on the underlying operational information?**

<p>For example:</p>

<div class="validation-example">
<div class="validation-values">
<div class="validation-value">
<span class="validation-label">SACS</span>
<span class="validation-number">100</span>
</div>
<div class="validation-value">
<span class="validation-label">IFX</span>
<span class="validation-number">100</span>
</div>
<div class="validation-value validation-expected">
<span class="validation-label">Expected</span>
<span class="validation-number">110</span>
</div>
</div>
<div class="validation-result">
<span>SACS = IFX</span>
<span class="validation-but">but</span>
<span>SACS ≠ Expected</span>
</div>
</div>

A direct comparison would show a match, when it is actually undercharged.

The validation tool identifies that both reported quantities differ from the independently calculated expectation and therefore require review. This creates a stronger validation process because agreement between two systems is not treated as proof of accuracy.

---

# Business Value

Customer billing is ultimately based on the quantities reported in IFX. Validating those quantities against actual passenger counts and applicable menu specifications provides an additional level of assurance before invoicing.

This tool helps identify both undercharges and overcharges, supporting more accurate customer billing while reducing the risk of discrepancies going undetected. It also standardizes a process that previously required repetitive manual comparison across multiple data sources.

---

# Impact

The tool was designed to:

- reduce repetitive manual invoice validation
- provide an independent check of invoiced quantities
- identify discrepancies before invoices are finalized
- standardize the reconciliation process
- improve confidence in customer billing accuracy
- direct attention towards records requiring review rather than manually checking every record

---

# Key Skills Demonstrated

## Excel & Data Analysis

- Pivot tables
- XLOOKUP
- Conditional logic
- Formula-driven calculations

## Business & Process Analysis

- Requirements translation
- Business-rule implementation
- Process improvement
- Data quality validation
- Reconciliation logic

---

# Portfolio Demonstration

Customer identifiers and pricing have been modified for portfolio purposes. The underlying workflow and validation logic have been preserved.
