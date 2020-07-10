---
layout: post
title: Dealing with Syncfusion Ribbon control
description: This topic dealing  with  the Syncfusion WPF Ribbon Control. Defines Ribbon state and grouping RibbonTabs using ContextTabGroups.
platform: wpf
control: Ribbon
documentation: ug
---
# Dealing with WPF Ribbon 

Ribbon can be changed into three different states such as `Normal`, `Hide` and `Adorner`

## Three types of RibbonState


**Normal** – Ribbon control displays the RibbonTab content and the window content is arranged below the Ribbon. This is the default state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Normal" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![RibbonStates](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img1.jpeg)

**Hide** - RibbonTab content gets hidden in this state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Hide" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![RibbonStates](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img2.jpeg)


**Adorner** – In this state, RibbonTab content adorned above the window content

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Adorner" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![Ribbon Adorner state](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img3.jpeg)

## How to change the RibbonState in run time

Ribbon State can also be changed at the Runtime.In the below code, Ribbon State has been changed dynamically in the button click event

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner

{% endhighlight %}

{% endtabs %}

## Resize Ribbon Window
The ribbon control dynamically resizes as width of the window decreases, when the windows border touches the last placed Ribbon bar, the total Ribbon bar will be converted into a dropdown button and the items can be accessed by clicking on that dropdown arrow.

The [`IsAutoSizeFormEnabled`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.Ribbon~SetIsAutoSizeFormEnabled.html) property must be set to True to get responsive ribbon window. Same behavior will be continued to every Ribbon bar while minimized continuously. Again, the Ribbon bar will be visible if the spacing between window border and Ribbon bar has enough space to allocate all the items in that Ribbon bar. The following snippet is used for resize the ribbon window.

{% tabs %}

{% highlight XAML %}

<Grid>
 <syncfusion:Ribbon syncfusion:Ribbon.IsAutoSizeFormEnabled="True" x:Name="_ribbon" VerticalAlignment="Top">            
 </syncfusion:Ribbon>
 </Grid>

{% endhighlight %}

{% endtabs %}

![Resize Ribbon Window](RibbonResizeWindow-images/ResizeRibbonWindow.gif)


## Grouping RibbonTabs using ContextTabGroups

ContextualTabGroups are used to group the RibbonTabs for easy Navigation. This ContextTabGroups appear when a user enable their context. 

## Creating ContextTabGroup 


This ContextTabGroup can also be kept hidden and shown while required cases like in Word Document’s TABLETOOLS ContextTabGroups which gets displayed automatically, while selecting the table.  The following code snippet used to create a ContextTabGroup

{% tabs %}
 
