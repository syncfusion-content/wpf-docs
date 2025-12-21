---
layout: post
title: Dependency Relationship in WPF Gantt control | Syncfusion
description: Learn about Dependency Relationship support in Syncfusion WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Dependency Relationship in WPF Gantt

Dependency relationship is the relationship between two tasks. These relationship has been categorized into four types based on the start and finish date of the task. They are:

* FinishToStart 
* FinishToFinish
* StartToStart
* StartToFinish

Finish-to-start—You cannot start a task until the other task is completed.

![Dependency-Relationship_img1](Dependency-Relationship_images/Dependency-Relationship_img1.png)

Finish-to-finish—You cannot finish a task until the other task is completed.

![Dependency-Relationship_img2](Dependency-Relationship_images/Dependency-Relationship_img2.png)

Start-to-start—You cannot start a task until the other task is also started.

![Dependency-Relationship_img3](Dependency-Relationship_images/Dependency-Relationship_img3.png)

Start-to-Finish—You cannot finish a task until another the other task is started.

![Dependency-Relationship_img4](Dependency-Relationship_images/Dependency-Relationship_img4.png)

## Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
{{'[Predecessor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Predecessor.html)'| markdownify }}</td><td>
This enables you to set the relationship between the tasks.</td><td>
Object</td><td>
Object</td><td>
NA</td></tr>
<tr>
<td>
{{'[GanttTaskRelationship](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Predecessor.html#Syncfusion_Windows_Controls_Gantt_Predecessor_GanttTaskRelationship)'| markdownify }}</td><td>
This contains four relationships. They are:

* StartToStart
* StartToFinish
* FinishToFinish
* FinishToStart

You can assign this to the {{ '_TaskDetails_' | markdownify }} to set the relationship between tasks.</td><td>
Predecessor</td><td>
Enum</td><td>
NA</td></tr>
</table>


Specifying the Relationship between Tasks 

The following code illustrates how to add the Dependency Relationship between tasks:

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         ItemsSource="{Binding TaskCollection}">
    <syncfusion:GanttControl.TaskAttributeMapping>
        <syncfusion:TaskAttributeMapping TaskIdMapping="ID"
                                         TaskNameMapping="Name"
                                         StartDateMapping="StartDate"
                                         ChildMapping="ChildCollection"
                                         FinishDateMapping="EndDate"
                                         DurationMapping="Duration"
                                         ProgressMapping="Progress"
                                         PredecessorMapping="Predecessor"
                                         ResourceInfoMapping="Resource"/>
    </syncfusion:GanttControl.TaskAttributeMapping>
    <syncfusion:GanttControl.DataContext>
        <local:ViewModel/>
    </syncfusion:GanttControl.DataContext>
</syncfusion:GanttControl>

