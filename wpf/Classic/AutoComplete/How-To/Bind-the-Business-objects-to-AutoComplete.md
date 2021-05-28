---
layout: post
title: Bind the Business objects to AutoComplete | wpf | Syncfusion
description: Learn here all about Bind the Business objects to AutoComplete support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
 documentation: ug
---

# Bind the Business objects in WPF AutoComplete (Classic)

AutoComplete supports binding the Business objects as its Data Source.

The Business objects can be bound to the AutoComplete by using the CustomSource property and also by setting the value of the Source property as Custom. If the Source property value is set as FilePath or Registry, Binding of Business objects will not be supported.

Also when binding the Business objects, the DisplayMemberPath and the SelectedValuePath property values has to be given so that the DisplayMemberPath value displays in the drop-down list and  the SelectedValuePath assigns values to the SelectedValue property.

You can bind the Business objects to the AutoComplete as mentioned below.

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoCompleteTextBox" Source="Custom" DisplayMemberPath="Name" SelectedValuePath="EmployeeID">   
<syncfusion:AutoComplete.CustomSource> 
<local:EmployeeListCollection/>  
</syncfusion:AutoComplete.CustomSource>
</syncfusion:AutoComplete></td></tr>

{% endhighlight %}

{% highlight c# %}

public class EmployeeList    
{        
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
public class EmployeeListCollection : ObservableCollection<EmployeeList>   
{        
    public EmployeeListCollection()        
    {            
        this.Add(new EmployeeList() { EmployeeID = 1001, Name = "John", Mailid = "john@syncfusion.com" });           
        this.Add(new EmployeeList() { EmployeeID = 1002, Name = "Jerry", Mailid = "Jerry@syncfusion.com" });            
        this.Add(new EmployeeList() { EmployeeID = 1003, Name = "Brad", Mailid = "Brad@syncfusion.com" });            
        this.Add(new EmployeeList() { EmployeeID = 1004, Name = "lanze", Mailid = "lanze@syncfusion.com" });            
        this.Add(new EmployeeList() { EmployeeID = 1005, Name = "Chambel", Mailid = "Chambel@syncfusion.com" });           
        this.Add(new EmployeeList() { EmployeeID = 1006, Name = "Crimson", Mailid = "Crimson@syncfusion.com" });        
    }    
}

{% endhighlight %}
{% endtabs %}