{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table tools" IsGroupVisible="True" BackColor="Green">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![ContextTabGroup](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img1.jpeg)

## Add ContextTabGroup to the simplified layout

When the simplified layout is enabled, the ContextTabGroup can be added and its items will be displayed in a single line as shown below. To know more about the simplified layout, refer [here](https://help.syncfusion.com/wpf/ribbon/simplifiedlayout).

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow x:Class="RibbonButton_IconTemp.Window1"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:RibbonButton_IconTemp" xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        skin:SfSkinManager.VisualStyle="MaterialLight"
        Title="Untitled 1 - Ribbon Control" Height="450" Width="800">
    <Grid x:Name="grid">
        <syncfusion:Ribbon VerticalAlignment="Top" EnableSimplifiedLayoutMode="True" LayoutMode="Simplified">
            <syncfusion:Ribbon.ContextTabGroups>
                <syncfusion:ContextTabGroup
                        BackColor="Orange" IsGroupVisible="True" Label="Tools">
                    <syncfusion:RibbonTab
                            Caption="Insert"
                            IsChecked="True">
                        <syncfusion:RibbonBar
                                Header="Illustrations"
                                IsLauncherButtonVisible="True">
                            <syncfusion:RibbonButton
                                    Label="Picture"
                                    MediumIcon="Resources/Picture20.png"
                                    SizeForm="Large">
                            </syncfusion:RibbonButton>
                            <syncfusion:RibbonButton
                                    Label="Comment"
                                    MediumIcon="Resources/New Comment20.png"
                                    SizeForm="Large">
                            </syncfusion:RibbonButton>
                            <syncfusion:DropDownButton
                                    Label="Shapes"
                                    MediumIcon="Resources/Insert Shapes20.png"
                                    SizeForm="Small">
                            </syncfusion:DropDownButton>
                            <syncfusion:DropDownButton
                                    Label="Chart"
                                    MediumIcon="Resources/Base chart20.png"
                                    SizeForm="Small">
                            </syncfusion:DropDownButton>
                        </syncfusion:RibbonBar>
                    </syncfusion:RibbonTab>
                </syncfusion:ContextTabGroup>
            </syncfusion:Ribbon.ContextTabGroups>
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

Ribbon ribbon = new Ribbon();
ribbon.VerticalAlignment = VerticalAlignment.Top;
ribbon.EnableSimplifiedLayoutMode = true;
ribbon.LayoutMode = LayoutMode.Simplified;

//Creating context tab group
ContextTabGroup contextTab = new ContextTabGroup();
contextTab.Label = "Tools";
contextTab.BackColor = Colors.Orange;
contextTab.IsGroupVisible = true;

// Creating new tabs
RibbonTab insertTab = new RibbonTab();
insertTab.Caption = "Insert";
insertTab.IsChecked = true;

// Creating new bar
RibbonBar illustrationsBar = new RibbonBar();
illustrationsBar.Header = "Illustrations";

// Creating items
// Creating items
RibbonButton pictureButton = new RibbonButton();
pictureButton.Label = "Picture";
pictureButton.SizeForm = SizeForm.Large;
pictureButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Picture20.png", UriKind.RelativeOrAbsolute));

RibbonButton commentButton = new RibbonButton();
commentButton.Label = "Comment";
commentButton.SizeForm = SizeForm.Large;
commentButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/New Comment20.png", UriKind.RelativeOrAbsolute));

DropDownButton shapesButton = new DropDownButton();
shapesButton.Label = "Shapes";
shapesButton.SizeForm = SizeForm.Small;
shapesButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Insert Shapes20.png", UriKind.RelativeOrAbsolute));

DropDownButton chartButton = new DropDownButton();
chartButton.Label = "Chart";
chartButton.SizeForm = SizeForm.Small;
chartButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Base chart20.png", UriKind.RelativeOrAbsolute));

// Adding items to bar
illustrationsBar.Items.Add(pictureButton);
illustrationsBar.Items.Add(commentButton);
illustrationsBar.Items.Add(shapesButton);
illustrationsBar.Items.Add(chartButton);

// Adding bars to the tabs
insertTab.Items.Add(illustrationsBar);
//Adding ribbon tab to the context tab
contextTab.RibbonTabs.Add(insertTab);

// Adding context tab
ribbon.ContextTabGroups.Add(contextTab);
grid.Children.Add(ribbon);

SfSkinManager.SetVisualStyle(this, VisualStyles.MaterialLight);

{% endhighlight %}

{% endtabs %}

![ContextTabGroup during simplified layout](GroupingRibbonTabsusingContextTabGroups_images/ContextTabGroup_Simplified.png)


## Multiple ContextTabs

To differentiate one ContextTabGroup with one another, change its `BackColor` property of the ContextTabGroup , Since a ContextTabGroup Support to have multiple context Tab.
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table Tools" BackColor="Green" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
<syncfusion:ContextTabGroup Label="Table Grid" BackColor="Red" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![Multiple ContextTabs](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img2.jpeg)


## ContextTabGroup heading

The `Label` property of the ContextTabGroup is used to define the Heading for the ContextTabGroup. 
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table tools" BackColor="Green" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}
 
{% endtabs %}

![ContextTabGroup heading](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img3.jpeg)




## Changing the visibility at run time

ContextTabGroup visibility can also be changed at the runtime. To change the visibility, enable `IsGroupVisible` property of the ContextTabGroup
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  VerticalAlignment="Top" >
<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup x:Name="_contextTabGroup" Label="Table tools" BackColor="Red"  >
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" >
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="Design" IsChecked="False" >
</syncfusion:RibbonTab>
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>
</syncfusion:Ribbon>

{% endhighlight %}
 
{% endtabs %}
 
{% tabs %}

{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)
{
    _contextTabGroup.IsGroupVisible = true;
}

{% endhighlight %}

{% highlight VB %}
 
Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
_contextTabGroup.IsGroupVisible = True
End Sub

{% endhighlight %}
 
{% endtabs %}

![Changing the visibility at run time](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img4.jpeg)


After the Button is clicked, the ContextTabGroup visibility changes as follows

![Changing the visibility at run time](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img5.jpeg)


## Creating ContextTabGroup in MVVM

To create context tab group in Ribbon, use  `ContextGroupSource` and `ContextGroupContainerStyle` properties. Similarly we can populate ContextTabGroup to corresponding RibbonTab using `ItemsSource` and `ItemContainerStyle` properties of ContextTabGroup.

To create a ContextTabGroup in MVVM, follow below steps. 

1. Create a class for ContextTabGroup, RibbonBar and RibbonItems in Model CS file.

{% tabs %}

{% highlight C# %}

  public class CustomContextTab : INotifyPropertyChanged
    {
        private string tabheader;

        public string TabHeader
        {
            get { return tabheader; }
            set
            {
                tabheader = value;
                RaisePropertyChanged("TabHeader");
            }
        }

        private Color _backcolor;

        public Color BackColor
        {
            get { return _backcolor; }
            set
            {
                _backcolor = value;
                RaisePropertyChanged("BackColor");
            }
        }

        private bool _isgroupvisible;

        public bool IsGroupVisible
        {
            get { return _isgroupvisible; }
            set
            {
                _isgroupvisible = value;
                RaisePropertyChanged("IsGroupVisible");
            }
        }

        public ObservableCollection<CustomRibbonTab> CustomContextRibbonTabs { get; set; }

        public CustomContextTab()
        {
            CustomContextRibbonTabs = new ObservableCollection<CustomRibbonTab>();
        }

        public void RaisePropertyChanged(string name)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(name));
            }
        }
        public event PropertyChangedEventHandler PropertyChanged;
    }
    public class CustomRibbonBar
    {
        public string BarHeader { get; set; }

        public ObservableCollection<CustomRibbonItem> CustomRibbonItems { get; set; }

        public CustomRibbonBar()
        {
            CustomRibbonItems = new ObservableCollection<CustomRibbonItem>();
        }

    }

    public class CustomRibbonItem
    {
        public CustomRibbonItem()
        {
            IsSplitButton = false;
            IsBoolean = true;
        }
        public string ItemHeader
        {
            get;
            set;
        }
        public string Image { get; set; }
        public bool IsBoolean { get; set; }

        public bool IsLarge { get; set; }

        public bool IsSplitButton { get; set; }
    }
{% endhighlight %}

