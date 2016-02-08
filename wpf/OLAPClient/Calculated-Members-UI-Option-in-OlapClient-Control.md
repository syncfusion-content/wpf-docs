---
layout: post
title: Calculated Members UI Option in OlapClient Control| OLAP Client  | Wpf | Syncfusion
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

### Sample Link

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

{% tabs %}
{% highlight C# %}  



////Enable the Calculated Members in current view of the OlapClient.



this.olapClient1.IsCalculatedMembersEnabled = true; 



//if set false, then it will be disabled or all calculated members will be deleted from the current view of the OlapClient.


{% endhighlight %} 

{% highlight vbnet %}



'Enable the Calculated Members in current view of the OlapClient.



Me.olapClient1.IsCalculatedMembersEnabled = True 
 {% endhighlight %}
{% endtabs %}



if set false, then it will be disabled or all calculated members will be deleted from the current view of the OlapClient.



{% highlight xaml %}





<CheckBox Name="chk_CalcMember  ToolTip="Enable/Disable Calculated Members" Content="Enable Calculated Members" IsChecked="{Binding ElementName=olapClient1, Path=IsCalculatedMembersEnabled}"/>



 {% endhighlight %}

