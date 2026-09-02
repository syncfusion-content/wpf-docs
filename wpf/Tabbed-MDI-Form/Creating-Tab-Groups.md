---
layout: post
title: Creating Tab Groups in WPF DocumentContainer | Syncfusion®
description: Group related documents into multiple tab groups within the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control for flexible layouts.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Creating Tab Groups in WPF Document Container

You can create tab groups for the tab items of a TDI mode [WPF Document Container](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html) by dragging a tab item, by using the context menu items, or programmatically. Tab groups are only supported in `TDI` mode.

## Creating Tab Groups Using the Context Menu

You can create new horizontal or vertical tab groups for the TDI `WPF Document Container` by clicking the `New Horizontal Tab Group` or `New Vertical Tab Group` options available in the tab item context menu.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Mode="TDI" 
                              x:Name="documentContainer" >
    <ContentControl syncfusion:DocumentContainer.Header="item1"
                    Name="item1" />
    <ContentControl syncfusion:DocumentContainer.Header="item2"
                    Name="item2" />
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Tab Groups created by ContextMenuItem](Creating-Tab-Groups_images/Tabgroup_Contextmenu.gif)

N> Tab groups can only be created in TDI mode of the `WPF Document Container`. You can enable it by setting the [Mode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_Mode) property to `TDI`.

## Creating Tab Groups by Dragging a Tab Item

You can create a new horizontal tab group for the TDI `WPF Document Container` tab item by dragging the tab item into the document area and then clicking the `New Tab Group` menu item from the context menu. You can cancel the tab group creation by clicking the `Cancel` menu item from the context menu.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Mode="TDI" 
                              x:Name="documentContainer" >
    <ContentControl syncfusion:DocumentContainer.Header="item1"
                    Name="item1" />
    <ContentControl syncfusion:DocumentContainer.Header="item2"
                    Name="item2" />
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Horizontal Tab Groups created by dragging](Creating-Tab-Groups_images/Tabgroup_dragging.gif)

## Creating Tab Groups Programmatically

You can create a tab group horizontally or vertically by using the [CreateHorizontalTabGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CreateHorizontalTabGroup_System_Windows_UIElement_) and [CreateVerticalTabGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CreateVerticalTabGroup_System_Windows_UIElement_) methods. Both methods accept the `UIElement` that should be moved into a new tab group.

{% tabs %}
{% highlight XAML %}

<syncfusion:DocumentContainer Mode="TDI"
                              Loaded="DocumentContainer_Loaded"
                              x:Name="documentContainer">
    <ContentControl syncfusion:DocumentContainer.Header="item1"
                    x:Name="item1" />
    <ContentControl syncfusion:DocumentContainer.Header="item2"
                    x:Name="item2" />
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

private void DocumentContainer_Loaded(object sender, RoutedEventArgs e)
{
    documentContainer.CreateVerticalTabGroup(item1);
}

{% endhighlight %}
{% endtabs %}

![Vertical Tab Groups created programmatically](Creating-Tab-Groups_images/Tabgroup_programmatically.png)
