---
layout: post
title: Expand|Collapse|Toggle CategoryGroup|PropertyGrid|WPF|Syncfusion
description: PropertyItems are grouped based on the Category name. This section explains about how the group can collapsed or expanded programmatically
platform: wpf
control: PropertyGrid 
documentation: ug
---

# CategoryGroup

PropertyItems of PropertyGrid is grouped based on the Category name of property item. A category can be collapsed or expanded by clicking the expander which is near to category name. Or using CollapseCategory and ExpandCategory methods, category groups can be collapsed or expanded programmatically. These methods will accept category name as argument.

{% tabs %}

{% highlight C# %}

      this.pgrid.CollapseCategory("Itentity");

{% endhighlight %}  

{% endtabs %}

![Itentity group has been collapsed](Toggle-Category-Images/Collapse-Category.png)

{% tabs %}

{% highlight C# %}

      this.pgrid.ExpandCategory("Itentity");

{% endhighlight %}  

{% endtabs %}

![Collapsed Itentity group has been expanded](Toggle-Category-Images/Expand-Category.png)