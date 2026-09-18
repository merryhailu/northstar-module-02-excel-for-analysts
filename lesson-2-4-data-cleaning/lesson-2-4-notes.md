# Every column you cleaned and what cleaning was applied

Return reasons: I used TRIM, PROPER, and SUBSTITUTE to clean the return reason text by removing extra spaces, standardizing capitalization, and replacing unnecessary punctuation such as periods and hyphens.

Supplier: I used Text to Columns to separate the supplier's city and state into separate columns.

Return reasons: I used Find and Replace to change abbreviations such as “cust” to “customer change mind” for consistency.

Units and unit prices: I used Conditional Formatting to flag values that were negative or below zero so they could be reviewed.

# Whether you preserved the original or replaced in place

For some cleaning steps, I preserved the original data because I wanted the appropriate team to review and make the final decision before changing the source information. For duplicate records that contained the same data across all columns, I removed the duplicates because they did not provide additional information.

# Any flagged rows you didn't yet fix (the negative-units, zero-price rows)

Yes. I did not change the rows with negative units or zero prices because these values may have a valid business explanation, such as a refund, adjustment, or another transaction recorded in a different dataset. I would first verify the information with the related data before making any changes.

# The AI's findings and your verification notes

Used Claude on 09/09/2026 to identify data quality patterns in a 50-row sample of return_reason. Claude correctly identified case inconsistencies, trailing periods, leading whitespace, and inconsistent separators. Verified each against the full column. Cleaning formulas from Step 2 address all four issues.
