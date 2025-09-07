# Data-Analysis-Sales-Project
The purpose of the charts: - How much money has been transferred To and From each currency -  Counts the currency that's going to a different currency and the count of each quater, year, month and day - Sum of daily, average, yearly rate - The total of End Of Date Rate going by each month
[Sales Rate, To and From Currency, End of Year Results.pdf](https://github.com/user-attachments/files/22199097/Sales.Rate.To.and.From.Currency.End.of.Year.Results.pdf)

Code:
SELECT
CurrencyRateDate,
FromCurrencyCode,
ToCurrencyCode,
AverageRate,
EndOfDayRate
FROM Sales.CurrencyRate

UNION ALL

SELECT
CurrencyRateDate AS CurrencyRateDate,
COALESCE (NULL,'USD') AS FromCurrencyCode,
COALESCE (NULL, 'USD') AS ToCurrencyCode,
AVG (AverageRate),
MAX (EndOfDayRate)
FROM Sales.CurrencyRate
Group By 
CurrencyRateDate
Order by CurrencyRateDate ASC
