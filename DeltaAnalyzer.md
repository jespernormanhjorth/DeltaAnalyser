## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, always use the data from the most recent **raw file** in the SharePoint `raw` folder as the single source of truth.

### Workflow Steps
1. **Retrieve all current customers:** Extract customer records from the latest report (`report<timestamp>.xls` or `.csv`) in the `raw` folder.
2. **Analyze product setup per customer:** Review each customer's current product mix against known Cegal offerings.
3. **Identify missing products:** Highlight any gaps where the customer does not utilize products or services typically relevant to their segment or current usage pattern.
4. **Propose adjacent offerings:** Based on Cegal’s portfolio and expertise, suggest complementary or adjacent products and services that could bring added value to the customer (e.g., new consulting services, managed cloud, cybersecurity enhancements).

This process ensures recommendations are data-driven and aligned with Cegal’s strategic offerings while leveraging up-to-date information.

---

### Product Hierarchy from Raw File
The raw opportunity report includes columns defining the active product set. To build the hierarchy and understand Cegal's portfolio structure:
- **Primary Column:** `Product:Portfolio` — top-level category representing the product portfolio.
- **Secondary Column:** `Product:Product line` — child category tied to one portfolio.

**Grouping Logic:**
1. Group all records by **Product:Portfolio**.
2. Within each portfolio, group by **Product:Product line** (each product line belongs to exactly one portfolio).

This hierarchy is the structural basis for gap analysis and targeted recommendations.

---

### Quick Reference: Adjacent Services
When analyzing gaps, consider the following Cegal service categories as potential upsell or cross-sell opportunities:
- **Cloud Services:** Migration, optimization, and management for Azure, AWS, and hybrid environments.
- **Cybersecurity:** Threat detection, compliance, identity management, and secure operations.
- **Data & Analytics:** Advanced analytics, data governance, and AI-driven insights.
- **Application Management:** ERP optimization, modernization strategies, and application hosting.
- **Consulting & Advisory:** Enterprise architecture, digital transformation, and IT strategy development.
