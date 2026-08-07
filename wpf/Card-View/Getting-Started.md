---
layout: post
title: Getting Started with WPF Card View control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF Card View control, its elements and more.
platform: wpf
control: CardView
documentation: ug
---

# Getting Started with WPF Card View

This section describes how to create a [CardView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html) control in a WPF application and overview of its basic functionalities.

## Structure of CardView control

![Structure of WPF CardView Control](Getting-Started_images/Structure.png)

## Assembly deployment

Install the Syncfusion WPF `Tools` NuGet package to add the required assemblies to your project:

```console
Install-Package Syncfusion.Tools.WPF
```

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#cardview) section to get the list of assemblies that are added by the NuGet package.

Refer to the [NuGet Packages Documentation](https://help.syncfusion.com/wpf/installation/install-nuget-packages) to find more details about installing NuGet packages in a WPF application.

## Adding WPF CardView control via designer

1. The `CardView` control can be added to an application by dragging it from the toolbox to a designer view. The following dependent assemblies will be added automatically:
	* Syncfusion.Shared.WPF
	* Syncfusion.Tools.WPF

![wpf card view control added by designer](Getting-Started_images/wpf-card-view-control-added-by-designer.png)

2. Set the properties for the `CardView` control in design mode using the SmartTag feature.

## Adding WPF CardView control via XAML

To add the `CardView` control manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio.
2. Add the following required assembly references to the project:
	* Syncfusion.Shared.WPF
	* Syncfusion.Tools.WPF
3. Import the Syncfusion WPF schema **http://schemas.syncfusion.com/wpf**.
4. Declare the `CardView` control in the XAML page.

{% capture codesnippet1 %}
{% tabs %}

{% highlight XAML %}

<Window x:Class="CardViewSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CardViewSample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="Card View" Height="450" Width="800">
    <Grid Name="grid">
        <syncfusion:CardView Name="cardView"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

## Adding WPF CardView control via C#

To add the `CardView` control manually in C#, follow these steps:

1. Create a new WPF application via Visual Studio.
2. Add the following required assembly references to the project:
	* Syncfusion.Shared.WPF
	* Syncfusion.Tools.WPF
3. Include the required namespace.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Tools.Controls;

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

4. Create an instance of `CardView` control, and add it to the window.

{% capture codesnippet3 %}
{% tabs %}
{% highlight C# %}

namespace CardViewSample
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of CardView control
            CardView cardView = new CardView();
            //Adding CardView as window content
            this.Content = cardView;
        }
    }
}

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet3 | OrderList_Indent_Level_1 }}

![wpf card view control added manually](Getting-Started_images/wpf-card-view-control-added-manually.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Getting-Started)

## Populating items using CardViewItem

You can add the card items inside the control by adding the [CardViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardViewItem.html) into the `CardView.Items` collection property.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView Name="cardView">
    <syncfusion:CardViewItem Header="Item 1">
        <TextBlock Text="Fruits"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 2">
        <TextBlock Text="Stationery"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 3">
        <TextBlock Text="Dresses"/>
    </syncfusion:CardViewItem>
</syncfusion:CardView>

