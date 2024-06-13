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

#### Adding Built-in Zooming to an Application

To add the built-in zooming:

1. Define the Gantt with initial values.
2. Set the UseOnDemandSchedule API value as _true_. If need set BaseCellMinLength and BaseCellMaxLength, the default value of these APIs are 20 and 40 respectively.
3. Use a slider or any control to provide the zoom factor dynamically. Bind the Gantt’s zoom factor to that control value.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

<Slider x:Name="ZoomSlider" Minimum="80" Maximum="600" Value="100" Width="150" ValueChanged="slider_ValueChanged"/>

 <syncfusion:GanttControl x:Name="Gantt"
                          ItemsSource="{Binding TaskCollection}" 
                          UseOnDemandSchedule="True"
                          ZoomFactor="{Binding ElementName=ZoomSlider, Path=Value}">
     <syncfusion:GanttControl.TaskAttributeMapping>
         <syncfusion:TaskAttributeMapping  TaskIdMapping="TaskId"
                                   TaskNameMapping="TaskName"
                                   StartDateMapping="StartDate"
                                   ChildMapping="Child"
                                   FinishDateMapping="FinishDate"
                                   DurationMapping="Duration"
                                   MileStoneMapping="IsMileStone"
                                   PredecessorMapping="Predecessor"
                                   ProgressMapping="Progress"/>
     </syncfusion:GanttControl.TaskAttributeMapping>

 </syncfusion:GanttControl>

{% endhighlight  %}
{% highlight c# %}

/// Defining the Slider
Slider slider = new Slider();
slider.Minimum = 1;
slider.Minimum = 600;

//Hooking the value changed event of the slider
slider.ValueChanged += slider_ValueChanged;

/// <summary>
/// Handles the ValueChanged event of the slider control.
/// </summary>
void slider_ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e)
{
    //Changing the value of zoom factor
    this.Gantt.ZoomFactor = (sender as Slider).Value;
}

