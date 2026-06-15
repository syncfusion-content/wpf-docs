---
layout: post
title: Vertical Tabs and Pin Support in WPF Tabbed Window | Syncfusion
description: Learn how to use vertical tab arrangement and pin/unpin functionality in WPF Tabbed Window for enhanced tab management.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Vertical Tabs and Pin Support in WPF Tabbed Window

This section explains how to use vertical tab arrangement and pin/unpin functionality in the WPF Tabbed Window interface for enhanced tab management.

## Vertical Tab Support

The Tabbed Window supports vertical tab arrangement, where tabs are displayed on the left side of the window instead of the top. This is useful for wide screens or when you want to maximize vertical content space.

Set the [TabArrangement](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html#Syncfusion_Windows_Controls_SfTabControl_TabArrangement) property to `Vertical` on [SfTabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html) to display tabs vertically on the left side of the window.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl TabArrangement="Vertical">
    <syncfusion:SfTabItem Header="Document 1">
        <TextBlock Text="Content 1" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem Header="Document 2">
        <TextBlock Text="Content 2" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem Header="Document 3">
        <TextBlock Text="Content 3" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>

{% endhighlight %}

{% highlight C# %}

tabControl.TabArrangement = TabArrangement.Vertical;

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow Vertical Tabs](tab-management_images/tabbedwindow_vertical_tabs.png)

### Vertical Tab Collapse Behavior

When using vertical tab arrangement, the tab header area can be collapsed to show only icons, helping maximize the content area.

**Collapse Behavior:**

- **Mouse Enter** - When the mouse enters the collapsed vertical tab area, it expands to show the full tab headers.
- **Mouse Leave** - When the mouse leaves the expanded tab area, it collapses back to icon-only view.
- **Pin Toggle Button** - Click the pin button in the vertical tab header to maintain the expanded state. This keeps the vertical tabs expanded until the pin is toggled off again.


![WPF TabbedWindow Collapse](tab-management_images/tabbedwindow_collapse.gif)


## Pin and Unpin Tabs

You can pin tabs to keep them always visible and prevent them from being closed accidentally. Pinned tabs appear first in the tab order and remain in place when other tabs are reordered.

### Showing Pin Button

Display a pin button on individual tabs using the [ShowPinButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabItem.html#Syncfusion_Windows_Controls_SfTabItem_ShowPinButton) property on [SfTabItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabItem.html).

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl>
    <syncfusion:SfTabItem Header="Document 1"
                          ShowPinButton="True">
        <TextBlock Text="Content 1" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem Header="Document 2"
                          ShowPinButton="True">
        <TextBlock Text="Content 2" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>

{% endhighlight %}

{% highlight C# %}

var tabItem = new SfTabItem
{
    Header = "Document",
    ShowPinButton = true,
    Content = new TextBlock { Text = "Tab Content" }
};
tabControl.Items.Add(tabItem);

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow Pin Button](tab-management_images/tabbedwindow_pin_button.gif)

### Pinning a Tab

When the pin button is clicked, the tab becomes pinned. Pinned tabs are automatically reordered to appear first in the tab strip.

### Context Menu Pinning

Use the context menu to pin or unpin tabs. Right-click on a tab header to access the pin option.

## Related Properties

| Property | Control | Description |
|----------|---------|-------------|
| [TabArrangement](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html#Syncfusion_Windows_Controls_SfTabControl_TabArrangement) | SfTabControl | Gets or sets the tab arrangement (Horizontal/Vertical) |
| [ShowPinButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabItem.html#Syncfusion_Windows_Controls_SfTabItem_ShowPinButton) | SfTabItem | Gets or sets the visibility of the pin button |