{% highlight VB %}
 
Public Class CustomContextTab
    Inherits INotifyPropertyChanged

    Private tabheader As String

    Public Property TabHeader As String
        Get
            Return tabheader
        End Get
        Set(ByVal value As String)
            tabheader = value
            RaisePropertyChanged("TabHeader")
        End Set
    End Property

    Private _backcolor As Color

    Public Property BackColor As Color
        Get
            Return _backcolor
        End Get
        Set(ByVal value As Color)
            _backcolor = value
            RaisePropertyChanged("BackColor")
        End Set
    End Property

    Private _isgroupvisible As Boolean

    Public Property IsGroupVisible As Boolean
        Get
            Return _isgroupvisible
        End Get
        Set(ByVal value As Boolean)
            _isgroupvisible = value
            RaisePropertyChanged("IsGroupVisible")
        End Set
    End Property

    Public Property CustomContextRibbonTabs As ObservableCollection(Of CustomRibbonTab)

    Public Sub New()
        CustomContextRibbonTabs = New ObservableCollection(Of CustomRibbonTab)()
    End Sub

    Public Sub RaisePropertyChanged(ByVal name As String)
        RaiseEvent PropertyChanged(Me, New PropertyChangedEventArgs(name))
    End Sub

    Public Event PropertyChanged As PropertyChangedEventHandler
