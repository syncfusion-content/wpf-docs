---
layout: post
title: Tab Management in WPF Tabbed Window| Syncfusion
description: Learn how to manage tabs in a WPF tabbed window by using close buttons, adding new tabs, customizing tab appearance, and using keyboard shortcuts.
platform: wpf
control: TabbedWindow
documentation: ug
---

# WPF Tabbed Window - Tab Management

This section explains how to manage tabs in a tabbed window interface and provides an overview of the available tab management features.

## Closing Tabs

You can display close buttons on individual tabs using the `CloseButtonVisibility` property on `SfTabItem`.

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

## Adding New Tabs

You can use the `EnableNewTabButton` property to display a new tab button in the SfTabControl. Clicking this button raises the NewTabRequested event, which can be used to add a new SfTabItem dynamically.

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

## Customization of New Tab Button

You can customize the appearance of the new tab button by using the `NewTabButtonStyle` property. This allows you to modify visual properties such as background, border, width, and height.

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

You can also customize the visual presentation of generated tab items by defining templates for the tab header and tab content.

{% tabs %}

{% highlight XAML %}

<DataTemplate x:Key="TabHeaderTemplate">
  <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
    <Image Source="/Images/doc.png" Width="16" Height="16"/>
    <TextBlock Text="{Binding Title}" Margin="6,0,0,0"/>
  </StackPanel>
</DataTemplate>

<DataTemplate x:Key="TabContentTemplate">
  <ContentPresenter Content="{Binding Content}" />
</DataTemplate>

<syncfusion:SfTabControl ItemsSource="{Binding OpenTabs}"
                         ItemTemplate="{StaticResource TabHeaderTemplate}"
                         ContentTemplate="{StaticResource TabContentTemplate}" />

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow customization](tab-management_images/wpf_customization.png)

## Keyboard Shortcuts

- `Ctrl + Tab` — move to the next tab.
- `Ctrl + Shift + Tab` — move to the previous tab.
- `Ctrl + T` — create a new `SfTabItem`.
- Mouse middle-click on a `SfTabItem` header — close that tab.
