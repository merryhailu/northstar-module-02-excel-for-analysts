# LinenLane Workbook First-Look Notes

Date: 09/04/2026
Reviewer: Meron Welderufael

## Tab: sales_2024

- Row count: 28000
- Column headers (with brief description):
  order_id — Format ORD-#####. One row per order.
  order_date — Real Excel dates covering 1 January to 31 December 2024.
  customer_id — Format CUST-####. Joins to customer_segments, but not every ID is there.
  sku — Format LL-####. Joins to inventory. A few SKUs do not follow the pattern.
  units — Integer quantity ordered.
  unit_price — Decimal price per unit at the time of order.
  gross_revenue — Units multiplied by unit price.
- Date range: 1/1/2024 - 12/31/2024
- Suspicious or unclear: No
- Questions for follow-up:

## Tab: inventory

- Row count: 280
- Column headers (with brief description):
  sku — Joins to sales_2024 and returns.
  product_name — Lookup formulas expect this in column 2.
  category — Bedding, Bath, Kitchen, Decor, Lighting, Storage.
  current_stock — Integer snapshot, not historical.
  unit_cost — Decimal cost to LinenLane, not the sale price.
  supplier — Supplier name, city, and state packed into one comma-separated field.
- Date range: -
- Suspicious or unclear: No
- Questions for follow-up:

## Tab: marketing_spend

- Row count: 60
- Column headers (with brief description):
  month — January through December.
  channel — Different marketing channels.
  spend — Amount spent on marketing.
  campaigns_count — Number of marketing campaigns.
- Date range: -
- Suspicious or unclear: No
- Questions for follow-up:

## Tab: customer_segments

- Row count: 7490
- Column headers (with brief description):
  customer_id — Not unique. The tab contains duplicate rows.
  segment — VIP, Regular, New, Lapsed. There is no stored Unknown segment.
  lifetime_value — Cumulative spend as of the CRM export.
  first_order_date — Stored as a date serial number, not a formatted date.
  email_subscribed — Boolean marketing opt-in status.
- Date range: -
- Suspicious or unclear: No
- Questions for follow-up:

## Tab: returns

- Row count: 1500
- Column headers (with brief description):
  return_id — Format RET-#####. Not strictly unique.
  order_id — Joins to sales_2024. Every value resolves.
  sku — Joins to inventory. A few values do not resolve.
  return_reason — Typed by hand over several years. Not standardized.
  refund_amount — Decimal amount. Some rows are zero or blank.
  return_date — Real Excel dates.
  units_returned — Integer number of units in the return.
- Date range: -
- Suspicious or unclear: No
- Questions for follow-up:
