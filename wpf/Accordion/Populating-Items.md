---
layout: post
title: Populating Items | SfAccordion | WPF | Syncfusion
description: Explains about Populating Items of SfAccordion control for WPF
platform: WPF
control: SfAccordion
documentation: ug
---

# Populating Items

`SfAccordionItem` are added as items of `SfAccordion`. Items can be added using `Items` or `ItemSource` property.

## Using Items

SfAccordion accepts `SfAccordionItem` as its children when added directly.

### Adding items to the control 

Here five SfAccordionItems are added as the children of the `SfAccordion`.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    <layout:SfAccordionItem/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

    SfAccordion accordion = new SfAccordion();

    accordion.Items.Add(new SfAccordionItem());

    accordion.Items.Add(new SfAccordionItem());

    accordion.Items.Add(new SfAccordionItem());

    accordion.Items.Add(new SfAccordionItem());

    accordion.Items.Add(new SfAccordionItem());

{% endhighlight %}

{% highlight VB %}

    Dim accordion As New SfAccordion()

    accordion.Items.Add(New SfAccordionItem())

    accordion.Items.Add(New SfAccordionItem())

    accordion.Items.Add(New SfAccordionItem())

    accordion.Items.Add(New SfAccordionItem())

    accordion.Items.Add(New SfAccordionItem())


{% endhighlight %}


{% endtabs %}

![Adding items to the control](Populating-Items-images/Populating-Items-img1.jpeg)

### Setting Header for items

`SfAccordionItem` provides a property [Header](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.headeredcontentcontrol.header?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_HeaderedContentControl_Header) that helps to set the header for the item. [Header](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.headeredcontentcontrol.header?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_HeaderedContentControl_Header) is visible in both expanded and collapsed state. Set the value as “WPF” for the first child and repeat the same procedure for the remaining children with values as “Silverlight”, “WinRT”, ”Windows Phone” and “Universal”.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion>

    <layout:SfAccordionItem Header="WPF"/>

    <layout:SfAccordionItem Header="Silverlight"/>

    <layout:SfAccordionItem Header="WinRT"/>

    <layout:SfAccordionItem Header="Windows Phone"/>

    <layout:SfAccordionItem Header="Universal"/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

    SfAccordion accordion = new SfAccordion();

    accordion.Items.Add(new SfAccordionItem() { Header = "WPF" });

    accordion.Items.Add(new SfAccordionItem() { Header = "Silverlight" });

    accordion.Items.Add(new SfAccordionItem() { Header = "WinRT" });

    accordion.Items.Add(new SfAccordionItem() { Header = "Windows Phone" });

    accordion.Items.Add(new SfAccordionItem() { Header = "Universal" });

{% endhighlight %}

{% highlight VB %}

    Dim accordion As New SfAccordion()

    accordion.Items.Add(New SfAccordionItem() With {.Header = "WPF"})

    accordion.Items.Add(New SfAccordionItem() With {.Header = "Silverlight"})

    accordion.Items.Add(New SfAccordionItem() With {.Header = "WinRT"})

    accordion.Items.Add(New SfAccordionItem() With {.Header = "Windows Phone"})

    accordion.Items.Add(New SfAccordionItem() With {.Header = "Universal"})

{% endhighlight %}

{% endtabs %}

`SfAccordion` control is populated as follows:

![Setting Header for items](Populating-Items-images/Populating-Items-img2.jpeg)

### Setting Content for items

[Content](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.contentcontrol.content?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_ContentControl_Content) property helps to set the content for `SfAccordionItem`. `SfAccordionItem` is a ContentControl so that any object can be added as its content. Content is visible only in expanded state.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion>

    <layout:SfAccordionItem Header="WPF" Content="Essential Studio for WPF"/>

    <layout:SfAccordionItem Header="Silverlight" Content="Essential Studio for Silverlight"/>

    <layout:SfAccordionItem Header="WinRT" Content="Essential Studio for WinRT"/>

    <layout:SfAccordionItem Header="Windows Phone" Content="Essential Studio for Windows Phone"/>

    <layout:SfAccordionItem Header="Universal" Content="Essential Studio for Universal"/>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}


{% tabs %}


