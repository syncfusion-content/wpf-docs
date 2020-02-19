---
layout: post
title: Filtering items in WPF PropertyGrid control | Syncfusion
description: This section explains about how the property items are filtered through attributes, event and property of WPF PropertyGrid control
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Filtering and Searching the properties in WPF PropertyGrid

We can decide the properties which are need to be displayed in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) by hiding the unwanted properties using collection and attributes. We can navigate to the particular property by using the default SearchBox.

## Hide the Properties using Collection

We can hide the properties using the [HidePropertiesCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~HidePropertiesCollection.html) property. It is used to hide the mentioned properties which are already present in [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html). Properties can also be hidden at runtime using  `HidePropertiesCollection`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public string Name { get; set; }
    public string Email { get; set; }
    public string Bank { get; set; }
    public string ID { get; set; }
    public string AccountNumber { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

 public class ViewModel {
    private ObservableCollection<string> hidePropertyItems = new ObservableCollection<string>();
    public Object SelectedEmployee { get; set; }
    public ObservableCollection<string> HidePropertyItems
    {
        get { return hidePropertyItems; }
        set { hidePropertyItems = value; }
    }
    public ViewModel() {
        var employee = new Employee()
        { 
            Email = "john@gta.com",
            AccountNumber="23456784",
            Bank="ABC bank",
            Name = "Johnson",
            Experience=5,
            ID = "895",
            Age = 35,
        };
        HidePropertyItems.Add(nameof(employee.AccountNumber));
        HidePropertyItems.Add(nameof(employee.Email));
        HidePropertyItems.Add(nameof(employee.Bank));
        SelectedEmployee = employee;
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid HidePropertiesCollection="{Binding HidePropertyItems}" 
                         SelectedObject="{Binding SelectedEmployee}" 
                         x:Name="propertyGrid1" Width="350" Height="200" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.HidePropertiesCollection = (propertyGrid1.DataContext as ViewModel).HidePropertyItems;
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;

{% endhighlight %} 
{% endtabs %} 

![AccountNumber, Bank and Email properties are not displayed in PropertyGrid](Filtering-Images\HideItemCollection.png)

Here, the `PropertyGrid` hides the properties `AccountNumber`, `Bank` and `Email` properties which are specified in the `HidePropertiesCollection`.

N>`HidePropertiesCollection` cannot hide the properties which are added using `DynamicDescriptor`.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-HidePropertyByCollection) to download the sample that showcases the filtering  support using the `HidePropertiesCollection`.

## Hide the Properties using Attributes

We can hide properties by setting the [Browsable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.browsableattribute?view=netframework-4.8) value as `false` or [Bindable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.bindableattribute?view=netframework-4.8) as `false`, which properties will not be displayed in `PropertyGrid`. Functionalities of `Browsable` and `Bindable` attributes are same.  

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;

public class Employee {
    [Browsable(false)]
    public string Bank { get; set; }
    [Bindable(false)]
    public string AccountNumber { get; set; }
    [Browsable(false)]
    public string Email { get; set; }
    public string Name { get; set; } 
    public string ID { get; set; }       
    public int Age { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Email = "john@gta.com",
            AccountNumber = "23456784",
            Bank = "ABC bank",
            Name = "Johnson",
            Experience = 5,
            ID = "895",
            Age = 35,
        };
    }
}

{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"                   
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% endtabs %} 

![AccountNumber, Bank and Email properties are not displayed in PropertyGrid](Filtering-Images\HideItem-Attribute.png)

Here, the `PropertyGrid` not displayed the `AccountNumber`, `Bank` and `Email` properties which are specified `Browsable` and `Bindable` attribute value as `false`. 

N> If we use both the `Browsable` and `Bindable` attributes, the `Browsable` attribute have a higher priority.

### Hide the Properties using Display.AutoGeneratedField

If a property has the value of `Browsable` attribute as `true` and `Bindable` attribute as `true`, then properties are not hidden. We can hide the property by using the [AutoGeneratedField](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.autogeneratefield?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_AutoGenerateField) of `Display` as `false`. Value of `AutoGeneratedField` has no effect when the property is marked `Browsable` or `Bindable` as `false`.

{% tabs %}
{% highlight C# %}

public class Employee
{        
    [Browsable(true)]
    [Bindable(true)]
    [Display(AutoGenerateField = false)]
    public string Bank { get; set; }
    [Display(AutoGenerateField = false)]
    [Browsable(true)]
    [Bindable(true)]
    public string AccountNumber { get; set; }  
    [Browsable(false)]
    [Bindable(true)]
    [Display(AutoGenerateField = false)]
    public string ID { get; set; }      
    public string Email { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Email = "john@gta.com",
            AccountNumber = "23456784",
            Bank = "ABC bank",
            Name = "Johnson",
            Experience = 5,
            ID = "895",
            Age = 35,
        };
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"          
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% endtabs %} 

![AccountNumber and Bank properties are not displayed in PropertyGrid](Filtering-Images\HideItem-AutoField.png)

Here, the `PropertyGrid` not displayed the `Bank` and `AccountNumber` properties. The `Bank` and `AccountNumber` property are not displayed by value of `Browsable` attribute as `true` and `Bindable` attribute as `true` and the `AutoGeneratedField` of `DisplayAttribute` is `false`.In `ID` property, the `Browsable` is `false`, then the `AutoGeneratedField` property have no effect. 

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-HidePropertyByAttribute) to download the sample that showcases the filtering  support using the attributes.

## Hide the Properties at runtime

We can hide the properties in the `PropertyGrid` without using the attributes at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event with [AutoGeneratingPropertyGridItemEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html).Cancel property as `true`.

{% tabs %}
{% highlight C# %}

/// <summary>
/// A class that represents the AutoGeneratingPropertyGridItem event to AutoGeneratingPropertyGridItem Command
/// </summary>
public class EventToCommandBehavior : Behavior<FrameworkElement> {
    private Delegate _handler;
    private EventInfo _oldEvent;

    // Event
    public string Event { 
        get { return (string)GetValue(EventProperty); }
        set { SetValue(EventProperty, value); }
    }
    public static readonly DependencyProperty EventProperty =
        DependencyProperty.Register("Event", 
        typeof(string),
        typeof(EventToCommandBehavior), 
        new PropertyMetadata(null, OnEventChanged));

    // Command
    public ICommand Command { 
        get { return (ICommand)GetValue(CommandProperty); } 
        set { SetValue(CommandProperty, value); }
    }
    public static readonly DependencyProperty CommandProperty =
        DependencyProperty.Register("Command",
        typeof(ICommand),
        typeof(EventToCommandBehavior),
        new PropertyMetadata(null));

    // PassArguments (default: false)
    public bool PassArguments { 
        get { return (bool)GetValue(PassArgumentsProperty); }
        set { SetValue(PassArgumentsProperty, value); } }
    public static readonly DependencyProperty PassArgumentsProperty = 
        DependencyProperty.Register("PassArguments",
        typeof(bool), 
        typeof(EventToCommandBehavior), 
        new PropertyMetadata(false));

    private static void OnEventChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
        var beh = (EventToCommandBehavior)d;
        if (beh.AssociatedObject != null) // is not yet attached at initial load
            beh.AttachHandler((string)e.NewValue);
    }

    protected override void OnAttached() {
        AttachHandler(this.Event); // initial set
    }

    /// <summary>
    /// Attaches the handler to the event
    /// </summary>
    private void AttachHandler(string eventName) {
        // detach old event
        if (_oldEvent != null)
            _oldEvent.RemoveEventHandler(this.AssociatedObject, _handler);

        // attach new event
        if (!string.IsNullOrEmpty(eventName)) {
            EventInfo ei = this.AssociatedObject.GetType().GetEvent(eventName);
            if (ei != null) {
                MethodInfo mi = this.GetType().GetMethod("ExecuteCommand",
                    BindingFlags.Instance | BindingFlags.NonPublic);
                _handler = Delegate.CreateDelegate(ei.EventHandlerType, this, mi);
                ei.AddEventHandler(this.AssociatedObject, _handler);
                _oldEvent = ei; // store to detach in case the Event property changes
            }
            else
                throw new ArgumentException(string.Format
                    ("The event '{0}' was not found on type '{1}'", 
                    eventName, this.AssociatedObject.GetType().Name));
        }
    }
    private void ExecuteCommand(object sender, EventArgs e) {
        object parameter = this.PassArguments ? e : sender;
        if (this.Command != null) {
            if (this.Command.CanExecute(parameter))
                this.Command.Execute(parameter);
        }
    }
}

/// <summary>
/// A clas that represents the Commend for the AutoGeneratingPropertyGridItem Event 
/// </summary>
class UpdaterValue : ICommand {
    #region ICommand Members  
    public bool CanExecute(object parameter) {
        return true;
    }
    public event EventHandler CanExecuteChanged {
        add { CommandManager.RequerySuggested += value; }
        remove { CommandManager.RequerySuggested -= value; }
    }
    public void Execute(object parameter) {
        //Name and Experience properties hided in the PropertGrid control.
        if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "Experience") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).Cancel =true;
        }
        else if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "Name") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).Cancel = true;
        }
    }
    #endregion
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    private ICommand autoGeneratingPropertyGridItemEventCommand;
    public object SelectedEmployee { get; set; }

    //Command for the AutoGeneratingPropertyGridItemEvent
    public ICommand AutoGeneratingPropertyGridItemEventCommand {
        get { if (autoGeneratingPropertyGridItemEventCommand == null)
                autoGeneratingPropertyGridItemEventCommand = new UpdaterValue();
              return autoGeneratingPropertyGridItemEventCommand;
        }
        set {
            autoGeneratingPropertyGridItemEventCommand = value;
        }
    }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Experience = 5;
        };
    }
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding IsAsync=True, Path=SelectedEmployee}" 
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
    <i:Interaction.Behaviors>
        <local:EventToCommandBehavior PassArguments="true" 
            Event="AutoGeneratingPropertyGridItem" 
            Command="{Binding Path=AutoGeneratingPropertyGridItemEventCommand}" />
    </i:Interaction.Behaviors>
