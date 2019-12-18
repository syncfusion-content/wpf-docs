---
layout: post
title: Adding controls in the Syncfusion's Chromeless Window Title bar
description: This section briefly describes the ability to add controls in Syncfusion's Chromeless Window Title bar.
platform: wpf
control: ChromelessWindow
documentation: ug
---
# Adding controls in the Title bar

 Users can add adaptive controls such as Button, TextBox, Label, Checkbox, etc to the title bar of the Chromeless Window. The `LeftHeaderItemsSource` property displays the controls stored in it on the left side of the title bar while the `RightHeaderItemsSource`' displays the controls stored in it on the right side of the title bar.

{% tabs %}
{% highlight XAML %}
<syncfusion:ChromelessWindow x:Class="Chromeless_Window_Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Chromeless_Window_Sample"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2016Colorful" TitleTextAlignment="Left"
        Title="Chromeless Window Sample" IconAlignment="Left" Height="350" Width="550"
         RightHeaderItemsSource="{DynamicResource rightHeaderItems}">
    <syncfusion:ChromelessWindow.Resources>
        <local:MyObservableCollection x:Key="rightHeaderItems">
            <syncfusion:SfTextBoxExt Watermark="Search..." Width="60" Height="20"/>
            <Button x:Name="help" Width="22" Height="22" Background="Transparent" BorderThickness="0" >
                <Path Data="M3.9400001,13.238 L5.5349999,13.238 5.5349999,14.833 3.9400001,14.833 z M4.7539988,0 C6.2060028,8.8817842E-16 7.3750015,0.39599991 8.2300044,1.1770003 9.0749989,1.9500008 9.5039998,2.8959999 9.5039998,3.9900017 9.5039998,4.6220016 9.3539982,5.2110023 9.0599995,5.743 8.7549992,6.2900009 8.1419993,6.9750023 7.2350021,7.7770004 6.5800033,8.3570023 6.1620041,8.7770004 5.9580017,9.0590019 5.7429972,9.3530006 5.5830012,9.6930008 5.4789973,10.070999 5.3929988,10.394001 5.3399974,10.871002 5.3170024,11.521999 L4.0500041,11.521999 C4.0479975,11.409 4.0459986,11.316002 4.0459986,11.244999 4.0459986,10.528 4.1480036,9.9029999 4.3499995,9.387001 4.4899989,9.0110016 4.7289973,8.618 5.0599986,8.2180023 5.310998,7.9189987 5.7679992,7.4770012 6.4180008,6.9049988 7.1190048,6.2859993 7.5660034,5.7989998 7.7829991,5.4169998 8.0100032,5.0200005 8.1240016,4.5839996 8.1240016,4.1189995 8.1240016,3.288002 7.796999,2.5480003 7.1510025,1.9220008 6.5110031,1.2989998 5.7139979,0.98400116&#xd;&#xa;4.784997,0.9840011 3.8870018,0.98400116 3.1250005,1.2709999 2.5199972,1.8380011 1.9710011,2.3500004 1.5930027,3.1230011 1.3939974,4.1389999 L0,3.9729996 C0.19999708,2.7350006 0.6869967,1.7670002 1.4499972,1.0950012 2.2720037,0.36900139 3.3850029,8.8817842E-16 4.7539988,0 z" 
                      Fill="#FF595858" HorizontalAlignment="Left" Height="11" Stretch="Fill" VerticalAlignment="Top" Width="7.504" />
            </Button>
        </local:MyObservableCollection>
    </syncfusion:ChromelessWindow.Resources>
    <Grid>
    </Grid>
</syncfusion:ChromelessWindow>
{% endhighlight %}
{% highlight C# %}

public class MyObservableCollection : ObservableCollection<object> { }

{% endhighlight %}
{% endtabs %}

![Title bar items added through collection](Getting-Started_images/Title-bar-items-using-collection.png)

We can also apply data template to define the visual appearance of the data stored in the `LeftHeaderItemsSource` and `RightHeaderItemsSource`. The `LeftHeaderItemTemplate` is used to define the visual appearance of the data stored in the `LeftHeaderItemsSource` while the `RightHeaderItemTemplate` is used to define the visual appearance of the data stored in the `RightHeaderItemsSource`.

{% tabs %}
{% highlight XAML %}
<syncfusion:ChromelessWindow x:Class="Chromeless_Window_Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Chromeless_Window_Sample"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2016Colorful" TitleTextAlignment="Left"
        Title="Chromeless Window Sample" IconAlignment="Left" Height="350" Width="550"
        RightHeaderItemsSource="{Binding Utilities}" RightHeaderItemTemplate="{DynamicResource Part_RightItemsTemplate}">
    <syncfusion:ChromelessWindow.DataContext>
        <local:UtilityViewModel/>
    </syncfusion:ChromelessWindow.DataContext>
    <syncfusion:ChromelessWindow.Resources>
        <DataTemplate x:Key="Part_RightItemsTemplate">
            <Grid>
                <syncfusion:ButtonAdv SmallIcon="{Binding Path = Icon, Mode = TwoWay}" Label="{Binding Path= Text, Mode=TwoWay}" SizeMode="{Binding Path=Mode}" Background="Transparent" BorderThickness="0" />
            </Grid>
        </DataTemplate>
    </syncfusion:ChromelessWindow.Resources>
    <Grid>
    </Grid>
</syncfusion:ChromelessWindow>
{% endhighlight %}
{% highlight C# %}

/// <summary>
/// View model class
/// </summary>
public class UtilityViewModel
{
    /// <summary>
    /// Constructor
    /// </summary>
    public UtilityViewModel()
    {
        LoadUtilities();
    }

    public ObservableCollection<Item> Utilities
    {
        get;
        set;
    }

    /// <summary>
    /// Adds object of type Item to the Utilities collection
    /// </summary>
    public void LoadUtilities()
    {
        ObservableCollection<Item> utilities = new ObservableCollection<Item>();
        var outPutDirectory = System.IO.Path.GetDirectoryName(Assembly.GetExecutingAssembly().CodeBase);
        var logoimage = System.IO.Path.Combine(outPutDirectory, "Images\\Help.png");
        utilities.Add(new Item { Name = "Account", Icon = null, Text = "Sign in", Mode = SizeMode.Normal });
        utilities.Add(new Item { Name = "Help", Icon = new BitmapImage(new Uri(logoimage.ToString())), Text="", Mode = SizeMode.Small });
        Utilities = utilities;
    }
}

public class Item
{
    public string Name
    {
        get; set;
    }
    public ImageSource Icon
    {
        get; set;
    }
    public string Text
    {
        get; set;
    }
    public SizeMode Mode
    {
        get; set;
    }
}



{% endhighlight %}
{% endtabs %}

![Template applied to the items source](Getting-Started_images/Title-bar-items-using-Template.png)