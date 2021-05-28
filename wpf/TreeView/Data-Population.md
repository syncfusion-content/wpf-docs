---
layout: post
title: Data Population in WPF TreeView control | Syncfusion
description: Learn here all about Data Population support in Syncfusion WPF TreeView (SfTreeView) control and more.
platform: wpf
control: SfTreeView
 documentation: ug
---
# Data Population in WPF TreeView (SfTreeView)

TreeView can be populated either with the data source by using a [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemsSource) property or by creating and adding the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) in hierarchical structure to [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_Nodes) property.

## Populating Nodes by data binding - Bound Mode

[Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_Nodes) can be populated in bound mode includes following steps.

   * Create hierarchical data model
   * Bind data model to treeview

To update the collection changes in UI, it is necessary to define [NotificationSubscriptionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_NotificationSubscriptionMode) to Treeview as CollectionChanged /PropertyChanged.
`NotificationSubscriptionMode` enum has following members:

   * CollectionChange - Updates its tree structure when child items collection gets changed.
   * PropertyChange - Updates its ChildItems when associated collection property gets changed.
   * None - It is a default mode and it doesn’t reflect collection/property changes in UI.
To decide how to populate the nodes, it is necessary to set this `NodePopulationMode` API to Treeview.

The [NodePopulationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_NodePopulationMode) API has following enum values:

   * OnDemand - Populate the child nodes only when parent nodes is expanded. It is the default value.
   * Instant - Populates all the child nodes when Treeview control is initially loaded.

### Create Data Model for treeview

Create a simple data source as shown in the following code example in a new class file, and save it as FileManager.cs file:

