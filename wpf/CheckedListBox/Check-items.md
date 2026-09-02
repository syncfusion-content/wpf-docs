---
layout: post
title: Check Items in WPF CheckListBox | Syncfusion®
description: Select or clear individual items in the Syncfusion WPF CheckListBox control with built-in check box support and flexible item interactions.
platform: wpf
control: CheckListBox
documentation: ug
---

# Check Items in WPF CheckListBox

In [CheckListBox](https://www.syncfusion.com/wpf-controls/checkedlistbox), items present in the control can be checked or unchecked in any of the following ways:

1. Programmatically, using the `SelectedItems` collection
2. Programmatically, by binding the `IsChecked` property
3. Using the mouse
4. Using the keyboard

## Check items programmatically

You can check or uncheck the items by using either a collection or a property.

### Check items using Collection

You can check or uncheck a particular item by adding or removing that item from the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html#Syncfusion_Windows_Tools_Controls_CheckListBox_SelectedItems) collection.

{% tabs %}
{% highlight C#%}

//Model.cs
class Vegetable {
    public string Category { get; set; }
    public int Price { get; set; }
    public string Name { get; set; }
}

//ViewModel.cs
class ViewModel : NotificationObject {
    private ObservableCollection<Vegetable> vegetables =
        new ObservableCollection<Vegetable>();
    private ObservableCollection<object> checkedVegetables = 
        new ObservableCollection<object>();

    //Vegetables collection
    public ObservableCollection<Vegetable> Vegetables {
        get {
            return vegetables;
        }
        set {
            vegetables = value;
            this.RaisePropertyChanged("Vegetables");
        }
    }

    //Selected vegetable collection
    public ObservableCollection<object> CheckedVegetables {
        get {
            return checkedVegetables;
        }
        set {
            checkedVegetables = value;
            this.RaisePropertyChanged("CheckedVegetables");
        }
    }
    public ViewModel() {
        //Adding a vegetables details
        Vegetables = new ObservableCollection<Vegetable>();
        Vegetables.Add(new Vegetable { Price = 10,
            Name = "Yarrow", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = 20,
            Name = "Cabbage", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = 30,
            Name = "Horse gram", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = 20,
            Name = "Green bean", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = 10,
            Name = "Onion",Category = "Bulb and Stem"});
        Vegetables.Add(new Vegetable { Price = 30, 
            Name = "Nopal", Category = "Bulb and Stem"});

        //Adding a selected vegetable
        CheckedVegetables = new ObservableCollection<object>();
        CheckedVegetables.Add(Vegetables[0]);
        CheckedVegetables.Add(Vegetables[2]);
        CheckedVegetables.Add(Vegetables[4]);
    }
}

{%endhighlight%}
{% endtabs %}

{% tabs %}
{% highlight xaml%}

<syncfusion:CheckListBox ItemsSource="{Binding Vegetables}"
                         SelectedItems="{Binding CheckedVegetables}" 
                         DisplayMemberPath="Name"
                         Margin="30"
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
</syncfusion:CheckListBox>

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked using SelectedItems Collection](item-Selection_images/CheckedItems.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/CheckItems) to download the sample that showcases check the items by using the collection.

### Check items using Property

We can change the item’s checked state by using the [CheckListBoxItem.IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBoxItem.html#Syncfusion_Windows_Tools_Controls_CheckListBoxItem_IsChecked) property bound to any boolean property. There is a limitation when using this approach. During virtualization, views are not loaded, so the bound value of the `CheckListBoxItem.IsChecked` property is not known. Hence, `SelectedItems` will not be synchronized. However, we can turn off virtualization if you want both the selected items and the bound boolean property to be in sync.

{% tabs %}
{% highlight C#%}

//Model.cs
public class GroupItem {
    public string Name { get; set; }
    public string GroupName { get; set; }
    public bool IsChecked { get; set; }
}
//ViewModel.cs
public class ViewModel : NotificationObject {
    private ObservableCollection<GroupItem> virtualCollection;
    private ObservableCollection<GroupDescription> groupDescriptions;

    public ObservableCollection<GroupItem> VirtualCollection {
        get {
            return virtualCollection;
        }
        set {
            virtualCollection = value;
            RaisePropertyChanged("VirtualCollection");
        }
    }
    public ObservableCollection<GroupDescription> GroupDescriptions {
        get {
            return groupDescriptions;
        }
        set {
            groupDescriptions = value;
            RaisePropertyChanged("GroupDescriptions");
        }
    }
    public ViewModel() {
        GroupDescriptions = new ObservableCollection<GroupDescription>();
        VirtualCollection = new ObservableCollection<GroupItem>();
        for (int i = 0; i < 1000; i++)
        {
            for (int j = 0; j < 10; j++)
            {
                GroupItem myitem = new GroupItem() 
                { 
                    Name = "Module " + i.ToString(), 
                    GroupName = "Group" + j.ToString() 
                };
                if (i % 2 == 0)
                {
                    //Define a checked state for items
                    myitem.IsChecked = true;
                }
                VirtualCollection.Add(myitem);
            }
        }
    }
}

{%endhighlight%}
{% endtabs %}

{% tabs %}
{% highlight xaml%}

<Window.Resources>
    
    <!-- Define view model with group description -->
    <local:ViewModel x:Key="viewModel">
        <local:ViewModel.GroupDescriptions>
            
            <!-- Define group details -->
            <PropertyGroupDescription PropertyName="GroupName" />
        </local:ViewModel.GroupDescriptions>
    </local:ViewModel>
</Window.Resources>
<Grid>
    <syncfusion:CheckListBox ItemsSource="{Binding VirtualCollection}"
                             GroupDescriptions="{Binding GroupDescriptions}"
                             DataContext="{StaticResource viewModel}"
                             DisplayMemberPath="Name" 
                             Name="checkListBox"
                             Margin="20">
        
                    <!--Binding the IsChecked property from ViewModel-->
                    <syncfusion:CheckListBox.Resources>
                        <Style TargetType="syncfusion:CheckListBoxItem">
                            <Setter Property="IsChecked" Value="{Binding IsChecked}"/>
                        </Style>
                    </syncfusion:CheckListBox.Resources>

                    <!--Disable the Virtualization to update the checked item-->
                    <syncfusion:CheckListBox.ItemsPanel>
                        <ItemsPanelTemplate>
                            <StackPanel></StackPanel>
                        </ItemsPanelTemplate>
                    </syncfusion:CheckListBox.ItemsPanel>
                </syncfusion:CheckListBox>
</Grid>

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked using IsChecked property](item-Selection_images/CheckedItems_property.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/CheckItem-By-Property) to download the sample that showcases check the items by using the `IsChecked` property.

## Check items using Mouse

The `CheckListBox` items can be checked or unchecked with a single click, either by clicking the `CheckBox` or by clicking the content of the item. You can check or uncheck a `GroupHeader` or `SelectAll` item to check or uncheck a group of items or all items. By default, the items are checked or unchecked with a single mouse click. If you want to check or uncheck the items only on a mouse double-click, set the [IsCheckOnFirstClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html#Syncfusion_Windows_Tools_Controls_CheckListBox_IsCheckOnFirstClick) property to `false`.

{% tabs %}
{% highlight C#%}
 
//ViewModel.cs
class ViewModel {  
    public ObservableCollection<string> DaysCollection { get; set; }

    public ViewModel() {
        //Days added in the collection
        DaysCollection = new ObservableCollection<string>();
        DaysCollection.Add("Sunday");
        DaysCollection.Add("Monday");
        DaysCollection.Add("Tuesday");
        DaysCollection.Add("Wednesday");
        DaysCollection.Add("Thursday");
        DaysCollection.Add("Friday");
        DaysCollection.Add("Saturday");
    }
}

{%endhighlight%}
{% endtabs %}

<syncfusion:CheckListBox IsCheckOnFirstClick="False"
                         ItemsSource="{Binding DaysCollection}"                 
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
</syncfusion:CheckListBox>

{% tabs %}
{% highlight C#%}

CheckListBox checkListBox = new CheckListBox();
checkListBox.DataContext = new ViewModel();
checkListBox.ItemsSource = (checkListBox.DataContext as ViewModel).DaysCollection;

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked or unchecked by mouse double click](item-Selection_images/IsCheckOnFirstClick.png)

## Check items using Keyboard

The `Space bar` key allows the user to check or uncheck the selected item. By default, the selected item is checked or unchecked with a single `Space bar` key press. If you want to check or uncheck the items only on a double `Space bar` key press, set the `IsCheckOnFirstClick` property to `false`. We can check or uncheck a `GroupHeader` or `SelectAll` item to check or uncheck a group of items or all items.

{% tabs %}
{% highlight C#%}
 
//ViewModel.cs
class ViewModel {  
    public ObservableCollection<string> DaysCollection { get; set; }

    public ViewModel() {
        //Days added in the collection
        DaysCollection = new ObservableCollection<string>();
        DaysCollection.Add("Sunday");
        DaysCollection.Add("Monday");
        DaysCollection.Add("Tuesday");
        DaysCollection.Add("Wednesday");
        DaysCollection.Add("Thursday");
        DaysCollection.Add("Friday");
        DaysCollection.Add("Saturday");
    }
}

{%endhighlight%}
{% endtabs %}

<syncfusion:CheckListBox IsCheckOnFirstClick="False"
                         ItemsSource="{Binding DaysCollection}"                 
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
</syncfusion:CheckListBox>

{% tabs %}
{% highlight C#%}

CheckListBox checkListBox = new CheckListBox();
checkListBox.DataContext = new ViewModel();
checkListBox.ItemsSource = (checkListBox.DataContext as ViewModel).DaysCollection;

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked or unchecked by Space bar key double press](item-Selection_images/IsCheckOnFirstClick_keypress.png)

Based on the checked state of a `GroupHeader` and `SelectAll` item, their corresponding child items will be updated and vice versa.

## Checked state changed notification

When the checked state of an item is changed, the [ItemChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html) event is raised. You can get the details about the checked item in [ItemCheckedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ItemCheckedEventArgs.html).

{% tabs %}
{% highlight XAML %}

<!--Adding CheckListBox control -->
<syncfusion:CheckListBox ItemChecked="CheckListBox_ItemChecked"  
                         x:Name="checkListBox">
</syncfusion:CheckListBox>

{% endhighlight %}
{% highlight C# %}

CheckListBox checkListBox = new CheckListBox();
checkListBox.ItemChecked += CheckListBox_ItemChecked;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void CheckListBox_ItemChecked(object sender, ItemCheckedEventArgs e)
{
    Console.WriteLine("ItemChecked event is raised");
}

{% endhighlight %}
{% endtabs %}
 
## Selection changed notification

When the selected item is changed, the [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html) event is raised. The [SelectionChangedEventArgs](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.selectionchangedeventargs?redirectedfrom=MSDN&view=netframework-4.8) has the following members that provide information for the `SelectionChanged` event:

* **Added items** : Gets a collection of the underlying data objects in which the selection has to be processed.

* **Removed items** : Gets a collection of the underlying data objects in which the selection has to be removed.

{% tabs %}
{% highlight XAML %}

<!--Adding CheckListBox control -->
<syncfusion:CheckListBox SelectionChanged = "CheckListBox_SelectionChanged"  
                         x:Name="checkListBox">
</syncfusion:CheckListBox>

{% endhighlight %}
{% highlight C# %}

CheckListBox checkListBox = new CheckListBox();
checkListBox.SelectionChanged += CheckListBox_SelectionChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void CheckListBox_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    Console.WriteLine("SelectionChanged event is raised");
}

{% endhighlight %}
{% endtabs %}
 
Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/FirstClick) to download the sample that showcases check the items by using the mouse and `Space` key.
