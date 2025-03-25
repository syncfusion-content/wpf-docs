---
layout: post
title: Data Binding in WPF Docking control | Syncfusion®
description: Learn here all about Data Binding support in Syncfusion® WPF Docking (DockingManager) control and more.
platform: WPF
control: DockingManager
documentation: ug
---

# Data Binding in WPF Docking (DockingManager)

Data Binding is the process of establishing a connection between the application UI and business logic. Data Binding can be unidirectional (Source -> Target or Target -> Source) or bidirectional (Source &lt;-&gt; target). 

## Adding Docking Window child through ItemsSource:

`DockingManager` [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ItemsSource) property allows to bind the Observable Collection of [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html). [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html) class which contains all attached properties of `DockingManager`.

The following code snippet explains how to use the [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ItemsSource) property

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager  x:Name="docking"  ItemsSource="{Binding DockCollections }" />

{% endhighlight %}

{% highlight C# %}

DockingManager docking = new DockingManager();

docking.ItemsSource = DockCollections;

{% endhighlight %}

{% endtabs %}

Adding `DockItem` to collection:

{% tabs %}

{% highlight C# %}

public partial class MainWindow : Window

{

public MainWindow()

{

InitializeComponent();

DockCollections = new ObservableCollection<DockItem>();

DockCollections.Add(new DockItem() { Header = "ToolBox"});

DockCollections.Add(new DockItem() { Header = "Integration"});

DockCollections.Add(new DockItem() { Header = "Features"});

this.DataContext = this;

}

private ObservableCollection<DockItem> _dockcollection;

public ObservableCollection<DockItem> DockCollections

{

get

{

return _dockcollection;

}

set

{

_dockcollection = value;

}

}

}

{% endhighlight %}

{% endtabs %}


![WPF Docking Data Binding](Data-Binding-images/wpf-docking-data-binding.jpeg)


## Docking Window in Different side

We have docked the docking child window in five sides these are,

* Left
* Right 
* Top
* Bottom
* Tabbed

To dock the children of `DockingManager` in different side, use [SideInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SideInDockedMode) mode property of [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html) class.

{% tabs %}

{% highlight C# %}

DockCollections.Add(new DockItem() { Header = "Docking Left", SideInDockedMode = DockSide.Left });

DockCollections.Add(new DockItem() { Header = "Docking Top", SideInDockedMode = DockSide.Top });

DockCollections.Add(new DockItem() { Header = "Docking Right",SideInDockedMode=DockSide.Right });

DockCollections.Add(new DockItem() { Header = "Docking Bottom", SideInDockedMode = DockSide.Bottom });

{% endhighlight %}

{% endtabs %}



![WPF Docking Window in Different Side](Data-Binding-images/wpf-docking-window-in-different-side.jpeg)


## Configure the Docking window through ItemsSource

Docking window can also be docked at any side of the Target Docking Window through an attached property named [TargetNameInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_TargetNameInDockedMode)

Also to set as Tabbed Window, the window should aware of a [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html) Name of corresponding target window. The following code helps to arrange children of `DockingManager` that targets a single Docking window docked along Left, Top, Right and Tabbed.

N> The following code snippet explains how to use all attached properties of `DockingManager` using [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html) class.

{% tabs %}

{% highlight C# %}

DockCollections = new ObservableCollection<DockItem>();

DockCollections.Add(new DockItem() { Header = "ToolBox", State = DockState.Dock, DesiredWidthInDockedMode = 300d });

DockCollections.Add(new DockItem() { Header = "Integration", State = DockState.Document});

DockCollections.Add(new DockItem() { Header = "Features",  State = DockState.Document });

DockCollections.Add(new DockItem() { Header = "Docking", State = DockState.Document});

DockCollections.Add(new DockItem() { Header = "Solution Explorer", Name = "solution", State = DockState.Dock, SideInDockedMode = DockSide.Right, DesiredWidthInDockedMode = 300d });

DockCollections.Add(new DockItem() { Header = "Properties Window", Name = "Properties", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "solution" });

DockCollections.Add(new DockItem() { Header = "OutPut", Name = "Output", State = DockState.Dock, SideInDockedMode = DockSide.Bottom,DesiredHeightInDockedMode=200d});

DockCollections.Add(new DockItem() { Header = "Error List", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "Output"});

DockCollections.Add(new DockItem() { Header = "Find Symbol Results", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "Output"});

DockCollections.Add(new DockItem() { Header = "Find Results", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "Output"});

{% endhighlight %}

{% endtabs %}


![WPF Docking Window Configuration through Items Source](Data-Binding-images/wpf-docking-window-configuration-through-items-source.jpeg)

## Customizing the Header of DockItem

Header of each [DockItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html) can be customizable using the [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_HeaderStyleProperty). The `Header` property supports objects, allowing flexible customization with text, images, or other UI elements. This enables unique header styling for each DockItem, providing better control over its appearance and visibility.

{% tabs %}

{% highlight C# %}

 public class Header
 {
     public string Title { get; set; }

     public Geometry IconData { get;set;}

     public Size IconSize { get; set; }
 }

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

public class DockViewModel : NotificationObject
{
    public DockViewModel()
    {
        GenerateDockItemCollection();
    }
    private ObservableCollection<DockItem> dockItems;

    public ObservableCollection<DockItem> DockItemCollection
    {
        get { return dockItems; }
        set { dockItems = value; this.RaisePropertyChanged(nameof(DockItemCollection)); }
    }

    private void GenerateDockItemCollection()
    {
        DockItemCollection = new ObservableCollection<DockItem>();

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "Toolbox", IconData = Geometry.Parse("M9.7000122,0L16.600006,1.6000004 11.100006,6.3999721 17.100006,13.099962 20.600006,9.5999738 20.5,9.3999626C20.299988,8.8999635 20.200012,8.2999603 20.200012,7.6999861 20.200012,4.4999849 22.799988,1.8999874 26,1.8999873 26.600006,1.8999874 27.100006,1.9999931 27.600006,2.0999989L24,3.8999805 24.600006,8.8999635 29.5,9.6999799 31.399994,6.0999858C31.899994,6.4999782 32,6.9999763 32,7.5999805 32,10.799952 29.399994,13.399949 26.200012,13.399949 25.299988,13.399949 24.399994,13.199968 23.700012,12.799945L23.600006,12.699969 20,16.299933 28.399994,25.699927 30.600006,28.099913C31.399994,28.999903 31.399994,30.399893 30.399994,31.299883 29.5,32.099898 28.100006,32.099898 27.200012,31.099901L26.5,30.299887 26.299988,30.099905 24.299988,27.899901C24.200012,27.799895,24.200012,27.799895,24.200012,27.699919L16.700012,19.399929 12.299988,23.699932 12.399994,23.899914C12.600006,24.499918 12.799988,25.199928 12.799988,25.899906 12.799988,29.099909 10.200012,31.699906 7,31.699906 6.3999939,31.699906 5.8999939,31.599901 5.3999939,31.499895L9,29.699913 8.3999939,24.69993 3.2999878,23.99992 1.3999939,27.599915C1.2000122,27.099915 1.2000122,26.499911 1.2000122,25.899906 1.2000122,22.699936 3.7999878,20.09994 7,20.09994 7.7999878,20.09994 8.6000061,20.299919 9.2999878,20.599938L9.3999939,20.699944 13.899994,16.299933 7.8999939,9.4999677 4,12.89995 0,8.5999777z") , IconSize = new Size(15,15) }, Name = "tool", State = DockState.Dock, DesiredWidthInDockedMode = 150, HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "MainWindow.xaml.cs" }, State = DockState.Document, HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "MainWindow.xaml", IconData = Geometry.Parse("M3.3169894,18.909973L3.3169894,20.480957 14.341993,20.480957 14.341993,18.909973z M3.3169894,12.10199L3.3169894,13.672974 19.114001,13.672974 19.114001,12.10199z M16.406999,1.1129761L21.374013,6.3989868 17.453996,6.3989868C16.875993,6.3989868,16.406999,5.9299927,16.406999,5.3519897z M2.2689838,0L14.893996,0 14.893996,5.6429443C14.893996,6.8959961,15.910995,7.9119873,17.163987,7.9119873L22.457999,7.9119873 22.457999,29.730957C22.457999,30.983948,21.442006,32,20.189015,32L2.2689838,32C1.0159922,32,4.4543413E-08,30.983948,0,29.730957L0,2.2689819C4.4543413E-08,1.0159912,1.0159922,0,2.2689838,0z"), IconSize = new Size(15,15) }, State = DockState.Document , HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "Properties", IconData = Geometry.Parse("M11.800031,24L31.799999,24 31.799999,32 11.800031,32z M0,24L7.999988,24 7.999988,32 0,32z M11.800031,12L31.799999,12 31.799999,20 11.800031,20z M0,12L7.999988,12 7.999988,20 0,20z M11.800031,0L31.799999,0 31.799999,8 11.800031,8z M0,0L7.999988,0 7.999988,8 0,8z"), IconSize = new Size(15, 15) }, Name = "Properties", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "solution", HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "Solution Explorer" }, DesiredWidthInDockedMode = 150, Name = "solution", State = DockState.Dock, SideInDockedMode = DockSide.Right, HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = new Header { Title = "Warning", IconData = Geometry.Parse("M14.966003,22.147998L17.112,22.147998 17.112,24.293016 14.966003,24.293016z M14.874008,13.098992L17.195007,13.098992 17.195007,15.726005 16.645004,21.407031 15.432007,21.407031 14.874008,15.726005z M16,5.1690032L4.1110077,27.212022 27.889008,27.212022z M16,0L24,14.832999 32,29.666 16,29.666 0,29.666 8,14.832999z") , IconSize = new Size(15, 15) }, Name = "Output", DesiredHeightInDockedMode = 150, State = DockState.Dock, SideInDockedMode = DockSide.Bottom, HeaderTemplate = (DataTemplate)Application.Current.FindResource("HeaderTemplate") });

        DockItemCollection.Add(new DockItem() { Header = "Error List", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "Output"});

        DockItemCollection.Add(new DockItem() { Header = "Find Results", State = DockState.Dock, SideInDockedMode = DockSide.Tabbed, TargetNameInDockedMode = "Output" });
    }
}

{% endhighlight %}

{% endtabs %}

![WPF DockItem Header Appearance Customization](Dealing-with-Windows_images/DockHeader.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-docking-manager-wpf-examples/tree/master/Samples/DockItem%20Header)