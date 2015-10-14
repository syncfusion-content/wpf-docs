---
layout: post
title: Layout Type | TabControlExt | wpf | Syncfusion
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

{% tabs %}

{% highlight xaml %}

<!-- Adding TabcontrolExt  -->

<syncfusion:TabControlExt Name="tabControlExt" TabItemLayout="MultiLine">

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

tabControlExt.TabItemLayout = TabItemLayoutType.MultiLine;  

//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);

{% endhighlight %}

{% endtabs %}

![](Layout-Type_images/Layout-Type_img1.jpeg)


## TabItemLayoutChanged Event

This event is triggered when the TabItemLayout property is changed.

The following code snippet illustrates handling the TabItemLayoutChanged event.


{% highlight c# %}

/// <summary>

/// Tabs the control ext_ tab item layout changed.

/// </summary>

/// <param name="d">The d.</param>

/// <param name="e">The <see cref="System.Windows.DependencyPropertyChangedEventArgs"/> instance 	containing the event data.</param>

private void tabControlExt_TabItemLayoutChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

if ((tabControlExt.TabItemLayout == TabItemLayoutType.MultiLine))

{

tabControlExt.TabScrollButtonVisibility = TabScrollButtonVisibility.Hidden;

}

}
{% endhighlight %}


In the above example, when the TabItemLayoutType property is set to MultiLine, the Tab Scroll button is hidden, as it is no longer needed to view the contents.