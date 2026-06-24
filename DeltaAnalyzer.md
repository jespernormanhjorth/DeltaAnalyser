## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, always use the data from the most recent **raw file** in the SharePoint `raw` folder as the single source of truth.

### Workflow Steps
1. **Retrieve all current customers:** Extract customer records from the latest report (`report<timestamp>.xls` or `.csv`) in the `raw` folder.
    - Consolidate records using **`ParentAccountName`** as the authoritative parent account column to group subsidiaries under the correct parent.
    - Determine **Customer Segment** strictly from the column **`Account Name: Customer Segment`**:
        - Use the exact value provided (Strategic, Premium, Priority, E-sell).
        - If the field is blank, default to **E-sell**.
        - Never infer or assume a higher rank than what is listed.
2. **Analyze product setup per account group:** Review the parent account's combined product mix against known Cegal offerings (ignore any `admin` portfolio). Subsidiary handling:
    - If **any subsidiary has a product**, treat it as covered for the entire parent group.
    - If a product exists only at the parent, assume coverage extends to subsidiaries (do not flag as a gap).
3. **Identify missing products:** Highlight only those portfolios/product lines absent across the entire parent group (parent plus all subsidiaries).
4. **Propose adjacent offerings:** Suggest missing product portfolios and complementary services based on Cegal’s service reference.

This ensures accurate group-level evaluation and strict segment prioritization.

---

### Product Hierarchy from Raw File
Relevant Columns:
- **Parent Account:** `ParentAccountName` (mandatory for grouping)
- **Portfolio:** `Product:Portfolio`
- **Product Line:** `Product:Product line`

Ignore:
- Any portfolio labeled `admin` (internal use only).

Grouping:
- Roll up all child records under `ParentAccountName` and aggregate product coverage before detecting gaps.

---

### Customer Segmentation Logic
From raw file column **`Account Name: Customer Segment`**:
1. Strategic
2. Premium
3. Priority
4. E-sell (or default if blank)

---

### Quick Reference: Adjacent Services
- **Cloud Services** – Multi-cloud migration, orchestration
- **Cybersecurity** – Compliance, identity, threat detection
- **Data & Analytics** – AI-driven insights, data governance
- **Application Management** – ERP optimization, hosting
- **Consulting & Advisory** – Strategy design, digital transformation
