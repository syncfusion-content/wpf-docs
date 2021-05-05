---
layout: post
title: Root lines for Items in WPF TreeViewAdv | Syncfusion
description: Learn here all about Root lines for Items in Syncfusion WPF TreeViewAdv (Classic) control, its elements and more details.
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Root lines for Items in WPF TreeViewAdv (Classic)

The TreeViewAdv displays root lines, which link the nodes of a tree structure. These TreeViewAdv root lines are displayed or hidden by using the ShowRootLines property of the class TreeViewAdv. To set this property, use the below code

{% tabs %}

{% highlight XAML %}

<!-- Adding TreeViewAdv With show root lines -->
<syncfusion:TreeViewAdv Name="treeViewAdv" ShowRootLines="False">
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information"/>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

// Show root lines
treeViewAdv.ShowRootLines = false;

{% endhighlight %}

{% highlight VB %}

' Show root lines
treeViewAdv.ShowRootLines = False

{% endhighlight %}

{% endtabs %} 

![Root Lines for Items in TreeViewAdv](Root_lines_for_items_in_treeviewadv_images/Root_lines_for_items_in_treeviewadv_img1.jpeg)
