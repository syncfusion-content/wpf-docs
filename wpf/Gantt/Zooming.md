---
layout: post
title: Zooming in WPF Gantt control | Syncfusion
description: Learn about Zooming support in Syncfusion Essential Studio WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Zooming in WPF Gantt

Zooming allows you to zoom in and zoom out of the schedule and chart of the Gantt control between year and minute time units. On zooming, the schedule’s time unit and schedule cell size will be dynamically changed based on the zoom factor. You can increase/decrease the width of the tasks in the chart based on the schedule’s time unit. Zooming can be categorized into two types: 

* Built-in zooming 
* Custom zooming

## Built-in Zooming


Built-in zooming allows you to zoom in and zoom out of the schedule rows. The built-in zoom options are handled by the Gantt control. The zoom operations take place dynamically based on the following zoom factors:

* Zoom-in: Zoom-in increases the cell size dynamically. When the cell size exceeds the specified range, it will split the schedule cells. When a cell cannot be split further, a new schedule row with the next time unit is added beneath the last row of the current schedule. The cell split-up and adding a new row inclusion is based on the zoom factor. 
* Zoom-out: Zoom-out decreases the cell size dynamically. When the cell size is within the specified range, it will merge the schedule cells. When the cells cannot be merged further, the last row of the current schedule is removed. Merging and removing a row is based on the zoom factor.

### Adding Built-in Zooming to an Application

To add the built-in zooming:

1. Define the Gantt with initial values.
2. Set the UseOnDemandSchedule API value as _true_. If need set BaseCellMinLength and BaseCellMaxLength, the default value of these APIs are 20 and 40 respectively.
3. Use a slider or any control to provide the zoom factor dynamically. Bind the Gantt’s zoom factor to that control value.

{% tabs %}
{% highlight xaml %}

<Slider Minimum="80" Maximum="600" Value="100" x:Name="ZoomSlider" Width="150"/>

<sync:GanttControl  x:Name="Gantt" 
                    ItemsSource="{Binding GanttItemSource}" 
                    UseOnDemandSchedule="True"
                    ZoomFactor="{Binding ElementName=ZoomSlider, Path=Value}"/>

{% endhighlight  %}
{% highlight c# %}

/// Defining the Slider
Slider slider = new Slider();
slider.Minimum = 1;
slider.Minimum = 600;

//Hooking the value changed event of the slider
slider.ValueChanged += slider_ValueChanged;

//Defining the Gantt
GanttControl Gantt = new GanttControl();
Gantt.ItemsSource = view.GanttItemSource;
Gantt.UseOnDemandSchedule = true;

/// <summary>
/// Handles the ValueChanged event of the slider control.
/// </summary>
void slider_ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e)
{
    //Changing the value of zoom factor
    this.Gantt.ZoomFactor = (sender as Slider).Value;
}

{% endhighlight  %}
{% endtabs %}

The following image shows Built-in Zooming in Gantt:



![Zooming_img1](Zooming_images/Zooming_img1.png)



### Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel.
4. Select Gantt.
5. Expand the Interactive Features item in the Sample Browser.
6. Choose the Built-in Zooming to launch the sample.



## Custom Zooming

In custom zooming, everything is handled at the application level. You can change the schedule row information and cell size dynamically by handling the provided event handler. While the zooming is handled at the application level, built-in zooming will not work. You cannot use built-in zooming and custom zooming together. 

### Use Case Scenarios

When you like to view tasks that are scheduled on a month unit in the day/hours unit, you have to restart the application by changing the schedule type to day/hours unit. Zooming allows you to easily zoom in on the day/hours unit by providing the zoom factor without restarting the application.

### Adding Custom Zooming to an Application

To add custom zooming:

1. Define the Gantt with initial values.
2. Set the UseOnDemandSchedule API value as true.
3. If needed, set BaseCellMinLength and BaseCellMaxLength. The default value of these APIs are 20 and 40 respectively.
4. Use any control to provide the zoom factor dynamically. Bind the Gantt’s zoom factor to that control value.
5. Handle the ZoomChanged event handler in code behind and change the schedule row information in that event handler as illustrated in the following code example:

{% tabs %}
{% highlight xaml %}

<ComboBox x:Name="ZoomBox" 
          Width="75" 
          ItemsSource="{Binding ZoomFactors}" 
          SelectedItem="{Binding ZoomFactor}"/>

<sync:GanttControl x:Name="Gantt" 
                   ItemsSource="{Binding GanttItemSource}" 
                   UseOnDemandSchedule="True"
                   ZoomFactor="{Binding ZoomFactor}"
                   ZoomChanged="Gantt_ZoomChanged"/>