//Initializing Gantt

 GanttControl Gantt = new GanttControl();
 ViewModel GanttControlViewModel =  new ViewModel();
 TaskAttributeMapping attributes = new TaskAttributeMapping();
 attributes.TaskIdMapping = "TaskId";
 attributes.TaskNameMapping = "TaskName";
 attributes.StartDateMapping = "StartDate";
 attributes.FinishDateMapping = "FinishDate";
 attributes.DurationMapping = "Duration";
 attributes.PredecessorMapping = "Predecessor";
 attributes.ProgressMapping = "Progress";
 attributes.ResourceInfoMapping = "Resources";
 attributes.ChildMapping = "Child"; 
 this.Gantt.DataContext = GanttControlViewModel;
 Gantt.TaskAttributeMapping = attributes;
 Gantt.ItemsSource = GanttControlViewModel.TaskCollection;

 public class GanttControlViewModel
 {
    /// <summary>
    /// Holds the task collections.
    /// </summary>
    private ObservableCollection<TaskDetails> _taskCollections;

    /// <summary>
    /// Initializes a new instance of the <see cref="ViewModel"/> class.
    /// </summary>
    public GanttControlViewModel()
    {
        _taskCollections = GetData();
    }
    
    /// <summary>
    /// Gets or sets the appointment item source.
    /// </summary>
    /// <value>The appointment item source.</value>
    public ObservableCollection<TaskDetails> TaskCollection
    {
        get
        {
            return _taskCollections;
        }
        set
        {
            _taskCollections = value;
        }
    }

    /// <summary>
    /// Gets the data.
    /// </summary>
    /// <returns></returns>
    public  ObservableCollection<TaskDetails> GetData()
    {
        var data = new ObservableCollection<TaskDetails>();
        data.Add(new TaskDetails() { TaskId = 1, TaskName = "Analysis/Planning", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 14), Progress = 40d });
        data[0].Child.Add((new TaskDetails() { TaskId = 2, TaskName = "Identify Components to be Localized", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 5), Progress = 20d }));
        data[0].Child.Add((new TaskDetails() { TaskId = 3, TaskName = "Ensure file localizability", StartDate = new DateTime(2011, 7, 6), FinishDate = new DateTime(2011, 7, 7), Progress = 20d }));
        data[0].Child.Add((new TaskDetails() { TaskId = 4, TaskName = "Identify tools", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));
        data[0].Child.Add((new TaskDetails() { TaskId = 5, TaskName = "Test tools", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 8, 1), Progress = 10d }));
        data[0].Child.Add((new TaskDetails() { TaskId = 6, TaskName = "Develop delivery timeline", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 8, 1), Progress = 10d }));
        data[0].Child.Add((new TaskDetails() { TaskId = 7, TaskName = "Analysis Complete", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 8, 10), Progress = 10d }));

        data.Add(new TaskDetails() { TaskId = 8, TaskName = "Production", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 14), Progress = 40d });
        data[1].Child.Add((new TaskDetails() { TaskId = 9, TaskName = "Software Components", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 5), Progress = 20d }));
        data[1].Child.Add((new TaskDetails() { TaskId = 10, TaskName = "Localization Component - User Interface", StartDate = new DateTime(2011, 7, 6), FinishDate = new DateTime(2011, 7, 7), Progress = 20d }));
        data[1].Child.Add((new TaskDetails() { TaskId = 11, TaskName = "User Assistance Components", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));
        data[1].Child.Add((new TaskDetails() { TaskId = 12, TaskName = "Software components complete", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 7, 19), Progress = 10d }));


        data.Add(new TaskDetails() { TaskId = 13, TaskName = "Quality Assurance", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 12), Progress = 40d, });
        data[2].Child.Add((new TaskDetails() { TaskId = 14, TaskName = "Review project information", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 15), Progress = 20d }));
        data[2].Child.Add((new TaskDetails() { TaskId = 15, TaskName = "Localization Component", StartDate = new DateTime(2011, 7, 6), FinishDate = new DateTime(2011, 7, 8), Progress = 20d }));
        data[2].Child.Add((new TaskDetails() { TaskId = 16, TaskName = "Localization Component", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));
        data[2].Child.Add((new TaskDetails() { TaskId = 17, TaskName = "Localization Component", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 7, 18), Progress = 10d }));

        data.Add(new TaskDetails() { TaskId = 18, TaskName = "Beta Testing", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 14), Progress = 40d });
        data[3].Child.Add((new TaskDetails() { TaskId = 19, TaskName = "Disseminate completed product", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 5), Progress = 20d }));
        data[3].Child.Add((new TaskDetails() { TaskId = 20, TaskName = "Obtain feedback", StartDate = new DateTime(2011, 7, 6), FinishDate = new DateTime(2011, 7, 7), Progress = 20d }));
        data[3].Child.Add((new TaskDetails() { TaskId = 21, TaskName = "Modify", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 19), Progress = 10d }));
        data[3].Child.Add((new TaskDetails() { TaskId = 22, TaskName = "Test", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 7, 19), Progress = 10d }));
        data[3].Child.Add((new TaskDetails() { TaskId = 23, TaskName = "Complete", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 19), Progress = 10d }));

        data.Add(new TaskDetails() { TaskId = 24, TaskName = "Post-Project Review", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 18), Progress = 40d, });
        data[4].Child.Add((new TaskDetails() { TaskId = 25, TaskName = "Finalize cost analysis", StartDate = new DateTime(2011, 7, 3), FinishDate = new DateTime(2011, 7, 5), Progress = 20d }));
        data[4].Child.Add((new TaskDetails() { TaskId = 26, TaskName = "Analyze performance", StartDate = new DateTime(2011, 7, 6), FinishDate = new DateTime(2011, 7, 7), Progress = 20d }));
        data[4].Child.Add((new TaskDetails() { TaskId = 27, TaskName = "Archive files", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));
        data[4].Child.Add((new TaskDetails() { TaskId = 28, TaskName = "Document lessons learned", StartDate = new DateTime(2011, 7, 14), FinishDate = new DateTime(2011, 7, 18), Progress = 10d }));
        data[4].Child.Add((new TaskDetails() { TaskId = 29, TaskName = "Distribute to team members", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));
        data[4].Child.Add((new TaskDetails() { TaskId = 30, TaskName = "Post-project review complete", StartDate = new DateTime(2011, 7, 10), FinishDate = new DateTime(2011, 7, 14), Progress = 10d }));

        data[0].Resources = new ObservableCollection<Resource>() { new Resource { ID = 1, Name = "John" }, new Resource { ID = 2, Name = "Neil" } };
        data[0].Child[3].Resources = new ObservableCollection<Resource>() { new Resource() { ID = 3, Name = "Peter" } };
        data[1].Resources = new ObservableCollection<Resource>() { new Resource() { ID = 4, Name = "David" } };

        data[0].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 2, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[0].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[0].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        data[1].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 9, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[1].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 10, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[1].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 7, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        data[2].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
        data[2].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
        data[2].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });

        data[3].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 18, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[3].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 18, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[3].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 19, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        data[4].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 25, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[4].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 28, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[4].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 30, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        data[4].Child[4].Predecessor.Add(new Predecessor() { GanttTaskIndex = 27, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        return data;

    }
}

