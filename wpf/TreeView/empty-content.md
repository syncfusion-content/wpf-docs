---
layout: post
title: EmptyContent in WPF TreeView control | Syncfusion®
description: Learn here about EmptyContent support in Syncfusion® WPF TreeView (SfTreeView) control, its elements and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# Empty Content WPF TreeView (SfTreeView)

The [SfTreeView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.html) control allows you to display and customize the empty content when no data is available. The `EmptyContent` property can be set to either a string or a view, and it will be displayed when the [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemsSource) is empty or null, or the [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_Nodes) collection is empty. `EmptyContentTemplate` is used to customize the appearance of `EmptyContent`.

## Display a string when TreeView has no items

The `EmptyContent` property in `SfTreeView` can be set to a string, which will be displayed when no items are present in the tree view.

{% tabs %}
{% highlight xaml hl_lines="3" %}
  <syncfusion:SfTreeView x:Name="treeView"
                         ItemsSource="{Binding Items}"
                         EmptyContent="No Items">
  </syncfusion:SfTreeView>
</ContentPage>
{% endhighlight %}
{% highlight c# hl_lines="3" %}
SfTreeView treeView = new SfTreeView();
treeView.ItemsSource = viewModel.Items;
treeView.EmptyContent = "No Items";
{% endhighlight %}
{% endtabs %}

## Display Content when TreeView has no items

The `SfTreeView` control uses the `EmptyContent` property to display a custom view when the tree view has no items.

{% tabs %}
{% highlight xaml hl_lines="14" %}

<Window x:Class="syncfusion.treeviewdemos.wpf.FilteringDemo"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:syncfusion.treeviewdemos.wpf"
        xmlns:behavior="http://schemas.microsoft.com/xaml/behaviors"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d">

    <Window.DataContext>
        <local:FileManagerViewModel/>
    </Window.DataContext>
    <Grid Width="450" Margin="0,50">
    <Grid.RowDefinitions>
        <RowDefinition Height="30"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <TextBox x:Name="TextBox" Padding="2,0,2,0" BorderThickness="0.5" Text="{Binding FilterText, UpdateSourceTrigger=PropertyChanged}" Margin="0,0,0,3" />
    <syncfusion:SfTreeView
        Grid.Row="1"
        x:Name="treeView"
        BorderThickness="1"
        AutoExpandMode="AllNodes"
        FocusVisualStyle="{x:Null}"
        IsAnimationEnabled="True"
        ItemsSource="{Binding CollectionView}"
        ChildPropertyName="SubFiles">
        <syncfusion:SfTreeView.ItemTemplate>
            <DataTemplate>
                <Grid>
                    <TextBlock VerticalAlignment="Center"
                           Text="{Binding FileName}" />
                </Grid>
            </DataTemplate>
        </syncfusion:SfTreeView.ItemTemplate>
        <behavior:Interaction.Triggers>
            <behavior:EventTrigger EventName="Loaded">
                <local:TreeViewFilterTrigger/>
            </behavior:EventTrigger>
        </behavior:Interaction.Triggers>
        <syncfusion:SfTreeView.EmptyContent>
            <Border Padding="10" BorderBrush="Blue" 
                    BorderThickness="2" CornerRadius="6">
                <TextBlock Text="No Items Found"
                           FontSize="16" FontWeight="Bold"/>
            </Border>
        </syncfusion:SfTreeView.EmptyContent>
    </syncfusion:SfTreeView>
</Grid>

{% endhighlight %}
{% highlight c# hl_lines="34" %}


public class FileManagerViewModel : NotificationObject
{
    private ObservableCollection<FileManager> imageNodeInfo;

    public object Item { get; set; }

    public FileManagerViewModel()
    {
        this.Folders = GetFiles();
        this.ImageNodeInfo = GenerateSource();
        CollectionView = new ListCollectionView(ImageNodeInfo);
        GenerateListViewData();
    }

    public ObservableCollection<Folder> Folders { get; set; }

    public ObservableCollection<FileManager> ImageNodeInfo
    {
        get { return imageNodeInfo; }
        set { this.imageNodeInfo = value; }
    }

    public ObservableCollection<Folder> ListViewCollection { get; set; }

    public ListCollectionView CollectionView { get; set; }

    internal delegate void FilterChanged();
    internal FilterChanged filterChanged;

    private string filterText = string.Empty;

    public string FilterText
    {
        get { return filterText; }
        set
        {
            filterText = value;
            if (filterChanged != null)
                filterChanged();
            RaisePropertyChanged("FilterText");
        }
    }

    private ObservableCollection<FileManager> GenerateSource()
    {
        var nodeImageInfo = new ObservableCollection<FileManager>();

        var doc = new FileManager() { FileName = "Documents", ImageIcon = folderIcon, Visibility = Visibility.Collapsed };
        var download = new FileManager() { FileName = "Downloads", ImageIcon = folderIcon, Visibility = Visibility.Collapsed };
        var mp3 = new FileManager() { FileName = "Music", ImageIcon = folderIcon, Visibility = Visibility.Collapsed };
        var pictures = new FileManager() { FileName = "Pictures", ImageIcon = folderIcon, Visibility = Visibility.Collapsed };
        var video = new FileManager() { FileName = "Videos", ImageIcon = folderIcon, Visibility = Visibility.Collapsed };

        var pollution = new FileManager()
        {
            FileName = "Environmental Pollution.docx",
            FileDescription = "A holistic examination of environmental pollution, from its sources to its effects on flora, fauna, and humans.",
            ImageIcon = this.wordIcon
        };
    }
}

{% endhighlight %}
{% endtabs %}

N> The view displayed by the `EmptyContent` can be a single view or a view that includes multiple child views.

![EmptyContent in WPF TreeView](EmptyContent_images\wpf-treeview-emptycontent.gif)

## Empty Content customization

The `SfTreeView` control allows you to fully customize the empty Content appearance by using the `EmptyContentTemplate` property. This property lets you define a custom view and style for the `EmptyContent`.

{% tabs %}
{% highlight xaml hl_lines="14" %}
<Grid>
    <syncfusion:SfTreeView x:Name="treeView"
                           ItemsSource="{Binding CollectionView}"
                           AutoExpandMode="AllNodes">

        <syncfusion:SfTreeView.EmptyContentTemplate>
            <DataTemplate>
                <Border>
                      ....
                </Border>
            </DataTemplate>
        </syncfusion:SfTreeView.EmptyContentTemplate>
    </syncfusion:SfTreeView>
</Grid>

{% endhighlight %}
{% endtabs %}

N>
* The `EmptyContentTemplate` will only be applied when the `EmptyContent` property is explicitly defined. If `EmptyContent` is not set, the template will not be displayed.
* `EmptyContent` can be set to custom data model and the appearance of the `EmptyContent` can be customized by using the `EmptyContentTemplate`.

