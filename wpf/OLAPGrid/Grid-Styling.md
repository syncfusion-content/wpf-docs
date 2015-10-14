---
layout: post
title: Grid Styling| OLAP Grid | Wpf | Syncfusion
description: grid styling 
platform: wpf
control: OLAP Grid
documentation: ug
---

# Grid Styling 

Grid can be formatted by the following way:

* By Grid Style Dialog
* By Configuring the properties of Cell Style

## Grid Style Dialog


The Grid Style Dialog is used to format the cells of OlapGrid. Styling can be applied to Column Header, Row Header, Summary cell and value cell. The following properties of Header and Summary cells can be formatted:

* Background Color
* Foreground Color
* Font Name 
* Font Size

The following were the properties of Value cells that can be formatted:

* Font Name
* Font Style
* Font Color
* Font Size



![Grid Style Dialog](Grid-Styling_images/Grid-Styling_img1.png)


The following code snippet will launch the Grid style dialog:

{% tabs %}
  {% highlight c# %}

   



// To Display Style Dialog

this.OlapGrid1.ShowStyleDialog();


    {% endhighlight %}





  {% highlight vbnet %}

    



' To Display Style Dialog

Me.OlapGrid1.ShowStyleDialog()

    {% endhighlight %}


{% endtabs %}


## Configuring the properties of Cell Style

The following properties of Grid cell can be customized, so that the grid appears in a custom style rather than the default one:



<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference Links</th></tr>
<tr>
<td>
Background</td><td>
Gets or sets the Background color of Grid cell.</td><td>
Brush</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontFamily</td><td>
Gets or sets the Font family of Grid cell.</td><td>
FontFamily</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontSize</td><td>
Gets or sets the Font size of Grid cell.</td><td>
int</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FontWeight</td><td>
Gets or sets the Font weigh of Grid cell.</td><td>
FontWeight</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Foreground</td><td>
Gets or sets the Foreground color of Grid cell.</td><td>
Brush</td><td>
-</td><td>
-</td></tr>
</table>


The Column, Row, Summary and Value cells of Grid can be formatted independently using the following properties:

* ColumnHeaderStyle
* RowHeaderStyle
* SummaryColumnStyle
* SummaryRowStyle
* ValueCellsStyle

{% tabs %}
  {% highlight c# %}

    



// Specifying the Background color for Grid column header

this.OlapGrid1.ColumnHeaderStyle.Background = new SolidColorBrush(Color.FromRgb(175, 209, 255));

// Specifying the Background color for Grid row header

this.OlapGrid1.RowHeaderCellStyle.Background = new SolidColorBrush(Color.FromRgb(175, 209, 255));

// Specifying the Background color for Grid summary cell

this.OlapGrid1.SummaryColumnStyle.Background = new SolidColorBrush(Color.FromRgb(206, 225, 248)); 

    {% endhighlight %}





  {% highlight vbnet %}

    



' Specifying the Background color for Grid column header

Me.OlapGrid1.ColumnHeaderStyle.Background = New SolidColorBrush(Color.FromRgb(175, 209, 255))

' Specifying the Background color for Grid row header

Me.OlapGrid1.RowHeaderCellStyle.Background = New SolidColorBrush(Color.FromRgb(175, 209, 255))

' Specifying the Background color for Grid summary cell

Me.OlapGrid1.SummaryColumnStyle.Background = New SolidColorBrush(Color.FromRgb(206, 225, 248))

    {% endhighlight %}


{% endtabs %}


The Value cell text alignment can be changed using the following property of OlapGrid,

  {% highlight c# %}

    



// Specifying the Value Cell TextAlignment as Center

this.OlapGrid1.ValueCellTextAlignment = HorizontalAlignment.Center;

    {% endhighlight %}







### Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Exporting\Exporting Grid Demo