{% endhighlight  %}
{% highlight c# %}

this.ganttControl.ItemsSource = new ViewModel().TaskCollection;

// Task attribute mapping
TaskAttributeMapping taskAttributeMapping = new TaskAttributeMapping();
taskAttributeMapping.TaskIdMapping = "ID";
taskAttributeMapping.TaskNameMapping = "Name";
taskAttributeMapping.StartDateMapping = "StartDate";
taskAttributeMapping.ChildMapping = "ChildCollection";
taskAttributeMapping.FinishDateMapping = "EndDate";
taskAttributeMapping.DurationMapping = "Duration";
taskAttributeMapping.ProgressMapping = "Progress";
taskAttributeMapping.PredecessorMapping = "Predecessor";
taskAttributeMapping.ResourceInfoMapping = "Resource";
this.ganttControl.TaskAttributeMapping = taskAttributeMapping;

{% endhighlight  %}
{% highlight c# tabtitle="Task.cs" %}

public class Task : INotifyPropertyChanged
{
    /// <summary>
    /// Holds the start date and end date value.
    /// </summary>
    private DateTime startDate, endDate;

    /// <summary>
    /// Holds the duration value.
    /// </summary>
    private TimeSpan duration;

    /// <summary>
    /// Holds the progress value.
    /// </summary>
    private double progress;

    /// <summary>
    /// Holds the id value.
    /// </summary>
    private int id;

    /// <summary>
    /// Holds the name value.
    /// </summary>
    private string name;

    /// <summary>
    /// Holds the collection value.
    /// </summary>
    private ObservableCollection<Task> childCollection;

    /// <summary>
    /// Holds the resource value.
    /// </summary>
    private ObservableCollection<Resource> resource;

    /// <summary>
    /// Holds the predecessor value.
    /// </summary>
    private ObservableCollection<Predecessor> predecessor;

    public Task()
    {
        this.ChildCollection = new ObservableCollection<Task>();
        this.Predecessor = new ObservableCollection<Predecessor>();
        this.Resource = new ObservableCollection<Resource>();
    }

    /// <summary>
    /// Gets or sets the start date.
    /// </summary>
    public DateTime StartDate
    {
        get
        {
            return this.startDate;
        }
        set
        {
            this.startDate = value;
            OnPropertyChanged("StartDate");
        }
    }

    /// <summary>
    /// Gets or sets the finish date.
    /// </summary>
    public DateTime EndDate
    {
        get
        {
            return this.endDate;
        }
        set
        {
            this.endDate = value;
            OnPropertyChanged("EndDate");
        }
    }

    /// <summary>
    /// Gets or sets the duration value.
    /// </summary>
    public TimeSpan Duration
    {
        get
        {
            return this.duration;
        }
        set
        {
            this.duration = value;
            OnPropertyChanged("Duration");
        }
    }

    /// <summary>
    /// Gets or sets the ID value.
    /// </summary>
    public int ID
    {
        get
        {
            return this.id;
        }
        set
        {
            this.id = value;
            OnPropertyChanged("ID");
        }
    }

    /// <summary>
    /// Gets or sets the Name.
    /// </summary>
    public string Name
    {
        get
        {
            return this.name;
        }
        set
        {
            this.name = value;
            OnPropertyChanged("Name");
        }
    }

    /// <summary>
    /// Gets or sets the progress value.
    /// </summary>
    public double Progress
    {
        get
        {
            return this.progress;
        }
        set
        {
            this.progress = value;
            OnPropertyChanged("Progress");
        }
    }

    /// <summary>
    /// Gets or sets the child collection.
    /// </summary>
    public ObservableCollection<Task> ChildCollection
    {
        get
        {
            return this.childCollection;
        }
        set
        {
            this.childCollection = value;
            OnPropertyChanged("ChildCollection");
        }
    }

    /// <summary>
    /// Gets or sets the resource value.
    /// </summary>
    public ObservableCollection<Resource> Resource
    {
        get
        {
            return this.resource;
        }
        set
        {
            this.resource = value;
            OnPropertyChanged("Resource");
        }
    }

    /// <summary>
    /// Gets or sets the predecessor value.
    /// </summary>
    public ObservableCollection<Predecessor> Predecessor
    {
        get
        {
            return this.predecessor;
        }
        set
        {
            this.predecessor = value;
            OnPropertyChanged("Predecessor");
        }
    }

    /// <summary>
    /// Method for property changed.
    /// </summary>
    private void OnPropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
}

{% endhighlight  %}
{% highlight c# tabtitle="ViewModel.cs" %}
 
public class ViewModel
{
    /// <summary>
    /// Gets or sets the task collection.
    /// </summary>
    public ObservableCollection<Task> TaskCollection { get; set; }

    public ViewModel()
    {
        this.TaskCollection = this.GetDataSource();
    }

    /// <summary>
    /// Method to get the data source.
    /// </summary>
    private ObservableCollection<Task> GetDataSource()
    {
        var taskDetails = new ObservableCollection<Task>();
        taskDetails.Add(new Task() { ID = 1, Name = "Analysis/Planning", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 8, 14), Progress = 40d });
        taskDetails[0].ChildCollection.Add((new Task() { ID = 2, Name = "IDentify Components to be Localized", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 5), Progress = 20d }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 3, Name = "Ensure file localizability", StartDate = new DateTime(2011, 7, 6), EndDate = new DateTime(2011, 7, 7), Progress = 20d }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 4, Name = "IDentify tools", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 5, Name = "Test tools", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 8, 1), Progress = 10d }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 6, Name = "Develop delivery timeline", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 8, 1), Progress = 10d }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 7, Name = "Analysis Progress", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 8, 10), Progress = 10d }));

        taskDetails.Add(new Task() { ID = 8, Name = "Production", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 14), Progress = 40d });
        taskDetails[1].ChildCollection.Add((new Task() { ID = 9, Name = "Software Components", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 5), Progress = 20d, }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 10, Name = "Localization Component - User Interface", StartDate = new DateTime(2011, 7, 6), EndDate = new DateTime(2011, 7, 7), Progress = 20d }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 11, Name = "User Assistance Components", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 12, Name = "Software components Progress", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 7, 18), Progress = 10d }));

        taskDetails.Add(new Task() { ID = 13, Name = "Quality Assurance", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 12), Progress = 40d, });
        taskDetails[2].ChildCollection.Add((new Task() { ID = 14, Name = "Review project information", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 15), Progress = 20d }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 15, Name = "Localization Component", StartDate = new DateTime(2011, 7, 6), EndDate = new DateTime(2011, 7, 8), Progress = 20d }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 16, Name = "Localization Component", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 17, Name = "Localization Component", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 7, 18), Progress = 10d }));

        taskDetails.Add(new Task() { ID = 18, Name = "Beta Testing", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 14), Progress = 40d });
        taskDetails[3].ChildCollection.Add((new Task() { ID = 19, Name = "Disseminate Progressd product", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 5), Progress = 20d }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 20, Name = "Obtain feedback", StartDate = new DateTime(2011, 7, 6), EndDate = new DateTime(2011, 7, 7), Progress = 20d }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 21, Name = "Modify", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 19), Progress = 10d }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 22, Name = "Test", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 7, 19), Progress = 10d }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 23, Name = "Progress", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 19), Progress = 10d }));

        taskDetails.Add(new Task() { ID = 24, Name = "Post-Project Review", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 14), Progress = 40d, });
        taskDetails[4].ChildCollection.Add((new Task() { ID = 25, Name = "Finalize cost analysis", StartDate = new DateTime(2011, 7, 3), EndDate = new DateTime(2011, 7, 5), Progress = 20d }));
        taskDetails[4].ChildCollection.Add((new Task() { ID = 26, Name = "Analyze performance", StartDate = new DateTime(2011, 7, 6), EndDate = new DateTime(2011, 7, 7), Progress = 20d }));
        taskDetails[4].ChildCollection.Add((new Task() { ID = 27, Name = "Archive files", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));
        taskDetails[4].ChildCollection.Add((new Task() { ID = 28, Name = "Document lessons learned", StartDate = new DateTime(2011, 7, 14), EndDate = new DateTime(2011, 7, 18), Progress = 10d }));
        taskDetails[4].ChildCollection.Add((new Task() { ID = 29, Name = "Distribute to team members", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));
        taskDetails[4].ChildCollection.Add((new Task() { ID = 30, Name = "Post-project review Progress", StartDate = new DateTime(2011, 7, 10), EndDate = new DateTime(2011, 7, 14), Progress = 10d }));

        taskDetails[1].Resource.Add(new Resource() { ID = 1, Name = "Localizer" });
        taskDetails[2].Resource.Add(new Resource() { ID = 2, Name = "Technical Reviewer" });
        taskDetails[3].Resource.Add(new Resource() { ID = 3, Name = "Project Manager" });

        taskDetails[0].ChildCollection[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 2, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[0].ChildCollection[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[0].ChildCollection[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        taskDetails[1].ChildCollection[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 9, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[1].ChildCollection[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 10, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[1].ChildCollection[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 7, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        taskDetails[2].ChildCollection[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
        taskDetails[2].ChildCollection[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
        taskDetails[2].ChildCollection[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 12, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });

        taskDetails[3].ChildCollection[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 18, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[3].ChildCollection[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 18, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[3].ChildCollection[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 19, GanttTaskRelationship = GanttTaskRelationship.StartToStart });

        taskDetails[4].ChildCollection[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 25, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[4].ChildCollection[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 28, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[4].ChildCollection[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 30, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        taskDetails[4].ChildCollection[4].Predecessor.Add(new Predecessor() { GanttTaskIndex = 27, GanttTaskRelationship = GanttTaskRelationship.StartToStart });
        return taskDetails;
    }
}

{% endhighlight  %}
{% endtabs %}

The following image shows the Dependency Relationship:

![gantt-control-dependency-relationship](Dependency-Relationship_images/gantt-control-dependency-relationship.png)

#### Samples Link

To view samples: 

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under User Interface Edition panel .
4. Select Gantt.
5. Expand the Connectors Features item in the Sample Browser.
6. Choose the Predecessor sample to launch. 

## Dynamic Predecessors and Resources

Essential Gantt provides support for dynamic editing of predecessors in the Grid area. Using this feature, you can dynamically add the predecessor on-demand basis to Gantt. You can add/remove the predecessor in the corresponding cell in the GanttGrid.

You can add/remove/update the predecessors and resources of tasks at run time. Initially, the Gantt is loaded with the Predecessor/Resource information in the underlying collection and you can update this information if required.

You can edit the predecessor information from the [GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttGrid.html). For resource, you can edit in the underlying source, Gantt will listen to the change in the underlying source and reflect it in both [GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttGrid.html) and [GanttChart](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttChart.html).

## Predecessor Validation

There are two predecessor validation modes in Gantt Control. 

* Auto - Successor nodes will adjust its position based on its predecessor nodes automatically.
* Manual - Successor nodes need to adjust manually with respect to predecessor.

#### Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
{{'[ValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_ValidationMode)'| markdownify }}</td><td>
This contains two modes.<ul><li>
Manual,</li><li>
Auto.</li></ul>
Default value is Manual.</td><td>
DependencyProperty</td><td>
Enum</td><td>
NA</td></tr>
</table>

The following image shows the Predecessor in Manual Mode:

![gantt-control-predecessors-in-manual-mode](Dependency-Relationship_images/gantt-control-predecessors-in-manual-mode.png)

The following image shows the Predecessor in Auto Mode:

![gantt-control-predecessors-in-auto-mode](Dependency-Relationship_images/gantt-control-predecessors-in-auto-mode.png)

#### Editing Predecessors

While creating a new predecessor in Grid, it should be in the following format:

{% highlight c# %}

	{Task ID}{GanttTaskRelationship} 
	
{% endhighlight  %}

Here the {[GanttTaskRelationship](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttTaskRelationship.html)} is any one of the following:

* SS
* FS
* SF
* FF

The following are what you should use for different relationships:

* Use “SS” to define the “StartToStart” relationship
* Use “FS” to define the “FinishToStart” relationship
* Use “SF” to define the “StartToFinish” relationship
* Use “FF” to define the “FinishToFinish” relationship

If any other data is added, the current editing relationship will be deleted and only the valid predecessors remain for the task.

#### Editing Resources

As of now, resources cannot be edited in Grid. You can update the resource collection in the underlying source whenever you need. Gantt will listen to the changes in the collection and will update the [GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttGrid.html) and [GanttChart](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttChart.html) accordingly.

#### Use Case Scenario

This helps to change the dependency relationships and resources of the tasks dynamically.

![gantt-control-predecessor-editing](Dependency-Relationship_images/gantt-control-predecessor-editing.png)

Adding Dynamic Predecessors and Resources to an Application

The dynamic editing of predecessor will be automatically included in the Gantt by default. There is no need to provide any additional data for that. The following codes illustrate this:

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         ItemsSource="{Binding TaskCollection}">
    <syncfusion:GanttControl.TaskAttributeMapping>
        <syncfusion:TaskAttributeMapping TaskIdMapping="ID"
                                         TaskNameMapping="Name"
                                         StartDateMapping="StartDate"
                                         ChildMapping="ChildCollection"
                                         FinishDateMapping="EndDate"
                                         DurationMapping="Duration"
                                         ProgressMapping="Progress"
                                         PredecessorMapping="Predecessor"
                                         ResourceInfoMapping="Resource"/>
    </syncfusion:GanttControl.TaskAttributeMapping>
    <syncfusion:GanttControl.DataContext>
        <local:ViewModel/>
    </syncfusion:GanttControl.DataContext>
</syncfusion:GanttControl>
 
{% endhighlight  %}
{% highlight c# %}

ViewModel viewModel = new ViewModel();
this.ganttControl.DataContext = viewModel;
this.ganttControl.ItemsSource = viewModel.TaskCollection;

// Task attribute mapping
TaskAttributeMapping taskAttributeMapping = new TaskAttributeMapping();
taskAttributeMapping.TaskIdMapping = "ID";
taskAttributeMapping.TaskNameMapping = "Name";
taskAttributeMapping.StartDateMapping = "StartDate";
taskAttributeMapping.ChildMapping = "ChildCollection";
taskAttributeMapping.FinishDateMapping = "EndDate";
taskAttributeMapping.DurationMapping = "Duration";
taskAttributeMapping.ProgressMapping = "Progress";
taskAttributeMapping.PredecessorMapping = "Predecessor";
taskAttributeMapping.ResourceInfoMapping = "Resource";
this.ganttControl.TaskAttributeMapping = taskAttributeMapping;

//// The following code will illustrate how to dynamically add resource and predecessor in the underlying collection:
// To Add the Dynamic Predecessors
viewModel.TaskCollection[2].Predecessor.Add(new Predecessor()
{
    GanttTaskIndex = 3,
    GanttTaskRelationship = GanttTaskRelationship.StartToFinish
});

// To Add the Dynamic Resources   
viewModel.TaskCollection[2].Resource.Add(new Resource { ID = 3, Name = "Resource3" });

{% endhighlight %}
{% endtabs %}

## Events

You can get the node and predecessor relationship details in [GanttControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html) by using the [PredecessorChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_PredecessorChanging) and [PredecessorChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_PredecessorChanged) events. 

### PredecessorChanging event 

This event is raised when a predecessor relationship is about to be added, updated, or removed. The [PredecessorChangingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangingEventArgs.html) provides the following properties:

* [CurrentNode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangingEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangingEventArgs_CurrentNode) - Gets the node that is about to undergo a dependency change.
* [DependencyNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangingEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangingEventArgs_DependencyNodes) - Gets the list of all nodes currently linked as dependencies to the task.
* [PredecessorChangeInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangingEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangingEventArgs_PredecessorChangeInfo) - Gets the details of the pending predecessor change, including old and new values.
    * [OldValues](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangeInfo.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangeInfo_OldValues) - Gets the previous value of the predecessor relationship before the change occurs.
    * [NewValues](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangeInfo.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangeInfo_NewValues) - Gets the new value of the predecessor relationship after the change occurred.

{% tabs %}
{% highlight XAML hl_lines="2" %}

<syncfusion:GanttControl x:Name="ganttControl" 
                         PredecessorChanging="OnGanttPredecessorChanging">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight C# hl_lines="1 5 6 7" %}

this.ganttControl.PredecessorChanging += this.OnGanttPredecessorChanging;

private void OnGanttPredecessorChanging(object sender, PredecessorChangingEventArgs e)
{
    var currentNode = e.CurrentNode;
    var dependencyNodes = e.DependencyNodes;
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### PredecessorChanged event

This event is raised after a predecessor relationship has been added, updated, or removed. The [PredecessorChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangedEventArgs.html) provides the following properties:

* [CurrentNode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangedEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangedEventArgs_CurrentNode) - Gets the details of the current node involved in the dependency relationship.
* [DependencyNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangedEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangedEventArgs_DependencyNodes) - Gets the list of all nodes that are linked as dependencies to the current task.
* [PredecessorChangeInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangedEventArgs.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangedEventArgs_PredecessorChangeInfo) - Gets the details of the predecessor change, including old and new values.
    * [OldValues](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangeInfo.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangeInfo_OldValues) - Gets the previous value of the predecessor relationship before the change occurs.
    * [NewValues](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.PredecessorChangeInfo.html#Syncfusion_Windows_Controls_Gantt_PredecessorChangeInfo_NewValues) - Gets the new value of the predecessor relationship after the change occurred.

{% tabs %}
{% highlight XAML hl_lines="2" %}

<syncfusion:GanttControl x:Name="ganttControl" 
                         PredecessorChanged="OnGanttPredecessorChanged">
</syncfusion:GanttControl>

{% endhighlight %}
{% highlight C# hl_lines="1 5 6" %}

this.ganttControl.PredecessorChanged += this.OnGanttPredecessorChanged;

private void OnGanttPredecessorChanged(object sender, PredecessorChangedEventArgs e)
{
    var currentNode = e.CurrentNode;
    var dependencyNodes = e.DependencyNodes;
}

{% endhighlight %}
{% endtabs %}