---
layout: post
title: Tab Management in WPF Tabbed Window | Syncfusion
description: Manage tabs dynamically by supporting close buttons, creating new tabs, and updating the selected tab during interactions.
platform: wpf
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Tab Management

## Overview

The Tabbed Window provides comprehensive tab management capabilities including dynamic tab creation, tab closing, and tab selection. These features enable flexible and responsive tab-based interfaces.

## Close Button Support

Display close buttons on individual tabs using the `CloseButtonVisibility` property on `SfTabItem`:

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl>
    <syncfusion:SfTabItem 
        Header="Document 1" 
        CloseButtonVisibility="Visible">
        <TextBlock Text="Click the X button to close this tab" />
    </syncfusion:SfTabItem>
    <syncfusion:SfTabItem 
        Header="Document 2" 
        CloseButtonVisibility="Visible">
        <TextBlock Text="Each tab has its own close button" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

var tabItem = new SfTabItem 
{ 
    Header = "Document", 
    CloseButtonVisibility = Visibility.Visible,
    Content = new TextBlock { Text = "Tab Content" }
};
tabControl.Items.Add(tabItem);

{% endhighlight %}

{% endtabs %}

When a user clicks the close button, the tab is automatically removed and the control selects the next available tab.

![WPF TabbedWindow CloseButton](tab-management_images/tabbedwindow_closebutton.gif)

## New Tab Button

Enable the new tab button to allow users to dynamically add tabs:

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl 
    EnableNewTabButton="True"
    NewTabRequested="OnNewTabRequested">
    <syncfusion:SfTabItem Header="Tab 1">
        <TextBlock Text="Content 1" />
    </syncfusion:SfTabItem>
</syncfusion:SfTabControl>

{% endhighlight %}

{% highlight C# %}

private void OnNewTabRequested(object sender, NewTabRequestedEventArgs e)
{
    // Create a new tab item when user clicks the + button
    var newTabContent = new TextBlock 
    { 
        Text = $"New Document {DateTime.Now:g}" 
    };
    
    var newTabItem = new SfTabItem 
    { 
        Header = $"Document {tabControl.Items.Count + 1}",
        Content = newTabContent,
        CloseButtonVisibility = Visibility.Visible
    };
    
    e.Item = newTabItem;
}

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow New Tab Button](tab-management_images/tabbedwindow_newbutton.gif)

### Customization of New tab button

`NewTabButtonStyle` targets the internal `Button` used for the new‑tab afford and controls visual properties such as size, background, border and padding without replacing the element tree. 

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTabControl EnableNewTabButton="True"
                         x:Name="maintabcontrol">
    <syncfusion:SfTabControl.NewTabButtonStyle>
        <Style TargetType="{x:Type Button}">
            <Setter Property="Background" Value="Red"/>
            <Setter Property="BorderBrush" Value="Yellow"/>
            <Setter Property="MinWidth" Value="30"/>
            <Setter Property="MinHeight" Value="30"/>
        </Style>
    </syncfusion:SfTabControl.NewTabButtonStyle>
    <syncfusion:SfTabItem Header="Tab 1" Content="Tab 1 Content"/>
    <syncfusion:SfTabItem Header="Tab 2" Content="Tab 2 Content"/>
    <syncfusion:SfTabItem Header="Tab 3" Content="Tab 3 Content"/>
</syncfusion:SfTabControl>

{% endhighlight %}

{% endtabs %}

![WPF NewButton style](tab-management_images/wpf_newbuttonstyle.png)

## Keyboard shortcuts

- `Ctrl + Tab` — move to the next tab.
- `Ctrl + Shift + Tab` — move to the previous tab.
- `Ctrl + T` — create a new `SfTabItem` (programmatic shortcut).
- Mouse middle‑click on a `SfTabItem` header — close that tab.