End Class

Public Class CustomRibbonBar
    Public Property BarHeader As String
    Public Property CustomRibbonItems As ObservableCollection(Of CustomRibbonItem)

    Public Sub New()
        CustomRibbonItems = New ObservableCollection(Of CustomRibbonItem)()
    End Sub
End Class

Public Class CustomRibbonItem
    Public Sub New()
        IsSplitButton = False
        IsBoolean = True
    End Sub

    Public Property ItemHeader As String
    Public Property Image As String
    Public Property IsBoolean As Boolean
    Public Property IsLarge As Boolean
    Public Property IsSplitButton As Boolean
End Class


{% endhighlight %}

{% endtabs %}

2. Create a View model class and then add ContextTabGroup , RibbonBars and RibbonItems with some properties.

{% tabs %}

{% highlight C# %}

  public class ViewModel
    {
        public ObservableCollection<CustomContextTab> CustomContextTabs { get; set; }

        public ViewModel()
        {
            CustomContextTabs = new ObservableCollection<CustomContextTab>();
            PopulateContextTabs();        
        }

        private void PopulateContextTabs()
        {
            CustomContextTab contexttab1 = new CustomContextTab() { TabHeader = "ContextTabGroup1",BackColor=Colors.Red,IsGroupVisible=true };
            CustomRibbonTab Tab1 = new CustomRibbonTab() { TabHeader = "TabGroup1" };
            PopulateRibbonHomeBars(Tab1);
            CustomRibbonTab Tab2 = new CustomRibbonTab() { TabHeader = "TabGroup2" };
            PopulateRibbonInsertBars(Tab2);

            contexttab1.CustomContextRibbonTabs.Add(Tab1);
            contexttab1.CustomContextRibbonTabs.Add(Tab2);

            CustomContextTabs.Add(contexttab1);

            CustomContextTab contexttab2 = new CustomContextTab() { TabHeader = "ContextTabGroup2",BackColor=Colors.Green,IsGroupVisible=true };
            CustomRibbonTab Tab11 = new CustomRibbonTab() { TabHeader = "TabGroup11" };
            PopulateRibbonHomeBars(Tab11);
            CustomRibbonTab Tab21 = new CustomRibbonTab() { TabHeader = "TabGroup21" };
            PopulateRibbonInsertBars(Tab21);

            contexttab2.CustomContextRibbonTabs.Add(Tab11);
            contexttab2.CustomContextRibbonTabs.Add(Tab21);

            CustomContextTabs.Add(contexttab2);
        }

        void PopulateRibbonHomeBars(CustomRibbonTab Tab)
        {
            CustomRibbonBar Bar1 = new CustomRibbonBar() { BarHeader = "Clipboard" };
            PopuplateRibbonNewItems(Bar1);
            CustomRibbonBar Bar2 = new CustomRibbonBar() { BarHeader = "Editing" };
            PopuplateRibbonEditingItems(Bar2);
            Tab.CustomRibbonBars.Add(Bar1);
            Tab.CustomRibbonBars.Add(Bar2);
        }

        void PopuplateRibbonNewItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Paste", IsLarge = true, Image = "Paste32.png" };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Cut", Image = "Cut16.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Copy", Image = "Copy16.png" };
            CustomRibbonItem Item4 = new CustomRibbonItem() { ItemHeader = "Format Painter", Image = "FormatPainter16.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
            Bar.CustomRibbonItems.Add(Item4);
        }

        private void PopuplateRibbonEditingItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Hyperlink", IsLarge = true, Image = "hyperlink32.png" };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Replace", IsLarge = true, Image = "replace_32.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Zoom", IsLarge = true, Image = "Zoom_32x32.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
        }

        private void PopulateRibbonInsertBars(CustomRibbonTab Tab)
        {
            CustomRibbonBar Bar2 = new CustomRibbonBar() { BarHeader = "Mail" };
            PopuplateRibbonMailItems(Bar2);
            CustomRibbonBar Bar1 = new CustomRibbonBar() { BarHeader = "Tables" };
            PopuplateRibbonTablesItems(Bar1);
            Tab.CustomRibbonBars.Add(Bar2);
            Tab.CustomRibbonBars.Add(Bar1);
        }

        private void PopuplateRibbonMailItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Attach File", IsLarge = true, Image = "base_paperclip_32.png",IsSplitButton=true };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Business card", IsLarge = true, Image = "base_business_contacts.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Audio", IsLarge = true, Image = "base_speaker_32.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
        }

        private void PopuplateRibbonTablesItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Tables", IsLarge = true, IsSplitButton = true, Image = "Table_32.png" };
            Bar.CustomRibbonItems.Add(Item1);
        }
    }

