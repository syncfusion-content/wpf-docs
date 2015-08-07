---
layout: post
title: Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-Item
description: setting tablistcontextmenu and tabitemcontextmenu for tab item
platform: wpf
control: TabControlExt
documentation: ug
---

# Setting TabListContextMenu and TabItemContextMenu For Tab Item

In TabControlExt, context menu can be displayed for the Tab Items by setting the ShowTabItemContextMenu property to True. This is a dependency property which is used to enable or disable the context menu for the Tab Item.

The context menu of the Tab Item has the following menu items.

* Close
* Close All But This
* Close All



To enable the Tab Item context menu, use the below code.


{% highlight xml %}
[XAML]



<!-- Adding TabControlExt  -->

<syncfusion:TabControlExt Name="tabControlExt" ShowTabItemContextMenu="True">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">

    </syncfusion:TabItemExt>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2">

    </syncfusion:TabItemExt>

</syncfusion:TabControlExt>
{% endhighlight %}

{% highlight  %}
[C#]



// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();



//Creating the instance of StackPanel

StackPanel stackPanel = new StackPanel();



//Creating instance of the TabItemExt 

TabItemExt tabItemExt1 = new TabItemExt();



// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";



//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt1);            



// Changing the Visibility of Scroll button 

tabControlExt.ShowTabItemContextMenu = true; 



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);
{% endhighlight %}


![](Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-Item_images/Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-Item_img1.jpeg)





## Tab Item Context Menu Events

###  OnCloseOtherTabs Event

This event is handled when the 'Close All But This' menu item in the TabItemContextMenu is clicked.

###OnCloseAllTabs Event

This event is handled when the 'Close All' menuitem in TabItemContextMenu is clicked.

###  Event

This event is handled when the 'Close' menu item in TabItemContextMenu is clicked.

See Also

Resizing the Tab Item, Editing the Tab Item Header at Run Time, Tab Item Header Image, Tab Item Header Image Alignment

