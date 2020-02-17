---
layout: post
title: ReadyOnly and Editable attributes in WPF PropertyGrid | Syncfusion
description: Learn about make the properties of selected object as readonly in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# ReadOnly properties properties in WPF PropertyGrid

We can decide the properties which are need to be readonly(non-editable) in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid). It can be achieved by attributes and event.

## ReadOnly properties using attributes

We can makes the properties as non-editable by using the [ReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.readonlyattribute?view=netframework-4.8) and [Editable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.editableattribute?view=netframework-4.8) attributes. When the property is marked as `ReadOnly` or `Editable` as `false`, the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) will not allow the user to change the property values.

`Password` property is marked as Editable false and `DOB` is marked as ReadOnly.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    public string Name
    {
        get;

        set;
    }

    [ReadOnly(true)]
    public DateTime DOB
    {
        get;

        set;
    }

    [Editable(false)]
    public Gender Gender
    {
        get;

        set;
    }
}

public enum Gender
{
    Male,
    Female
}

{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight C# %}

//ViewModel.cs

using System;
using System.Collections.ObjectModel;

public class ViewModel 
{
    private Object items = null;

    public Object Items
    {
        get
        {
            return items;
        }
        set
        {
            items = value;
        }
    }
    public ViewModel()
    {
        Items = new Model() { Name = "Johnson", Gender= Gender.Male, DOB = new DateTime(2000,01,25), };
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<Window x:Class="PropertyGrid_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:PropertyGrid_WPF"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d" WindowStartupLocation="CenterScreen"
        Title="MainWindow" Height="572" Width="800">
    <Window.DataContext>
        <local:ViewModel></local:ViewModel>
    </Window.DataContext>
    <Grid x:Name="LayoutRoot" Background="White" HorizontalAlignment="Stretch" VerticalAlignment="Stretch">
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


Here, the `DOB` and `Gender` properties not editable,

![DOB and Gender is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)

## Setting properties as readonly at runtime

We can makes the properties as readonly without using the attributes and can change the property readonly state at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html)  event with [AutoGeneratingPropertyGridItemEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html).[ReadOnly](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs~ReadOnly.html) property.

When `AutoGeneratingPropertyGridItemEventArgs.ReadOnly` property value sets as `true`, the property will be classified as read only, then the `PropertyGrid` will not allow the user to change the property values. The Default value of `AutoGeneratingPropertyGridItemEventArgs.ReadOnly` property is `false`.

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
        if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "DOB") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).ReadOnly = true;
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
                         EnableGrouping="True"
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

![DOB is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)

Here, the `DOB` property non-editable.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property `ReadOnly` support using `AutoGeneratingPropertyGridItem` event.