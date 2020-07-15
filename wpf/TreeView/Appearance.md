---
layout: post
title: Appearance in WPF TreeView control | Syncfusion
description: This section describes about the Appearance support in Syncfusion Wpf TreeView (SfTreeView) control and more details. 
platform: wpf
control: SfTreeView
documentation: ug
---

# Appearance in WPF TreeView (SfTreeView)

The TreeView allows customizing appearance of the underlying data, and provides different functionalities to the end-user.

## ItemTemplate

The TreeView allows you to customize the appearance of content view and expander view by setting the [ItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemTemplate.html) and [ExpanderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ExpanderTemplate.html) properties.

{% tabs %}
{% highlight xaml %}

<Window x:Class="NodeWithImageDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:NodeWithImageDemo"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d">

    <Window.DataContext>
        <local:FileManagerViewModel/>
    </Window.DataContext>

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition/>
        </Grid.RowDefinitions>

        <syncfusion:SfTreeView x:Name="sfTreeView" Grid.Row="1"
                               ChildPropertyName="SubFiles"
                               FullRowSelect="True"
                               ItemsSource="{Binding ImageNodeInfo}" >

            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <Grid x:Name="grid">
                        <Grid Grid.Row="0">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="20" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <Grid>
                                <Image Source="{Binding ImageIcon}"
                                               VerticalAlignment="Center"
                                               HorizontalAlignment="Center"
                                               Height="16"
                                               Width="16"/>
                            </Grid>
                            <Grid Grid.Column="1"
                                              Margin="1,0,0,0"
                                              VerticalAlignment="Center">
                                <Label Content="{Binding ItemName}"
                                                   Foreground="Black"
                                                   FontSize="11"
                                                   VerticalContentAlignment="Center" />
                            </Grid>
                        </Grid>
                    </Grid>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
        </syncfusion:SfTreeView>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## BindingContext for ItemTemplate

By default, the binding context of tree view item will be the data model object for Bound Mode and [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) for Unbound Mode.

For Bound Mode, you can change the binding context of the treeview items by using [ItemTemplateContextType](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemTemplateDataContextType.html) property.

{% tabs %}
{% highlight xaml %}

<Window x:Class="NodeWithImageDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:NodeWithImageDemo"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d">

    <Window.DataContext>
        <local:FileManagerViewModel/>
    </Window.DataContext>

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition/>
        </Grid.RowDefinitions>

        <TextBlock VerticalAlignment="Center" 
                       TextWrapping="Wrap" 
                       Padding="5,0,0,0" 
                       FontSize="14" 
                       Margin="5,5,5,20">
                <Run Text="This sample demonstrates the default functionalities to include images in SfTreeView."/>
        </TextBlock>

        <syncfusion:SfTreeView x:Name="sfTreeView" Grid.Row="1"
                               ChildPropertyName="SubFiles"
                               FullRowSelect="True"
                               ItemTemplateDataContextType="Node"
                               ItemsSource="{Binding ImageNodeInfo}" >

            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <Grid x:Name="grid">
                        <Grid Grid.Row="0">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="20" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <Grid>
                                <Image Source="{Binding Content.ImageIcon}"
                                               VerticalAlignment="Center"
                                               HorizontalAlignment="Center"
                                               Height="16"
                                               Width="16"/>
                            </Grid>
                            <Grid Grid.Column="1"
                                              Margin="1,0,0,0"
                                              VerticalAlignment="Center">
                                <Label Content="{Binding Content.ItemName}"
                                                   Foreground="Black"
                                                   FontSize="11"
                                                   VerticalContentAlignment="Center" />
                            </Grid>
                        </Grid>
                    </Grid>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
        </syncfusion:SfTreeView>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## ItemTemplate Selector

