---
layout: post
title: DisplayName of the Properties in WPF PropertyGrid control | Syncfusion
description: This section explains how the display name of the property item has been customized through attributes.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Display name of the Properties in WPF PropertyGrid

We can change the display name of the properties instead of the property name by using the attributes and event.

## Property display name using Attributes

We can give a meaningful name to the properties that are displayed in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) instead of the property name by using the [Name](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.name?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_Name) field of the [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute and [DisplayName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.displaynameattribute?view=netframework-4.8) attribute.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee
{
    [Display(Name = "Employee Name")] 
    public string Name { get; set; }
    [DisplayName("Employee ID")]
    public string ID { get; set; }
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24)
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
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;

{% endhighlight %} 
{% endtabs %} 


![Value specified in the Name field of the Display attribute and DisplayName attributes is displayed as Name of the property in PropertyGrid](Attribute-Images\Display-Name-Attribute.png)

Here, the `Name` and `ID` properties is displayed as `Employee Name` and  `Employee ID` respectively. 

N> If you use both the `DisplayName` attribute and `Name` field of the `Display` attribute, the `Name` field of the `Display` attribute will have higher priority.

 Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-Name-Description) to download the sample that showcases the property `Display Name` support using attributes.

## Changing Property display name at runtime

We can change the property display name instead of the property name at runtime without using attributes by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html)  event with [AutoGeneratingPropertyGridItemEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html).[DisplayName](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs~DisplayName.html) property.

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
        //Name and DOB property name changed as 'Employee Name' and 'Date of Birth'.
        if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "Name") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName = "Employee Name";
        }
        else if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "DOB") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName = "Date of Birth";
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
            DOB = new DateTime(1995, 12, 24)
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

![Display name of the ID property changed to Employee ID by the DisplayName property of the AutoGeneratingPropertyGridItemEventArgs](Attribute-Images\DisplayName-AutoGeneratingPropertyGridItem.png)

Here, the `Name` and `DOB`property display name is changed as `Employee Name` and `Date of Birth` by the `AutoGeneratingPropertyGridItemEventArgs.Name` property of the `AutoGeneratingPropertyGridItem` event, not by any attributes.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property `Display Name` support using `AutoGeneratingPropertyGridItem` event.