{% tabs %}
{% highlight c# %}

//FileManager.cs
public class FileManager : INotifyPropertyChanged
{
   private string fileName;
   private ImageSource imageIcon;
   private ObservableCollection<FileManager> subFiles;

   public ObservableCollection<FileManager> SubFiles
   {
      get { return subFiles; }
      set
      {
         subFiles = value;
         RaisedOnPropertyChanged("SubFiles");
      }
   }

   public string ItemName
   {
      get { return fileName; }
      set
      {
         fileName = value;
         RaisedOnPropertyChanged("FolderName");
      }
   }
   
   public ImageSource ImageIcon
   {
       get { return imageIcon; }
       set
       {
          imageIcon = value;
          RaisedOnPropertyChanged("ImageIcon");
       }
   }

   public event PropertyChangedEventHandler PropertyChanged;

   public void RaisedOnPropertyChanged(string _PropertyName)
   {
      if (PropertyChanged != null)
      {
         PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
      }
   }
}

{% endhighlight %}
{% endtabs %}

Create a model repository class with ImageNodeInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as FileManagerViewModel.cs file:

{% tabs %}
{% highlight c# %}

public class FileManagerViewModel
{
   private ObservableCollection<FileManager> imageNodeInfo;

   public FileManagerViewModel()
   {
      GenerateSource();
   }

   public ObservableCollection<FileManager> ImageNodeInfo
   {
      get { return imageNodeInfo; }
      set { this.imageNodeInfo = value; }
   }

   private void GenerateSource()
   {
      var nodeImageInfo = new ObservableCollection<FileManager>();
      Assembly assembly = typeof(GettingStated).GetTypeInfo().Assembly;
      var doc = new FileManager() { ItemName = "Documents", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var download = new FileManager() { ItemName = "Downloads", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var mp3 = new FileManager() { ItemName = "Music", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var pictures = new FileManager() { ItemName = "Pictures", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var video = new FileManager() { ItemName = "Videos", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };

      var pollution = new FileManager() { ItemName = "Environmental Pollution.docx", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_word.png", assembly) };
      var globalWarming = new FileManager() { ItemName = "Global Warming.ppt", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_ppt.png", assembly) };
      var sanitation = new FileManager() { ItemName = "Sanitation.docx", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_word.png", assembly) };
      var socialNetwork = new FileManager() { ItemName = "Social Network.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };
      var youthEmpower = new FileManager() { ItemName = "Youth Empowerment.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };

      var games = new FileManager() { ItemName = "Game.exe", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_exe.png", assembly) };
      var tutorials = new FileManager() { ItemName = "Tutorials.zip", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_zip.png", assembly) };
      var TypeScript = new FileManager() { ItemName = "TypeScript.7z", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_zip.png", assembly) };
      var uiGuide = new FileManager() { ItemName = "UI-Guide.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };

      var song = new FileManager() { ItemName = "Goutiest", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_mp3.png", assembly) };

      var camera = new FileManager() { ItemName = "Camera Roll", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var stone = new FileManager() { ItemName = "Stone.jpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_png.png", assembly) };
      var wind = new FileManager() { ItemName = "Wind.jpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_png.png", assembly) };

      var img0 = new FileManager() { ItemName = "WIN_20160726_094117.JPG", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_img0.png", assembly) };
      var img1 = new FileManager() { ItemName = "WIN_20160726_094118.JPG", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_img1.png", assembly) };

      var video1 = new FileManager() { ItemName = "Naturals.mp4", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_video.png", assembly) };
      var video2 = new FileManager() { ItemName = "Wild.mpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_video.png", assembly) };

      doc.SubFiles = new ObservableCollection<FileManager>
      {
         pollution,
         globalWarming,
         sanitation,
         socialNetwork,
         youthEmpower
      };

      download.SubFiles = new ObservableCollection<FileManager>
      {
         games,
         tutorials,
         TypeScript,
         uiGuide
      };

      mp3.SubFiles = new ObservableCollection<FileManager>
      {
         song
      };

      pictures.SubFiles = new ObservableCollection<FileManager>
      {
         camera,
         stone,
         wind
      };
      
      camera.SubFiles = new ObservableCollection<FileManager>
      {
         img0,
         img1
      };

      video.SubFiles = new ObservableCollection<FileManager>
      {
         video1,
         video2
      };

      nodeImageInfo.Add(doc);
      nodeImageInfo.Add(download);
      nodeImageInfo.Add(mp3);
      nodeImageInfo.Add(pictures);
      nodeImageInfo.Add(video);
      imageNodeInfo = nodeImageInfo;
  }
}
{% endhighlight %}
{% endtabs %}


### Bind to hierarchical datasource

To create a tree view using data binding, set a hierarchical data collection to the [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemsSource) property. And set the child object name to the [ChildPropertyName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ChildPropertyName) property.

{% tabs %}
{% highlight xaml %}

<Window x:Class="NodeWithImageDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:NodeWithImageDemo"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf" xmlns:Engine="clr-namespace:Syncfusion.UI.Xaml.TreeView.Engine;assembly=Syncfusion.SfTreeView.WPF"
        mc:Ignorable="d">

    <Window.DataContext>
        <local:FileManagerViewModel/>
    </Window.DataContext>

    <Grid>
        <syncfusion:SfTreeView x:Name="sfTreeView" 
                               ChildPropertyName="SubFiles"
                               ItemsSource="{Binding ImageNodeInfo}">

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
                                <TextBlock Text="{Binding ItemName}"
                                                   Foreground="Black"
                                                   FontSize="14"
                                                   VerticalAlignment="Center" 
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

![Populating Nodes by data binding](DataPopulation_images/wpf-treeview-populating-nodes-by-data-binding.png)

N> View sample in [GitHub](https://github.com/SyncfusionExamples/How-to-populate-nodes-with-binding-to-a-data-in-wpf-treeview).

## Populating Nodes without data source - Unbound Mode

You can create and manage the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) objects by yourself to display the data in a hierarchical view. To create a tree view, you use a `SfTreeView` control and a hierarchy of `TreeViewNode` objects. You create the node hierarchy by adding one or more root nodes to the [SfTreeView.Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_Nodes) collection. Each `TreeViewNode` can have more nodes added to its Children collection. You can nest tree view nodes to whatever depth you require.

{% tabs %}
{% highlight xaml %}
<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:GettingStarted"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf" xmlns:Engine="clr-namespace:Syncfusion.UI.Xaml.TreeView.Engine;assembly=Syncfusion.SfTreeView.WPF" x:Class="GettingStarted.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <Syncfusion:SfTreeView HorizontalAlignment="Left" Height="414" Margin="318,0,0,0" VerticalAlignment="Center" Width="250">
            <Syncfusion:SfTreeView.Nodes>
                <Engine:TreeViewNode Content="Grains" IsExpanded="True">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Cereals" IsExpanded="True">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Rice"/>
                                <Engine:TreeViewNode Content="Barley"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                        <Engine:TreeViewNode Content="Oilseeds">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Safflower"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
                <Engine:TreeViewNode Content="Fruits" IsExpanded="true">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Orange"/>
                        <Engine:TreeViewNode Content="Apples" IsExpanded="true"/>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
                <Engine:TreeViewNode Content="Vegetables" IsExpanded="true">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Root Vegetables" IsExpanded="true">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Potato"/>
                                <Engine:TreeViewNode Content="Carrot"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                        <Engine:TreeViewNode Content="Podded">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Peanut"/>
                                <Engine:TreeViewNode Content="Lentil"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
            </Syncfusion:SfTreeView.Nodes>
        </Syncfusion:SfTreeView>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

![Populating nodes without data source in SfTreeView ](DataPopulation_images/wpf-treeview-populating-nodes-without-data-source.png)

N> View sample in [GitHub](https://github.com/SyncfusionExamples/How-to-populate-nodes-without-binding-data-as-unbound-mode-in-wpf-treeview).
