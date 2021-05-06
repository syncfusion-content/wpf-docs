---
layout: post
title: Drill Down/Up in WPF Olap Grid control | Syncfusion
description: Learn about Drill Down/Up support in Syncfusion WPF Olap Grid control and more.
platform: wpf
control: OlapGrid
documentation: ug
---

# Drill Down/Up in WPF Olap Grid

This is the basic feature of OLAP grid through which the amount of information can be limited. It allows you to drill down to access the detailed level of data, or drill up to see the summarized data using the expanders present in the grid. The expander here refers to the plus or minus or arrow sign present in the grid prior to a member. The expanders can be made hidden by setting the `ShowExpander` property of the OLAP report to **"false"**.

{% tabs %}
  
{% highlight c# %}

// Hiding Expanders
this.OlapGrid1.OlapDataManager.CurrentReport.ShowExpanders = false;

{% endhighlight %}

{% highlight vbnet %}

' Hiding Expanders
Me.OlapGrid1.OlapDataManager.CurrentReport.ShowExpanders = False

{% endhighlight %}

{% endtabs %}




