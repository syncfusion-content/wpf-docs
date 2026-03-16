---
layout: post
title: Data Binding in WPF Step ProgressBar control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion<sup>&reg;</sup>; WPF Step ProgressBar (SfStepProgressBar) control and more.
platform: wpf
control: Step ProgressBar
documentation: ug
---

# Data Binding in WPF Step ProgressBar (SfStepProgressBar)

You can add a [StepViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.StepViewItem.html) using the data binding in the WPF [SfStepProgressBar](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html).

## Data binding to Objects

The [SfStepProgressBar](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html) can bound to an external source to auto-create [StepViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.StepViewItem.html) and display the data using the [ItemsSource](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/ms593015(v=vs.95)#:~:text=You%20can%20add%20items%20to,items%20property%20are%20read%2Donly.) property.   

N> To bind the [ItemsSource](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/ms593015(v=vs.95)#:~:text=You%20can%20add%20items%20to,items%20property%20are%20read%2Donly.) to [SfStepProgressBar](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html), you need to have a collection with a data object which holds the step view item details.

Here, the `StepItem` class defined with [Content](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.contentcontrol.content?view=net-5.0) and its properties, and the `ViewModel` class has the [ItemsSource](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/ms593015(v=vs.95)#:~:text=You%20can%20add%20items%20to,items%20property%20are%20read%2Donly.) property of type `ObservableCollection<StepItem>`.

{% tabs %}
{% highlight C# %}

// Model.cs
/// <summary>
/// Represents the model.
/// </summary>
public class StepItem 
{
    /// <summary>
    /// Gets or sets the text for step view item.
    /// </summary>
    public string ModelText { get; set; } 
        
    /// <summary>
    /// Gets or sets the space between text and step view item.
    /// </summary>
    public double TitleSpace { get; set; }
}

//ViewModel.cs
/// <summary>
/// Represents the view model class.
/// </summary>
public class ViewModel : INotifyPropertyChanged
{
    /// <summary>
    /// Represents the step view items.
    /// </summary>
    private ObservableCollection<StepItem> m_stepViewItems;

    /// <summary>
    /// Represents the property changed event.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Gets or sets the step view items.
    /// </summary>
    public ObservableCollection<StepItem> StepViewItems
    {
        get
        {
            return m_stepViewItems;
        }
        set
        {
            m_stepViewItems = value;
            OnPropertyChanged(new PropertyChangedEventArgs("StepViewItems"));
        }
    }

    /// <summary>
    /// Trigress the on property changed event.
    /// </summary>
    /// <param name="e"></param>
    public void OnPropertyChanged(PropertyChangedEventArgs e)
    {
        if (PropertyChanged != null)
            PropertyChanged(this, e);
    }

    /// <summary>
    /// Initialize the instance of <see cref="ViewModel"/> class.
    /// </summary>
    public ViewModel()
    {
        StepViewItems = new ObservableCollection<StepItem>();
        PopulateData();
    }

    /// <summary>
    /// Populates the data.
    /// </summary>
    private void PopulateData()
    {
        //Adding the step view items into the collection
        StepItem orderedStepViewItem = new StepItem()
        {
            ModelText = "Ordered",
            TitleSpace = 8
        };

        StepItem shippedStepViewItem = new StepItem()
        {
            ModelText = "Shipped",
            TitleSpace = 8
        };

        StepItem packedStepViewItem = new StepItem()
        {
            ModelText = "Packed",
            TitleSpace = 8
        };

        StepItem deliveredStepViewItem = new StepItem()
        {
            ModelText = "Delivered",
            TitleSpace = 8
        };

        StepViewItems.Add(orderedStepViewItem);
        StepViewItems.Add(shippedStepViewItem);
        StepViewItems.Add(packedStepViewItem);
        StepViewItems.Add(deliveredStepViewItem);
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Grid Name="grid">
    <syncfusion:SfStepProgressBar
        x:Name="stepperControlName"
        Margin="40"
        ItemsSource="{Binding StepViewItems}"
        Orientation="Horizontal"
        SelectedIndex="2">
        <syncfusion:SfStepProgressBar.ItemContainerStyle>
            <Style TargetType="syncfusion:StepViewItem">
                <Setter Property="Content" Value="{Binding ModelText}" />
                <Setter Property="TextSpacing" Value="{Binding TitleSpace}" />
            </Style>
        </syncfusion:SfStepProgressBar.ItemContainerStyle>
        <syncfusion:SfStepProgressBar.DataContext>
            <local:ViewModel />
        </syncfusion:SfStepProgressBar.DataContext>
    </syncfusion:SfStepProgressBar>
</Grid>
{% endhighlight %}
{% endtabs %}

![WPF Step ProgressBar control auto creates stepview item from objects using data binding](Data-binding_images/Data-Binding.png)

Download demo from [GitHub](https://github.com/SyncfusionExamples/WPF-StepProgressBar-Demos/tree/master/Samples/DataBindingToObjects).

## Data-Binding with XML

An XML file can also be used as the [ItemsSource](https://docs.microsoft.com/en-us/previous-versions/windows/silverlight/dotnet-windows-silverlight/ms593015(v=vs.95)#:~:text=You%20can%20add%20items%20to,items%20property%20are%20read%2Donly.) for the Step Progress Bar control. The following example shows this.

Create an XML file with the following information and name it Data.xml.

{% tabs %}
{% highlight XAML %}
<?xml version="1.0" encoding="utf-8" ?>

<StepItems SelectedIndex="3">

<Step Name="Ordered"/>
<Step Name="Shipped"/>
<Step Name="Packed"/>
<Step Name="Delivered"/>

</StepItems>
{% endhighlight %}
{% endtabs %}			

The ItemsSource property for the Step ProgressBar control.

{% tabs %}
{% highlight XAML %}
<Window.Resources>
<XmlDataProvider x:Key="xmlSource" Source="Data.xml" XPath="StepItems" />
</Window.Resources>

<syncfusion:SfStepProgressBar x:Name="stepperControlName"
    ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Step}"
    SelectedIndex="{Binding Source={StaticResource xmlSource}, XPath=@SelectedIndex}">
    <syncfusion:SfStepProgressBar.ItemContainerStyle>
        <Style TargetType="syncfusion:StepViewItem">
            <Setter Property="Content" Value="{Binding XPath=@Name}" />
        </Style>
    </syncfusion:SfStepProgressBar.ItemContainerStyle>
</syncfusion:SfStepProgressBar>
{% endhighlight %}
{% endtabs %}
		
This will create the following Step ProgressBar control.

![WPF Step ProgressBar auto creates stepview item from XML using data binding](Data-Binding_images/Data-Binding_img.png)

Download demo from [GitHub](https://github.com/SyncfusionExamples/WPF-StepProgressBar-Demos/tree/master/Samples/DataBindingWithXml).