{% endhighlight  %}
{% highlight c# %}

/// APIs in View Model.
private List<double> _zoomFactors  = new List<double> { 100d, 200d, 300d, 400d, 600d, 800d, 1000d };

/// <summary>
/// Gets or sets the zoom factors.
/// </summary>
/// <value>The zoom factors.</value>
public List<double> ZoomFactors
{
    get
    {
        return _zoomFactors;
    }
    set
    {
        _zoomFactors = value;
        this.OnPropertyChanged("ZoomFactors");
    }
}

private double _zoomFactor;

/// <summary>
/// Gets or sets the zoom factor.
/// </summary>
/// <value>The zoom factor.</value>
public double ZoomFactor
{
    get
    {
        return _zoomFactor;
    }
    set
    {
        _zoomFactor = value;
        this.OnPropertyChanged("ZoomFactor");
    }
}

/// Event Handler in code behind
/// <summary>
/// Handles the ZoomChanged event of the Gantt control.
/// </summary>
/// <param name="sender">The source of the event.</param>
/// <param name="args">The <see cref="Syncfusion.Windows.Controls.Gantt.ZoomChangedEventArgs"/> instance containing the event data.</param>
private void Gantt_ZoomChanged(object sender, ZoomChangedEventArgs args)
{
    if (args.ZoomFactor == 100)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Weeks },
            new GanttScheduleRowInfo{CellsPerUnit=1,TimeUnit = TimeUnit.Days, PixelsPerUnit= 20}
        };
    }
    else if (args.ZoomFactor == 200)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Days, CellTextFormat ="ddd d MMM" },
            new GanttScheduleRowInfo{CellsPerUnit=12,TimeUnit = TimeUnit.Hours, PixelsPerUnit= 4, CellTextFormat="hh tt"}
        };
    }
    else if (args.ZoomFactor == 300)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Days, CellTextFormat ="ddd d MMM"  },
            new GanttScheduleRowInfo{CellsPerUnit=6,TimeUnit = TimeUnit.Hours, PixelsPerUnit= 8, CellTextFormat="hh tt"}
        };
    }
    else if (args.ZoomFactor == 400)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Days, CellTextFormat ="ddd d MMM"  },
            new GanttScheduleRowInfo{CellsPerUnit=1,TimeUnit = TimeUnit.Hours, PixelsPerUnit= 69, CellTextFormat="hh tt"}
        };
    }
    else if (args.ZoomFactor == 600)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Hours, CellTextFormat="hh:mm tt" },
            new GanttScheduleRowInfo{CellsPerUnit=15,TimeUnit = TimeUnit.Minutes, PixelsPerUnit= 2}
        };
    }
    else if (args.ZoomFactor == 800)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Hours, CellTextFormat="hh:mm tt" },
            new GanttScheduleRowInfo{CellsPerUnit=5,TimeUnit = TimeUnit.Minutes, PixelsPerUnit= 4}
        };
    }
    else if (args.ZoomFactor == 1000)
    {
        args.ScheduleHeaderInfo = new List<GanttScheduleRowInfo> 
        {
            new GanttScheduleRowInfo{ CellsPerUnit=1, TimeUnit= TimeUnit.Hours, CellTextFormat="hh:mm tt" },
            new GanttScheduleRowInfo{CellsPerUnit=1,TimeUnit = TimeUnit.Minutes, PixelsPerUnit= 20}
        };
    }

    args.Handled = true;
}

{% endhighlight  %}
{% endtabs %}

The following image shows Custom Zooming in Gantt:



![Zooming_img2](Zooming_images/Zooming_img2.png)



### Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel.
4. Select Gantt.
5. Expand the Interactive Features item in the Sample Browser.
6. Choose the Custom Zooming to launch the sample.

## Tables for Zooming Properties and Events


### Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
UseOnDemandSchedule</td><td>
To get the expected performance you need to use dynamic schedule rendering. </td><td>
Dependency</td><td>
boolean</td></tr>
<tr>
<td>
BaseCellMaxLength</td><td>
Splits the schedule cells by comparing the cell size with the API value on zooming-in </td><td>
Dependency</td><td>
double</td></tr>
<tr>
<td>
BaseCellMinLength</td><td>
Merges schedule cells by comparing the cell size with the API value on zooming-out</td><td>
Dependency</td><td>
double</td></tr>
<tr>
<td>
ZoomFactor</td><td>
Zooming takes place based on the ZoomFactor. The ZoomFactor should be greater than zero.</td><td>
Dependency</td><td>
double</td></tr>
</table>


### Events

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th></tr>
<tr>
<td>
ZoomChanged</td><td>
Event triggers when the zoom factor is changed. This can be handled in application level.</td><td>
ZoomChangedEventArgs</td><td>
Simple event </td></tr>
</table>


