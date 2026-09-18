# The three pivot tables you built

Revenue by Category × Month – Shows total revenue for each product category across different months.
Orders by Segment × Tier – Shows the number of orders for each customer segment and tier.
Returns Reason – Shows return reason, including return counts and refund amounts and its average with the calculated field.

# The slicer behavior (what fields it controls, what pivots it connects to)

The slicer controls the Category field. It connects to the Revenue by Category × Month and Orders by Segment × Tier PivotTables, as well as the dashboard. When I select a category, the connected PivotTables and dashboard update to show the selected category.

# The calculated field formula

The intended return rate was calculated as return_amount / gross_revenue, but because we could not match the gross revenue values to the returns data in this exercise, we used SUM and AVERAGE on the available data instead.

# What the AI suggested for chart types and what you accepted

Used Claude on sep 8,2026 to recommend chart type for segment-trends question. Claude recommended a line chart with rationale matching what Lesson 2.3 teaches. Verified the recommendation against the question; accepted.

# One question you still have about pivot table

I don't have any questions about PivotTables at this time. Everything is clear to me.
