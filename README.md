# Amol Mahale

![Amol Mahale](https://github.com/Amolmahale01/Resume/blob/main/linkdin_wallpaper-removebg-preview.png)  

Email: [amolm01rcpit@gmail.com](mailto:amolm01rcpit@gmail.com) | Phone: +91-9579842665  
LinkedIn: [linkedin.com/in/amol-mahale-9aa796215](https://www.linkedin.com/in/amol-mahale-9aa796215) | GitHub: [github.com/Amolmahale01](https://github.com/Amolmahale01)

<!-- Profile README for Amol Mahale -->

<h1 align="center">Hi, I'm Amol Mahale 👋</h1>
<p align="center">
  ERPNext Developer • Python • Frappe • React • SQL
</p>

<p align="center">
  <a href="mailto:amolm01rcpit@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-amolm01rcpit%40gmail.com-informational"></a>
  <a href="https://www.linkedin.com/in/amol-mahale-9aa796215"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-Amol%20Mahale-blue"></a>
  <a href="https://github.com/Amolmahale01"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-Amolmahale01-black"></a>
  <a href="https://amolmahaleportfolio.netlify.app/"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-Visit-success"></a>
</p>

---

## 🚀 About Me
- **ERPNext Developer @ CBD IT Solutions** (≈1 year)
- I build and customize ERPNext using **Frappe Framework (Python, JS)** to automate Accounting, Manufacturing, CRM, Stock & Helpdesk.
- Love turning business logic into **clean scripts, reports, print formats, and dashboards** (Frappe Insights).

---

## 🧰 Tech Stack
**Languages:** Python, JavaScript, SQL, HTML, CSS  
**Frontend:** React, Next.js, React Query  
**Backend:** Frappe Framework, Django, REST APIs  
**ERP:** ERPNext (DocType, Client/Server Script, Custom App, Print Format, Reports, Insights)  
**DB:** MySQL, PostgreSQL, MS SQL Server  
**Tools:** GitHub, VS Code, Postman, Cursor

---

## 🏗️ ERPNext / Frappe Highlights
- Built **client & server scripts**, **custom apps**, **REST integrations**
- Designed **GST/TDS reports**, **Aging & Reconciliation**, **Manufacturing BOM/WO flows**
- **Print Formats** (A4 PDFs, conditional GST sections, barcodes)
- **Frappe Insights** dashboards: TAT, stock, sales, production KPIs

```py
# Server Script example (Python)
import frappe

@frappe.whitelist()
def check_rm_availability(work_order):
    wo = frappe.get_doc("Work Order", work_order)
    shortages = []
    for d in wo.required_items:
        qty = frappe.db.get_value("Bin", {"item_code": d.item_code, "warehouse": d.source_warehouse}, "actual_qty") or 0
        if qty < d.required_qty:
            shortages.append(f"{d.item_code}: need {d.required_qty}, have {qty}")
    return "All good ✅" if not shortages else "Shortages:\n" + "\n".join(shortages)
