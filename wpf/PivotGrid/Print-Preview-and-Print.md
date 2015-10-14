---
layout: post
title: Print Preview and Print| PivotGrid | Wpf | Syncfusion
description: Print Preview and Print
platform: wpf
control: PivotGrid
documentation: ug
---

# Print Preview and Print

Essential PivotGrid for WPF provides in-built support for printing and print preview. This feature provides a print dialog that allows you to preview the output and make any modifications if required before printing.

### Use Case Scenarios

Printing option allows you to have a hard copy of the PivotGrid.



### Properties



<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type}</td><td>
Reference links</td></tr>
<tr>
<td>
PrintHeader </td><td>
Add/Remove the Header in the Print Preview dialog</td><td>
Attached Property</td><td>
Boolean</td><td>
-</td></tr>
<tr>
<td>
PrintFooter</td><td>
Add/Remove the Footer in the Print Preview dialog</td><td>
Attached Property</td><td>
Boolean</td><td>
-</td></tr>
</table>

### Methods



<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th><th>
Reference links</th></tr>
<tr>
<th>
ShowPrintPreview</th><th>
Shows the Print Preview window with empty template and default title</th><th>
(Window Win)</th><th>
-</th><th>
Void</th><th>
-</th></tr>
<tr>
<th>
ShowPrintPreview</th><th>
Shows the Print Preview window with templates for header, footer and default title.</th><th>
(DataTemplate headerTemplate, DataTemplate footerTemplate, Window win)</th><th>
-</th><th>
Void</th><th>
-</th></tr>
<tr>
<th>
ShowPrintPreview</th><th>
Shows the Print Preview window with templates for header, footer and user defined title</th><th>
(DataTemplate headerTemplate, DataTemplate footerTemplate, string title, Window win)</th><th>
</th><th>
</th><th>
</th></tr>
</table>

### Adding Print Preview and Print for PivotGrid in an Application

This feature has been implemented to provide printing support for PivotGrid control along with grouping bar. You can use the method “ShowPrintPreview” to preview the PivotGrid control before printing by opening the PrintPreview Window. The properties “PrintHeader” and “PrintFooter” helps to add or remove the header and footer information while printing.

Following code example shows how to set the PrintHeader and PrintFooter properties.

{% tabs %}
{% highlight xml %} 



<syncfusion:PivotGridControl x:Name="pivotGrid1" syncfusion:PrintSettings.PrintFooter="True" syncfusion:PrintSettings.PrintHeader="True" VerticalAlignment="Top" ItemSource="{Binding ProductSalesData}">


{% endhighlight %} 

Following code example shows how to call ShowPrintPreview methods.

{% highlight C# %} 



    //	Shows the Print Preview window with templates for header, footer and with user defined title          
	this.pivotGrid1.ShowPrintPreview((DataTemplate)this.Resources["HeaderTemplate"], (DataTemplate)this.Resources["FooterTemplate"],"Print Preview", this);



    //	Shows the Print Preview window with empty template and default title this.pivotGrid1.ShowPrintPreview(this);



    //	Shows the Print Preview window with templates for header, footer and with default title.            
	this.pivotGrid1.ShowPrintPreview((DataTemplate)this.Resources["HeaderTemplate"], (DataTemplate)this.Resources["FooterTemplate"], this);


 {% endhighlight %} 
{% endtabs %}

### Print Preview

The following screenshot displays a Print Preview window along with a header and footer:

![](Features_images/Features_img59.png)



Print Preview
{:.caption}

The Print Preview window provides the following options:  “Zooming”, “Page Settings”,”Print”. 

You can use these options to get a magnified view of the PivotGrid or to change the page setup or to print the PivotGrid 
control respectively.

### Zooming

Click on the “Zoom” drop-down button in the print preview window and select the desired percentage to magnify the print 
preview in PivotGrid. You can choose from various preset zoom level options such as 50%, 100%, 200% or 400%.

The following screen shot shows the zooming options dropdown in the Print preview window:

![](Features_images/Features_img60.png)



Zooming
{:.caption}

### Page Settings

Click the “PageSettings” button in the print preview to change the page settings while printing.

The following screenshot shows the Page setting icon in a Print preview window:

![](Features_images/Features_img61.png)



Page settings
{:.caption}

### Print 

Click the “Print” button in the print preview window to print the PivotGrid content.

The following screen shot shows the Print icon in the print preview window.

![](Features_images/Features_img62.png)



Print option
{:.caption}

### Sample Link

#### Windows 8/7/Vista

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version number>\BI\WPF\PivotAnalysis.Wpf\Printing\Printing Demo



