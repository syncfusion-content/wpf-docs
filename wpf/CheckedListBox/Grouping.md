---
layout: post
title: Grouping the items in WPF CheckListBox control | Syncfusion
description: This section describes how to group the Checklistbox items present in the CheckListBox and its basic features.
platform: wpf
control: CheckListBox
documentation: ug
---

# Grouping in WPF CheckListBox

 By default, the [CheckListBox](https://www.syncfusion.com/wpf-ui-controls/CheckedListBox) items are in the listed view. We can group the `CheckListBox` items by adding the group description to the `CollectionView.GroupDescriptions` collection.

 The selection state of group header varies based on the checked or unchecked state of the child items. Group can be expanded or collapsed and the child items present in the group can be checked or unchecked based on the user’s perspective.

{% tabs %}
{% highlight C# %}

//Model.cs
class Vegetable {
    public string Category { get; set; }
    public string Price { get; set; }
    public string Name { get; set; }
}

//ViewModel.cs
class ViewModel {
    public ObservableCollection<Vegetable> Vegetables { get; set; }
    public ICommand LoadedCommand { get; set; }
    public void OnLoaded(object param) {
        CollectionView view = (CollectionView)CollectionViewSource.GetDefaultView(Vegetables);
       
        //Adding group description
            view.GroupDescriptions.Add(new PropertyGroupDescription("Price"));
    }
    public ViewModel() {
        Vegetables = new ObservableCollection<Vegetable>();
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Yarrow", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Cabbage", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Horse gram", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Green bean", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Onion", Category = "Bulb and Stem" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Nopal", Category = "Bulb and Stem" });

        //Initialize the CheckListBox LoadedCommand
        LoadedCommand = new DelegateCommand<object>(OnLoaded);
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:CheckListBox ItemsSource="{Binding Vegetables}" DisplayMemberPath="Name"
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
    <i:Interaction.Triggers>
        <i:EventTrigger EventName="Loaded">
            <i:InvokeCommandAction Command="{Binding LoadedCommand}" />
        </i:EventTrigger>
    </i:Interaction.Triggers>
</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

Here, the `Vegetables` items are grouped based on their price.

![CheckListBox items grouped by the Price property](Grouping-Sorting_images/Grouping_image.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/Grouping) to download the sample that showcases the grouping support in the `CheckListBox`.

## Nested Grouping

 We can create a multi-level nested groups for the `CheckListBox` items by adding the two or more group descriptions to the `CollectionView.GroupDescriptions` collection. Child level groups are created by order of group descriptions added to the collection.

{% tabs %}
{% highlight C# %}

//Model.cs
class Vegetable {
    public string Category { get; set; }
    public string Price { get; set; }
    public string Name { get; set; }
}

//ViewModel.cs
class ViewModel {
    public ObservableCollection<Vegetable> Vegetables { get; set; }
    public ICommand LoadedCommand { get; set; }
    public void OnLoaded(object param) {
        CollectionView view = (CollectionView)CollectionViewSource.GetDefaultView(Vegetables);
       
        //Adding the multiple group description
            view.GroupDescriptions.Add(new PropertyGroupDescription("Category"));
            view.GroupDescriptions.Add(new PropertyGroupDescription("Price"));
    }
    public ViewModel() {
        Vegetables = new ObservableCollection<Vegetable>();
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Yarrow", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Pumpkins", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Cabbage", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Spinach", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Wheat Grass", Category = "Leafy and Salad" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Horse gram", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Chickpea", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Green bean", Category = "Beans" });
        Vegetables.Add(new Vegetable { Price = "$30", Name = "Garlic", Category = "Bulb and Stem" });
        Vegetables.Add(new Vegetable { Price = "$10", Name = "Onion", Category = "Bulb and Stem" });
        Vegetables.Add(new Vegetable { Price = "$20", Name = "Nopal", Category = "Bulb and Stem" });

        //Initialize the checklistbox LoadedCommand
        LoadedCommand = new DelegateCommand<object>(OnLoaded);
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:CheckListBox ItemsSource="{Binding Vegetables}" DisplayMemberPath="Name"
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
    <i:Interaction.Triggers>
        <i:EventTrigger EventName="Loaded">
            <i:InvokeCommandAction Command="{Binding LoadedCommand}" />
        </i:EventTrigger>
    </i:Interaction.Triggers>
</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

Here, the `Vegetables` items are grouped based on their Category and then, the categorized properties are grouped by price.

![CheckListBox items with nested grouping ](Grouping-Sorting_images/NestedGrouping_image.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/NestedGrouping) to download the sample that showcases the nested grouping support in the `CheckListBox`.

## Custom grouping

`CheckListBox` allows you to group the items based on custom logic when the common grouping functionality doesn’t meet your requirement. We can achieve this by using the `IValueConverter`.

{% tabs %}
{% highlight C# %}

//Model.cs
public class Employee {
    public string Name { get; set; }
    public int Age { get; set; }
    public DateTime DOB { get; set; }
}

public class ViewModel : NotificationObject {
    private CollectionView view;
    private ICommand loadedCommand;
    private ObservableCollection<Employee> employees = new ObservableCollection<Employee>();

    public ObservableCollection<Employee> Employees {
        get {
            return employees;
        }
        set {
            employees = value;
            RaisePropertyChanged("Employees");
        }
    }

    public ICommand LoadedCommand {
        get {
            return loadedCommand;
        }
    }

    public void OnLoaded(object param) {
        view = (CollectionView)CollectionViewSource.GetDefaultView(Employees);

        //Group descriptions for the employees
        view.GroupDescriptions.Add(new PropertyGroupDescription("DOB", new DataConvert("Year")));
        view.GroupDescriptions.Add(new PropertyGroupDescription("DOB", new DataConvert("Month")));
    }

    public ViewModel() {
        loadedCommand = new DelegateCommand<object>(OnLoaded);
        //Adding the items in Vegetable collection
        Employees = new ObservableCollection<Employee>();
        Employees.Add(new Employee() { Name = "Daniel", DOB = new DateTime(1983, 02, 15), Age = 37 });
        Employees.Add(new Employee() { Name = "James", DOB = new DateTime(1988, 06, 29), Age = 32 });

        Employees.Add(new Employee() { Name = "Michael", DOB = new DateTime(1987, 06, 10), Age = 33 });
        Employees.Add(new Employee() { Name = "Robert", DOB = new DateTime(1980, 08, 23), Age = 40 });

        Employees.Add(new Employee() { Name = "John", DOB = new DateTime(1990, 12, 22), Age = 30 });
        Employees.Add(new Employee() { Name = "Paul", DOB = new DateTime(1997, 04, 08), Age = 23 });
       
        Employees.Add(new Employee() { Name = "Mark", DOB = new DateTime(1994, 08, 05), Age = 26 });
        Employees.Add(new Employee() { Name = "George", DOB = new DateTime(1998, 10, 01), Age = 22 });

        Employees.Add(new Employee() { Name = "Kevin", DOB = new DateTime(1996, 12, 02), Age = 24 });
        
        Employees.Add(new Employee() { Name = "Thomes", DOB = new DateTime(1995, 10, 08), Age = 25 });
       Employees.Add(new Employee() { Name = "Steven", DOB = new DateTime(1982, 12, 15), Age = 38 });
         }
}


//Converter for the Custom Grouping
public class DataConvert : IValueConverter {
    string Category;
    public DataConvert(string category) {
        Category = category;
    }
    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture) {            
        DateTime result;
        string MyString = value.ToString();
        DateTime.TryParse(MyString, out result);

        if (Category == "Year") {
            //Grouping the employee who are all born on 1980-1990 
            if ((DateTime.Compare(new DateTime(1980,01,01), result)) <= 0 && (DateTime.Compare(new DateTime(1990, 12, 31), result)) >= 0) {
                return "Birth Year(1980 - 1990)";
            }
            //Grouping the employee who are all born on 1990-2000 
            else if ((DateTime.Compare(new DateTime(1991, 01, 01), result)) <= 0 && (DateTime.Compare(new DateTime(2000, 12, 31), result)) >= 0) {
                return "Birth Year(1991 - 2000)";
            }

        }
        else if (Category == "Month") {
            //Sub-Grouping the employee who are all born on Jan-Mar 
            if (result.Month >=1 && result.Month<=3) {
                return "Jan-Mar";
            }
            //Sub-Grouping the employee who are all born on Apr-Jun
            else if (result.Month >= 4 && result.Month <= 6) {
                return "Apr-Jun";
            }
            //Sub-Grouping the employee who are all born on Jul-Sep
            else if (result.Month >= 7 && result.Month <= 9) {
                return "Jul-Sep";
            }
            //Sub-Grouping the employee who are all born on Oct-Dec
            else {
                return "Oct-Dec";
            }
        }
        return "Others";
    }
    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture) {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:CheckListBox ItemsSource="{Binding Employees}" 
                         DisplayMemberPath="Name"
                         Name="checkListBox" >
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
    <i:Interaction.Triggers>
        <i:EventTrigger EventName="Loaded">
            <i:InvokeCommandAction Command="{Binding LoadedCommand}" />
        </i:EventTrigger>
    </i:Interaction.Triggers>
</syncfusion:CheckListBox>

{% endhighlight %}
{% endtabs %}

![CheckListBox items with custom grouping](Grouping-Sorting_images/Custom-Grouping_image.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/Custom-Grouping) to download the sample that showcases the custom grouping support.