{% highlight C# %}

    SfAccordion accordion = new SfAccordion();

    accordion.Items.Add(new SfAccordionItem() { Header = "WPF", Content = "Essential Studio for WPF" });

    accordion.Items.Add(new SfAccordionItem() { Header = "Silverlight" , Content = "Essential Studio for Silverlight"});

    accordion.Items.Add(new SfAccordionItem() { Header = "WinRT", Content = "Essential Studio for WinRT" });

    accordion.Items.Add(new SfAccordionItem() { Header = "Windows Phone" , Content = "Essential Studio for Windows Phone"});

    accordion.Items.Add(new SfAccordionItem() { Header = "Universal" , Content = "Essential Studio for Universal"});

{% endhighlight %}

{% highlight VB %}

    Dim accordion As New SfAccordion()

    accordion.Items.Add(New SfAccordionItem() With {
        .Header = "WPF",
        .Content = "Essential Studio for WPF"
    })

    accordion.Items.Add(New SfAccordionItem() With {
        .Header = "Silverlight",
        .Content = "Essential Studio for Silverlight"
    })

    accordion.Items.Add(New SfAccordionItem() With {
        .Header = "WinRT",
        .Content = "Essential Studio for WinRT"
    })

    accordion.Items.Add(New SfAccordionItem() With {
        .Header = "Windows Phone",
        .Content = "Essential Studio for Windows Phone"
    })

    accordion.Items.Add(New SfAccordionItem() With {
        .Header = "Universal",
        .Content = "Essential Studio for Universal"
    })

{% endhighlight %}

{% endtabs %}

![Setting Content for items](Populating-Items-images/Populating-Items-img3.jpeg)

## Using ItemsSource

SfAccordion accepts any business object collection to be bound to its [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssource?view=netframework-4.7.2) property. 

### Adding items to the control

Follow the below steps to add the Items through [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssource?view=netframework-4.7.2) property.

1.Create a model

{% tabs %}

{% highlight C# %}

    public class Employee
    {
    public string Name { get; set; }

    public string Description { get; set; }
    }

{% endhighlight %}

{% highlight VB %}

    Public Class Employee
    Public Property Name() As String

    Public Property Description() As String
    End Class

{% endhighlight %}

{% endtabs %}

2.Create a collection of model

{% tabs %}

{% highlight C# %}

    private List<Employee> employees;

    public List<Employee> Employees
    {
        
    get { return employees; }

    set { employees = value; }

    }

{% endhighlight %}

{% highlight VB %}

    Private employees_Renamed As List(Of Employee)

    Public Property Employees() As List(Of Employee)

    Get
        Return employees_Renamed
    End Get

    Set(ByVal value As List(Of Employee))
        employees_Renamed = value
    End Set

    End Property

{% endhighlight %}

{% endtabs %}

3.Populate the collection

{% tabs %}

{% highlight C# %}

    Employees = new List<Employee>();

    Employees.Add(new Employee() { Name = "James", Description = "Description about James" });

    Employees.Add(new Employee() { Name = "Linda", Description = "Description about Linda" });

    Employees.Add(new Employee() { Name = "Carl", Description = "Description about Carl" });

    Employees.Add(new Employee() { Name = "Niko", Description = "Description about Niko" });

{% endhighlight %}

{% highlight VB %}

    Employees = New List(Of Employee)()

    Employees.Add(New Employee() With {
        .Name = "James",
        .Description = "Description about James"
    })

    Employees.Add(New Employee() With {
        .Name = "Linda",
        .Description = "Description about Linda"
    })

    Employees.Add(New Employee() With {
        .Name = "Carl",
        .Description = "Description about Carl"
    })

    Employees.Add(New Employee() With {
        .Name = "Niko",
        .Description = "Description about Niko"
    })

{% endhighlight %}

{% endtabs %}

4.Bind the Employees collection to [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssource?view=netframework-4.7.2) property of `SfAccordion` Control

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion ItemsSource="{Binding Employees}"/>

{% endhighlight %}

{% endtabs %}

`SfAccordion` control is populated as follows:

![Adding items to the control](Populating-Items-images/Populating-Items-img4.jpeg)

### Setting Header for items

Header can be displayed using the property [DisplayMemberPath](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.displaymemberpath?view=netframework-4.7.2). This property is used to get the header from Model class. Header is visible in both expanded and collapsed state. 

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion ItemsSource="{Binding Employees}" DisplayMemberPath="Name"/>

{% endhighlight %}

{% endtabs %}

![Setting Header for items](Populating-Items-images/Populating-Items-img5.jpeg)

[HeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_HeaderTemplate) property can also be used to display the header. [HeaderTemplateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_HeaderTemplateSelector) property is also provided to apply header template based on the selection logic. 

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion ItemsSource="{Binding Employees}">

    <layout:SfAccordion.HeaderTemplate>

    <DataTemplate>

    <TextBlock Text="{Binding Name}"/>

    </DataTemplate>

    </layout:SfAccordion.HeaderTemplate>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

![Setting Header for items](Populating-Items-images/Populating-Items-img6.jpeg)

### Setting Content for items

Content can be displayed using the [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_ContentTemplate) property. Content is visible only in the expanded state. [ContentTemplateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Layout.SfAccordion.html#Syncfusion_Windows_Controls_Layout_SfAccordion_ContentTemplateSelector) property is also provided to apply content template based on the selection logic.

{% tabs %}

{% highlight XAML %}

    <layout:SfAccordion ItemsSource="{Binding Employees}" DisplayMemberPath="Name">

    <layout:SfAccordion.ContentTemplate>

    <DataTemplate>

    <TextBlock Text="{Binding Description}"/>

    </DataTemplate>

    </layout:SfAccordion.ContentTemplate>

    </layout:SfAccordion>

{% endhighlight %}

{% endtabs %}

![Setting Content for items](Populating-Items-images/Populating-Items-img7.jpeg)
