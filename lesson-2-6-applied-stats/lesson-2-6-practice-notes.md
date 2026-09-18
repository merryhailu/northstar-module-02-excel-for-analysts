# The means, sample sizes, and CIs you computed for each return reason

- Damaged: Mean = $100.74, n = 313, 95% CI [$92.73, $108.74]
- Wrong Size: Mean = $82.36, n = 183, 95% CI [$70.78, $93.94]

# The t-test p-value

t(352) = 2.57, two-tailed p = 0.0105

# Your one-sentence memo phrasing of the result

Damaged returns had a significantly higher average refund amount ($100.74, 95% CI [$92.73, $108.74]) than Wrong Size returns ($82.36, 95% CI [$70.78, $93.94]), t(352) = 2.57, p = .010 (two-tailed, Welch’s t-test). The results indicate a statistically significant difference, with a moderate practical effect despite some overlap between the confidence intervals.

# One observation from the histograms about the distribution shape that would affect how you'd interpret the means

Both distributions are right-skewed, with most refund amounts concentrated in the lower range $25-$75 and a long right tail extending to approximately $400–$500. The high-value outliers can pull the mean upward, so the median may provide a better representation of the typical refund amount. However, with relatively large sample sizes (n = 313 and n = 183), the t-test remains reasonably robust to this skew when comparing the means.

# One sentence on whether the difference (if there is one) is practically significant for a home-goods e-commerce business

An ~$18 average difference in refund amount is likely practically meaningful at scale —
if Damaged returns are also more frequent or growing, this gap could represent a
non-trivial recurring cost (e.g., 313 Damaged returns × $18 extra ≈ $5,600+ in this
sample alone), making it worth investigating whether damaged-item refunds are being
over-issued or whether packaging/shipping improvements could reduce the underlying
damage rate.
