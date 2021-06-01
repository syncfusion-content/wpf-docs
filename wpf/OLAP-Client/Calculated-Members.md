---
layout: post
title: Calculated Members in WPF Olap Client control | Syncfusion
description: Learn about Calculated Members support in Syncfusion Essential Studio WPF Olap Client control, its elements and more details.
platform: wpf
control: OLAP Client
 documentation: ug
---

# Calculated Members in WPF Olap Client

This feature allows users to define measures and members using the calculated member editor. The calculated member editor can be opened just by clicking the respective icon available in the OLAP client toolbar. The icon will be visible only by setting the `IsCalculatedMembersEnabled` property to true.

![Calculated memeber option is enabled in OlapClient toolbar](Calculated-Members_images/Calculated-Members_img1.png)

![Calculated member editor window](Calculated-Members_images/Calculated-Members_img2.png)

{% tabs %}

{% highlight xaml %}

<CheckBox Name="chk_CalcMember  ToolTip="Enable/Disable Calculated Members" Content="Enable Calculated Members" 
          IsChecked="{Binding ElementName=olapClient1, Path=IsCalculatedMembersEnabled}"/>

{% endhighlight %}

{% highlight C# %}  

this.olapClient1.IsCalculatedMembersEnabled = true; 

{% endhighlight %} 

{% highlight vbnet %}

Me.olapClient1.IsCalculatedMembersEnabled = True 

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapClient.WPF\Samples\Product Showcase\CalculatedMembers