{% endhighlight %}
{% highlight C# %}

CardViewItem cardViewItem1 = new CardViewItem()
{
    Header = "Item 1",
    Content = new TextBlock() { Text = "Fruits" }
};
CardViewItem cardViewItem2 = new CardViewItem()
{
    Header = "Item 2",
    Content = new TextBlock() { Text = "Stationery" }
};
CardViewItem cardViewItem3 = new CardViewItem()
{
    Header = "Item 3",
    Content = new TextBlock() { Text = "Dresses" }
};

CardView cardView = new CardView();
cardView.Items.Add(cardViewItem1);
cardView.Items.Add(cardViewItem2);
cardView.Items.Add(cardViewItem3);
this.Content = cardView;

{% endhighlight %}
{% endtabs %}

![wpf card view items added into CardView control](Getting-Started_images/wpf-card-view-item.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Getting-Started)

## Populating items using ItemsSource

You can populate the card items in the `CardView` control by using the `ItemsSource` property. You need to use [HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_HeaderTemplate) and `ItemTemplate` to render the items in the view.

N> Grouping, sorting, filtering, and editing are supported only when the card items are populated through the `ItemsSource` property.

{% tabs %}
{% highlight C# %}

//Model.cs
public class CardViewModel
{
    public string Item { get; set; }
    public string Name { get; set; }     
}

//ViewModel.cs
public class ViewModel : NotificationObject
{
    private ObservableCollection<CardViewModel> cardViewItems;
    public ObservableCollection<CardViewModel> CardViewItems
    {
        get { return cardViewItems; }
        set { cardViewItems = value;
            this.RaisePropertyChanged(nameof(CardViewItems)); }
    }
    public ViewModel()
    {
        CardViewItems = new ObservableCollection<CardViewModel>();
        populateItems();
    }
    private void populateItems()
    {
        CardViewItems.Add(new CardViewModel() { Item = "Item 1", Name = "Fruits" });
        CardViewItems.Add(new CardViewModel() { Item = "Item 2", Name = "Stationery" });
        CardViewItems.Add(new CardViewModel() { Item = "Item 3", Name = "Dresses" });
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window x:Class="CardViewSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CardViewSample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    <syncfusion:CardView ItemsSource="{Binding CardViewItems}"
                      Name="cardView">
        <syncfusion:CardView.HeaderTemplate>
            <DataTemplate>
                <TextBlock Text="{Binding Item}"/>
            </DataTemplate>
        </syncfusion:CardView.HeaderTemplate>
        <syncfusion:CardView.ItemTemplate>
            <DataTemplate>
                <StackPanel Orientation="Horizontal">
                    <TextBlock Text="Name:"
                           Margin="5" />
                    <TextBlock Margin="5"
                           Text="{Binding Name, UpdateSourceTrigger=PropertyChanged}" />
                </StackPanel>
            </DataTemplate>
        </syncfusion:CardView.ItemTemplate>
    </syncfusion:CardView>
</Window>

{% endhighlight %}
{% endtabs %}

![wpf card view items added into CardView control using data binding](Data-Binding-to-Objects_images/databinding.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/PopulateItems)

## Select a CardViewItem

You can select any card item by mouse click on the specific item. You can get the selected item by using the [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_SelectedItem) property. The default value of `SelectedItem` property is `null`.

N> You can select only one item at a time.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView Name="cardView">
    <syncfusion:CardViewItem Header="Item 1">
        <TextBlock Text="Fruits"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 2">
        <TextBlock Text="Stationery"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 3">
        <TextBlock Text="Dresses"/>
    </syncfusion:CardViewItem>
</syncfusion:CardView>

{% endhighlight %}
{% highlight C# %}

CardViewItem cardViewItem1 = new CardViewItem()
{
    Header = "Item 1",
    Content = new TextBlock() { Text = "Fruits" }
};
CardViewItem cardViewItem2 = new CardViewItem()
{
    Header = "Item 2",
    Content = new TextBlock() { Text = "Stationery" }
};
CardViewItem cardViewItem3 = new CardViewItem()
{
    Header = "Item 3",
    Content = new TextBlock() { Text = "Dresses" }
};

CardView cardView = new CardView();
cardView.Items.Add(cardViewItem1);
cardView.Items.Add(cardViewItem2);
cardView.Items.Add(cardViewItem3);
this.Content = cardView;

{% endhighlight %}
{% endtabs %}

![wpf card view items selected using mouse click](Getting-Started_images/selectitem.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Getting-Started)

## Select CardViewItem programmatically using property

You can select a particular card item programmatically by using the [CardViewItem.IsSelected](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardViewItem.html#Syncfusion_Windows_Tools_Controls_CardViewItem_IsSelected) property. The default value of `CardViewItem.IsSelected` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:CardView Name="cardView">
    <syncfusion:CardViewItem Header="Item 1" >
        <TextBlock Text="Fruits"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 2"
                             IsSelected="True">
        <TextBlock Text="Stationery"/>
    </syncfusion:CardViewItem>
    <syncfusion:CardViewItem Header="Item 3">
        <TextBlock Text="Dresses"/>
    </syncfusion:CardViewItem>
</syncfusion:CardView>

{% endhighlight %}
{% highlight C# %}

CardViewItem cardViewItem1 = new CardViewItem()
{
    Header = "Item 1",
    Content = new TextBlock() { Text = "Fruits" }
};
CardViewItem cardViewItem2 = new CardViewItem()
{
    Header = "Item 2",
    IsSelected = true,
    Content = new TextBlock() { Text = "Stationery" }
};
CardViewItem cardViewItem3 = new CardViewItem()
{
    Header = "Item 3",
    Content = new TextBlock() { Text = "Dresses" }
};

CardView cardView = new CardView();
cardView.Items.Add(cardViewItem1);
cardView.Items.Add(cardViewItem2);
cardView.Items.Add(cardViewItem3);
this.Content = cardView;

{% endhighlight %}
{% endtabs %}

![wpf card view item selected programmatically](Getting-Started_images/selectitem_programmatically.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Getting-Started)

## Group the CardViewItems

You can group the cards inside the `CardView` control by dragging the required fields from the list and dropping them into the drop region of the `CardView` control header. The field names in the drop region are automatically populated from the `HeaderTemplate` data context. To disable grouping, set the [CanGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanGroup) property to `false`. The default value of `CanGroup` is `true`.

{% tabs %}
{% highlight C# %}

//Model.cs
public class CardViewModel
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int Age { get; set; }
}

//ViewModel.cs
public class ViewModel : NotificationObject
{
    private ObservableCollection<CardViewModel> cardViewItems;
    public ObservableCollection<CardViewModel> CardViewItems
    {
        get { return cardViewItems; }
        set { cardViewItems = value;
            this.RaisePropertyChanged(nameof(CardViewItems)); }
    }
    public ViewModel()
    {
        CardViewItems = new ObservableCollection<CardViewModel>();
        populateItems();
    }
    private void populateItems()
    {
        CardViewItems.Add(new CardViewModel() { FirstName = "John", LastName= "Paulin", Age = 23});
        CardViewItems.Add(new CardViewModel() { FirstName = "Mark", LastName = "Paulin",Age = 26 });
        CardViewItems.Add(new CardViewModel() { FirstName = "Steven", LastName = "John", Age = 25 });
        CardViewItems.Add(new CardViewModel() { FirstName = "John", LastName = "Steven", Age = 23 });
        CardViewItems.Add(new CardViewModel() { FirstName = "Steven", LastName = "Smith", Age = 25 });
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window x:Class="CardViewSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CardViewSample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    <syncfusion:CardView CanGroup="True"
                     ItemsSource="{Binding CardViewItems}"
                     Name="cardView">
        <syncfusion:CardView.HeaderTemplate>
            <DataTemplate>
                <TextBlock Text="{Binding Age}"/>
            </DataTemplate>
        </syncfusion:CardView.HeaderTemplate>
        <syncfusion:CardView.ItemTemplate>
            <DataTemplate >
                <ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled">
                    <ListBoxItem Padding="1">
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="75" />
                                <ColumnDefinition />
                            </Grid.ColumnDefinitions>
                            <TextBlock Text="First Name:" />
                            <TextBlock Grid.Column="1"
                                   Text="{Binding FirstName,
                                          UpdateSourceTrigger=PropertyChanged}" />
                        </Grid>
                    </ListBoxItem>
                    <ListBoxItem Padding="1">
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="75" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <TextBlock Text="Last Name:" />
                            <TextBlock Grid.Column="1" 
                                   Text="{Binding LastName, 
                                          UpdateSourceTrigger=PropertyChanged}" />
                        </Grid>
                    </ListBoxItem>
                    <ListBoxItem Padding="1">
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="75" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <TextBlock Text="Age:" />
                            <TextBlock Grid.Column="1"
                                   Text="{Binding Age,
                                          UpdateSourceTrigger=PropertyChanged}" />
                        </Grid>
                    </ListBoxItem>
                </ListBox>
            </DataTemplate>
        </syncfusion:CardView.ItemTemplate>
    </syncfusion:CardView>
</Window>

{% endhighlight %}
{% highlight C# %}

cardView.CanGroup = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items grouped based on age field](Grouping-Sorting-Filtering_images/grouping.gif)

Here, `CardViewItems` grouped based on `Age` field.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Editing)

## Sort the CardViewItems

You can sort the cards inside the `CardView` control in the default, ascending, or descending order by clicking the field names listed in the header. To disable sorting, set the [CanSort](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanSort) property to `false`. The default value of `CanSort` is `true`.

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<syncfusion:CardView CanSort="True"
                     ItemsSource="{Binding CardViewItems}"
                     Name="cardView"/>

{% endhighlight %}
{% highlight C# %}

cardView.CanSort = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items sorted in ascending and descending order](Grouping-Sorting-Filtering_images/sorting.gif)

Here, `CardViewItems` sorted based on `FirstName` field.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Editing)

## Edit the CardViewItems

You can edit the selected `CardViewItem` value by double-clicking on that item or by pressing the `F2` key. To exit editing mode, press the `Esc` or `Enter` key. Enable the editing mode of card items by setting the [CanEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_CanEdit) property to `true`. The default value of `CanEdit` is `false`.

N> To perform an edit operation on the selected `CardViewItem`, define the `CardViewItem` edit mode UI with editable functionalities by using [EditItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_EditItemTemplate). The binding context of `EditItemTemplate` is the underlying data item.

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<syncfusion:CardView CanEdit="True"
                     ItemsSource="{Binding CardViewItems}"
                     Name="cardView">
    <syncfusion:CardView.EditItemTemplate>
        <DataTemplate>
            <ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled">
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="First Name:" />
                        <TextBox
                            Grid.Column="1"
                            Text="{Binding FirstName, 
                                   UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="Last Name:" />
                        <TextBox Grid.Column="1" 
                                 Text="{Binding LastName, 
                                        UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
                <ListBoxItem Padding="1">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="75" />
                            <ColumnDefinition Width="*" />
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="Age:" />
                        <TextBox Grid.Column="1" 
                                 Text="{Binding Age, 
                                        UpdateSourceTrigger=PropertyChanged}" />
                    </Grid>
                </ListBoxItem>
            </ListBox>
        </DataTemplate>
    </syncfusion:CardView.EditItemTemplate>
</syncfusion:CardView>

{% endhighlight %}
{% highlight C# %}

cardView.CanEdit = true;

{% endhighlight %}
{% endtabs %}

![wpf card view items edited by keyboard and mouse interaction](Grouping-Sorting-Filtering_images/editing.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Editing)

## Orientation of CardViewItems

You can arrange the cards either vertically or horizontally by using the [Orientation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_Orientation) property. The default value of the `Orientation` property is `Vertical`.

N> If there is not enough space to arrange the cards in the orientation set by the `Orientation` property, `CardView` will automatically arrange the cards in the available space.

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<syncfusion:CardView Orientation="Horizontal"
                     ItemsSource="{Binding CardViewItems}"
                     Name="cardView"/>

{% endhighlight %}
{% highlight C# %}

cardView.Orientation = Orientation.Horizontal;

{% endhighlight %}
{% endtabs %}

![wpf card view items arranged in horizontal orientation](Getting-Started_images/orientation.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Editing)

## Selected item changed notification

You will be notified when the selected card item changes in the [CardView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html) by using the [SelectedItemChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CardView.html#Syncfusion_Windows_Tools_Controls_CardView_SelectedItemChanged) callback. The `SelectedItemChanged` callback receives a `DependencyPropertyChangedEventArgs` that contains the previously selected card item in the `OldValue` property and the newly selected card item in the `NewValue` property.

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<syncfusion:CardView SelectedItemChanged="CardView_SelectedItemChanged"
                     ItemsSource="{Binding CardViewItems}"
                     Name="cardView"/>

{% endhighlight %}
{% highlight C# %}

cardView.SelectedItemChanged += CardView_SelectedItemChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

// Required namespaces:
// using System.Windows;
// using Syncfusion.Windows.Tools.Controls;

private void CardView_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    var newItem = e.NewValue;
    var oldItem = e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Theme

CardView supports various built-in themes. Refer to the below links to apply themes for the CardView,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
  
N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-card-view-examples/tree/master/Samples/Themes)

  ![Setting theme to WPF CardView](Getting-Started_images/wpf-card-view-theme-support.png)