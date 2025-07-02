# Zoho Kanban Stage Validation

🚀 This Deluge script is used to validate stage movements on a Kanban pipeline in Zoho CRM Deals.  
It ensures proper forward progression and controls allowed backward moves (e.g. from Negotiation back to Quotation Created).

## 🔍 What this script does
- Enforces a strict stage order for your CRM pipeline:
  - `Qualified Deal → Quotation Created → Negotiation → Quotation Accepted → Sales Order Created → Deal Won`
- Allows:
  - Moving forward to later stages
  - Moving backward **only from `Negotiation` to `Quotation Created`**
- Blocks invalid backward transitions.

## ✅ Modules involved
- Zoho CRM `Deals` module

## 💡 Usage
Attach this function to a `before update` or `on update` webhook in Zoho CRM, passing the record payload.  
It returns:
- `status: success` if the stage change is valid
- `status: error` with a message if invalid.

## 📂 Files
- `kanban-stage-validation.deluge` — the Deluge script
- `README.md` — this documentation

## ✍️ Author
Amal Dev Anilkumar ([@theframer](https://github.com/theframer))
