## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, always use the data from the most recent **raw file** in the SharePoint `raw` folder as the single source of truth.

### Workflow Steps
1. **Retrieve all current customers:** Extract customer records from the latest report (`report<timestamp>.xls` or `.csv`) in the `raw` folder.
    - Consolidate by **Parent Account** to ensure subsidiaries roll up to the main corporate account.
    - Include **Customer Segment** (explained below) for prioritization.
2. **Analyze product setup per account:** Review each parent account's current product mix against known Cegal offerings **(excluding internal-use portfolios such as `admin`, which should never be considered for gap analysis)**.
3. **Identify missing products:** Highlight any gaps where the customer does not utilize products or services typically relevant to their segment or current usage pattern.
4. **Propose adjacent offerings:** Based on Cegal’s portfolio and expertise, suggest complementary or adjacent products and services that could bring added value (e.g., consulting, managed cloud, cybersecurity enhancements).

This process ensures recommendations are data-driven and aligned with Cegal’s strategic offerings while leveraging up-to-date information.

---

### Product Hierarchy from Raw File
The raw opportunity report includes columns defining the active product set:
- **Primary Column:** `Product:Portfolio` — top-level category representing the product portfolio.
- **Secondary Column:** `Product:Product line` — child category tied to one portfolio only.

**Grouping Logic:**
1. Group all records by **Product:Portfolio**.
2. Within each portfolio, group by **Product:Product line**.

**Ignore:**
- Any portfolio labeled as **`admin`** (used solely for internal hour tracking). It should **not** be included in gap or coverage analysis.

---

### Customer Segmentation
To prioritize opportunities, accounts are categorized into **segments** by importance:
1. **Strategic** — High-value, top-priority clients with broad engagement potential.
2. **Premium** — Significant customers with strong growth opportunities.
3. **Priority** — Mid-tier accounts requiring focused offerings to expand services.
4. **E-sell** — Digital-first or small accounts suitable for scalable online interaction.

Segment influences recommendation urgency and expected revenue opportunity.

---

### Quick Reference: Adjacent Services
When analyzing gaps, consider these service areas:
- **Cloud Services:** Migration, optimization, and multi-cloud management.
- **Cybersecurity:** Compliance, identity, and threat prevention.
- **Data & Analytics:** Predictive analytics, governance, and AI solutions.
- **Application Management:** ERP optimization, modernization, application hosting.
- **Consulting & Advisory:** Digital transformation, enterprise architecture, strategy design.
