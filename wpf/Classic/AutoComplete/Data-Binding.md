---
layout: post
title: Data Binding | AutoComplete | wpf | Syncfusion
description: Learn about data binding support in Syncfusion WPF AutoComplete control and more details about the control features.
platform: wpf
control: AutoComplete
documentation: ug
---

# Data Binding in WPF AutoComplete

Data Binding is the process of establishing a connection between the application UI and business logic. Data Binding can be unidirectional (Source -> target or target -> Source) or bidirectional (Source <-> target). You can bind the data to the AutoComplete through the [CustomSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~CustomSource.html) property. While binding the [CustomSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~CustomSource.html) to the AutoComplete, you must set the value of the DisplayMemberPath and the SelectedValuePath properties.

## Adding data binding to an application 

You can add the custom source for the `AutoComplete` by binding the source to the `CustomSource` property. You can use the `DisplayMemberPath` property to set the value for items that needs to be displayed in the drop-down list. Also you can use the [SelectedValuePath](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~SelectedValuePath.html) property which can be used to set the value of the [SelectedValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~SelectedValue.html) property. 

{% tabs %}
{% highlight c# %}

//Model.cs
public class EmployeeList {    
    public int EmployeeID { get; set; }    
    public string Name { get; set; }    
    public string Mailid { get; set; }    
    public EmployeeList() { }    
    public EmployeeList(string name, string mail, int id)   
    {            
        Name = name;            
        Mailid = mail;            
        EmployeeID = id;    
    }
}

//ViewModel.cs
public class EmployeeListCollection : ObservableCollection<EmployeeList> {
    public EmployeeListCollection() {
        this.Add(new EmployeeList() { EmployeeID = 1001, Name = "John", Mailid = "john@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1002, Name = "Jerry", Mailid = "Jerry@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1004, Name = "lanze", Mailid = "lanze@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1005, Name = "Chambel", Mailid = "Chambel@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1006, Name = "Crimson", Mailid = "Crimson@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1001, Name = "Smith", Mailid = "john@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1002, Name = "Sheron", Mailid = "Jerry@syncfusion.com" });
        this.Add(new EmployeeList() { EmployeeID = 1003, Name = "Sliver", Mailid = "Brad@syncfusion.com" });
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="autoComplete" 
                         Source="Custom" 
                         DisplayMemberPath="Name"
                         SelectedValuePath="EmployeeID">
<syncfusion:AutoComplete.CustomSource>
<local:EmployeeListCollection/>
</syncfusion:AutoComplete.CustomSource>
</syncfusion:AutoComplete>

{% endhighlight %}
{% endtabs %}

![AutoComplete data binding](Data-Binding_images/Data-Binding_img1.png)

AutoComplete Bound with Data Source
{:.caption}

N> View [Sample]() in GitHub

## Tables for properties and events

### Events

* [SelectedValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~SelectedValueChanged_EV.html)
* [CustomSourceChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~CustomSourceChanged_EV.html)

