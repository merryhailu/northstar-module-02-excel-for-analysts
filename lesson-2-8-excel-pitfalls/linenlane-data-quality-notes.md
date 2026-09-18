Compose a one-page memo Beatrix could read. Title it "Data Quality Notes" or similar. Structure:

# What I checked. Brief description of the audits run.

I reviewed the LinenLane workbook for data quality and consistency across the dashboard and supporting analyses. I checked all six dashboard KPIs against independent recalculations, reviewed the source ranges for all 3 PivotTables, verified the sources for all 4 charts, and recomputed the Lesson 2.7 A/B test conversion rates using fresh COUNTIFS formulas.

# What I found. Numbered list of issues, with severity and impact.

- Dashboard KPIs — Low severity: All six dashboard KPIs match independent recalculations. However, the Average Refunds KPI is calculated from 1,483 numeric refund amounts, while Return Count includes all 1,500 return records.
- PivotTable sources — Low severity: All PivotTables include the current source rows, with 0 rows excluded. However, some PivotTables use fixed ranges, and some later-added columns fall outside those ranges.
- Chart sources — Low severity: All pivot-backed charts are connected to current PivotTables, and no stale pivot output was found. Two charts use duplicate PivotTables rather than the dashboard PivotTables originally expected, but the duplicate pivots currently contain identical source rows, so the charts remain current. The practice histogram should be treated as a copy, with the maintained version in the returns sheet.
- A/B test conversion rates — No issue: Fresh COUNTIFS calculations exactly matched the original conversion rates: Variant A = 1.85% and Variant B = 2.10%. No mismatch was found.

# What I fixed. What's already corrected in the current workbook.

I created audit worksheets documenting the KPI, PivotTable source, and chart-source checks. I also created a fresh A/B test comparison using COUNTIFS to independently verify the original conversion rates. No PivotTable or chart connections were changed because the current results are valid.

# What's still pending. What requires Beatrix's input or a follow-up engagement.

The main follow-up items are deciding whether the returns KPIs should use a consistent population and whether the pasted KPI values should be converted to live formulas.

# What I'd want for next time. Recommendations for LinenLane's data team to prevent recurrence (e.g., "the CSV exports should preserve SKU column as Text type to prevent auto-conversion").

For future workbook updates, I recommend using Excel Tables for PivotTables so new rows and columns are included automatically. KPI calculations should also use live formulas where possible rather than pasted values. This would reduce the risk of outdated results and make future dashboard refreshes more reliable.

# summary

I reviewed the LinenLane workbook for data quality and consistency by auditing all six dashboard KPIs, PivotTables, charts, and the A/B test analysis. All six KPIs matched independent recalculations, although Average Refunds uses 1,483 numeric refund amounts while Return Count includes all 1,500 return records. All PivotTables include the current source rows with no rows omitted, but some use fixed ranges that exclude later-added columns. All pivot-backed charts use current PivotTables, and fresh COUNTIFS calculations confirmed the original A/B conversion rates of 1.85% for Variant A and 2.10% for Variant B. I documented these checks in audit worksheets, and no chart or PivotTable connections required changes. For future updates, I recommend using Excel Tables and live formulas to make the workbook easier to maintain and reduce the risk of outdated results.
