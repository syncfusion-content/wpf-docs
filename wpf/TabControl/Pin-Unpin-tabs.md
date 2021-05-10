---
layout: post
title: Pin and Unpin TabItems in WPF TabControl control | Syncfusion
description: Learn here all about Pin and Unpin TabItems support in Syncfusion WPF TabControl (TabControlExt) control and more.
platform: wpf
control: TabControlExt
documentation: ug
---

# Pin and Unpin TabItems in WPF TabControl (TabControlExt)

This section explains the pin and unpin tab items in [TabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html). 

## Enabling pin and unpin behaviors

If you want to pin or unpin the tab items, use the [TabItemExt.AllowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabItemExt.html#Syncfusion_Windows_Tools_Controls_TabItemExt_AllowPin) property as `true`. When this property is set to `false`, the pin and unpin behaviors of tab item will be disabled. The default value of the `TabItemExt.AllowPin` property is `false`.

{% tabs %}
{% highlight XAML %}
 
<syncfusion:TabControlExt  Name="tabControlExt">
    <syncfusion:TabItemExt AllowPin="True"
                           Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt AllowPin="True" 
                           Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabItemExt1.AllowPin = true;
tabItemExt2.AllowPin = true;

{% endhighlight %}
{% endtabs %}

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Pin-UnPin) in GitHub

## Functionality of PinButton

 When the corresponding tab item is pinned, it will be inserted at first position of the tab header panel(if its not have any pinned tab. Otherwise, the pinned tab item will be added next to last pinned item). When the tab item is unpinned, it will be placed after to the pinned tab items.

## Pin and Unpin tab items using PinButton

If you want to pin or unpin the tab item using the pin button, use the [TabItemExt.ShowPin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabItemExt.html#Syncfusion_Windows_Tools_Controls_TabItemExt_ShowPin) property value as `true` and set the `TabItemExt.AllowPin` property value as `true`. The default value of `TabItemExt.ShowPin` property is `false`, so the PinButton is collapsed from header panel of the tab item.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt  Name="tabControlExt">
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True"
                           Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True" 
                           Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

//Showing the pin buttons
tabItemExt1.ShowPin = true;
tabItemExt2.ShowPin = true;

//Enabling the pin buttons
tabItemExt1.AllowPin = true;
tabItemExt2.AllowPin = true;

{% endhighlight %}
{% endtabs %}

![Displaying PinButton to specific items](pin-unpin-tabs-images\displaying-pinbutton.png)

N> If the `ShowPin` property is `true`, and the `AllowPin` property is `false`, the PinButton will be displayed as a disabled button.

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Pin-UnPin) in GitHub

## Pin and Unpin the tab items programmatically

You can pin or unpin the tab items programmatically by using the [TabItemExt.IsPinned](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabItemExt.html#Syncfusion_Windows_Tools_Controls_TabItemExt_IsPinned) property. If the `TabItemExt.IsPinned` property is set to `true`, the corresponding item will be pinned. Also, if the `TabItemExt.IsPinned` property is set as `false` and the item is pinned, then it will be unpinned. The default value of `TabItemExt.IsPinned` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt Name="tabControlExt">
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True"
                           IsPinned="False"
                           Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True" 
                           IsPinned="True"
                           Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

//Pin or unpin the tab items programmatically
tabItemExt1.IsPinned = false;
tabItemExt2.IsPinned = true;

//Showing the pin buttons
tabItemExt1.ShowPin = true;
tabItemExt2.ShowPin = true;

//Enabling the pin buttons
tabItemExt1.AllowPin = true;
tabItemExt2.AllowPin = true;

{% endhighlight %}
{% endtabs %}

![Tab items pinned and unpinned programmatically](pin-unpin-tabs-images\Ispinned-pinbutton.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/Pin-UnPin) in GitHub

## Pin and Unpin tab items using ContextMenu

You can pin or unpin the tab items using the context menu. You can enable it by setting the `TabItemExt.AllowPin` property value as `true`. If the `TabItemExt.AllowPin` property is `true`, and the tab item is not pinned, "Pin Tab" option will be visible. If the tab item is pinned already, "Unpin Tab" option will be visible in the context menu. 

N> If you want to show the pin and unpin buttons , use the `TabItemExt.ShowPin` value as `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt Name="tabControlExt">
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True"
                           IsPinned="False"
                           Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt ShowPin="True" 
                           AllowPin="True" 
                           IsPinned="True"
                           Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

//Pin or unpin the tab items programmatically
tabItemExt1.IsPinned = false;
tabItemExt2.IsPinned = true;

//Showing the pin buttons
tabItemExt1.ShowPin = true;
tabItemExt2.ShowPin = true;

//Enabling the pin buttons
tabItemExt1.AllowPin = true;
tabItemExt2.AllowPin = true;

{% endhighlight %}
{% endtabs %}

![Displays option to pin and Unpin the tab items](pin-unpin-tabs-images\unpintab-option-contextmenu.png)

## Re-order pinned tabs

You can re-order the pinned item within the pinned items and re-order the un-pinned item within the unpinned, but re-ordering between pinned and unpinned or unpinned and pinned has been restricted. If the pinned tab item is dropped inside the unpinned tab items, the dragged item will be inserted at the last position of pinned tab item and if the unpinned tab item is dropped inside pinned tab items, the dragged item will be inserted after the last pinned item. You can disable this reordering by using th `AllowDragDrop` property as `false`.

![Re-ordering pin and unpinned tab items](pin-unpin-tabs-images\Reorder.gif)