{% endhighlight %}

{% highlight VB %}

Public Class ViewModel
    Public Property CustomContextTabs As ObservableCollection(Of CustomContextTab)

    Public Sub New()
        CustomContextTabs = New ObservableCollection(Of CustomContextTab)()
        PopulateContextTabs()
    End Sub

    Private Sub PopulateContextTabs()
        Dim contexttab1 As CustomContextTab = New CustomContextTab() With {
            .TabHeader = "ContextTabGroup1",
            .BackColor = Colors.Red,
            .IsGroupVisible = True
        }
        Dim Tab1 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup1"
        }
        PopulateRibbonHomeBars(Tab1)
        Dim Tab2 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup2"
        }
        PopulateRibbonInsertBars(Tab2)
        contexttab1.CustomContextRibbonTabs.Add(Tab1)
        contexttab1.CustomContextRibbonTabs.Add(Tab2)
        CustomContextTabs.Add(contexttab1)
        Dim contexttab2 As CustomContextTab = New CustomContextTab() With {
            .TabHeader = "ContextTabGroup2",
            .BackColor = Colors.Green,
            .IsGroupVisible = True
        }
        Dim Tab11 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup11"
        }
        PopulateRibbonHomeBars(Tab11)
        Dim Tab21 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup21"
        }
        PopulateRibbonInsertBars(Tab21)
        contexttab2.CustomContextRibbonTabs.Add(Tab11)
        contexttab2.CustomContextRibbonTabs.Add(Tab21)
        CustomContextTabs.Add(contexttab2)
    End Sub

    Private Sub PopulateRibbonHomeBars(ByVal Tab As CustomRibbonTab)
        Dim Bar1 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Clipboard"
        }
        PopuplateRibbonNewItems(Bar1)
        Dim Bar2 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Editing"
        }
        PopuplateRibbonEditingItems(Bar2)
        Tab.CustomRibbonBars.Add(Bar1)
        Tab.CustomRibbonBars.Add(Bar2)
    End Sub

    Private Sub PopuplateRibbonNewItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Paste",
            .IsLarge = True,
            .Image = "Paste32.png"
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Cut",
            .Image = "Cut16.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Copy",
            .Image = "Copy16.png"
        }
        Dim Item4 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Format Painter",
            .Image = "FormatPainter16.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
        Bar.CustomRibbonItems.Add(Item4)
    End Sub

    Private Sub PopuplateRibbonEditingItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Hyperlink",
            .IsLarge = True,
            .Image = "hyperlink32.png"
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Replace",
            .IsLarge = True,
            .Image = "replace_32.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Zoom",
            .IsLarge = True,
            .Image = "Zoom_32x32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
    End Sub

    Private Sub PopulateRibbonInsertBars(ByVal Tab As CustomRibbonTab)
        Dim Bar2 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Mail"
        }
        PopuplateRibbonMailItems(Bar2)
        Dim Bar1 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Tables"
        }
        PopuplateRibbonTablesItems(Bar1)
        Tab.CustomRibbonBars.Add(Bar2)
        Tab.CustomRibbonBars.Add(Bar1)
    End Sub

    Private Sub PopuplateRibbonMailItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Attach File",
            .IsLarge = True,
            .Image = "base_paperclip_32.png",
            .IsSplitButton = True
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Business card",
            .IsLarge = True,
            .Image = "base_business_contacts.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Audio",
            .IsLarge = True,
            .Image = "base_speaker_32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
    End Sub

    Private Sub PopuplateRibbonTablesItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Tables",
            .IsLarge = True,
            .IsSplitButton = True,
            .Image = "Table_32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
    End Sub
