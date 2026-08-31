---
layout: post
title: Select Tab in WPF TabControlExt | Syncfusion®
description: Select a tab item in the Syncfusion WPF TabControl (TabControlExt) programmatically or through user interaction.
platform: wpf
control: TabControlExt
documentation: ug
---

# Select Tab in WPF Tab Control

This section explains how to select tab item and selection functionalities in the [WPF Tab Control](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html).

## Select tab item using mouse or keyboard

You can select a particular tab item by using the mouse click on the tab header. You can use the `Ctrl + Tab` key to select the next tab item when the control is in a focused state. You can also use the `Left-Arrow` and `Right-Arrow` keys to select the previous or next tab item relative to the currently selected tab item when the control is focused. You can get the selected item by using the `SelectedItem` property. By default, the first tab item is selected.

N> You can select only one tab item at a time.

![Tab items selected by clicking the tab header](Tab-Item-Header_images/SelectItem.gif)

## Tab selection changed notification

The `WPF Tab Control` notifies that the selected tabitem is changed by user through the [SelectedItemChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) event. You can use the [OldSelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.SelectedItemChangedEventArgs.html#Syncfusion_Windows_Tools_Controls_SelectedItemChangedEventArgs_OldSelectedItem) and [NewSelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.SelectedItemChangedEventArgs.html#Syncfusion_Windows_Tools_Controls_SelectedItemChangedEventArgs_NewSelectedItem) properties to get the old and new selected tabitem in the `SelectedItemChangedEvent` event.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt SelectedItemChangedEvent="TabControlExt_SelectedItemChangedEvent"
                          Name="tabControlExt" />

{% endhighlight %}
{% highlight C# %}

TabControlExt tabControlExt = new TabControlExt();
tabControlExt.SelectedItemChangedEvent += TabControlExt_SelectedItemChangedEvent;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void TabControlExt_SelectedItemChangedEvent(object sender, SelectedItemChangedEventArgs e) {
    var newTabItem = e.NewSelectedItem.Header;
    if (e.OldSelectedItem != null) {
        var oldTabItem = e.OldSelectedItem.Header;
    }
    else {
        var oldTabItem = string.Empty;
    }
}

{% endhighlight %}
{% endtabs %}

## Load the previously selected tab item content

If you want to load the previously selected tab item in background after new tab item is selected, use the [IsDisableUnloadTabItemExtContent](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_IsDisableUnloadTabItemExtContent) property value as `true`. The default value of `IsDisableUnloadTabItemExtContent` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt IsDisableUnloadTabItemExtContent="True"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tab1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tab2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.IsDisableUnloadTabItemExtContent = true;

{% endhighlight %}
{% endtabs %}

![TabControl loads the previously selected tab item content](Tab-Item-Header_images/Loadall.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/SelectedItem) in GitHub

## Display mode of the selected tab item

If you want to show tab items without its headers in the `WPF Tab Control`, use the [FullScreenMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_FullScreenMode) property. If you set `FullScreenMode` property value as `ControlMode`, then it will auto hide headers and show it only on when hover the mouse on respective tab header placed area. You can also display the `WPF Tab Control` in the full window by setting the `FullScreenMode` property value as `WindowMode`. The default value of `FullScreenMode` property is `None`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt FullScreenMode="ControlMode"
                          TabStripPlacement="Bottom"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" />
    <syncfusion:TabItemExt Header="tabItem2" />
    <syncfusion:TabItemExt Header="tabItem3" />
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.FullScreenMode = FullScreenMode.ControlMode;
tabControlExt.TabStripPlacement = Dock.Bottom;

{% endhighlight %}
{% endtabs %}

![Show the tab item without its header](Getting-Started_images/FullScreenMode.gif)

## Customize selected tab item header

You can change the selected tab item header font weight, background and foreground.

### Change selected tab header font weight

If you want to highlight the selected tab header, change the font of tab header from semi bold to extra bold by using the [SelectedItemFontWeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_SelectedItemFontWeight) property. The default value of `SelectedItemFontWeight` property is `SemiBold`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt SelectedItemFontWeight="ExtraBold"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.SelectedItemFontWeight = FontWeights.ExtraBold;

{% endhighlight %}
{% endtabs %}

![TabControl SelectedItem font weight changed to ExtraBold](Tab-Item-Header_images/SelectedItemFontWeight.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/SelectedItem) in GitHub

### Change selected tab header background and foreground 

You can change the highlighting background and foreground of the selected tab item by using the [TabItemSelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html#Syncfusion_Windows_Tools_Controls_TabControlExt_TabItemSelectedForeground) and [TabItemSelectedBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabControlExt.html) properties. The default value of `TabItemSelectedForeground` property is `Black`  and `TabItemSelectedBackground` property is `Lavender`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TabControlExt TabItemSelectedForeground="Red" 
                          TabItemSelectedBackground="Green"
                          Name="tabControlExt">
    <syncfusion:TabItemExt Header="tabItem1" Name="tabItemExt1"/>
    <syncfusion:TabItemExt Header="tabItem2" Name="tabItemExt2"/>
</syncfusion:TabControlExt>

{% endhighlight %}
{% highlight C# %}

tabControlExt.TabItemSelectedForeground = Brushes.Red;
tabControlExt.TabItemSelectedBackground = Brushes.Green;

{% endhighlight %}
{% endtabs %}

![TabControl SelectedItem background and foreground changed](Tab-Item-Header_images/SelectedItemBackground.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-tabcontrolext-examples/tree/master/Samples/SelectedItem) in GitHub
