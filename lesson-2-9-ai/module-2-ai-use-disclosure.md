# AI Use Disclosure: Module 2 Lesson 2.9 Guided Example

## Interaction 1

**Task**: Generate a formula for an "Early High-Value" classification column.

**Tool**: Copilot, accessed 09/16/2026.

**Prompt**:
Write a formula that labels this cell as 'Early High-Value' if the order_date in B2 is between January 1, 2024 and January 30, 2024, and gross_revenue in G2 is greater than $500. Otherwise, 'Standard.

**Original output**:
=IF(AND(B2>=DATE(2024,1,1),B2<=DATE(2024,1,30),G2>500),"Early High-Value","Standard")

**Verification**:

- Cell references: B2 and G2 both exist and hold the expected data. Confirmed.
- Function calls: IF, AND, DATE. All valid Excel functions. Confirmed.
- Boundary conditions: tested rows on January 1 ($750 revenue produced "Early High-Value"), January 31 ($750 revenue produced "Standard"), January 15 ($300 revenue produced "Standard"), and January 15 ($750 revenue produced "Early High-Value"). All matched expectations.

**Decision**: Accepted the formula as-is. Pasted into column R2 and filled down.

## Interaction 2

**Task**: Explain what this Excel formula does in plain English.

**Tool**: Copilot, accessed 09/16/2026.

**Prompt**:
=IF(G2<25, "Tiny", IF(G2<75, "Small", IF(G2<200, "Medium", IF(G2<500, "Large", "XL"))))
Explain this formula

**Original output**:
This formula classifies sales_2024!G2 into revenue tiers:
Gross revenue Result
Under $25 Tiny
$25–$74.99 Small
$75–$199.99 Medium
$200–$499.99 Large
$500+ XL
It is a good candidate for the simpler IFS function:
=IFS(G2<25,"Tiny",G2<75,"Small",G2<200,"Medium",G2<500,"Large",TRUE,"XL")
It is also a good candidate for a lookup table if the thresholds may change frequently.

**Verification**:

- Cell references: G2 exist and hold the expected data. Confirmed.
- Function calls: Nested IF valid Excel functions. Confirmed.
- Boundary conditions: tested, matches correct
  Tiny: under $25(G2<25)
  Small: $25 to $74
  Medium: $75 to $199
  Large: $200 to $499
  XL: $500 and up. All matched expectations.
- Good candidate: Instead of using multiple nested IF statements with many parentheses, the IFS function would be a simpler and cleaner option.

**Decision**: The explanation is right and useful.

## Interaction 3

**Task**: Recommend a chart type for a specific dashboard question.

**Tool**: Copilot, accessed 09/16/2026.

**Prompt**:
What chart type would best show how refund amounts are distributed across product categories for a non-technical executive audience?

**Original output**:
A sorted horizontal bar chart is best for a non-technical executive audience.

Category: product category
Value: total refund amount
Sort highest to lowest and add currency data labels.
Avoid a box-and-whisker chart unless they specifically need the statistical spread of individual refunds—it is less intuitive for executives.

**Verification**:

- Comparing values across categories : calls for bar or column. Correct.
- box-and-whisker chart noted as the to avoid. Correct
- Recommendation includes sorting (a specific senior-analyst touch). Correct.

**Decision**: Accept the horizontal bar recommendation.Build it inside the workbook.

## Interaction 4

**Task**:Write a Power Query M expression for a custom column.

**Tool**: Copilot, accessed 09/16/2026.

**Prompt**:
Generate a Power Query M custom column that returns ‘High Refund Ratio’ when refund_amount is more than 50% of the order’s gross revenue; otherwise return ‘Normal’.

**Original output**:
Use this Power Query M step after merging tbl_returns with sales_2024 and expanding gross_revenue:
= Table.AddColumn(
#"Expanded sales_2024",
"high_refund_ratio_flag",
each if [gross_revenue] <> null
and [gross_revenue] > 0
and [refund_amount] > [gross_revenue] \* 0.5
then "High Refund Ratio"
else "Normal",
type text
)
Tabs used: tbl_returns and sales_2024, matched using order_id. This safely treats missing or zero revenue as Normal.

