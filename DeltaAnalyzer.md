# Delta Analyzer – Gap Analysis Instruction Set

---

## 1. Purpose
Explain objective: Identify coverage gaps in Salesforce RAW data by Product Line.

---

## 2. Data Sources
- Location: SharePoint → `AI Agent Documents/Delta Analyser/Data/Raw/`
- File naming pattern: `report*.csv`
- Key columns required:
  - Account name
  - Product: Product Line
  - Optional: Total Price, Quantity

---

## 3. Core Principle
- **Product Line = MASTER CATEGORY**
- Ignore Product/Portfolio for grouping
- Blank Product Line → tag as "Uncategorized"

---

## 4. Step-by-Step Process
### Step 1: Data Fetch
Locate latest RAW CSV.

### Step 2: Normalize and Master List
Extract unique Product Lines → master set.

### Step 3: Build Coverage
Group by account → Owned vs Missing.

### Step 4: Generate Coverage Matrix
Account vs Product Lines → ✔ or ✖.

### Step 5: Compute Metrics
- Missing_Count
- Gap Score %

### Step 6: Identify Top 10 Opportunities
Rank by Missing_Count desc.

---

## 5. Deliverables
- **Summary Table**:
  - Account | Owned Product Lines | Missing Product Lines | Missing_Count | Gap Score%
- **Coverage Matrix**:
  - Row: Account | Columns: Product Lines (✔/✖)
- **Top 10 Leaderboard**:
  - Rank | Account | Missing_Count | Missing Lines | Gap Score%

---

## 6. Output Formats
- **CSV/XLSX** with 3 sheets:
  1. Summary
  2. Coverage Matrix
  3. Top 10
- Default filename: `GapReport_<YYYY-MM-DD>.xlsx`

---

## 7. Quick Commands (Agent Trigger Keywords)
- "Perform gap analysis"
- "Salesforce RAW coverage report"
- "Find biggest gaps"
- "Top 10 opportunities"

---

## 8. Ranking Logic
- Primary: Missing_Count
- Secondary: Revenue weighting (future option)

---

## 9. Example Outputs
### Leaderboard:
| Rank | Account Name            | Missing_Count | Missing Product Lines            |
|------|--------------------------|---------------|-----------------------------------|
| 1    | BW Energy USA Mgmt Inc  | 6             | energyx, cetegra care, oracle... |

---

## 10. Edge Cases
- If no valid Product Line → return "No data."
- If single Product Line in Master → gap = N/A.

# DeltaAnalyser

## Purpose
Describe what DeltaAnalyser is and why it exists.

---

## Scope
Define what is included and excluded.

---

## Core Concepts
Define key terms clearly and consistently.

Example:
- Delta
- Analysis scope
- Data source
- Output

---

## Workflow

### Step 1 – Input
Describe what data is needed.

### Step 2 – Processing
Describe how analysis is performed.

### Step 3 – Output
Describe results and how they are used.

---

## Rules & Constraints
List:
- limitations
- assumptions
- mandatory steps

---

## Use Cases
Examples of where DeltaAnalyser is used.

---

## Known Gaps / To Be Improved
(Optional section the agent can help improve)

---

## Version
Last updated: YYYY-MM-DD
Version: X.X

---


