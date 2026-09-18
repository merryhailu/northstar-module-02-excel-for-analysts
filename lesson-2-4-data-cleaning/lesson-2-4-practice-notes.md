# which two or three channels have the most variant-splitting?

Email had the most variant-splitting because it appeared as two separate versions due to an extra space. After cleaning, these variants were combined into one Email channel, giving a more accurate total spend.

# Compare the baseline and cleaned pivots:

# How many distinct channels are there now versus before?

Before cleaning, there were 6 distinct channels. After cleaning the channel names using functions TRIM and PROPER, there are now 5 distinct channels. The reduction occurred because one of the channels had an extra leading space, which caused Excel to treat it as a separate channel. Cleaning standardized the names and allowed the records to be correctly grouped.

# Which channels had their totals change the most (because their variants were being counted separately and are now aggregated)?

The Email channel had the most significant change. Before cleaning, Email spending was split between two separate entries because one version contained an extra space. One entry had approximately $55K in spending and the other approximately $51K. After cleaning, both entries were recognized as the same channel and were combined, resulting in approximately $107K in total Email spending.

This shows why standardizing text fields is important: without cleaning, the pivot table underreported the total for Email and made the channel appear as two separate channels.

# Did any single channel's total change by more than 20%?

Yes. The Email channel changed significantly—by more than 20%—because its spending was previously split between two versions of the same channel. After cleaning and combining the two Email entries, the total increased to approximately $107K. This was not a real increase in marketing spending; it was a correction that made the pivot table reflect the true combined Email spending.

# Summary

During this exercise, I found that the channel column contained inconsistent variations of the same channel name. In particular, the Email channel appeared in two different forms: one as “Email” and another with an extra space before the word “ Email” Because Excel treats these as different text values, their spending was initially counted separately in the pivot table.

To clean the channel names, I used the formula TRIM(PROPER()). The TRIM function removed extra spaces, while PROPER standardized the capitalization. I used these functions together to make the channel names consistent before creating the cleaned pivot table.

Before cleaning, there were 6 distinct channels. After cleaning, there were 5 distinct channels, because the two Email variations were recognized as the same channel and combined. The Email channel had the largest swing in total spend. Before cleaning, one Email variation had approximately $55K in spending and the other had approximately $51K. After cleaning, these were combined into approximately $107K of total Email spending. This was not an actual increase in spending; rather, it corrected the way the spending was grouped and represented in the pivot table.

This exercise showed me that cleaning data before aggregating is important because inconsistent values can split one category into multiple groups and lead to inaccurate totals and misleading business insights.
