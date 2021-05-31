---
layout: post
title: Populating Data in WPF Domain Updown control | Syncfusion
description: Learn here all about Populating Data support in Syncfusion WPF Domain Updown (SfDomainUpDown) control and more.
platform: wpf
control: DomainUpDown
 documentation: ug
---

# Populating Data in WPF Domain Updown (SfDomainUpDown)

The DomainUpDown control can be populated with a predefined list of items. 

For example, in the following code, the DomainUpDown populates a list of employees:

{% tabs %}
{%highlight c#%}

public class Employee
{
    public string Name { get; set; }
    public string Email { get; set; }
}

{%endhighlight%}
{% endtabs %}

Create a collection attribute:

{% tabs %}
{%highlight c#%}

private List<Employee> employees;
public List<Employee> Employees
{
    get { return employees; }
    set { employees = value; }
}

{%endhighlight%}
{% endtabs %}

Populate the collection with items:

{% tabs %}
{%highlight c#%}

Employees = new List<Employee>();
Employees.Add(new Employee{Name = "Lucas", Email = "lucas@syncfusion.com"});
Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });
Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });

{%endhighlight%}
{% endtabs %}

## ItemsSource

Bind the Employees collection to the ItemsSource property of DomainUpDown:

{% tabs %}
{%highlight c#%}

<Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf">
<Grid>
<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                      ItemsSource="{Binding Employees}" >           
</editors:SfDomainUpDown>
</Grid>
</Page>

{%endhighlight%}
{% endtabs %}

N> When the ContentTemplate property of the DomainUpDown control is not set, Items will be displayed as business objects in the control.

## ContentTemplate

ContentTemplate helps the user decorate the content with visual elements. At this point, the control is populated with list of employees, and the Employee model contains two properties: Name and Email. In this example, the control is set to display content based on Name.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                      ItemsSource="{Binding Employees}">
<editors:SfDomainUpDown.ContentTemplate>
<DataTemplate>
<StackPanel Orientation="Horizontal">
<Image Height="24" Width="24" Source="Image.png"/>
<TextBlock Text="{Binding Name}"/>
</StackPanel>
</DataTemplate>
</editors:SfDomainUpDown.ContentTemplate>
</editors:SfDomainUpDown>

{%endhighlight%}
{% endtabs %}

![Populating-Data_img1](Populating-Data_images/Populating-Data_img1.png)
