---
layout: post
title: Data Binding in WPF Step ProgressBar Control | Syncfusion
description: Learn here about the Data Binding support in Syncfusion WPF Step ProgressBar control and how to bind the properties.
platform: wpf
control: SfStepProgressBar
documentation: ug
---

# Binding StepViewItems in WPF Step ProgressBar

You can add a [StepViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.StepViewItem.html) using data binding in the WPF [SfStepProgressBar](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfStepProgressBar.html).

## Data binding to Objects

The `SfStepProgressBar` can bound to an external source to auto create `StepViewItem` and display the data using `ItemsSource` property.   

N> To bind `ItemsSource` to `SfStepProgressBar`, you need to have collection with data object which holds step view item details.

Here, `StepItem` class defined with `Content` and its properties and `ViewModel` class has `ItemsSource` property of type `ObservableCollection<StepItem>`.

{% tabs %}
{% highlight C# %}

// Model.cs
public class StepItem 
    {
        public string ModelText { get; set; }       
        public Thickness TitleSpace { get; set; }
    }
}

//ViewModel.cs
public class ViewModel : INotifyPropertyChanged
{
        private ObservableCollection<StepItem> m_stepViewItems;
        public event PropertyChangedEventHandler PropertyChanged;
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

        public void OnPropertyChanged(PropertyChangedEventArgs e)
        {
            if (PropertyChanged != null)
                PropertyChanged(this, e);
        }

        public ViewModel()
        {
            StepViewItems = new ObservableCollection<StepItem>();
            PopulateData();
        }

        private void PopulateData()
        {
            //Adding the stepview items into the collection
            StepItem orderedStepViewItem = new StepItem()
            {
                ModelText = "Ordered",
                TitleSpace = new Thickness(0, 8, 0, 0)
            };

            StepItem shippedStepViewItem = new StepItem()
            {
                ModelText = "Shipped",
                TitleSpace = new Thickness(0, 8, 0, 0)
            };

            StepItem packedStepViewItem = new StepItem()
            {
                ModelText = "Packed",
                TitleSpace = new Thickness(0, 8, 0, 0)
            };

            StepItem deliveredStepViewItem = new StepItem()
            {
                ModelText = "Delivered",
                TitleSpace = new Thickness(0, 8, 0, 0)
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

![SfStepProgressBar control auto creates stepview item from objects using data binding](Data-binding_images/Data-Binding.png)


## StepViewItem content

You can define the `StepViewItem` content using `ContentTemplate` property. 

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl"
                            ItemsSource="{Binding TileViewItems}">  
    <syncfusion:TileViewControl.ItemTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Content}"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center" />
        </DataTemplate>
    </syncfusion:TileViewControl.ItemTemplate>
    
    <syncfusion:TileViewControl.ItemContainerStyle>
        <Style TargetType="syncfusion:TileViewItem">
            <Setter Property="Header" Value="{Binding Header}"/>
        </Style>
    </syncfusion:TileViewControl.ItemContainerStyle>

    <syncfusion:TileViewControl.DataContext>
        <viewmodel:ViewModel/>
    </syncfusion:TileViewControl.DataContext>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

![TileViewItem content assigned by using the ItemTemplate](Data-binding_images/content.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/Binding-Object)

## Different UI for TileViewItem content

You can change the various UI for the content of `TileViewItem` based on the provided logic by using the `ItemTemplateSelector`. You can also use the `ItemContainerStyleSelector` property to apply the different UI for the `TileViewItem` content.  The `DataContext` of the `ItemTemplate` property is `TileViewItem.Content`.

{% tabs %}
{% highlight C# %}

//ItemTemplateSelector class for select a DataTemplate
public class MyTemplateSelector : DataTemplateSelector {
    public DataTemplate Template1 { get; set; }
    public DataTemplate Template2 { get; set; }
    public DataTemplate Template3 { get; set; }

    public override DataTemplate SelectTemplate(object item, DependencyObject container) {
        if (item is TileItem && (item as TileItem).Header == "Item 1")
            return Template1;
        else if (item is TileItem && (item as TileItem).Header == "Item 4")
            return Template2;
        else
            return Template3;
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <local:MyTemplateSelector x:Key="Mytemplate">
        <local:MyTemplateSelector.Template1>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Red"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template1>
        <local:MyTemplateSelector.Template2>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Blue"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template2>
        <local:MyTemplateSelector.Template3>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Goldenrod"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template3>
    </local:MyTemplateSelector>
</Window.Resources>

<Grid>
    <syncfusion:TileViewControl ItemTemplateSelector="{StaticResource Mytemplate}" 
                                ItemsSource="{Binding TileViewItems}"
                                Name="tileViewControl">
        <syncfusion:TileViewControl.ItemContainerStyle>
            <Style TargetType="syncfusion:TileViewItem">
                <Setter Property="Header" Value="{Binding Header}"/>
            </Style>
        </syncfusion:TileViewControl.ItemContainerStyle>
        <syncfusion:TileViewControl.DataContext>
            <viewmodel:ViewModel/>
        </syncfusion:TileViewControl.DataContext>
    </syncfusion:TileViewControl>
</Grid>

{% endhighlight %}
{% endtabs %}

![TileViewItem with various content UI](Data-binding_images/ItemTemplateSelector.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/ItemTemplate-Selector)