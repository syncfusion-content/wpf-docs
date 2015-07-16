---
layout: post
title: Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-List
description: setting tablistcontextmenu and tabitemcontextmenu for tab list
platform: wpf
control: TabControlExt
documentation: ug
---

# Setting TabListContextMenu and TabItemContextMenu For Tab List

In TabControlExt, context menu is displayed for the Tab List by setting the ShowTabListContextMenu property to _true_. This dependency property is used to enable or disable the context menu for the Tab List.

The headers of all the Tab Items are displayed as the menu items of the Tab List context menu using the below code snippet.



[XAML]



&lt;!-- Adding TabControlExt  --&gt;

&lt;syncfusion:TabControlExt Name="tabControlExt" ShowTabListContextMenu="True"&gt;



    &lt;!-- Adding TabItemExt --&gt;

    &lt;syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"&gt;

    &lt;/syncfusion:TabItemExt&gt;



    &lt;!-- Adding TabItemExt --&gt;

    &lt;syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"&gt;

    &lt;/syncfusion:TabItemExt&gt;

&lt;/syncfusion:TabControlExt&gt;



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

tabControlExt.ShowTabListContextMenu = true;



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);



{ ![](Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-List_images/Setting-TabListContextMenu-and-TabItemContextMenu-For-Tab-List_img1.jpeg) | markdownify }
{:.image }




