# Workflow

## Overview

The Procure-to-Pay workflow defines the end-to-end movement of a procurement request from initiation to final payment. Each stage is governed by system-driven transitions, role-based actions and validation rules to ensure control and accuracy.

---

## End-to-End Flow

Purchase Request → Approval → RFQ → Vendor Selection →  
Purchase Order Creation → PO Approval → PO Dispatch →  
Goods Receipt → Inspection → GRN Generation →  
Invoice Upload → Three-Way Matching → Payment Processing  

---

## Stage Breakdown

### 1. Purchase Request

The process begins when the requester creates a purchase request with item details, quantity, required date and business justification.

- Request is saved as draft or submitted  
- On submission, the system generates a PR number  
- Request is routed for approval based on cost thresholds  

---

### 2. Approval

The request is reviewed by the appropriate manager.

- Manager approves or rejects the request  
- Rejection requires a reason  
- Approved requests move to the Purchase Team  

---

### 3. RFQ and Vendor Interaction

The Purchase Team initiates vendor engagement.

- RFQ is created and sent to selected vendors  
- Vendor responses are recorded  
- Quotations are documented for comparison  

---

### 4. Vendor Selection

The Purchase Team evaluates vendor quotations.

- Vendor is selected based on price and criteria  
- Selection requires justification  
- Selected vendor details are used for PO creation  

---

### 5. Purchase Order Creation

A Purchase Order is created based on the selected vendor.

- Financial values are auto-calculated  
- PO is saved as draft or submitted  
- On submission, PO is routed for approval  

---

### 6. Purchase Order Approval

The Purchase Manager reviews the PO.

- PO is approved or rejected  
- Approved PO becomes eligible for vendor dispatch  
- Rejected PO requires revision  

---

### 7. PO Dispatch

The approved PO is sent to the vendor.

- System records dispatch  
- Status updates to indicate vendor commitment  
- Warehouse is notified for expected delivery  

---

### 8. Goods Receipt

The Warehouse records delivery of goods.

- Received quantity is captured  
- Partial delivery is supported  
- Pending quantity is calculated automatically  

---

### 9. Inspection and GRN

The received goods are inspected for quality.

- Accepted and rejected quantities are recorded  
- GRN is generated for accepted quantity  
- Rejected items trigger replacement workflow  

---

### 10. Invoice Processing

The Accounts team uploads the vendor invoice.

- Invoice details are recorded  
- Invoice is linked to PO and GRN  
- System prepares for validation  

---

### 11. Three-Way Matching

The system validates financial accuracy.

- PO amount, GRN amount, and invoice amount are compared  
- If matched → payment can proceed  
- If mismatch → payment is placed on hold  

---

### 12. Payment Processing

The final stage completes the procurement lifecycle.

- Payment is approved after successful validation  
- Transaction is recorded  
- Process is marked as completed  

---

## Workflow Controls

- All transitions are system-driven  
- Status updates automatically based on actions  
- Financial values are system-calculated  
- Approval decisions are recorded with timestamps  
- Payment is blocked if validation fails  

---

## Traceability

Each stage is linked through system-generated references:

- PR Number → PO Number → GRN → Invoice  

This ensures complete traceability across the procurement lifecycle.

---

## Supporting Documentation

Detailed functional requirements and validation rules are available in the documentation section of this repository.
