---
layout: post
title: Customizing Data Templates
description: Customizing Data Templates
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Customizing Data Templates

This section explains about customizing the TreeViewItemAdv using DataTemplate

## ItemTemplate

The user can customize the business object that has to be displayed as TreeViewItemAdv using the ItemTemplate of TreeViewAdv. Since TreeViewAdv displays the hierarchical data, the HierarchicalDataTemplate is used to define the ItemTemplate. In the following example, business object is displayed as CheckBox

We have generate Business object 

Model class:
{% tabs %}
{% highlight C# %}
public class Model : NotificationObject

{

public Model()

{

Models = new ObservableCollection<Model>();

}

private string caption = string.Empty;

public string Caption

{

Get

{

return caption;

}

Set

{

caption = value;

this.RaisePropertyChanged(() => this.Caption);

}

}

private bool isChekced = false;

public bool IsChecked

{

Get

{

return isChekced;

}

Set

{

isChekced = value;

this.RaisePropertyChanged(() => this.IsChecked);

}

}

private bool isChekable = false;

public bool IsCheckable

{

Get

{

return isChekable;

}

Set

{

isChekable = value;

this.RaisePropertyChanged(() => this.IsCheckable);

}

}

private ObservableCollection<Model> models = null;

public ObservableCollection<Model> Models

{

Get

{

return models;.

}

Set

{

models = value;

this.RaisePropertyChanged(() => this.Models);

}

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}

ViewModel class:
{% tabs %}
{% highlight C# %}
public class ViewModel : NotificationObject

{

public ViewModel()

{

TreeItems = new ObservableCollection<Model>();

Model model1 = new Model() { Caption = "WPF" };

Model model2 = new Model() { Caption = "Silverlight" }; 

Model model3 = new Model() { Caption = "ASP.Net" }; 

Model model4 = new Model() { Caption = "ASP.Net MVC" }; 

Model mainmodel1 = new Model() { Caption = "User Interface" };

mainmodel1.Models.Add(model1);

mainmodel1.Models.Add(model2);

mainmodel1.Models.Add(model3);

mainmodel1.Models.Add(model4);

Model model5 = new Model() { Caption = "WPF",IsCheckable=true };

Model model6 = new Model() { Caption = "Silverlight", IsCheckable = true };

Model model7 = new Model() { Caption = "ASP.Net", IsCheckable = true };

Model model8 = new Model() { Caption = "ASP.Net MVC", IsCheckable = true };

Model mainmodel2 = new Model() { Caption = "Business Intelligence", IsCheckable = true };

mainmodel2.Models.Add(model5);

mainmodel2.Models.Add(model6);

mainmodel2.Models.Add(model7);

mainmodel2.Models.Add(model8);

Model model9 = new Model() { Caption = "WPF" };

Model mode20 = new Model() { Caption = "Silverlight" };

Model mode21 = new Model() { Caption = "ASP.Net" };

Model mainmodel3 = new Model() { Caption = "Reporting" };

mainmodel3.Models.Add(model9);

mainmodel3.Models.Add(mode20);

mainmodel3.Models.Add(mode21);

Model mod = new Model() { Caption = "Syncfusion Essential Studio" };

mod.Models.Add(mainmodel1);

mod.Models.Add(mainmodel2);

mod.Models.Add(mainmodel3);

TreeItems.Add(mod);

}

public ObservableCollection<Model> _treeitems;

public ObservableCollection<Model> TreeItems

{

Get

{

return _treeitems;

}

Set

{

_treeitems = value;

}

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}

{% tabs %}
{% highlight XAML %}
<Window x:Class="ItemTemplateSample.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

xmlns:local="clr-namespace:ItemTemplateSample" syncfusion:SkinStorage.VisualStyle="Metro"

Title="MainWindow" Height="350" Width="525">

<Window.DataContext>

<local:ViewModel />

</Window.DataContext>

<Grid>

<syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}" >

<syncfusion:TreeViewAdv.ItemTemplate>

<HierarchicalDataTemplate ItemsSource="{Binding Models}">

<CheckBox Content="{Binding Caption}" IsChecked="{Binding Path=IsChecked,Mode=TwoWay}"/>

</HierarchicalDataTemplate>

</syncfusion:TreeViewAdv.ItemTemplate>

</syncfusion:TreeViewAdv>

</Grid>

</Window>


{% endhighlight %}
{% endtabs %}

![](Customizing_data_templates_images/Customizing_data_templates_img1.jpeg)


## Item Template Selector

Different templates can be used for items based on specific constraints using the ItemTemplateSelector.

The following example illustrates this:

1.Create the template selector as shown in the following code snippet:
{% tabs %}
{% highlight C# %}
public class TreeViewAdvItemTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate(object item, DependencyObject container)

{

Window window = Application.Current.MainWindow;

if (((Model)item).IsCheckable)

{

return window.Resources["CheckableTemplate"] as DataTemplate;

}

else

{

return window.Resources["NormalTemplate"] as DataTemplate;

}

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}

2.Define the Data templates in the Window’s resources as follows:

{% tabs %}
{% highlight XAML %}
<HierarchicalDataTemplate ItemsSource="{Binding Models}" x:Key="CheckableTemplate">

<CheckBox Content="{Binding Caption}" />

</HierarchicalDataTemplate>

<HierarchicalDataTemplate ItemsSource="{Binding Models}" x:Key="NormalTemplate">

<TextBlock Text="{Binding Caption}" />

</HierarchicalDataTemplate>

{% endhighlight %}
{% endtabs %}

3.Create the instance for the template selector in the Window’s resources as follows:

{% tabs %}

{% highlight XAML %}

<local:TreeViewAdvItemTemplateSelector x:Key="treeViewItemTemplateSelector"/>

{% endhighlight %}

{% endtabs %}

4.Use the template selector to choose the template for the TreeViewAdv as follows:

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}" ItemTemplateSelector="{StaticResource treeViewItemTemplateSelector}" >

</syncfusion:TreeViewAdv>

{% endhighlight %}

{% endtabs %}

The TreeVewAdv generates as shown in the following screenshot:

![](Customizing_data_templates_images/Customizing_data_templates_img2.jpeg)


## Edit Template

The user can modify the template while editing the TreeViewItemAdv. The following example illustrates the process of changing the template:

1.Create the DataTemplate instance for the EditTemplate as follows:

{% tabs %}

{% highlight XAML %}
<DataTemplate x:Key="EditTemplate">

<TextBox Text="{Binding Header}" FontStyle="Italic" FontWeight="Bold" />

</DataTemplate>

{% endhighlight %}

{% endtabs %}

2.Set the EditedItemTemplate for the TreeViewAdv to the above template as follows:

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}" EditedItemTemplate="{StaticResource EditTemplate}" >

<syncfusion:TreeViewAdv.ItemTemplate>

<HierarchicalDataTemplate ItemsSource="{Binding Models}">

<TextBlock Text="{Binding Caption}" />

</HierarchicalDataTemplate>

</syncfusion:TreeViewAdv.ItemTemplate>

</syncfusion:TreeViewAdv>

{% endhighlight %}

{% endtabs %}

While editing the TreeViewItemAdv appears as shown in the following screen shot:

![](Customizing_data_templates_images/Customizing_data_templates_img3.jpeg)


## Edit Template Selector

The user can choose the template at runtime for editing the TreeViewAdv.

The following example explains how to choose the template at runtime:

1.Create the template selector as given in the following code snippet:

{% tabs %}

{% highlight C# %}
public class TreeViewAdvEditTemplateSelector : DataTemplateSelector

{

public override DataTemplate SelectTemplate(object item, DependencyObject container)

{

Window window = Application.Current.MainWindow;

if (((Model)item).IsCheckable)

{

return window.Resources["CheckableEditTemplate"] as DataTemplate;

}

Else

{

return window.Resources["NormalEditTemplate"] as DataTemplate;

}

}

}

{% endhighlight %}

{% highlight VB %}

{% endhighlight %}

{% endtabs %}

2.Define the Data templates in the Window’s resources as follows:

{% tabs %}

{% highlight XAML %}
<DataTemplate  x:Key="CheckableEditTemplate">

<TextBox Text="{Binding Header}" FontStyle="Italic" FontWeight="Bold" Foreground="Blue"/>

</DataTemplate>

<DataTemplate  x:Key="NormalEditTemplate">

<TextBox Text="{Binding Header}" FontStyle="Italic" FontWeight="Bold" Foreground="Green"/>

</DataTemplate>

{% endhighlight %}

{% endtabs %}

3.Create the instance for the template selector in the Window’s resources as follows:

{% tabs %}

{% highlight XAML %}
<local:TreeViewAdvEditTemplateSelector x:Key="TreeViewAdvEditTemplateSelector"/>

{% endhighlight %}

{% endtabs %}

4.Use the template selector to choose the template for the TreeViewAdv as follows:

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv ItemsSource="{Binding TreeItems}" EditedItemTemplateSelector="{StaticResource TreeViewAdvEditTemplateSelector}" >

<syncfusion:TreeViewAdv.ItemTemplate>

<HierarchicalDataTemplate ItemsSource="{Binding Models}">

<TextBlock Text="{Binding Caption}" />

</HierarchicalDataTemplate>

</syncfusion:TreeViewAdv.ItemTemplate>

</syncfusion:TreeViewAdv>

{% endhighlight %}

{% endtabs %}

The TreeViewAdv generates as shown in the following screenshot:

![](Customizing_data_templates_images/Customizing_data_templates_img4.jpeg)


## Header Template

User can customize the header of the treeview item by using HeaderTemplate using the below code snippet.

{% tabs %}

{% highlight XAML %}
<Window x:Class="ItemTemplateSample.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion=[http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "")

syncfusion:SkinStorage.VisualStyle="Metro"

Title="MainWindow" Height="350" Width="525">

<Window.Resources>

<DataTemplate x:Key="HeaderTemplate">

<StackPanel Orientation="Horizontal">

<TextBlock FontWeight="Bold" Text="Marital Status" />

</StackPanel>

</DataTemplate>

</Window.Resources>

<Grid>

<!-- Adding TreeViewAdv with HeaderTemplate -->

<syncfusion:TreeViewAdv Name="treeViewAdv">

<!-- Adding TreeViewItemAdv -->

<syncfusion:TreeViewItemAdv Name="treeViewItemAdv1" HeaderTemplate="{StaticResource HeaderTemplate}">

<syncfusion:TreeViewItemAdv Header="Single"/>

<syncfusion:TreeViewItemAdv Header="Married"/>

<syncfusion:TreeViewItemAdv Header="Married with Children"/>

</syncfusion:TreeViewItemAdv>

</syncfusion:TreeViewAdv>

</Grid>

</Window>

{% endhighlight %}

{% endtabs %}

![](Customizing_data_templates_images/Customizing_data_templates_img5.jpeg)


## Cell Template 

TreeViewAdv allow user to customize the items under a column header by defining a cell template for the TreeViewColumns. To create a cell template use the below code

{% tabs %}

{% highlight XAML %}
<!-- Adding TreeViewAdv with Enabling multiple column -->

<syncfusion:TreeViewAdv Name="treeViewAdv" MultiColumnEnable="True">

<!-- Adding TreeViewItemAdv -->

<syncfusion:TreeViewItemAdv Name="treeViewItemAdv" Header="Marital Status">

<syncfusion:TreeViewItemAdv Header="Single"/>

<syncfusion:TreeViewItemAdv Header="Married"/>

<syncfusion:TreeViewItemAdv Header="Married with Children"/>

</syncfusion:TreeViewItemAdv>

<syncfusion:TreeViewItemAdv Header="Baby Vaccines">

<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>

<syncfusion:TreeViewItemAdv Header="Tetanus"/>

<syncfusion:TreeViewItemAdv Header="Polio"/>

<syncfusion:TreeViewItemAdv Header="Measles"/>

</syncfusion:TreeViewItemAdv>

<syncfusion:TreeViewItemAdv Header="Country Information">

<syncfusion:TreeViewItemAdv Header="Canada"/>

<syncfusion:TreeViewItemAdv Header="France"/>

<syncfusion:TreeViewItemAdv Header="Germany"/>

<syncfusion:TreeViewItemAdv Header="UK"/>

<syncfusion:TreeViewItemAdv Header="USA"/>

</syncfusion:TreeViewItemAdv>

<!-- Adding header -->

<syncfusion:TreeViewAdv.Columns>

<syncfusion:TreeViewColumnCollection>

<syncfusion:TreeViewColumn Width="150" Header="Status"

DisplayMemberBinding="{Binding Path=Header, RelativeSource={RelativeSource AncestorType={x:Type syncfusion:TreeViewItemAdv}}}"/>

<syncfusion:TreeViewColumn Width="100" Header="Vaccines"

DisplayMemberBinding="{Binding Path=Header, RelativeSource={RelativeSource AncestorType={x:Type syncfusion:TreeViewItemAdv}}}"/>

<syncfusion:TreeViewColumn Width="50" Header="Country">

<!-- Cell Template -->

<syncfusion:TreeViewColumn.CellTemplate>

<DataTemplate>

<Border Margin="1" Width="150" BorderBrush="Red" BorderThickness="1">

<TextBlock Margin="2" Text="{Binding Path=Header, RelativeSource={RelativeSource AncestorType={x:Type syncfusion:TreeViewItemAdv}}}"/>

</Border>

</DataTemplate>

</syncfusion:TreeViewColumn.CellTemplate>

</syncfusion:TreeViewColumn>

</syncfusion:TreeViewColumnCollection>

</syncfusion:TreeViewAdv.Columns>

</syncfusion:TreeViewAdv>

{% endhighlight %}

{% endtabs %}

![](Customizing_data_templates_images/Customizing_data_templates_img6.jpeg)


