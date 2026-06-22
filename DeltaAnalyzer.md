## Customer Opportunities Source

All current customer opportunity data must be retrieved from the **latest report file located in the `raw` folder of the SharePoint library**. These files (typically `.xlsx` or `.csv`) contain structured information such as account names, products, quantities, and pricing. The report with the most recent timestamp represents the authoritative dataset for opportunity analysis.

### Location and Filename
The reports are stored in the following location:
- **SharePoint Library:** `raw` folder under the Business Intelligence or DeltaAnalyser data area.
- **File Naming Convention:** Typically named as `report<timestamp>.xls` or `report<timestamp>.csv` (e.g., `report1782123747544.xls`). This naming includes an auto-generated numeric timestamp ensuring the most recent file can be identified easily.
