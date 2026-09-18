# Which lookup function you'd reach for in different situations

For different situations, I would use INDEX-MATCH when I need more flexibility or have a more complex lookup. For ordinary lookups, I would use XLOOKUP because it is simple, flexible, and easy to understand.

# What error codes you saw and how you debugged them

I used the IFNA function to handle #N/A errors that occurred when lookup values were not found in the source data. By wrapping my XLOOKUP formula with IFNA, I was able to identify missing records and replace the error with a clear message such as “Data not in source.” This made it easier to identify and troubleshoot missing data without leaving error codes in the final dataset.

# What the AI got right or wrong on the IFS conversion

The AI's IFS conversion worked as I wanted, but I still verified the formula myself. I learned that < and <= are very different when working with data tiers, so it is important to check the conditions carefully to make sure the ranges do not overlap or leave gaps.

# One question you still have about lookups or logic

I don't have any additional questions about lookups or logic at this time.
