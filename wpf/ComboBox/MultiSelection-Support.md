---
layout: post
title: MultiSelection Support in WPF ComboBox control | Syncfusion
description: Learn here all about MultiSelection Support support in Syncfusion WPF ComboBox (ComboBoxAdv) control and more.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# MultiSelection Support in WPF ComboBox (ComboBoxAdv)

This section explains how to select the multiple items and select the items programmatically in the [ComboBoxAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html) control.

## Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
AllowMultiSelect</td><td>
Multiple items can be selected.</td><td>
Dependency Property</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
SelectedItems</td><td>
It contains the selected items value</td><td>
Dependency Property</td><td>
ObservableCollection&lt;object&gt;</td><td>
NA</td></tr>
</table>

## Adding multiple selections to an application

You can select the multiple items in the WPF `ComboBoxAdv` control by setting the [AllowMultiSelect](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_AllowMultiSelect) property to `true`.

{% tabs %}

{% highlight XAML %}

<syncfusion:ComboBoxAdv x:Name="comboBoxAdv" AllowMultiSelect="True">
</syncfusion:ComboBoxAdv>

{% endhighlight %}

{% highlight C# %}

ComboBoxAdv comboBoxAdv = new ComboBoxAdv();
comboBoxAdv.AllowMultiSelect = true;

{% endhighlight %}
{% endtabs %}

## Selecting an item through programmatically

You can select the items programmatically by using the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_SelectedItems) property. When `AllowMultiSelect` is set to `true`, the `SelectedItems` property exposes the items that are selected in the drop-down list.

In the below example, first two items from the Observable Collection bound to the `SelectedItems` property.

### Creating Model and ViewModel data for DataBinding

1.Create a data object class named **Country** and declare the property as follows.

{% tabs %}

{% highlight C# %}

public class Country
{
    public string Name { get; set; }
}

{% endhighlight %}

{% endtabs %}

2.Create a **ViewModel** class with `SelectedItems`, which are initialized with data objects in constructor.

{% tabs %}

{% highlight C# %}

public class ViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> _items;

    private ObservableCollection<object> selectedItems;
    public ObservableCollection<object> SelectedItems
    {
        get { return selectedItems; }
        set
        {
            selectedItems = value;
            RaisePropertyChanged("SelectedItems");
        }
    }
    private ObservableCollection<Country> countries;
    public ObservableCollection<Country> Countries
    {
        get { return countries; }
        set
        {
            countries = value;
        }
    }
    public ViewModel()
    {
        Countries = new ObservableCollection<Country>();
        Countries.Add(new Country() { Name = "Denmark" });
        Countries.Add(new Country() { Name = "New Zealand" });
        Countries.Add(new Country() { Name = "Canada" });
        Countries.Add(new Country() { Name = "Russia" });
        Countries.Add(new Country() { Name = "Japan" });

        _items = new ObservableCollection<object>();
        for (int i = 0; i < 2; i++)
        {
            _items.Add(Countries[i]);
        }
        SelectedItems = new ObservableCollection<object>(_items);
    }

    public event PropertyChangedEventHandler PropertyChanged;
    public void RaisePropertyChanged(string PropertyName)
    {
        var property = PropertyChanged;
        if (property != null)
            property(this, new PropertyChangedEventArgs(PropertyName));
    }
}

{% endhighlight %}

{% endtabs %}

3.To bind the `ComboBoxAdv` to data, bind the collection created in the previous step to the [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssource?view=netcore-3.1#System_Windows_Controls_ItemsControl_ItemsSource) property in XAML by setting the `ViewModel` as `DataContext`.

{% tabs %}

{% highlight Xaml %}

<Window.DataContext>
    <local:ViewModel />
</Window.DataContext>
<Grid>
    <syncfusion:ComboBoxAdv DisplayMemberPath="Name" SelectedItems="{Binding SelectedItems, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"
            AllowMultiSelect="True" Name="comboboxadv"  HorizontalAlignment="Center" Height="30"
            VerticalAlignment="Center" Width="150" ItemsSource="{Binding Products}"/>
</Grid>

{% endhighlight %}

{% endtabs %}

![Adding multiple selections to an application in WPF ComboBoxAdv](Comboboxadv_images/ComboBoxAdv_img14.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-ComboBoxAdv-MultiSelection)