</syncfusion:PropertyGrid>


{% endhighlight %} 
{% endtabs %} 

![Designation and Age properties are not displayed in PropertyGrid](Filtering-Images\AutoGeneratingPropertyGridItem.png)

Here, the `Experience` and `Name` properties are not displayed in the `PropertyGrid`, since the properties was restricted to be added in `PropertyGrid` by the `AutoGeneratingPropertyGridItem` event.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property filtering support using `AutoGeneratingPropertyGridItem` event.

## Searching the Properties

If the `PropertyGrid.SelectedObject` contains more properties, it is difficult to find the specific property. Now, we can easily get the required properties by searching the property name in the SearchBox. SearchBox will be filter and display the properties which are contains the searched text. SearchBox is shown by default, we can hide it by setting [SearchBoxVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SearchBoxVisibility.html) property as `Collapsed`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public int Age { get; set; }
    public string Name { get; set; }
    public string EmailID { get; set; }
    public string ID { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        { 
            EmailID="johnson@gta.com",
            Age = 23, 
            ID = "1207", 
            Name = "John Son"
        };
    }
}

{% endhighlight %} 
{% endtabs %}

**SearchBoxVisibility = Visible**

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid Name="propertyGrid1" SelectedObject="{Binding SelectedEmployee }" SearchBoxVisibility="Visible" />

{% endhighlight %} 
% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;
propertyGrid1.SearchBoxVisibility = Visibility.Visible;

{% endhighlight %} 
{% endtabs %}

![SearchBox filter the Age property in PropertyGrid](Filtering-Images\Searching.png)


Here, The `Age` property is searched in the SearchBox.                                             

**SearchBoxVisibility = Collapsed**

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid Name="propertyGrid1" SelectedObject="{Binding SelectedEmployee }" SearchBoxVisibility="Collapsed" />

{% endhighlight %} 
% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;
propertyGrid1.SearchBoxVisibility = Visibility.Collapsed;

{% endhighlight %} 
{% endtabs %}

![SearchBox not displayed in PropertyGrid](Filtering-Images\SearchBox-collapsed.png)

Here, The SearchBox is hidden in the `PropertyGrid`.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-Grouping-Sorting-Ordering) to download the sample that showcases the property searching in the SearchBox support.

                                           







