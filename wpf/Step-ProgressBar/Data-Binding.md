---
layout: post
title: Data Binding in WPF Step ProgressBar Control | Syncfusion
description: Learn about the Data Binding support in Syncfusion WPF Step ProgressBar control and how to bind the properties.
platform: wpf
control: Step ProgressBar
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

![WPF Step ProgressBar control auto creates stepview item from objects using data binding](Data-binding_images/Data-Binding.png)


## Data-Binding with XML

An XML file can also be used as the ItemsSource for the Step Progress Bar control. The following example illustrates this.

1. Create an XML file with the following information and name it Data.xml.

   ~~~xaml

	<?xml version="1.0" encoding="utf-8" ?>

    <StepItems SelectedIndex="3">

     <Step Name="Ordered"/>
     <Step Name="Shipped"/>
     <Step Name="Packed"/>
     <Step Name="Delivered"/>

    </StepItems>
   ~~~

			


2. Add the XmlDataProvider for the XML document.

   ~~~xaml

    <XmlDataProvider x:Key="xmlSource" Source="Data.xml" XPath="StepItems" />
			
   ~~~



3. ItemsSource property for the Step ProgressBar control.


   ~~~xaml
   
	<syncfusion:SfStepProgressBar
                x:Name="stepperControlName"
                Margin="40"
                ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Step}"
                SelectedIndex="{Binding Source={StaticResource xmlSource}, XPath=@SelectedIndex}">
                <syncfusion:SfStepProgressBar.ItemContainerStyle>
                    <Style TargetType="syncfusion:StepViewItem">
                        <Setter Property="Content" Value="{Binding XPath=@Name}" />
                    </Style>
                </syncfusion:SfStepProgressBar.ItemContainerStyle>
    </syncfusion:SfStepProgressBar>

   ~~~
		


This will create the following Step ProgressBar control.



![WPF Step ProgressBar auto creates stepview item from XML using data binding](Data-Binding_images/Data-Binding_img.png)

