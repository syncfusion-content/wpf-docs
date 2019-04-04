---
layout: post
title: Styling and formatting using MDX query | OLAP Grid | Syncfusion
description: Section helps to know how to apply styling and formatting to grid cells using MDX query in OLAP Grid control | Syncfusion
platform: wpf
control: OlapGrid
documentation: ug
---

# Styling and formatting using MDX query

In OlapGrid, grid cells can be formatted and styled by using **Cell Properties** in MDX (Multidimensional Expressions). Cell Properties contains information about the content and format of cells in a multidimensional data source, such as OLAP cube. Following cell properties are supported for styling and formatting the grid cell values.

    * BACK_COLOR - Indicates the background color of the cell value.
    * FORE_COLOR - Indicates the foreground color of the cell value.
    * FONT_SIZE - Indicates the font size of the cell value.
    * FONT_NAME - Indicates the font family of the cell value.
    * FONT_FLAGS - Indicates the font effect of the cell value.

N> *FONT_FLAGS* cell property applies bitmask detailing effects on the font. It is defined by using constant values (i.e., 1- Bold, 2- Italic, 4- Underline and 8- Strikeout). For example, if the value for FONT_FLAGS property is set as 3, then both the effects of Bold and Italic will be applied to the particular cell.

The following code sample illustrates how to apply formatting and styling for grid cells using MDX query.

{% tabs %}

{% highlight C# %}

string formattedMDXQuery = @"WITH MEMBER [Measures].[Customers] As [Measures].[Customer Count] , FORE_COLOR=RGB(255,255,255), BACK_COLOR = IIF([Measures].[Customer Count]>1500,RGB(0,255,0), RGB(220,0,0)) MEMBER [Measures].[Internet Sales] As [Measures].[Internet Sales Amount], BACK_COLOR=IIF([Measures].[Internet Sales Amount]>7000000,RGB(255,255,0),RGB(255,255,255)) SELECT NON EMPTY({ { Hierarchize({[Customer].[Customer Geography].[Country] })} * {[Measures].[Customers],[Measures].[Internet Sales]}} ) dimension properties member_type ON COLUMNS, NON EMPTY({ { Hierarchize({[Date].[Fiscal].[Fiscal Year]})}} ) dimension properties member_type ON ROWS FROM[Adventure Works] CELL PROPERTIES VALUE, FORMAT_STRING, FORMATTED_VALUE, FORE_COLOR, FONT_FLAGS, FONT_SIZE, FONT_NAME, BACK_COLOR";

{% endhighlight %}

{% highlight VB %}

Dim formattedMDXQuery As String = "WITH MEMBER [Measures].[Customers] As [Measures].[Customer Count] , FORE_COLOR=RGB(255,255,255), BACK_COLOR = IIF([Measures].[Customer Count]>1500,RGB(0,255,0), RGB(220,0,0)) MEMBER [Measures].[Internet Sales] As [Measures].[Internet Sales Amount], BACK_COLOR=IIF([Measures].[Internet Sales Amount]>7000000,RGB(255,255,0),RGB(255,255,255)) SELECT NON EMPTY({ { Hierarchize({[Customer].[Customer Geography].[Country] })} * {[Measures].[Customers],[Measures].[Internet Sales]}} ) dimension properties member_type ON COLUMNS, NON EMPTY({ { Hierarchize({[Date].[Fiscal].[Fiscal Year]})}} ) dimension properties member_type ON ROWS FROM[Adventure Works] CELL PROPERTIES VALUE, FORMAT_STRING, FORMATTED_VALUE, FORE_COLOR, FONT_FLAGS, FONT_SIZE, FONT_NAME, BACK_COLOR"

{% endhighlight %}

{% endtabs %}

![To format the OlapGrid using MDX query](Styling-and-Formatting-using-MDX-query-images/Formatted_Grid.png)

A sample demo is available at the following location:

{System Drive}:\Users\<User Name>\AppData\Local\Syncfusion\EssentialStudio\<Version Number>\WPF\OlapGrid.WPF\Samples\Defining Reports\MDX Query