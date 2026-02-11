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
{% highlight xaml %}
  <syncfusion:SfTreeView x:Name="treeView"
                         ItemsSource="{Binding Items}"
                         EmptyContent="No Items">
  </syncfusion:SfTreeView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
treeView.ItemsSource = viewModel.Items;
treeView.EmptyContent = "No Items";
{% endhighlight %}
{% endtabs %}

## Display Content when TreeView has no items

The `SfTreeView` control allows you to fully customize the empty Content appearance by using the `EmptyContentTemplate` property. This property lets you define a custom view and style for the `EmptyContent`.

{% tabs %}
{% highlight xaml %}
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
         <syncfusion:SfTreeView.EmptyContentTemplate>
            <DataTemplate>
                <Border Padding="10" BorderBrush="Blue" 
                        BorderThickness="2" CornerRadius="6">
                    <TextBlock Text="No Items Found"
                               FontSize="16" FontWeight="Bold"/>
                </Border>
            </DataTemplate>
        </syncfusion:SfTreeView.EmptyContentTemplate>
    </syncfusion:SfTreeView>
</Grid>

{% endhighlight %}
{% highlight c# %}
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

![EmptyContent in WPF TreeView](EmptyContent_images\wpf-treeview-emptycontent.gif)

## Binding for Empty Content Customization

The `SfTreeView` control allows data binding, enabling you to dynamically update the empty content based on values provided by the ViewModel.

{% tabs %}
{% highlight xaml %}
<Grid>
    <syncfusion:SfTreeView x:Name="treeView"
                               ItemsSource="{Binding Items}"
                               EmptyContent="{Binding EmptyContentText}">
</Grid>

{% endhighlight %}
{% highlight c# %}
public class EmptyContentSampleViewModel 
{
    private string _emptyContentText = "No items to display";
    public string EmptyContentText
    {
        get {return _emptyContentText;}
        set { _emptyContentText = value;}
    }
}
{% endhighlight %}
{% endtabs %}

