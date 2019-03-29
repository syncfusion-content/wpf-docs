---
layout: post
title: Tab list and tab item context menu | TabControlExt | wpf | Syncfusion
description: setting tablistcontextmenu and tabitemcontextmenu for tab list
platform: wpf
control: TabControlExt
documentation: ug
---

# Setting TabListContextMenu and TabItemContextMenu For Tab List

In TabControlExt, context menu is displayed for the Tab List by setting the [ShowTabListContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~ShowTabItemContextMenu.html) property to _true_. This dependency property is used to enable or disable the context menu for the Tab List.

The headers of all the Tab Items are displayed as the menu items of the Tab List context menu using the below code snippet.

{% tabs %}

{% highlight xaml %}

<!-- Adding TabControlExt  -->

<syncfusion:TabControlExt Name="tabControlExt" ShowTabListContextMenu="True">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">

    </syncfusion:TabItemExt>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2">

    </syncfusion:TabItemExt>

</syncfusion:TabControlExt>
{% endhighlight %}

{% highlight c# %}


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

tabControlExt.ShowTabListContextMenu = true;



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);

{% endhighlight %}

{% endtabs %}

![Tab list context menu](Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-List_images/Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-List_img1.jpeg)

