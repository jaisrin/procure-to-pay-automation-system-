# Purchase Order Creation & Submission

---

## Overview

This module enables the Purchase Team to generate a formal Purchase Order (PO) based on the selected vendor’s approved quotation and submit it for managerial approval.

It ensures structured data capture, financial accuracy, and controlled workflow transition from procurement decision to approval.

---

## Screens Covered

- Purchase Order Creation
- Submit Purchase Order for Approval (Confirmation Modal)

---

# Screen: Purchase Order Creation

## Overview

The Purchase Order Creation screen allows the Purchase Team to create a PO using system-populated vendor and request data while capturing required commercial and delivery details.

This screen ensures that all financial calculations and business rules are enforced before submission.

---

## Wireframe

![Purchase Order Creation](./po_creation.png)

## Payment Terms Dropdown

![Purchase Order Creation](./payment_terms.png)
---

## Header Section

Displays:

- Purchase Request Reference (PR ID & Title)
- Selected Vendor
- Required By Date
- Days Remaining (auto-calculated)
- Current PO Status (Draft)

### Logic

- Days Remaining is dynamically calculated based on Required By Date
- Status updates automatically based on workflow stage
- PO Number is generated only after submission

---

## PO Details Section

### System-Controlled Fields

- Vendor Name (auto-populated, read-only)
- Vendor Contact Details
- PO Date (auto-filled)
- PO Number (generated post submission)

### Editable Fields

- Delivery Address
- Payment Terms
- Expected Delivery Date

### Business Rule

- Vendor details cannot be modified at this stage to maintain data integrity

---

## Order Summary Section

Displays:

- Item Name
- Quantity
- Unit Price
- Calculated Subtotal
- Tax (based on predefined rules)
- Final Total Amount

### Automation

- All calculations are system-driven
- Tax is auto-computed
- No manual override allowed

### Purpose

- Ensures financial accuracy
- Maintains compliance
- Keeps cross-screen data consistency

---

## Action Controls

Available Actions:

- Save Draft
- Submit for Approval
- Cancel

### Workflow Logic

- Save Draft → Retains editable state
- Submit for Approval →
  - Locks financial values
  - Updates status to "Pending Approval"
  - Routes PO to Purchase Manager
  - Generates official PO Number

---

# Screen: Submit Purchase Order for Approval

## Overview

The Submit PO confirmation modal ensures that users explicitly confirm submission before triggering the approval workflow.

This prevents accidental submissions and reinforces workflow control.

---

## Wireframe

![Submit PO](./submit_po.png)

---

## Modal Structure

### Header

- Title: "Submit PO for Approval?"
- Close (X) option

### Body

Displays confirmation message:

- "This Purchase Order will be sent to the Purchase Manager for review and approval."

Optional Context:

- Vendor Name
- Total Amount

---

## Action Controls

- Cancel → Closes modal without changes
- Submit → Confirms submission

---

## System Behavior

On Submit:

- PO status updates to "Pending Approval"
- PO becomes non-editable
- Routed to Purchase Manager
- Official PO Number generated

On Cancel:

- Modal closes
- No changes applied

---

## Governance & Controls

- Submission is irreversible from user end
- Financial data is locked post submission
- Workflow transitions are system-driven
- Audit traceability is maintained

---

## Key Observations

- Prevents accidental submission through confirmation step
- Ensures data integrity before approval
- Maintains strict workflow control
- Supports audit and compliance requirements

---

# Purchase Order Review & Approval

## Overview
This screen enables the Purchase Manager to review the submitted Purchase Order in detail and make an approval decision.  
It acts as the final governance checkpoint before vendor commitment and financial execution.

---

## PO Context Header

### Displays:
- PO Number  
- Linked Purchase Request Reference  
- Vendor Name  
- Required By Date (with days remaining indicator)  
- Current Status (Submitted for Approval)  

### Logic:
- Days Remaining is auto-calculated based on Required By Date  
- Status is system-controlled  
- No editing is allowed at approval stage  

---

## Vendor & Delivery Details

### Shows:
- Vendor Contact Details  
- Delivery Address  
- Payment Terms  
- Expected Delivery Date  

### Control:
- All fields are read-only to ensure financial and contractual integrity  

---

## Financial Summary

### Displays:
- Quantity  
- Unit Price  
- Subtotal  
- Tax (e.g., GST)  
- Total Amount  

### Automation:
- All financial values are system-calculated  
- No manual overrides allowed  
- Ensures alignment with selected vendor quotation  

---

## Approval Decision Controls

### Available Actions:
- Approve  
- Reject  

---

### Decision Logic

#### If Approved:
- Status updates to **PO Approved**  
- Purchase Team receives notification  
- “Send PO to Vendor” action becomes enabled  

#### If Rejected:
- Mandatory rejection remarks required  
- Status updates to **PO Rejected**  
- Purchase Team must revise and resubmit  

---

## Approval Modal (Confirmation Layer)

### Trigger:
- Clicking **Approve**

### Purpose:
- Prevent accidental approvals  
- Reinforce financial commitment  

### Displays:
- Vendor Name  
- Total Amount  
- Confirmation message  

### Sample Message:
> You are approving a purchase of ₹63,720 for vendor XYZ Systems.  
> This action will finalize the order, notify the vendor, and commit company funds.  
> This action cannot be undone.

### Actions:
- Cancel  
- Confirm Approval  

---

## Action Logic

- Pending Approval → Action: Review  
- Approved → Action: View  
- Rejected → Action: View  

Approval or rejection can only occur within the PO Review screen.

---

## Urgency Logic

- Days Remaining is dynamically calculated  
- If deadline is near or overdue:
  - Visual indicator is displayed  
  - Enables prioritization of approvals  

---

## Governance & Controls

- PO data cannot be edited from dashboard  
- Financial data is read-only  
- Approval decisions are timestamped  
- Approver identity is recorded  
- Rejection requires mandatory remarks  
- Ensures separation between creator and approver  

---

## Key Observations

- Ensures financial commitment is validated before execution  
- Prevents unauthorized or accidental approvals  
- Maintains audit traceability for all decisions  
- Provides complete visibility into vendor and cost details  
- Strengthens governance in procurement lifecycle  

---
