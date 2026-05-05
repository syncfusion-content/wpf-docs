---
layout: post
title: Data Binding in WPF Tabbed Window | Syncfusion
description: Learn how to bind tabs to a collection in Syncfusion® WPF Tabbed Window by using the ItemsSource property and templates for tab headers and content.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Data Binding in WPF Tabbed Window

This section explains how to bind tabs to a collection in a WPF tabbed window by using the `ItemsSource` property of [SfTabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html) and defining templates for tab headers and content.

## Populating Tab Items using ItemsSource

You can bind the `ItemsSource` property of [SfTabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html) to a collection in the ViewModel to generate tabs automatically. Each item in the bound collection creates a corresponding tab.

{% tabs %}

{% highlight C# %}

// TabModel.cs
public class TabModel
{
    public string Header { get; set; }
    public string Content { get; set; }
}

// MainViewModel.cs
public class MainViewModel : NotificationObject
{
    public ObservableCollection<TabModel> TabItems { get; } = new ObservableCollection<TabModel>();

    public MainViewModel()
    {
        TabItems.Add(new TabModel { Header = "Tab 1", Content = "First tab content" });
        TabItems.Add(new TabModel { Header = "Tab 2", Content = "Second tab content" });
    }
}

{% endhighlight %}

{% highlight XAML %}

<Window.DataContext>
    <local:MainViewModel />
</Window.DataContext>

<syncfusion:SfTabControl ItemsSource="{Binding TabItems}"
                         x:Name="MainTabControl">
    <syncfusion:SfTabControl.ItemContainerStyle>
        <Style TargetType="{x:Type syncfusion:SfTabItem}">
            <Setter Property="HeaderTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <TextBlock Text="{Binding Header}" />
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfTabControl.ItemContainerStyle>

    <syncfusion:SfTabControl.ContentTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Content}" />
        </DataTemplate>
    </syncfusion:SfTabControl.ContentTemplate>
</syncfusion:SfTabControl>

{% endhighlight %}

{% endtabs %}

![WPF TabbedWindow](data-binding_images/wpf_tabbedwindow.png)

## Customizing Tab Header and Content

You can customize the visual presentation of tab headers and tab content by defining data templates and applying them to the [SfTabControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfTabControl.html).

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