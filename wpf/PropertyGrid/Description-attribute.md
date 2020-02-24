---
layout: post
title: Description settings in WPF PropertyGrid control | Syncfusion
description: This section explains how a description of the property item has been added through attributes in the WPF PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Describe the Properties

We can display the description about the property using the  Description panel which is placed on the bottom of the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control. Description panel visibility can be managed by [DescriptionPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelVisibility.html) property . The default value of the `DescriptionPanelVisibility` is `Collapsed`. To display the Description panel, we should set `DescriptionPanelVisibility`  property value as `Visible` .

 We can change Description panel height by using the [DescriptionPanelHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelHeight.html)  property.

## Property Description using attributes

We can give a meaningful description about the properties by using the [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.descriptionattribute?view=netframework-4.8) attribute and [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute's [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.description?view=netframework-4.8) field. This description will be displayed in `PropertyGrid` Description panel while focusing the property or its value editor.


{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    [Display(Description = "Name of the employee")]
    public string Name { get; set; }
    public string ID { get; set; }
    [Description("Birth date of the employee")]
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

<syncfusion:PropertyGrid DescriptionPanelVisibility="Visible" 
                         DescriptionPanelHeight="50"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid1.DescriptionPanelVisibility = Visibility.Visible;
propertyGrid1.DescriptionPanelHeight = new GridLength(50);

{% endhighlight %} 
{% endtabs %} 

![Value specified in the Description field of the Display attribute is displayed in the Description Panel](Attribute-Images\Display-Description-Attribute.png)

Here, the description about the `Name` property  is displayed by using the `Display` attribute's `Description` field.

![Value specified in the Description attribute is displayed in the Description Panel](Attribute-Images\Description-Attribute.png)

Here, the description about the `DOB` property  is displayed by using the `Description` attribute.

N> If you use both the `Description` attribute and `Description` field of the `Display` attribute, the `Description` attribute will have higher priority.

 N> The Display attribute is contained in the [System.ComponentModel.Annotations.dll](https://www.nuget.org/packages/System.ComponentModel.Annotations/) assembly.

 Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Name-Description) to download the sample that showcases the property `Description` support using attributes.

## Change Property Description at runtime

We can set the property description without using the attributes and can change the property description at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html)  event with [AutoGeneratingPropertyGridItemEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html).[Description](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs~Description.html) property.

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
        //Descrition about the DOB properties is added.
        if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "DOB") {
            (parameter as AutoGeneratingPropertyGridItemEventArgs).Description ="Birth date of the Employee";
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
                         DescriptionPanelVisibility="Visible"
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

![Description of the Properties added by the Description property of the AutoGeneratingPropertyGridItem event](Attribute-Images\Description-AutoGeneratingPropertyGridItem.png)

Here, the `DOB` property description is added by the `AutoGeneratingPropertyGridItemEventArgs.Description` property of the `AutoGeneratingPropertyGridItem` event, not by any attributes.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property `Description` support using `AutoGeneratingPropertyGridItem` event.
