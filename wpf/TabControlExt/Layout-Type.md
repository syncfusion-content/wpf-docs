---
layout: post
title: Layout-Type
description: layout type
platform: wpf
control: TabControlExt
documentation: ug
---

# Layout Type

You can set the layout type for the TabControlExt control by using the TabItemLayoutType property. This dependency property sets the layout type of the Tab Item. It provides the following layout types.

* SingleLine–tab items are displayed in single line
* MultiLine–tab items are shrunk and displayed in multiple lines
* MultiLineWithFillWidth–tab items are displayed in multiple lines without being shrunk



Here is the code snippet to set the layout type as "MultiLine".



[XAML]



&lt;!-- Adding TabcontrolExt  --&gt;

&lt;syncfusion:TabControlExt Name="tabControlExt" TabItemLayout="MultiLine"&gt;



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

tabControlExt.TabItemLayout = TabItemLayoutType.MultiLine;  



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);



{ ![](Layout-Type_images/Layout-Type_img1.jpeg) | markdownify }
{:.image }




TabItemLayoutChanged Event

This event is triggered when the TabItemLayout property is changed.

The following code snippet illustrates handling the TabItemLayoutChanged event.



[C#]



/// &lt;summary&gt;

/// Tabs the control ext_ tab item layout changed.

/// &lt;/summary&gt;

/// <param name="d">The d.&lt;/param&gt;

/// <param name="e">The &lt;see cref="System.Windows.DependencyPropertyChangedEventArgs"/&gt; instance 	containing the event data.&lt;/param&gt;

private void tabControlExt_TabItemLayoutChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

if ((tabControlExt.TabItemLayout == TabItemLayoutType.MultiLine))

{

tabControlExt.TabScrollButtonVisibility = TabScrollButtonVisibility.Hidden;

}

}



In the above example, when the TabItemLayoutType property is set to MultiLine, the Tab Scroll button is hidden, as it is no longer needed to view the contents.

