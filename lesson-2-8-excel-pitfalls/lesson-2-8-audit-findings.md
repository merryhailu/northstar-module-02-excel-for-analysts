## Finding 1

**Tab/Cell**: inventory
**Category**: (auto-conversion / floating-point / date / truncation / other)
auto conversion
**Description**: Excel automatically converted Mar-12,jan-15 and oct-07 sku into number because it interpreted it as a date.
**Impact on analysis**:
**Recommended fix**: Before pasting/importing SKUs, format the entire SKU column as Text first. This prevents Excel from converting SKU values into dates.

## Finding 2

**Tab/Cell**: sales_2024
**Category**: (auto-conversion / floating-point / date / truncation / other)
floating-point
**Description**: Excel automatically round the gross revenue to 2 round so it makes a diffeence when we sum.
**Impact on analysis**: comparing or displaying values that depend on floating-point arithmetic
**Recommended fix**: explicit rounding is required.

## Finding 3

**Tab/Cell**: sales_2024.order_date, marketing_spend.month, customer_segments.first_order_date, returns.return_date, email_campaign_q4_2024.sent_date
**Category**: (auto-conversion / floating-point / date / truncation / other)
date
**Description**: inconsistent date formatting
**Impact on analysis**: biasing any cross-tab analysis / inconsistency
**Recommended fix**: Power Query, explicitly set the type of every date column to Date

## AI scan

**Tool**: Claude
**Date**:
**Sample provided**: [describe what you pasted]
**Findings reported**: [AI's numbered list]
**Verified findings**: [which you confirmed]
**Hallucinated findings**: [which you rejected]
**Missed findings**: [things you found that the AI didn't]
