## Data Cleaning
- Rename tables
- Replace the data type of region in the location table with country/region

## Calculated Fields 
### Total Sales KPI
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

#### _Repeat for Profit and Quantity_

### Sub-Category Comparison
- KPI CY Sales < than PY Sales
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
- KPI Sales AVG
```
IF SUM([CY Sales]) > WINDOW_AVG(SUM([CY Sales])) THEN 'Above'
ELSE 'Below' END
```
- KPI Profit AVG
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

### Total Sales per Customer KPI 
- CY Sales per Customer
```
SUM([CY Sales]) / COUNTD([CY Customers])
```

- PY Sales per Customer
```
SUM([PY Sales]) / COUNTD([PY Customers])
```

- % Diff Sales per Customer
```
([CY Sales per Customer] - [PY Sales per Customer]) / [PY Sales per Customer]
```

Change to percent -> Right-click on the calculated field -> Default Properties -> Number Format -> Percentage -> Remove Decimals -> OK

Format the % Diff Sales per Customer -> Right-click -> Format -> ▲0.00%; ▼-0.00%;

- Min/Max Sales per Customer
```
IF [CY Sales per Customer] = WINDOW_MAX([CY Sales per Customer])
THEN [CY Sales per Customer] 
ELSEIF [CY Sales per Customer] = WINDOW_MIN([CY Sales per Customer])
THEN [CY Sales per Customer]
END
```

Under All in the Marks pane: Change the SUM([CY Sales per Customer]) to {SUM([CY Sales per Customer])} and [% Diff Sales per Customer] to {[% Diff Sales per Customer]} to return from revenue range to total sales per customer for the selected year

### Total Orders KPI
- % Diff Orders
```
(COUNTD([CY Orders]) - COUNTD([PY Orders])) / COUNTD([PY Orders])
```

Change to percent -> Right-click on the calculated field -> Default Properties -> Number Format -> Percentage -> Remove Decimals -> OK

Format the % Diff Orders -> Right-click -> Format -> ▲0.00%; ▼-0.00%;

- Min/Max Orders
```
IF COUNTD([CY Orders]) = WINDOW_MAX(COUNTD([CY Orders]))
THEN COUNTD([CY Orders])
ELSEIF COUNTD([CY Orders]) = WINDOW_MIN(COUNTD([CY Orders]))
THEN COUNTD([CY Orders])
END
```

Under All in the Marks pane: Change the SUM([CY Orders]) to {SUM([CY Orders])} and [% Diff Orders] to {[% Diff Orders]} to return from orders range to total orders for the selected year

#### _Repeat for Total Customers KPI_

### Customer Distribution
- No of Orders per Customer
```
{FIXED [Customer ID] : COUNTD([CY Orders])}
```

Convert to Dimension
