---
layout: post
title: MultiSelection Support | wpf | Syncfusion
description: Learn here about how to select the multiple items in Syncfusion WPF ComboBoxAdv control and more details.
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Multiple Selections in ComboBoxAdv

This section explains how to select the multiple items and select the items programmatically in [ComboBoxAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html) control.

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

You can select the multiple items in WPF `ComboBoxAdv` control by setting the [AllowMultiSelect](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_AllowMultiSelect) property to `true`.

{% tabs %}

{% highlight XAML %}

<syncfusion:ComboBoxAdv x:Name="comboBoxAdv" AllowMultiSelect="True" DefaultText="ComboBox Items" Height="30" Width="150">
    <syncfusion:ComboBoxItemAdv Content="United States"/>
    <syncfusion:ComboBoxItemAdv Content="India"/>
    <syncfusion:ComboBoxItemAdv Content="Canada"/>
    <syncfusion:ComboBoxItemAdv Content="German"/>
</syncfusion:ComboBoxAdv>

{% endhighlight %}

{% highlight C# %}

//Initialize the ComboBoxAdv control.
ComboBoxAdv comboBoxAdv = new ComboBoxAdv();
comboBoxAdv.Height = 30;
comboBoxAdv.Width = 150;
comboBoxAdv.DefaultText = "ComboBox Items";
comboBoxAdv.AllowMultiSelect = true;

//Initialize the ComboBox items and set the items.
ComboBoxItemAdv item1 = new ComboBoxItemAdv() { Content = "United States" };
ComboBoxItemAdv item2 = new ComboBoxItemAdv() { Content = "India" };
ComboBoxItemAdv item3 = new ComboBoxItemAdv() { Content = "Canada" };
ComboBoxItemAdv item4 = new ComboBoxItemAdv() { Content = "German" };

//Adding items to the control.
comboBoxAdv.Items.Add(item1);
comboBoxAdv.Items.Add(item2);
comboBoxAdv.Items.Add(item3);
comboBoxAdv.Items.Add(item4);

//Adding control to the window
grid.Children.Add(comboBoxAdv);

{% endhighlight %}
{% endtabs %}

![Adding multiple selections to an application](ComboBoxAdv_images/wpf-comboboxadv-multiselect.png)

## Select the items

You can select the items programmatically by using [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ComboBoxAdv.html#Syncfusion_Windows_Tools_Controls_ComboBoxAdv_SelectedItems) property. When `AllowMultiSelect` is true, the SelectedItems property exposes the items that are selected in the drop down list.

In the below example, first two items from the Observable Collection bound to the `SelectedItems` property.

**MainWindow.Xaml:**

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

**Model.cs:**

{% tabs %}

{% highlight C# %}

public class Model
{
    public string Name { get; set; }
}

{% endhighlight %}

{% endtabs %}

**ViewModel.cs:**

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
    private ObservableCollection<Model> products;
    public ObservableCollection<Model> Products
    {
        get { return products; }
        set
        {
            products = value;
        }
    }
    public ViewModel()
    {
        Products = new ObservableCollection<Model>();

        Products.Add(new Model() { Name = "United States" });
        Products.Add(new Model() { Name = "India " });
        Products.Add(new Model() { Name = "Canada" });
        Products.Add(new Model() { Name = "German" });

        _items = new ObservableCollection<object>();
        for (int i = 0; i < 2; i++)
        {
            _items.Add(Products[i]);
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

![Select the item using SelectedItems property in WPF ComboBoxAdv](Comboboxadv_images/wpf-comboboxadv-selection.png)