**Verification**:

- Syntax: valid M code for a Custom Column step; no syntax errors on execution. Confirmed.
- Field references: [gross_revenue] and [refund_amount] both exist data. Confirmed.
- Null handling: [gross_revenue] <> null and [gross_revenue] > 0 checks correctly prevent errors and division-style misclassification on missing or zero revenue. Confirmed.
- Gap identified: [refund_amount] has no equivalent null check. If [refund_amount] is null for any row, the comparison [refund_amount] > [gross_revenue] \* 0.5 evaluates to null, and M's if statement requires a strict true/false — this throws "Expression.Error: The condition must be a logical value," failing the entire query rather than just mislabeling the row. Not confirmed as safe.
- Boundary conditions tested: refund_amount exactly 50% of gross_revenue (e.g., $250 refund on $500 revenue) produced "Normal" as expected (strict > required); refund_amount just above 50% (e.g., $250.01 on $500) produced "High Refund Ratio." Confirmed.

**Decision**: Rejected as-is due to the unhandled null refund_amount case. Revised formula before applying:

= Table.AddColumn(
#"Expanded sales_2024",
"high_refund_ratio_flag",
each if [gross_revenue] <> null
and [gross_revenue] > 0
and [refund_amount] <> null
and [refund_amount] > [gross_revenue] \* 0.5
then "High Refund Ratio"
else "Normal",
type text
)

Revised version applied as the custom column step.

## Interaction 5

**Task**: Verify whether this formula correctly returns the second-highest
value in a column of numbers. Identify any edge cases or issues.

**Tool**: tool #1 - Copilot,tool #2 - claude, accessed 09/16/2026.

**Prompt**:
Write a formula that returns the second-highest gross_revenue value in column G.

**Original output**:
tool #1 response:
=LARGE(G2:G28001,2)

tool #2 responds:
The formula =LARGE(G2:G28001, 2) is correct for returning the second-highest value in the specified range, and using a bounded range like this (rather than the full column G:G) is good practice, since it avoids unnecessary calculation overhead and makes clear exactly which rows are included; however, it still carries a few risks depending on the nature of the data within that range.

Duplicate values: if the highest value in G2:G28001 appears more than once, LARGE(G2:G28001, 2) will return that same duplicated value again rather than the next distinct lower value, so this returns the second-largest entry, not the second-largest unique value.
Range boundary accuracy: this formula assumes the data occupies exactly rows 2 through 28001 — if new rows are added beyond row 28001, or if the actual data range shifts, the formula won't automatically capture the new values, so it's worth confirming the range matches the current data extent or converting the data to an Excel Table with structured references (e.g., =LARGE(Table1[gross_revenue], 2)) so the range auto-expands.
Fewer than two numeric values: if the range contains fewer than two numeric entries (e.g., mostly blanks or text), the formula will return a #NUM! error, so wrapping it in IFERROR is a good safeguard if that's a realistic possibility.
Distinct-value alternative: if the goal is the second-highest unique value rather than the second-highest entry, a formula like =LARGE(UNIQUE(G2:G28001),2) (in versions supporting UNIQUE) would better match that intent.
Blank or text cells within range: LARGE correctly ignores blank cells and text values within the range, so mixed data types won't cause errors — this is a strength of the formula, not a concern.

**Verification**:

- LARGE is a valid Excel function and the formula works correctly.
- G2:G28001 contains the expected gross revenue data.
- The range is correct for the current data, but new rows would need to be added manually.
- With duplicate values, LARGE(...,2) returns the second-highest entry, not the second-highest distinct value.
- Blanks and text are ignored, and the formula handles ranking as expected.
- If you want the second-highest distinct value, use =LARGE(UNIQUE(G2:G28001),2).

**Decision**: two-AI verification pattern.It gives you a deeper view of the formula.
