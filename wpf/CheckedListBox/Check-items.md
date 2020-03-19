---
layout: post
title: Check an item in WPF CheckListBox control | Syncfusion
description: This section describes about different ways available to check an item present in the CheckListBox control.
platform: wpf
control: CheckListBox
documentation: ug
---

# Check the items in WPF CheckListBox

In [CheckListBox](https://www.syncfusion.com/wpf-ui-controls/CheckedListBox), items present in the control can be checked or unchecked either by using any one of the following ways:

1. Using Collection
2. Using Property
2. Using Mouse
3. Using Keyboard

##  Check items using Collection

We can check or uncheck the particular item by add or remove that items into the [SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~SelectedItems.html) collection. 

{% tabs %}
{% highlight C#%}

//Model.cs
class Vegetable {
    public string Category { get; set; }
    public string Price { get; set; }
    public string Name { get; set; }
}

//ViewModel.cs
class ViewModel : NotificationObject {
    private ObservableCollection<Vegetable> vegetables = new ObservableCollection<Vegetable>();
    private ObservableCollection<object> checkedVegetables = new ObservableCollection<object>();

    //Vegetables collection
    public ObservableCollection<Vegetable> Vegetables        {
        get {
            return vegetables;
        }
        set {
            vegetables = value;
            this.RaisePropertyChanged("Vegetables");
        }
    }

    //Checked vegetable collection
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
        //Adding a vegetables details into the Vegetables collection
        Vegetables = new ObservableCollection<Vegetable>();
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Yarrow", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Cabbage", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Horse gram", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Green bean", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Onion", Category = "Bulb and Stem" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Nopal", Category = "Bulb and Stem" });
        
        //Adding a checked vegetable into the CheckedVegetables collection
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
                          Name="checkListBox">
     <i:Interaction.Triggers>
         <i:EventTrigger EventName="Loaded">
             <i:InvokeCommandAction Command="{Binding SelectionChangedCommand}" CommandParameter="{Binding ElementName=checkListBox}" />
         </i:EventTrigger>
     </i:Interaction.Triggers>
 </syncfusion:CheckListBox>

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked using SelectedItems Collection](item-Selection_images/CheckedItems.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/CheckItems) to download the sample that showcases check the items by using the collection.

## Check items using Property

We can change the item’s checked state by using the [CheckListBoxItem.IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBoxItem~IsChecked.html) property bounded with any boolean property. There is limitation when using this approach. During virtualization, views will not be loaded, so it does not know the bounded value of `CheckListBoxItem.IsChecked` property. Hence, `SelectedItems` will not be in synchronized. However we can turnoff virtualization if you want both selected items to be in sync with bounded boolean property.

{% tabs %}
{% highlight C#%}

//Model.cs
public class Model {
    public string Name { get; set; }
    public string GroupName { get; set; }
    public bool IsChecked { get; set; }
}

//ViewModel.cs
public class ViewModel {
    private ObservableCollection<Model> collection = new ObservableCollection<Model>();
    public ObservableCollection<Model> Collection {
        get { return collection; }
        set { collection = value; }
    }

    public ICommand LoadedCommand { get; set; }
    public void OnLoaded(object param) {
        CollectionView view = (CollectionView)CollectionViewSource.GetDefaultView(Collection);

        //Adding group description
        view.GroupDescriptions.Add(new PropertyGroupDescription("GroupName"));
    }

    public ViewModel() {
        Collection = new ObservableCollection<Model>();
        for (int i = 0; i < 100; i++) {
            for (int j = 0; j < 10; j++) {
                Model myitem = new Model() { Name = "Module " + i.ToString(), GroupName = "Group" + j.ToString() };
                if (i % 2 == 0)
                    myitem.IsChecked = true;
                Collection.Add(myitem);
            }
        }

        //Initialize the checklistbox LoadedCommand
        LoadedCommand = new DelegateCommand<object>(OnLoaded);
    }
}

{%endhighlight%}
{% endtabs %}

{% tabs %}
{% highlight xaml%}

<syncfusion:CheckListBox ItemsSource="{Binding Collection}"           
                 DisplayMemberPath="Name"
                 Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
    <i:Interaction.Triggers>
        <i:EventTrigger EventName="Loaded">
            <i:InvokeCommandAction Command="{Binding LoadedCommand}" />
        </i:EventTrigger>
    </i:Interaction.Triggers>

    <!--Binding the IsChecked property from ViewModel-->
    <syncfusion:CheckListBox.ItemContainerStyle>
        <Style TargetType="syncfusion:CheckListBoxItem">
            <Setter Property="IsChecked" Value="{Binding IsChecked}"/>
        </Style>
    </syncfusion:CheckListBox.ItemContainerStyle>

    <!--Disable the Virtualization to update the checked item-->
    <syncfusion:CheckListBox.ItemsPanel>
        <ItemsPanelTemplate>
            <StackPanel></StackPanel>
        </ItemsPanelTemplate>
    </syncfusion:CheckListBox.ItemsPanel>
</syncfusion:CheckListBox>

{%endhighlight%}
{% endtabs %}

![CheckListBox items checked using IsChecked property](item-Selection_images/CheckedItems_property.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/CheckItem-By-Property) to download the sample that showcases check the items by using the `IsChecked` property.

## Check items using Mouse

The `CheckListBox` items can be checked or unchecked in a single click either by clicking the `CheckBox` or clicking the content of the item. We can check or uncheck a `GroupHeader` or `SelectAll` item to check or uncheck a group of items or all items. By default, the items are checked or unchecked by the  single mouse click. If we want to check or uncheck the items only on mouse double click use the [IsCheckOnFirstClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~IsCheckOnFirstClick.html) property as `false`.

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

`Space bar` key allows the users to check or uncheck the selected item. By default, the selecteditem is checked or unchecked by the single `Space bar` key press. If we want to check or uncheck the items only on double `Space bar` key press use the `IsCheckOnFirstClick` property as `false`. We can check or uncheck a `GroupHeader` or `SelectAll` item to check or uncheck a group of items or all items

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

When the checked state of an item is changed, it will be notified by using the [ItemChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~ItemChecked_EV.html) event. You can get the details about the checked item in [ItemCheckedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.ItemCheckedEventArgs.html).

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

When the selected item is changed, it will be notified by using the [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~SelectionChanged_EV.html) event.The [SelectionChangedEventArgs](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.selectionchangedeventargs?redirectedfrom=MSDN&view=netframework-4.8) has the following members that provides information for the `SelectionChanged` event:

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