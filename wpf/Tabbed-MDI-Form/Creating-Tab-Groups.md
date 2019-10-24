---
layout: post
title: Creating Tab Groups| DocumentContainer | Wpf | Syncfusion
description: creating tab groups
platform: wpf
control: DocumentContainer
documentation: ug
---

# Creating Tab Groups

To create tab groups programmatically in DocumentContainer, two methods are used; they are 

CreateHorizontalTabGroup() and CreateVerticalTabGroup(). Their usages are given below.

{% tabs %}
{% highlight xaml %}
<syncfusion:DocumentContainer  Name="documentcontainer1" Mode="TDI">      
      <Grid Name="grid1"/>         
	  <Grid Name="grid2"/>        
	  </syncfusion:DocumentContainer>
	  {% endhighlight %}

{% highlight C# %}
//To create horizontal tab groupdocumentcontainer1.
CreateHorizontalTabGroup(grid1);
//To create vertical tab group  documentcontainer1.
CreateVerticalTabGroup(grid1);
{% endhighlight %}
{% endtabs %}


