---
layout: post
title: Setting Scroll Style | TabControlExt | wpf | Syncfusion
description: setting scroll style
platform: wpf
control: TabControlExt
documentation: ug
---

# Setting Scroll Style

TabControlExt control can be implemented with different Tab Scroll styles to give a professional look to your WPF applications. This is achieved by using the [TabScrollStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabScrollStyle.html) dependency property, which is used to set the scroll style for navigating the Tab Items. It returns the object of the Tab Item currently in focus. The focus depends upon the click event of the Scroll button.

The following Tab Scroll styles supported by the TabControlExt control.

* Extended Mode-provides the Next, Previous, Last and First navigation options
* Normal Mode–provides the Next and Previous navigation options only



The following code snippet illustrates how to set the Tab Scroll style as "Extended".

{% tabs %}

{% highlight xaml %}


<!-- Adding TabControlExt -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" TabScrollStyle="Extended">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">

    </syncfusion:TabItemExt>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2">

    </syncfusion:TabItemExt>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt3" Header="TabItemExt3">

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



//Setting tab scroll type

tabControlExt.TabScrollStyle = TabScrollStyle.Extended;     



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 
{% endhighlight %}

{% endtabs %}



![Tab scroll style](Setting-Scroll-Style_images/Setting-Scroll-Style_img1.jpeg)





## TabScrollStyleChanged Event

This [TabScrollStyleChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabScrollStyleChanged_EV.html) event is triggered when the [TabScrollStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabScrollStyle.html) property is changed.

When the TabControlExt has many Tab Items, it is complicated to scroll the Tab Items in the Normal mode. In such cases, the Tab Scroll style is switched to the Extended mode. The following code illustrates how this is done.


{% highlight c# %}

/// <summary>

/// Tabs the control ext_ tab scroll style changed.

/// </summary>

/// <param name="d">The d.</param>

/// <param name="e">The <see cref="System.Windows.DependencyPropertyChangedEventArgs"/> instance containing the event data.</param>

private void tabControlExt_TabScrollStyleChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

{

if (tabControlExt.TabScrollStyle == TabScrollStyle.Extended)

tabControlExt.TabItemSize = TabItemSizeMode.ShrinkToFit;

}
{% endhighlight %}


In the above example, the Tab Item Size Mode is set to "ShrinkToFit" when the Tab Scroll style is switched to the Extended mode.

{% seealso %}

[Tab Scrolling Time](https://help.syncfusion.com/wpf/tabext/setting-tab-scrolling-time)

[Tab Scroll Button](https://help.syncfusion.com/wpf/tabext/setting-tab-scroll-button)

{% endseealso %}



