---
layout: post
title: Creating Tab Groups in WPF Tabbed MDI Form control | Syncfusion®
description: Learn here all about Creating Tab Groups support in Syncfusion® WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: WPF
control: DocumentContainer
documentation: ug
---

# Creating Tab Groups in WPF Tabbed MDI Form (DocumentContainer)

you can create tab groups for the tabitem of TDI mode [DocumentContainer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html) by dragging and also using the options in context menu items.

## Creating tab groups using context menu item

You can create a new horizontal or vertical tab groups for the TDI `DocumentContainer` by clicking the `New Horizontal Tab Group` or `New Vertical Tab Group` options available in the tabitem context menu. 

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

N> Tab groups created only in TDI mode of the `DocumentContainer`. You can enable it by setting the [Mode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_Mode) property value as `TDI`.

## Creating tab groups using tabitem dragging

You can create new horizontal tab group for the TDI `DocumentContainer` tab item by dragging the tabitem into the Document area and click the `New Tab Group` menu item from context menu item. You can cancel this tab group creation by clicking the `Cancel` menu item from context menu item.

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

## Creating tab groups programmatically

You can programmatically creates a tab group on horizontally or vertically by using the [CreateHorizontalTabGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CreateHorizontalTabGroup_System_Windows_UIElement_) and [CreateVerticalTabGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CreateVerticalTabGroup_System_Windows_UIElement_) methods.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Mode="TDI" 
                              Loaded="DocumentContainer_Loaded"
                              x:Name="documentContainer" >
    <ContentControl syncfusion:DocumentContainer.Header="item1"
                    Name="item1" />
    <ContentControl syncfusion:DocumentContainer.Header="item2"
                    Name="item2" />
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

private void DocumentContainer_Loaded(object sender, RoutedEventArgs e) {
    documentContainer.CreateVerticalTabGroup(item1 as UIElement);
}

{% endhighlight %}
{% endtabs %}

![Vertical Tab Groups created programmatically](Creating-Tab-Groups_images/Tabgroup_programmatically.png)
