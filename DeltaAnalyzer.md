## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, always use the data from the most recent **raw file** in the SharePoint `raw` folder as the single source of truth.

### Workflow Steps
1. **Retrieve all current customers:** Extract customer records from the latest report (`report<timestamp>.xls` or `.csv`) in the `raw` folder.
    - Consolidate by **Parent Account** to ensure subsidiaries roll up to the main corporate account.
    - Include **Customer Segment** (explained below) for prioritization.
2. **Analyze product setup per account:** Review each parent account's current product mix against known Cegal offerings (excluding internal-use portfolios such as `admin`). When checking child accounts:
    - If **any subsidiary has a product**, treat that product as present for the entire parent account group (since shared usage is possible or likely).
    - If **a product exists only at the parent** and not at the subsidiary, assume coverage extends to the subsidiary (do not flag as a gap).
3. **Identify missing products:** Highlight only those portfolios/product lines absent across both parent and all subsidiaries combined.
4. **Propose adjacent offerings:** Based on Cegal’s portfolio and expertise, suggest complementary or adjacent products and services that could bring added value (e.g., consulting, managed cloud, cybersecurity enhancements).

This ensures a true **group-level coverage assessment**, avoiding false positives from internal registration practices.

---

### Product Hierarchy from Raw File
Columns:
- **Primary:** `Product:Portfolio` (top-level category).
- **Secondary:** `Product:Product line` (second-level category, tied to one portfolio).

**Ignore:**
- Any portfolio labeled as `admin` (internal use).

**Grouping:**
1. Aggregate by `Product:Portfolio`.
2. For each, group by `Product:Product line`.

---

### Customer Segmentation
Segments:
1. **Strategic** — High-priority, broad potential.
2. **Premium** — Significant, growth-oriented.
3. **Priority** — Mid-tier expansion accounts.
4. **E-sell** — Small/digital-first accounts.

---

### Quick Reference: Adjacent Services
- **Cloud Services** — Migration, optimization, multi-cloud.
- **Cybersecurity** — Compliance, identity, threat mitigation.
- **Data & Analytics** — Predictive analytics, AI insights.
- **Application Management** — ERP modernization, hosting.
- **Consulting & Advisory** — Digital transformation, strategy.
