---
layout: post
title: Resizing-the-Tab-Item
description: resizing the tab item
platform: wpf
control: TabControlExt
documentation: ug
---

# Resizing the Tab Item

Tab Items are resized by using the TabItemSize property. This property comes with the following resizing modes.

* Normal–the header of the Tab Items are displayed normally
* ShrinkToFit–the header of the Tab Items are shrunk to fit the header area



To set the Tab Item Size mode to "ShrinkToFit", refer the code snippet.



[XAML]



&lt;!-- Adding TabcontrolExt  --&gt;

&lt;syncfusion:TabControlExt Name="tabControlExt" TabItemSize="ShrinkToFit"&gt;

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



//Creating instance of the TabItemExt2 

TabItemExt tabItemExt2 = new TabItemExt();



// Setting header of the TabItemExt

tabItemExt2.Header = "TabItemExt2";



//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt2);



// Changing the TabItemSize property

tabControlExt.TabItemSize = TabItemSizeMode.ShrinkToFit;   



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);



{ ![](Resizing-the-Tab-Item_images/Resizing-the-Tab-Item_img1.jpeg) | markdownify }
{:.image }




See Also

Editing the Tab Item Header at Run Time, Tab Item Header Image, Tab Item Header Image Alignment, Context Menu for the Tab Item

