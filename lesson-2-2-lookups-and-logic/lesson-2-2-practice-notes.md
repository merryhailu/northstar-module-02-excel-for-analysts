# Which lookup function you used in each column and why (1 sentence each)

I used the XLOOKUP function in all columns because of its simplicity, flexibility, and ability to easily retrieve the required information from the source data.

# One row that surprised you

No rows particularly surprised me during the analysis.

# Any error codes you encountered and how you fixed them

I encountered #N/A errors in the category column because some categories in the inventory data were not available in the source data. I handled these missing values by using the IFNA function to replace the errors with an appropriate ("data not in source") message.

# Whether you used IFNA or IFERROR for column N, and why

I used IFNA because the incorrect rows were specifically returning #N/A, while the other rows were returning the correct values. Therefore, I chose IFNA as the most appropriate solution. If I encountered other types of errors, I would use IFERROR to handle them.
