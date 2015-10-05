---
layout: post
title: Removing Fields from Grouping Area| PivotGrid | Wpf | Syncfusion
description: Removing Fields from Grouping Area
platform: wpf
control: PivotGrid
documentation: ug
---


# Removing Fields from Grouping Area


Essential PivotGrid provides a remove button for fields in grouping area. This helps you to remove the fields from _Grouping Area._ Removed fields will be stored in the _PivotTable Field List_ dialog for later use. Instead of dragging the field from _Grouping Area_, you can click the remove button to achieve this.

### Property Table

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
AllowRemove </td><td>
Enables remove button. </td><td>
Dependency </td><td>
Boolean  </td><td>
NA</td></tr>
</table>


### Enabling Remove Button 

To add the remove button for fields in grouping area, set the _AllowRemove_ property to true. By default this is set to false. 

The following code illustrates how to enable the remove button:

{% tabs %}
{% highlight C# %}  



this.pivotGrid1.GroupingBar.AllowRemove = true;

{% endhighlight %} 

{% highlight vbnet %}  



Me.pivotGrid1.GroupingBar.AllowRemove = True

{% endhighlight %}
{% endtabs %}

![](Features_images/Features_img24.png)



### Sample Link

A demo of this feature is available in the following location:

#### Windows 7/Vista

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\PivotAnalysis.Wpf\Samples\Grouping Bar\Grouping Bar Demo_

#### Windows XP

SystemDrive:\Syncfusion\EssentialStudio\<version_number>\ BI\WPF\PivotAnalysis.Wpf\Samples\Grouping Bar\Grouping Bar Demo_ 


