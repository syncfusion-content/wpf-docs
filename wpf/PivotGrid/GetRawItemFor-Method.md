---
layout: post
title: GetRawItemFor Method 
description: GetRawItemFor Method 
platform: wpf
control: PivotGrid
documentation: ug
---

## GetRawItemFor Method 

The GetRawItemFor method is used to obtain the list of raw items for value cell, total cell or grand total cell in PivotGrid. This method has been implemented in the PivotEngine which can be used independently from the PivotGrid control. 

#### Use Case Scenarios

The user can utilize this method when they want to know the raw item from which the Pivot Cell’s value is obtained and also they can get the raw items of the summary cells.

![](Features_images/Features_img48.png)



Methods


_Method Table_

<table>
<tr>
<th>
 {{ '**Method**' | markdownify }}</th><th>
 {{ '**Description**' | markdownify }}</th><th>
 {{ '**Parameters**' | markdownify }}</th><th>
 {{ '**Return Type**' | markdownify }}</th></tr>
<tr>
<th>
GetRawItemFor </th><th>
This method allows you to get the raw item of the selected cell (Value cell or Summary cell). </th><th>
int row, int column</th><th>
List(object)</th></tr>
</table>


#### Sample Link

You can find a sample in the following location:

{Installed Drive}:\Users\<UserName>\AppData\Local\Syncfusion\EssentialStudio\<Version>\BI\Wpf\PivotAnalysis.Wpf\Samples\Interactive Features\DrillThroughDemo

### Adding GetRawItemFor method  to an Application 

Adding the GetRawItemFor method to an application is described in the following steps:

1. Add the GridData control to the application.
{% highlight xml %} 
<syncfusion:GridDataControl x:Name="gridDataControl1" />
{% endhighlight %} 

2. Enable Hyperlink to Value and Total Cells.

{% highlight C# %}  

this.pivotGridControl1.ValueCellStyle.IsHyperlinkCell = true;       
     this.pivotGridControl1.SummaryCellStyle.IsHyperlinkCell = true;
	 
{% endhighlight %}


3. Call the GetRawItemFor method inside the Hyperlink click event and bind the result of GetRawItemFor() to GridDataControl.

{% highlight C# %}  
void pivotGridControl1_HyperlinkCellClick(object sender, Syncfusion.Windows.Controls.PivotGrid.HyperlinkCellClickEventArgs e)        

{           

 this.gridDataControl1.ItemsSource = this.pivotGridControl1.PivotEngine.GetRawItemsFor(e.RowColumnIndex.RowIndex, e.RowColumnIndex.ColumnIndex);       

 }
 
{% endhighlight %}
 
 
