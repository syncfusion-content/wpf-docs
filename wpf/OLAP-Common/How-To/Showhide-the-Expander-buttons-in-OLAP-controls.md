---
layout: post
title: Showhide the Expander buttons in OLAP controls| OLAPCommon | Wpf | Syncfusion
description: show/hide the expander buttons in olap controls
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Show/hide the Expander buttons in OLAP controls

There is a property in OlapReport called ShowExpanders, which is used to show/hide the expander buttons in the OLAP controls. By using this property, we can disable or enable the drill down/up behavior of the OLAP control. 

To show the Expanders:

{% tabs %}
{% highlight c# %}



 //// Displaying the Expander button in Controls
 olapReport.ShowExpanders = true;


{% endhighlight  %}


{% highlight vbnet %}



'Displaying the Expander button in Controls

olapReport.ShowExpanders = True 



{% endhighlight  %}
{% endtabs %}

To hide the Expanders: 

{% tabs %}
{% highlight c# %}



 //// Displaying the Expander button in Controls
 olapReport.ShowExpanders = false;



{% endhighlight  %}

{% highlight vbnet %}



'Displaying the Expander button in Controls

olapReport.ShowExpanders = False 




{% endhighlight  %}
{% endtabs %}