End Class

{% endhighlight %}

{% endtabs %}

3. Now bind the properties of View model in XAML.

{% tabs %}

{% highlight XAML %}

  <DataTemplate x:Key="Ribbonbutton">
     <syncfusion:RibbonButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}" Visibility="{Binding IsBoolean, Converter={StaticResource visibility}}" LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>
  </DataTemplate>

  <DataTemplate x:Key="Splitbutton">
     <syncfusion:SplitButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}" Visibility="{Binding IsBoolean, Converter={StaticResource visibility}}" LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>
   </DataTemplate>
    <syncfusion:Ribbon VerticalAlignment="Top"
                   Name="Ribbon1"     RibbonBarCollapseImage="App.ico"
			       ItemsSource="{Binding CustomRibbonTabs}" ContextGroupSource="{Binding CustomContextTabs}" >
            
            <syncfusion:Ribbon.ItemContainerStyle>
                            <Style TargetType="{x:Type syncfusion:RibbonTab}">
                                <Setter Property="Caption" Value="{Binding TabHeader}"></Setter>
                                <Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}"/>
                                <Setter Property="ItemContainerStyle">
                                    <Setter.Value>
                                        <Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">
                                <Setter Property="Header" Value="{Binding BarHeader}"/>
                                            <Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/>
                                <Setter Property="ItemTemplateSelector" Value="{StaticResource selector}"/>
                              
                            </Style>
                                    </Setter.Value>
                                </Setter>
                            </Style>
            </syncfusion:Ribbon.ItemContainerStyle>

            <syncfusion:Ribbon.ContextGroupContainerStyle>
                <Style TargetType="syncfusion:ContextTabGroup">
                    <Setter Property="Label" Value="{Binding TabHeader}" />
                    <Setter Property="BackColor" Value="{Binding BackColor, Mode=TwoWay}" />
                    <Setter Property="IsGroupVisible" Value="{Binding IsGroupVisible, Mode=TwoWay}" />
                    <Setter Property="ItemsSource" Value="{Binding CustomContextRibbonTabs}" />
                    <Setter Property="ItemContainerStyle">
                        <Setter.Value>
                            <Style TargetType="syncfusion:RibbonTab">
                                <Setter Property="Caption" Value="{Binding TabHeader}" />
                                <Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}" />
                                <Setter Property="ItemContainerStyle">
                                    <Setter.Value>
                                        <Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">
                                            <Setter Property="Header" Value="{Binding BarHeader}"/>
                                            <Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/>
                                            <Setter Property="ItemTemplateSelector" Value="{StaticResource selector}"/>

                                            <Setter Property="CollapseImage" Value="/Images/FormatPainter16.png" />
                                
                                        </Style>
                                    </Setter.Value>
                                </Setter>
                            </Style>
                        </Setter.Value>
                    </Setter>

                </Style>
            </syncfusion:Ribbon.ContextGroupContainerStyle>
         
        </syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}


