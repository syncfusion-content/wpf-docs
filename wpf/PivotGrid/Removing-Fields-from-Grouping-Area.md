---
layout: post
title: Removing Fields from Grouping Area
description: Removing Fields from Grouping Area
platform: wpf
control: PivotGrid
documentation: ug
---


## Removing Fields from Grouping Area


Essential PivotGrid provides a remove button for fields in grouping area. This helps you to remove the fields from _Grouping Area._ Removed fields will be stored in the _PivotTable Field List_ dialog for later use. Instead of dragging the field from _Grouping Area_, you can click the remove button to achieve this.

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td><td>
{{ '**Reference links**' | markdownify }}</td></tr>
<tr>
<td>
AllowRemove </td><td>
Enables remove button. </td><td>
Dependency </td><td>
Boolean  </td><td>
NA</td></tr>
</table>


#### Enabling Remove Button 

To add the remove button for fields in grouping area, set the _AllowRemove_ property to true. By default this is set to false. 

The following code illustrates how to enable the remove button:

{% highlight C# %}  

[C#]

this.pivotGrid1.GroupingBar.AllowRemove = true;

{% endhighlight %} 

{% highlight vbnet %}  

[VB]

Me.pivotGrid1.GroupingBar.AllowRemove = True

{% endhighlight %}

![](Features_images/Features_img24.png)



#### Sample Link

A demo of this feature is available in the following location:

#### Windows 7/Vista

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\PivotAnalysis.Wpf\Samples\Grouping Bar\Grouping Bar Demo_

#### Windows XP

SystemDrive:\Syncfusion\EssentialStudio\<version_number>\ BI\WPF\PivotAnalysis.Wpf\Samples\Grouping Bar\Grouping Bar Demo_ 


