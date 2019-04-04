---
layout: post
title: Setting Tab Scroll Button | TabControlExt | wpf | Syncfusion
description: setting tab scroll button
platform: wpf
control: TabControlExt
documentation: ug
---

# Setting Tab Scroll Button

Tab Scroll button visibility is controlled by using the [TabScrollButtonVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabScrollButtonVisibility.html) property of the TabControlExt control. This is a dependency property which provides the following options to control the visibility of the Scroll button.

* Hidden–Scroll button is hidden
* Visible–Scroll button is displayed
* Auto–Scroll button is displayed automatically, if needed



Here is the code snippet to set the Tab Scroll Button Visibility as "Visible".

{% tabs %}

{% highlight xaml %}

<!-- Adding TabcontrolExt -->

<syncfusion:TabControlExt Name="tabControlExt" TabScrollButtonVisibility="Visible">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1">

    </syncfusion:TabItemExt>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2" >

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

tabControlExt.TabScrollButtonVisibility = TabScrollButtonVisibility.Visible;



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt);

{% endhighlight  %}

{% endtabs %}


![Tab scroll button visibility](Setting-Tab-Scroll-Button_images/Setting-Tab-Scroll-Button_img1.jpeg)



{% seealso %}

[Tab Scroll Style](https://help.syncfusion.com/wpf/tabext/setting-scroll-style)

[Tab Scrolling Time](https://help.syncfusion.com/wpf/tabext/setting-tab-scrolling-time)

{% endseealso %}



