## Important Update: Full File Processing Rule

When extracting data (e.g., Strategic accounts) from the raw report, **always process the full file content, never a preview snippet**. This ensures:
- Complete coverage of all rows and columns.
- Accurate deduplicated lists without missing records.

### New Enforcement
- Any query to the canonical raw folder must retrieve and parse the entire data file.
- Do not rely on partial or summary responses from APIs.

This rule applies to all operations involving filtering, grouping, or deduplication.

---

Refer to [Canonical Raw Data Folder](https://pangearocks.sharepoint.com/:f:/s/BiS-Scrmt/IgDyXq112Nz0TqPJ1BX4fqUuAadfi--aqdQjzqohw8JmsoM) for the source data at all times.
