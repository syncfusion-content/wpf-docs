---
layout: post
title: Disables the TabItemExt Content | TabControlExt | wpf | Syncfusion
description: disables the unload of tabitemext content
platform: wpf
control: TabControlExt
documentation: ug
---

# Disables the Unload of TabItemExt Content

While switching the TabItems in TabControl the content of previously selected items will be unloaded. To enable or disable unload of TabItemExt content the [IsDisableUnloadTabItemExtContent](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~IsDisableUnloadTabItemExtContent.html) property can be used. 

{% tabs %}

{% highlight xaml %}

<syncfusion:TabControlExt Name="tabcontrol" IsDisableUnloadTabItemExtContent="True">

   <syncfusion:TabItemExt Header="tab1">

     <TextBlock Text="content1" Unloaded="TextBlock_Unloaded"/>

   </syncfusion:TabItemExt>

   <syncfusion:TabItemExt Header="tab2">

     <TextBlock Text="content2" Unloaded="TextBlock_Unloaded_1"/>

   </syncfusion:TabItemExt>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

tabcontrol.IsDisableUnloadTabItemExtContent = true;

{% endhighlight %}

{% endtabs %}

When the value is set to true the TabItem content will not get unloaded during tab switching.