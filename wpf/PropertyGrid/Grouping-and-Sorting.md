---
layout: post
title: Grouping the Properties in WPF PropertyGrid control | Syncfusion
description: Learn about grouping the properties of selected object in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Grouping the Properties

We can combine the properties and create multiple groups according to our needs. You can group the property items based on `CategoryAttribute` or `Display Attribute`'s `GroupName` field of the property. By default, the grouped properties are displayed in normal mode. If you want to display the property in group mode, you can set the [EnableGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableGrouping.html) property to `true`. 

![Properties of PropertyGrid is in group mode](Sorting-Images/Grouping.png)

## Show or Hide the Group Button

The User can change the states of the properties from sorting state to grouping state by the `GroupButton`. You can show or hide the group button by using the [ButtonPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ButtonPanelVisibility.html) property. If you want to hide the `GroupButton`, set the `ButtonPanelVisibility` property as `Collapsed`. The Default value of the `ButtonPanelVisibility` property is `Visible`.

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="400"
                         ButtonPanelVisibility="Collapsed">
    <syncfusion:PropertyGrid.SelectedObject>
        <Button></Button>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>


{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid = new PropertyGrid();
propertyGrid.Width = 350;
propertyGrid.Height = 400;propertyGrid.SelectedObject = new Button();
propertyGrid1.ButtonPanelVisibility = Visibility.Collapsed;

{% endhighlight %}
{% endtabs %}

![PropertyGrid with and without Sort button panel](Sorting-Images/GroupButton_visibility.png)

## Grouping using Category Attributes

Properties in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) will be grouped based on the name specified in the [CategoryAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.categoryattribute?view=netframework-4.8). If the property item doesn't have any category name, that property will be grouped under `Misc` category. In following example, `Name` and `DOB` properties is grouped under `Misc` category and `ID` property is grouped under `Identity` category.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;

public class Model
{    
    [Category("Identity")]
    public string ID
    {
        get;

        set;
    }

    [Category()]
    public string Name
    {
        get;

        set;
    }
  
    public DateTime DOB
    {
        get;

        set;
    }
}
      
{% endhighlight %}
{% endtabs %} 


{% tabs %}
{% highlight C# %}

//ViewModel.cs

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
        Items = new Model() { Name = "John", DOB = new DateTime(2000, 01, 08), ID = "SF001" };
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="220" SelectedObject="{Binding Items}" 
                                 EnableGrouping="True">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight %} 
{% endtabs %} 

![Properties are grouped based on the value specified in the Category attribute](Grouping-and-sorting-Images\Category-Attribute.png)

## Grouping using Display Attribute’s GroupName field

Properties in the `PropertyGrid` will be grouped based on the value specified in the [GroupName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.groupname?view=netframework-4.8) field of [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) Attribute. If the property item doesn't have any Display Attribute’s GroupName field, that property will be grouped under `Misc` category. In following example, `Name` and `ID` properties is grouped under `Identity` category.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel.DataAnnotations;

public class Model
{    
    [Display(GroupName = "Identity")]
    public string ID
    {
        get;

        set;
    }

    [Display(GroupName = "Identity")]
    public string Name
    {
        get;

        set;
    }

    public DateTime DOB
    {
        get;

        set;
    }
}
      
{% endhighlight %}
{% endtabs %} 


{% tabs %}
{% highlight C# %}

//ViewModel.cs

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
        Items = new Model() { Name = "John", DOB = new DateTime(2000, 01, 08), ID = "SF001" };
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="220" SelectedObject="{Binding Items}" 
                                 EnableGrouping="True">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight %} 
{% endtabs %} 

![Properties are grouped based on the value specified in the GroupName field of the Display attribute](Grouping-and-sorting-Images\Display-GroupName-Attribute.png)


N> If you use both the `Category` attribute and `GroupName` field of the `Display` attribute, the `Category` attribute will have higher priority.

## Grouping the Properties at runtime

We can group the properties in the `PropertyGrid` without using the attributes at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event with [AutoGeneratingPropertyGridItemEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html).[Category](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs~Category.html) property. Based on the value of `Category` property, the properties are grouped.

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
       //Experience and DOB properties grouped under 'Additional Info' category.
       if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "Experience") {
           (parameter as AutoGeneratingPropertyGridItemEventArgs).Category ="Additional Info";
       }
       else if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "DOB")
       {
           (parameter as AutoGeneratingPropertyGridItemEventArgs).Category = "Additional Info";
       }
       //Name and ID properties grouped under 'Basic Info' category.
       else if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "Name") {
           (parameter as AutoGeneratingPropertyGridItemEventArgs).Category = "Basic Info";
       }
       else if ((parameter as AutoGeneratingPropertyGridItemEventArgs).DisplayName == "ID") {
           (parameter as AutoGeneratingPropertyGridItemEventArgs).Category = "Basic Info";
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

![Properties are grouped based on the value specified in the Category property of the AutoGeneratingPropertyGridItem event](Grouping-and-sorting-Images\AutoGeneratingPropertyGridItem.png)

Here, the `DOB` and `Experience` properties are grouped under the `Additional Info` category and `Name` and `ID` properties are grouped under the `Basic Info` category

## Expand or Collapse Category group

Category can be collapsed or expanded programmatically by using [CollapseCategory](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CollapseCategory.html) and [ExpandCategory](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ExpandCategory.html) methods in the `PropertyGrid`. These methods will accept category name as argument.

{% tabs %}
{% highlight C# %}

//Model.cs

using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    [Display(GroupName = "Contact details")]
    public int MobileNumber
    {
        get;

        set;
    }

    [Category("Identity")]
    public string Name
    {
        get;

        set;
    }

    [Display(GroupName = "Identity")]
    public string ID
    {
        get;

        set;
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight C# %}

//ViewModel.cs

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
        Items = new Model() { Name = "John", ID="SF001",Location = "America"  };
    }
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="230" SelectedObject="{Binding Items}" 
                                 EnableGrouping="True">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight C# %}

//Collapse the Identity category properties
this.propertyGrid1.CollapseCategory("Identity");

{% endhighlight %} 
{% endtabs %} 

![Itentity group has been collapsed](Grouping-and-sorting-Images\Collapse-Category.png)

{% tabs %}
{% highlight C# %}

//Expand the Identity category properties
this.propertyGrid1.ExpandCategory("Identity");

{% endhighlight %} 
{% endtabs %} 

![Itentity group has been expanded](Grouping-and-sorting-Images\Expand-Category.png)

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/PropertyGrid-AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property grouping support using `AutoGeneratingPropertyGridItem` event.
