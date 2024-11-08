## Calculated Fields 
### Total Sales
- Order Date (Year)
```
YEAR([Order Date])
```
- Parameter to select year
  - Data Type: Integer
  - Current value: Recent year from the data source
  - Add values from Order Date (Year) - The calculated Field
  - List to display all years
  - Display Format: Remove Thousand separators and decimals
- Current Year Sales
```
IF YEAR([Order Date]) = [Select Year] THEN [Sales] END
```
- Previous Year Sales
```
IF YEAR([Order Date]) = [Select Year] - 1 THEN [Sales] END
```
- % Difference Sales
```
(SUM([CY Sales]) - SUM([PY Sales]))/SUM([PY Sales])
```

Change to percent -> Right-click on the calculated field -> Default Properties -> Number Format -> Percentage -> Remove Decimals -> OK

Format the % Diff Sales -> Right-click -> Format -> ▲0.00%; ▼-0.00%;

- Min/Max Sales
```
IF SUM([CY Sales]) = WINDOW_MAX(SUM([CY Sales]))
THEN SUM([CY Sales])
ELSEIF SUM([CY Sales]) = WINDOW_MIN(SUM([CY Sales]))
THEN SUM([CY Sales])
END
```

Under All in the Marks pane: Change the SUM([CY Sales]) to {SUM([CY Sales])} and [% Diff Sales] to {[% Diff Sales]} to return from revenue range to total revenue for the selected year

- Current Year
```
[Select Year]
```
- Previous Year
```
[Select Year] - 1
```

Convert both to dimension

Tooltip
```
Sales of <MONTH(Order Date)>, <ATTR(Current Year)>: <SUM(CY Sales)>
Sales of <MONTH(Order Date)>, <ATTR(Previous Year)>: <SUM(PY Sales)>
Sales Differences: <AGG(% Diff Sales)>
Highest/Lowest Sales: <AGG(Min/Max Sales)>
```

#### Repeat for Profit and Quantity

### Sub-Category Comparison
- KPI CY Sales less than PY Sales
```
IF SUM([CY Sales]) < SUM([PY Sales]) THEN '⬤' ELSE '' END
```
- Tooltip
```
Sub-Category:	<Sub-Category>
Sales of <ATTR(Current Year)>:	<SUM(CY Sales)>
Sales of  <ATTR(Previous Year)>:	<SUM(PY Sales)>
% Diff Sales:	<AGG(% Diff Sales)>
Profit of <ATTR(Current Year)>:	<SUM(CY Profit)>
```
### Weekly Trends for Sales & Profit
- Current Year Sales
```
IF SUM([CY Sales]) > WINDOW_AVG(SUM([CY Sales])) THEN 'Above'
ELSE 'Below' END
```
- Current Year Profit
```
IF SUM([CY Profit]) > WINDOW_AVG(SUM([CY Profit])) THEN 'Above'
ELSE 'Below' END
```
- Tooltip
```
No of Week:	<WEEK(Order Date)>
Sales of <ATTR(Current Year)>:	<SUM(CY Sales)>
<AGG(KPI Sales AVG)> the average
Profit of <ATTR(Current Year)>:	<SUM(CY Profit)>
<AGG(KPI Profit Avg)> the average
```
## Customer Dashboard
- CY Sales per Customer
```
SUM([CY Sales]) / COUNTD([CY Customers])
```
