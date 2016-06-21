---
layout: post
title: Drill UpDown| OlapGrid | Wpf | Syncfusion
description: drill-up/down
platform: wpf
control: OlapGrid
documentation: ug
---

# Drill Up/Down

This is the basic feature of OlapGrid through which the amount of information can be limited. It allows you to drill down to access the detailed level of data, or drill up to see the summarized data using the expanders present in the Grid. The expander here refers to the plus/minus or arrow sign present in the Grid prior to a member. The expanders can be made hidden by setting the **"ShowExpander"** property of OlapReport to **"false"**.

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




