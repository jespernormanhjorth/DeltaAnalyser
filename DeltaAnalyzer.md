## Column Name Update: Ultimate Parent Name

Effective immediately, the raw data column previously referenced as `ParentAccountName` is now correctly named:

**`Account Name: Ultimate Parent Name`**

### Enforcement
- All grouping and analysis at group-level must now use **`Account Name: Ultimate Parent Name`** for determining the top hierarchical account.
- Any legacy references to `ParentAccountName` must be retired.
- Still apply the same roll-up logic (subsidiaries under their ultimate parent).

---

Updated rule is mandatory for all DeltaAnalyzer workflows.
