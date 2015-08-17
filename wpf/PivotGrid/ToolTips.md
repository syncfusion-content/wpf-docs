---
layout: post
title: ToolTips
description: ToolTips
platform: wpf
control: PivotGrid
documentation: ug
---

## ToolTips

ToolTips can be set to individual cells. The ToolTip information has the cell value and its respective row and column data and it is set in the style’s Tag property. Using a simple Boolean property, it can be set to the PivotGrid. A ToolTip’s skin will be set depending upon the theme set for the PivotGrid. Also, users can customize the ToolTip skin at the sample level. ToolTip text can be localized for its “Value”, “Row”, and “Column” text. Users can also set custom text for ToolTips.

#### Use Case Scenarios

ToolTips can be used to show the data of any cell so that user can get the cell’s full information, e.g., the row and column on which it depends.

### Properties

_Properties Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td></tr>
<tr>
<td>
TooltipEnabled</td><td>
Enable/disable the ToolTip for the PivotGrid control.</td><td>
Dependency</td><td>
Boolean </td></tr>
<tr>
<td>
TooltipEnabled</td><td>
Enable/disable the ToolTip for individual cell styles (ColumnHeaderStyle, RowHeaderStyle, ValueCellStyle, SummaryCellStyle, SummaryHeaderStyle)</td><td>
Dependency</td><td>
Boolean </td></tr>
<tr>
<td>
CustomToolTipTemplateKey</td><td>
Gets/sets the DataTemplate key for custom ToolTips for the entire PivotGrid control.</td><td>
CLR</td><td>
String</td></tr>
<tr>
<td>
CustomToolTipTemplateKey</td><td>
Gets/sets DataTemplate key for custom ToolTip for individual cell styles (ColumnHeaderStyle, RowHeaderStyle, ValueCellStyle, SummaryCellStyle, SummaryHeaderStyle)</td><td>
CLR</td><td>
String</td></tr>
</table>


### Sample Link

A sample is available in the Essential Studio WPF dashboard in the following location.

PivotAnalysis > Appearance > ToolTipDemo

{InstalledDrive}\Users\ {User}\AppData\ Local \Syncfusion\ EssentialStudio\{Installed Version}\BI\WPF\PivotAnalysis.Wpf\Samples\Appearance \Tooltip Demo

### Adding ToolTip to an Application 

To show the ToolTip in the PivotGrid control you need to set the PivotGrid control’s TooltipEnabled property to true. This is the master property which controls all the styles of the ToolTip property. The following code explains its usage.

