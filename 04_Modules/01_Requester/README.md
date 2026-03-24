## Screen: Requester Dashboard

### Overview

The Requester Dashboard provides a consolidated view of all purchase requests created by the user. It enables tracking of request status, quick access to actions and initiation of new purchase requests.

This screen acts as the control center for the requester, offering visibility into the lifecycle of each request.

---

### Wireframe

![Requester Dashboard](./requester_dashboard.png)

---

### Layout and Sections

#### 1. Header Section
- Displays welcome message with user name  
- Provides primary action: **Create Purchase Request**

**Purpose:**
- Personalization  
- Quick access to request creation  

---

#### 2. Status Summary Cards

Cards displayed:
- Pending  
- Approved  
- In Progress  
- Completed  
- Rejected  
- Total PRs  
- Saved Drafts  

**Purpose:**
- Snapshot view of request distribution  
- Helps user quickly understand current workload  

---

#### 3. Search Bar

- Allows search by Request ID / Item  

**Purpose:**
- Quick retrieval of specific requests  
- Reduces dependency on scrolling  

---

#### 4. Request Table

Columns:
- Request ID  
- Item  
- Amount  
- Status  
- Action  

**Purpose:**
- Displays all requests created by the user  
- Acts as the primary interaction area  

---

#### 5. Action Column

Actions vary by status:
- View → for submitted/processed requests  
- Edit → for Draft / Rejected requests  

---

### System Logic

- Data displayed is filtered based on logged-in requester  
- Status cards are dynamically calculated from request data  
- Table is sorted by latest request by default  
- Search filters results in real-time  
- Pagination is applied for large datasets  

---

### Status Logic

Each request follows defined states:

- Draft → Editable  
- Pending Approval → Locked  
- Approved → Moves to next stage  
- In Progress → Under processing (RFQ / PO stage)  
- Completed → Fully processed  
- Rejected → Editable with changes  

---

### Action Logic

- Draft → Edit allowed  
- Rejected → Edit allowed  
- All other statuses → View only  

---

### Business Rules

- User can only view their own requests  
- Status counts must match table data  
- Requests once submitted cannot be edited  
- Rejected requests must allow re-submission after edit  
- “Create Purchase Request” is always enabled  

---

### Edge Cases

- No requests → Show empty state  
- Large number of requests → Pagination enabled  
- Search with no result → Display “No results found”  
- Status mismatch → System should recalculate counts  
- Deleted/archived request → Should not appear  

---

### Workflow Transition

- Clicking **Create Purchase Request** → Navigates to Create PR screen  
- Clicking **View** → Opens request details  
- Clicking **Edit** → Opens editable PR (Draft/Rejected only)  

---

### Key Observations

- Dashboard focuses on visibility and control  
- Action availability is strictly status-driven  
- Ensures user cannot modify submitted requests  
- Maintains clear separation between editable and non-editable states  
