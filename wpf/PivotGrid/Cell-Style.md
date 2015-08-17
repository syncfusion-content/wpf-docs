---
layout: post
title: Cell Style 
description: Cell Style
platform: wpf
control: PivotGrid
documentation: ug
---


## Cell Style

The following properties of a grid cell can be customized so that the grid appears in a custom style rather than the default one.

_Property Table_

<table>
<tr>
<td>
{{ '**Property Name**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Value it Accepts**' | markdownify }}</td><td>
{{ '**Reference link**' | markdownify }}</td></tr>
<tr>
<td>
Background</td><td>
Gets or sets the background color of a grid cell.</td><td>
Brush</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontFamily</td><td>
Gets or sets the font family of a grid cell.</td><td>
FontFamily</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontSize</td><td>
Gets or sets the font size of a grid cell.</td><td>
int</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontWeight</td><td>
Gets or sets the font weigh of a grid cell.</td><td>
FontWeight</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Foreground</td><td>
Gets or sets the foreground color of a grid cell.</td><td>
Brush</td><td>
-</td><td>
-</td></tr>
</table>


Column, row, summary, and value cells of a grid can be formatted independently using the following properties:

 * ColumnHeaderCellStyle – Specifies the style for column headers.
 * RowHeaderCellStyle – Specifies the style for row headers.
 * SummaryCellStyle – Specifies the style for summary cells.
 * ValueCellStyle  –  Specifies the style for value cells.



{% highlight C# %} 

[C#] 

    		// Specifying the Background color for Grid column header

            this.PivotGridControl1.ColumnHeaderCellStyle.Background = new SolidColorBrush(Color.FromRgb(175, 209, 255));

            // Specifying the Background color for Grid row header

            this.PivotGridControl1.RowHeaderCellStyle.Background = new SolidColorBrush(Color.FromRgb(175, 209, 255));

            // Specifying the Background color for Grid summary cell

            this.PivotGridControl1.SummaryCellStyle.Background = new SolidColorBrush(Color.FromRgb(206, 225, 248)); 

 {% endhighlight %} 



{% highlight vbnet %}  

[VB]

' Specifying the Background color for Grid column header

Me.PivotGridControl1.ColumnHeaderCellStyle.Background = New SolidColorBrush(Color.FromRgb(175, 209, 255))

' Specifying the Background color for Grid row header

Me.PivotGridControl1.RowHeaderCellStyle.Background = New SolidColorBrush(Color.FromRgb(175, 209, 255))

' Specifying the Background color for Grid summary cell

Me.PivotGridControl1.SummaryCellStyle.Background = New SolidColorBrush(Color.FromRgb(206, 225, 248))


{% endhighlight %}


The formatting set in the above code generates the following PivotTable.

![](Features_images/Features_img2.png)



