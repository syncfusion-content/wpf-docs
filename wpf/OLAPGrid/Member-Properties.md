---
layout: post
title: Member-Properties
description: member properties
platform: wpf
control: OLAP Grid
documentation: ug
---

# Member Properties

OlapGrid allows binding of Dimension Members along with their properties. Member properties cover the basic information about each member in each tuple. This basic information includes the member name, parent level, the number of children, and so on. Member properties are available for all members at a given level. In order to display member properties along with the dimension member, OlapReport requires member properties to be defined in the concerned dimension element. Also, the grid layout should be set to ExcelLikeLayoutWithMemberProperties.

## Click here for Sample Report with Member Properties

![](Member-Properties_images/Member-Properties_img1.png)
{:.image }

To display member properties via header tooltip, the following property of OlapGrid should be set to true.
{% highlight c# %}
[C#]



// To Display Member Properties in ToolTip

this.OlapGrid1.ShowMemberPropertiesToolTip = true;


{% endhighlight  %}
{% highlight vbnet %}


[VB]



' To Display Member Properties in ToolTip

Me.OlapGrid1.ShowMemberPropertiesToolTip = True

{% endhighlight  %}



![](Member-Properties_images/Member-Properties_img2.png)



### Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Application Scenario\Member Properties Demo