The TreeView allows you to customize the appearance of each item with different templates based on specific constraints by using the [ItemTemplateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemTemplateSelector.html). You can choose a [DataTemplate](https://docs.microsoft.com/en-us/dotnet/api/system.windows.datatemplate?view=netcore-3.1) for each item at runtime based on the value of data-bound property using `ItemTemplateSelector`.

{% tabs %}
{% highlight xaml %}

<Window x:Class="NodeWithImageDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:NodeWithImageDemo"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d">

    <Window.DataContext>
        <local:FileManagerViewModel/>
    </Window.DataContext>
    <Window.Resources>
        <local:ItemTemplateSelector x:Key="itemTemplateSelector"/>
    </Window.Resources>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition/>
        </Grid.RowDefinitions>

        <syncfusion:SfTreeView x:Name="sfTreeView" 
		                       Grid.Row="1"
                               ChildPropertyName="SubFiles"
                               FullRowSelect="True"
                               ItemTemplateDataContextType="Node"
                               ItemsSource="{Binding ImageNodeInfo}" 
							   ItemTemplateSelector="{StaticResource itemTemplateSelector}" >
        </syncfusion:SfTreeView>
    </Grid>
</Window>

{% endhighlight %}
{% highlight c# %}

class ItemTemplateSelector : DataTemplateSelector
{
    public override DataTemplate SelectTemplate(object item, DependencyObject container)
    {
        var treeviewNode = item as TreeViewNode;
        if (treeviewNode == null)
            return null;
        if (treeviewNode.Level == 0)
            return Application.Current.MainWindow.FindResource("RootTemplate") as DataTemplate;
        else
            return Application.Current.MainWindow.FindResource("ChildTemplate") as DataTemplate;
    }
}

{% endhighlight %}
{% endtabs %}

![ItemTemplateSelector in SfTreeView ](Appearance_images/Appearance_images2.png)

You can also download the entire source code of this demo from [here](
https://github.com/SyncfusionExamples/How-to-customize-tree-nodes-using-data-template-selector-in-wpf-treeview)

## Indentation

The TreeView allows customizing the indent spacing of items by setting the [Indentation](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~Indentation.html) property. The default value of this property is 20. This property can be customized at runtime.

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfTreeView x:Name="sfTreeView" Indentation="40" />

{% endhighlight %}
{% highlight c# %}

SfTreeView sfTreeView = new SfTreeView();
sfTreeView.Indentation = 40;

{% endhighlight %}
{% endtabs %}

## ExpanderWidth

The TreeView allows customizing the width of expander view by setting the [ExpanderWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ExpanderWidth.html) property. The default value of this property is 20. This property can be customized at runtime.

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfTreeView x:Name="sfTreeView" ExpanderWidth="40" />

{% endhighlight %}
{% highlight c# %}

SfTreeView sfTreeView = new SfTreeView();
sfTreeView.ExpanderWidth = "40";

{% endhighlight %}
{% endtabs %}

## ExpanderPosition

The TreeView allows you change the position of expander view by setting the [ExpanderPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ExpanderPosition.html) property. The default value of this property is `Start`. This property has following two positions:

Start: Allows displaying the expander view at the start position.
End: Allows displaying the expander view at the end position.

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfTreeView x:Name="sfTreeView" ExpanderPosition="End">

{% endhighlight %}
{% highlight c# %}

SfTreeView sfTreeView = new SfTreeView();
sfTreeView.ExpanderPosition = ExpanderPosition.End;

{% endhighlight %}
{% endtabs %}

## Level based styling

The TreeView allows you to customize the style of [TreeViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeViewItem.html) based on different levels by using [IValueConverter](https://docs.microsoft.com/en-us/dotnet/api/system.windows.data.ivalueconverter?view=netcore-3.1).

{% tabs %}
{% highlight xaml %}

<Window.Resources>
    <local:FontAttributeConverter x:Key="FontAttributeConverter"/>
</Window.Resources>
<Window.DataContext>
    <local:MailFolderViewModel x:Name="viewModel"/>
</Window.DataContext>

<Grid>
    <Syncfusion:SfTreeView HorizontalAlignment="Left" ItemTemplateDataContextType="Node"  ItemsSource="{Binding Folders}"  ChildPropertyName="SubFolder" >
        <Syncfusion:SfTreeView.ItemTemplate>
            <DataTemplate>
                <Label  Content="{Binding Content.FolderName}" FontWeight="{Binding Level, Converter={StaticResource FontAttributeConverter}}"
                FontSize="14"/>
            </DataTemplate>
        </Syncfusion:SfTreeView.ItemTemplate>
    </Syncfusion:SfTreeView>
</Grid>

{% endhighlight %}
{% highlight c# %}

public class FontAttributeConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var level = (int)value;
        return level == 0 ? FontWeights.Bold : FontWeights.Regular;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

![ItemTemplateSelector in SfTreeView ](Appearance_images/Appearance_images3.png)

You can also download the entire source code of this demo from [here](
https://github.com/SyncfusionExamples/How-to-customize-the-style-of-tree-nodes-based-on-its-level-using-converter-in-wpf-treeview)

## Animation

The SfTreeView supports to animate expanding or collapsing the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.TreeNodeView.html). To enable/disable the animation use [IsAnimationEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~IsAnimationEnabled.html) property of SfTreeView.

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfTreeView x:Name="sfTreeView" IsAnimationEnabled="true">

{% endhighlight %}
{% highlight c# %}

SfTreeView sfTreeView = new SfTreeView();
sfTreeView.IsAnimationEnabled = true;

{% endhighlight %}
{% endtabs %}

![ItemTemplateSelector in SfTreeView ](Appearance_images/Appearance_images1.gif)