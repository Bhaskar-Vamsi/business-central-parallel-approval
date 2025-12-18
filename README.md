# Business Central – Parallel Approval (Any One Approver)

This repository demonstrates how to configure **parallel approvals** in Microsoft Dynamics 365 Business Central where **any one approver can approve** and the document is **auto-released**, using **standard configuration only**.

No AL extensions. No customization.

---

## 🔍 What this solves

By default, Business Central approval workflows behave sequentially or expect all approvers to approve.

This setup enables:

- Parallel approval requests
- Only **one approval required**
- Automatic document release
- Automatic cancellation of remaining approvals

---

## 📂 Included Files

### 1. Workflow XML
`workflows/PurchaseInvoice_ParallelApproval.xml`

- Ready-to-import workflow
- Uses **Workflow User Group**
- Implements **First Approver Wins** logic

### 2. Configuration Documentation
`documentation/Purchase Invoice Approval Work Flow.xlsx`

- Step-by-step setup reference
- Workflow logic breakdown
- Approval user configuration

---

## ⚙️ High-level configuration logic

### Workflow User Group
- Add all approvers
- Same **Sequence No = 1**
- Enables parallel routing

### Approval User Setup
- Configure approvers with proper limits or unlimited approval
- Requester is NOT an approver

### Workflow behavior
- On request → restrict record, set Pending Approval, send approvals
- On first approval → release document + cancel remaining approvals
- Reject / cancel → standard Business Central behavior

---

## 📌 Applicable for

- Purchase Invoices
- Purchase Orders
- Sales Orders
- Credit Memos
- Journals
- Any document using the Business Central approval framework

---

## 👤 Author

Business Central Functional Consultant  
Focused on practical, real-world ERP solutions.

---

If you find this useful, feel free to share or adapt it for your projects.