{% endhighlight  %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

The following image shows Built-in Zooming in Gantt:

![Zooming_img1](Zooming_images/Zooming_img1.png)

#### Samples Link

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

#### Use Case Scenarios

When you like to view tasks that are scheduled on a month unit in the day/hours unit, you have to restart the application by changing the schedule type to day/hours unit. Zooming allows you to easily zoom in on the day/hours unit by providing the zoom factor without restarting the application.

#### Adding Custom Zooming to an Application

To add custom zooming:

1. Define the Gantt with initial values.
2. Set the UseOnDemandSchedule API value as true.
3. If needed, set BaseCellMinLength and BaseCellMaxLength. The default value of these APIs are 20 and 40 respectively.
4. Use any control to provide the zoom factor dynamically. Bind the Gantt’s zoom factor to that control value.
5. Handle the ZoomChanged event handler in code behind and change the schedule row information in that event handler as illustrated in the following code example:

{% capture codesnippet2 %}
{% tabs %}
{% highlight xaml %}

<ComboBox x:Name="ZoomBox" 
          Width="75" 
          ItemsSource="{Binding ZoomFactors}" 
          SelectedItem="{Binding ZoomFactor}"/>

 <syncfusion:GanttControl x:Name="Gantt"
                          ItemsSource="{Binding TaskCollection}" 
                          UseOnDemandSchedule="True"
                          ZoomFactor="{Binding ZoomFactor}"
                          ZoomChanged="Gantt_ZoomChanged">
     <syncfusion:GanttControl.TaskAttributeMapping>
         <syncfusion:TaskAttributeMapping  TaskIdMapping="TaskId"
                                   TaskNameMapping="TaskName"
                                   StartDateMapping="StartDate"
                                   ChildMapping="Child"
                                   FinishDateMapping="FinishDate"
                                   DurationMapping="Duration"
                                   MileStoneMapping="IsMileStone"
                                   PredecessorMapping="Predecessor"
                                   ProgressMapping="Progress"/>
     </syncfusion:GanttControl.TaskAttributeMapping>

 </syncfusion:GanttControl>

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
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

The following image shows Custom Zooming in Gantt:

![Zooming_img2](Zooming_images/Zooming_img2.png)

#### Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel.
4. Select Gantt.
5. Expand the Interactive Features item in the Sample Browser.
6. Choose the Custom Zooming to launch the sample.

## Tables for Zooming Properties and Events

#### Properties

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


#### Events

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