## Customer Analysis Workflow

When performing customer analysis with DeltaAnalyzer, the **single source of truth** is the most recent raw dataset located in SharePoint at this fixed location:

> **Canonical Raw Folder:** [BiS-Scrmt / raw](https://pangearocks.sharepoint.com/:f:/s/BiS-Scrmt/IgDyXq112Nz0TqPJ1BX4fqUuAadfi--aqdQjzqohw8JmsoM)

### Live Data Requirement
- All queries into this folder **must be executed live** (real-time calls), avoiding any cached or stale results.
- Always target this exact folder for true raw data. **Do not attempt tenant-wide searches or heuristic matching.**

### Workflow Steps
1. **Retrieve all current customers:**
    - Identify the latest report file in the above folder.
    - Parse columns strictly:
        - Parent account group from **`ParentAccountName`**.
        - Customer segment from **`Account Name: Customer Segment`**.
          - If blank → **E-sell** default.
          - No guessing or inference.
        - Product structure from `Product:Portfolio` and `Product:Product line`.
        - Ignore portfolios labeled `admin`.
2. **Analyze product setup per account group:**
    - Roll up child accounts under their parent.
    - If any subsidiary has a product → mark as covered for parent group.
    - If parent has product and subsidiary lacks → assume shared → not a gap.
3. **Identify missing products:** Only those absent across the combined group.
4. **Output Recommendations:**
    - List missing product portfolios and lines.
    - Suggest adjacent services (Cloud, Cybersecurity, Data & AI, App Mgmt, Consulting).

### Important Enforcement
- Folder path for raw data is **hardcoded in process**, never optional.
- No cached lookups are allowed; each analysis session must run against **live data** from this folder.

---

Refer to this location for every analysis or refresh cycle:  
[Canonical Raw Data Folder](https://pangearocks.sharepoint.com/:f:/s/BiS-Scrmt/IgDyXq112Nz0TqPJ1BX4fqUuAadfi--aqdQjzqohw8JmsoM)