{% highlight C# %} 

[C#]

//Enable Tooltip for PivotGridControl

this.pivotGrid1.ToolTipEnabled = true;

 {% endhighlight %} 

{% highlight vbnet %} 

[VB]

//Enable Tooltip for PivotGridControl

Me.pivotGrid1.ToolTipEnabled = True

{% endhighlight %} 

You can set the appearance of ToolTips with respect to their styles. Each style has its own ToolTipEnabled property. These properties help to set the appearance individually for each style. The following code explains its implementation.

{% highlight C# %}  

[C#]

//Enable Tooltip for RowHeaderCellStyle

this.pivotGrid1.RowHeaderCellStyle.ToolTipEnabled = true;

//Enable Tooltip for ColumnHeaderCellStyle

this.pivotGrid1.ColumnHeaderCellStyle.ToolTipEnabled = true;

//Enable Tooltip for ValueCellStyle

this.pivotGrid1.ValueCellStyle.ToolTipEnabled = true;

//Enable Tooltip for SummaryHeaderStyle

this.pivotGrid1.SummaryHeaderStyle.ToolTipEnabled = true;

//Enable Tooltip for SummaryCellStyle

this.pivotGrid1.SummaryCellStyle.ToolTipEnabled = true;

{% endhighlight %} 



{% highlight vbnet %} 

[VB]

//Enable Tooltip for RowHeaderCellStyle

Me.pivotGrid1.RowHeaderCellStyle.ToolTipEnabled = True

//Enable Tooltip for ColumnHeaderCellStyle

Me.pivotGrid1.ColumnHeaderCellStyle.ToolTipEnabled = True

//Enable Tooltip for ValueCellStyle

Me.pivotGrid1.ValueCellStyle.ToolTipEnabled = True

//Enable Tooltip for SummaryHeaderStyle

Me.pivotGrid1.SummaryHeaderStyle.ToolTipEnabled = True

//Enable Tooltip for SummaryCellStyle

Me.pivotGrid1.SummaryCellStyle.ToolTipEnabled = True

{% endhighlight %} 



![C:/Users/arulraja/Desktop/Toolto.png](Features_images/Features_img37.png)



![C:/Users/arulraja/Desktop/TooltipColumn.png](Features_images/Features_img38.png)



![C:/Users/arulraja/Desktop/TooltipRow.png](Features_images/Features_img39.png)



Custom data templates can be set to the PivotGrid control’s ToolTip. To do so, you need to write a data template and bind the style’s Tag property and set the key to the PivotGrid control’s CustomToolTipTemplateKey property. The following code explains its implementation.

{% highlight C# %}   

[C#]

//Set the Custom DataTemplate for PivotGridControl’s Tooltip

this.pivotGrid1.CustomToolTipTemplateKey = "CustomTemplateTooltip";

{% endhighlight %}

{% highlight vbnet %} 

[VB]

//Set the Custom DataTemplate for PivotGridControl’s Tooltip

Me.pivotGrid1.CustomToolTipTemplateKey = "CustomTemplateTooltip"


{% endhighlight %} 


![C:/Users/arulraja/Desktop/TooltipCustom.png](Features_images/Features_img40.png)



You can set the data template of ToolTip with respect to its styles. Each style has its own CustomToolTipTemplateKey property. These properties help to set the appearance individually for each style. The following code explains its implementation.

{% highlight C# %}  

[C#]

//Set the Custom DataTemplate for ColumnHeaderCellStyle Tooltip

this.pivotGrid1.ColumnHeaderCellStyle.CustomToolTipTemplateKey = "ColumnTemplateTooltip";

//Set the Custom DataTemplate for RowHeaderCellStyle Tooltip

this.pivotGrid1.RowHeaderCellStyle.CustomToolTipTemplateKey = "RowTemplateTooltip";

//Set the Custom DataTemplate for 	ValueCellStyle Tooltip

this.pivotGrid1.ValueCellStyle.CustomToolTipTemplateKey = "ValueTemplateTooltip";

//Set the Custom DataTemplate for 	SummaryHeaderStyle Tooltip

this.pivotGrid1.SummaryHeaderStyle.CustomToolTipTemplateKey = "SummaryHeaderTemplateTooltip";

//Set the Custom DataTemplate for SummaryCellStyle Tooltip

this.pivotGrid1.SummaryCellStyle.CustomToolTipTemplateKey = "SummaryCellTemplateTooltip";

{% endhighlight %} 

{% highlight vbnet %} 

[VB]

//Set the Custom DataTemplate for ColumnHeaderCellStyle Tooltip

Me.pivotGrid1.ColumnHeaderCellStyle.CustomToolTipTemplateKey = "ColumnTemplateTooltip"

//Set the Custom DataTemplate for RowHeaderCellStyle Tooltip

Me.pivotGrid1.RowHeaderCellStyle.CustomToolTipTemplateKey = "RowTemplateTooltip"

//Set the Custom DataTemplate for 	ValueCellStyle Tooltip

Me.pivotGrid1.ValueCellStyle.CustomToolTipTemplateKey = "ValueTemplateTooltip"

//Set the Custom DataTemplate for 	SummaryHeaderStyle Tooltip

Me.pivotGrid1.SummaryHeaderStyle.CustomToolTipTemplateKey = "SummaryHeaderTemplateTooltip"

//Set the Custom DataTemplate for SummaryCellStyle Tooltip

Me.pivotGrid1.SummaryCellStyle.CustomToolTipTemplateKey = "SummaryCellTemplateTooltip"

{% endhighlight %} 

![C:/Users/arulraja/Desktop/TooltipColumnCustom.png](Features_images/Features_img41.png)



