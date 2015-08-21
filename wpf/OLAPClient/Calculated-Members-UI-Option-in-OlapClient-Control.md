---
layout: post
title: Calculated-Members-UI-Option-in-OlapClient-Control
description: calculated members ui option in olapclient control
platform: wpf
control: OLAP Client 
documentation: ug
---

# Calculated Members UI Option in OlapClient Control

This feature allows users to enable/disable, create, and edit the calculated members on the fly in the current OLAP report or current view of 
the OlapClient control. Using this feature, users can define measures and members as they wish using the Calculated Member Editor (as shown in 
the following image). The Calculated Member Editor dialog can be opened by clicking the button available in the toolbar of the OlapClient 
control.

![](Calculated-Members-UI-Option-in-OlapClient-Control_images/Calculated-Members-UI-Option-in-OlapClient-Control_img1.png)



## Use Case Scenarios

This feature can be used to add one or more measures that will be derived from the existing measure collection.

For example, users can define the discount on a measure called Order Quantity (and its unique name is [Measures].[Order Quantity]), by 
expressing the calculated measure “[Measures].[Order Quantity] + (0.1 * [Measures].[Order Quantity])”.

Properties

_Property Table_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
IsCalculatedMembersEnabled</td><td>
Gets or sets a value indicating whether calculated members are to be enabled</td><td>
Dependency </td><td>
Boolean</td></tr>
</table> 


## Sample Link

1. Open the Syncfusion Dashboard.
2. Navigate to Business Intelligence.
3. Select WPF.
4. Click Run Selected Samples.
5. Navigate to OlapClient.
6. Expand the Product Showcase feature (this feature list is on the left side as a navigation tree).
7. Click the Calculated Members Demo item.
8. Click Run Sample button. 

## Adding Calculated Members UI Option to an Application 


The following code sample explains how to enable or disable the Calculated Members UI option in an OlapClient application:

{% highlight C# %}  



////Enable the Calculated Members in current view of the OlapClient.



this.olapClient1.IsCalculatedMembersEnabled = true; 



//if set false, then it will be disabled or all calculated members will be deleted from the current view of the OlapClient.


{% endhighlight %} 

{% highlight vbnet %}



'Enable the Calculated Members in current view of the OlapClient.



Me.olapClient1.IsCalculatedMembersEnabled = True 



''''if set false, then it will be disabled or all calculated members will be deleted from the current view of the OlapClient.

 {% endhighlight %}

{% highlight xml %}





<CheckBox Name="chk_CalcMember  ToolTip="Enable/Disable Calculated Members" Content="Enable Calculated Members" IsChecked="{Binding ElementName=olapClient1, Path=IsCalculatedMembersEnabled}"/>



 {% endhighlight %}

