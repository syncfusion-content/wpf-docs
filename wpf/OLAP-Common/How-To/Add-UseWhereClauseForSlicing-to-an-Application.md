---
layout: post
title: Add UseWhereClauseForSlicing to an Application| OLAPCommon | Wpf | Syncfusion
description: add usewhereclauseforslicing to an application
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Add UseWhereClauseForSlicing to an Application

The user can add the UseWhereClauseForSlicing property to an application by setting the property to a Boolean value.  To perform the slicing operation using the ‘Where’ clause, set the property to _true_. To perform the slicing operation using the ‘Select’ clause, set the property to _false_.  By default, the value of the UseWhereClauseForSlicing property is _true_.



To perform slicing operation using ‘Where’ clause:

{% tabs %}
{% highlight c# %}

OlapDataManager.UseWhereClauseForSlicing = true;

{% endhighlight  %}

{% highlight vbnet %}

OlapDataManager.UseWhereClauseForSlicing = True 

{% endhighlight  %}
{% endtabs %}

To perform slicing operation using ‘Select’ clause:
{% tabs %}
{% highlight c# %}

this.olapGridControl1.OlapDataManager.UseWhereClauseForSlicing = false;


{% endhighlight  %}
{% highlight vbnet %}

Me.olapGridControl1.OlapDataManager.UseWhereClauseForSlicing = False

{% endhighlight  %}
{% endtabs %}
