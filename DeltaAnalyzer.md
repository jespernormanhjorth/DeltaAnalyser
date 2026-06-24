## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, always use the data from the most recent **raw file** in the SharePoint `raw` folder as the single source of truth.

### Workflow Steps
1. **Retrieve all current customers:** Extract customer records from the latest report (`report<timestamp>.xls` or `.csv`) in the `raw` folder.
    - Consolidate by **Parent Account** to ensure subsidiaries roll up to the main corporate account.
    - Determine **Customer Segment** strictly from the column **`Account Name: Customer Segment`** in the raw file:
        - If the field is empty, default to **E-sell** (lowest rank).
        - Do not infer or assume a higher rank if missing.
2. **Analyze product setup per account:** Review each parent account's current product mix against known Cegal offerings (excluding internal-use portfolios such as `admin`). For child accounts:
    - If **any subsidiary has a product**, treat that product as present for the entire parent account group.
    - If **a product exists only at the parent** and not at subsidiaries, assume shared access and do not mark as a gap.
3. **Identify missing products:** Highlight only those portfolios/product lines absent across both parent and all subsidiaries combined.
4. **Propose adjacent offerings:** Based on Cegal’s portfolio and expertise, suggest additional services (cloud, cybersecurity, analytics, etc.).

This ensures fully accurate segment priority and group-level evaluation.

---

### Product Hierarchy from Raw File
Columns:
- **Primary:** `Product:Portfolio`
- **Secondary:** `Product:Product line`

**Ignore:** Portfolios labeled `admin`.

---

### Customer Segmentation Logic
Segments read only from **`Account Name: Customer Segment`**:
1. Strategic
2. Premium
3. Priority
4. E-sell (or default if field blank)

---

### Quick Reference: Adjacent Services
- **Cloud Services** – Multi-cloud migration, orchestration.
- **Cybersecurity** – Threat detection, compliance.
- **Data & Analytics** – AI, forecasting.
- **Application Management** – ERP modernization.
- **Consulting & Advisory** – Strategic roadmaps.
