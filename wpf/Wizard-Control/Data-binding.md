---
layout: post
title: DataBinding support
description: Description about how to create MVVM structure sample with Wizard control
platform: wpf
control: Wizard
documentation: ug
---
# Data Binding 

Data Binding is the process of establishing a connection between the application UI and business logic. ItemSource and ItemTemplate properties of WizardControl are used to bind the business object collection.

## Adding Data Binding to an Application

Below steps will explain on how to add the Items through ItemsSource property of Wizard control.

1.Create a Model class with the necessary properties.

{% highlight C# %}

public class Model : NotificationObject

{

private string title;

public string Title

{

get

{

return title;

}

set

{

title = value;

RaisePropertyChanged("Title");

}

}

private string content;

public string Content

{

get

{

return content;

}

set

{

content = value;

RaisePropertyChanged("Description");

}

}     

}

{% endhighlight %}

2.Create collection of PageItems in ViewModel class as given in the following code snippet:

{% highlight C# %}

private ObservableCollection<Model> items;

public ObservableCollection<Model> PageItems

{

get

{

return items;

}

set

{

items = value;

RaisePropertyChanged("PageItems");

}

}

{% endhighlight %}

3.Populate the PageItems collection as follows.

{% highlight C# %}

private void PopulatePageItems()

{

items.Add(new Model { Title = "XML Developer's Guide", Content = "An in-depth look at creating applications with XML."});

items.Add(new Model { Title = "Midnight Rain", Content = "A former architect battles corporate zombies, an evil sorceress, and her own childhood to become queen of the world."});

items.Add(new Model { Title = "Oberon's Legacy", Content = "In post apocalypse England, the mysterious agent known only as Oberon helps to create a new life for the inhabitants of London."});

items.Add(new Model { Title = "Lover Birds", Content = "When Carla meets Paul at an ornithology conference, tempers fly as feathers get ruffled."});

items.Add(new Model { Title = "Science Fiction", Content = "After an inadvertent trip through a Heisenberg Uncertainty Device, James discovers the problems of being quantum."});

}

{% endhighlight %}

4.Create a ViewModel instance and use it as DataContext for the Root Window as given in the following code snippet,

{% highlight XAML %}

<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>    

{% endhighlight %}

5.Bind the PageItems collection to the ItemsSource property of the WizardControl. Content of the WizardPage can be displayed using the ItemTemplate property.

{% highlight XAML %}

<Window.Resources>

<Style x:Key="WizardPageStyle" TargetType="syncfusion:WizardPage">

<Setter Property="Title" Value="{Binding Title}"/>

<Setter Property="PageType" Value="Exterior"/>

<Setter Property="BannerImage" Value="/Images/W_O-BG.png"/>

</Style>

<DataTemplate x:Key="WizardPageItemTemplate">

<TextBlock Text="{Binding Content}" TextWrapping="Wrap"/>

</DataTemplate>

</Window.Resources>

<Grid>

<syncfusion:WizardControl x:Name="wizardcontrol" ItemContainerStyle="{StaticResource WizardPageStyle}" ItemsSource="{Binding PageItems}" ItemTemplate="{StaticResource WizardPageItemTemplate}"/>

</Grid>

{% endhighlight %}

![](Interactive-Features_images/data-binding_img1.png)

Sample has been created with MVVM structure using above steps and it can be downloaded from below link,

#### Sample Link:
[http://www.syncfusion.com/downloads/support/directtrac/general/ze/Wizard_ItemsSource_Sample418091351.zip](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Wizard_ItemsSource_Sample418091351.zip)
