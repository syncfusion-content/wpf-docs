---
layout: post
title: 13423-Custom-Calculations
description: 1.3.4.23 custom calculations
platform: wpf
control: PivotGridControl
documentation: ug
---

# Custom Calculations

**CalculationType** is an enumerator defined in the PivotComputationInfo class which is used to specify the type of the calculation. The various calculation types that are used for performing calculations are as follows.
 
* **NoCalculation** - Remove the custom calculations and restore to original values (Default value). Display the pivot values as default value
* **PercentageOfGrandTotal** - Displays a value cell as a percentage of grand total of all value cells of Pivot Engine.
* **PercentageOfColumnTotal** - Displays all value cells in each column as a percentage of its corresponding column total. 
* **PercentageOfRowTotal** - Displays all value cells in each row as a percentage of its corresponding row total.
* **PercentageOfParentColumnTotal** - Displays a value cell as a percentage of parent column item values.
* **PercentageOfParentRowTotal** - Displays a value cell as a percentage of parent row item values.
* **PercentageOfParentTotal** - Displays a value cell as a percentage of Base Field (Parent Row/Column Total).
* **Index** - Displays a value cell as an index value based on PivotEngine generation.
* **Formula** - Displays a calculation based on a well formed algebraic expression involving other calculations.
* **PercentageOf** - Displays values as a percentage of the value of the Base item in the Base field.
* **DifferenceFrom** - Displays values as the difference from the value of the Base item in the Base field.
* **PercentageOfDifferenceFrom** - Displays values as the percentage difference from the value of the Base item in the Base field.
* **RunningTotalIn** - Displays the value for successive items in the Base field as a running total.
* **PercentageOfRunningTotalIn** - Calculates the value for successive items in the Base field that are displayed as a running total as a percentage
* **RankSmallestToLargest** - Displays the rank of selected values in a specific field, listing the smallest item in the field as 1, and each larger value will have a higher rank value.
* **RankLargestToSmallest** - Displays the rank of selected values in a specific field, listing the largest item in the field as 1, and each smaller value will have a higher rank value.