4. Add a converter class for binding conversions

{% tabs %}

{% highlight C# %}

 public class BooltoSizeformConverter:IValueConverter
    {
        #region IValueConverter Members

        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
           
            if (value.Equals(true))
            {
                return "Large";
            }
            else
            {
                return "Small";
            }
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new NotImplementedException();
        }

        #endregion
    }

    public class BooltoVisibilityConverter : IValueConverter
    {
        #region IValueConverter Members

        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            
            if (value.Equals(true))
            {
                return Visibility.Visible;
            }
            else
            {
                return Visibility.Collapsed;
            }
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new NotImplementedException();
        }

        #endregion
    }

    public class ItemDataTemplateSelector : DataTemplateSelector
    {
        public override DataTemplate SelectTemplate(object item, DependencyObject container)
        {
            FrameworkElement element = container as FrameworkElement;

            if (element != null && item != null )
            {
                if (item is CustomRibbonItem && (item as CustomRibbonItem).IsSplitButton)
                {
                    return
                        element.FindResource("Splitbutton") as DataTemplate;
                }
                else
                {
                    return element.FindResource("Ribbonbutton") as DataTemplate;
                }
                
            }

            return null;
        }
    }

    public class ImageConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            if (value != null)
            {
                string str = value.ToString();

                return "../Images/" + str;
            }
            else
                return value;
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new System.NotImplementedException();
        }
    }

{% endhighlight %}

{% highlight VB %}

Public Class BooltoSizeformConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value.Equals(True) Then
            Return "Large"
        Else
            Return "Small"
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New NotImplementedException()
    End Function
End Class

Public Class BooltoVisibilityConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value.Equals(True) Then
            Return Visibility.Visible
        Else
            Return Visibility.Collapsed
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New NotImplementedException()
    End Function
End Class

Public Class ItemDataTemplateSelector
    Inherits DataTemplateSelector

    Public Overrides Function SelectTemplate(ByVal item As Object, ByVal container As DependencyObject) As DataTemplate
        Dim element As FrameworkElement = TryCast(container, FrameworkElement)

        If element IsNot Nothing AndAlso item IsNot Nothing Then

            If TypeOf item Is CustomRibbonItem AndAlso (TryCast(item, CustomRibbonItem)).IsSplitButton Then
                Return TryCast(element.FindResource("Splitbutton"), DataTemplate)
            Else
                Return TryCast(element.FindResource("Ribbonbutton"), DataTemplate)
            End If
        End If

        Return Nothing
    End Function
End Class

Public Class ImageConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value IsNot Nothing Then
            Dim str As String = value.ToString()
            Return "../Images/" & str
        Else
            Return value
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New System.NotImplementedException()
    End Function
End Class


{% endhighlight %}

{% endtabs %}

![RibbonContextTabGroupMVVM](GroupingRibbonTabsusingContextTabGroups_images/RibbonContextTabGroupMVVM.png)

## Detecting selection changes in RibbonTab

The [`SelectionChanging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.Ribbon~SelectionChanging_EV.html) event notifies when the user attempts to switch tab in the Ribbon control. The [`SelectionChanging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.Ribbon~SelectionChanging_EV.html) event  receives an argument of the type **CancelEventArgs** that allows us to cancel the switching operation. 

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top" SelectionChanging="Ribbon_SelectionChanging">
    <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
    <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
    <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
    <syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>


{% endhighlight %}
 
{% endtabs %}
 
{% tabs %}

{% highlight C# %}

private void Ribbon_SelectionChanging(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}

{% endhighlight %}

{% highlight VB %}
 
Private Sub Ribbon_SelectionChanging(ByVal sender As Object, ByVal e As System.ComponentModel.CancelEventArgs)
    e.Cancel = True
End Sub

{% endhighlight %}
 
{% endtabs %}

