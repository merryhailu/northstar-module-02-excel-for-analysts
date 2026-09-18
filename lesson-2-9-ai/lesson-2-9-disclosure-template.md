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
