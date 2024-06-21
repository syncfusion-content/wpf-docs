---
layout: post
title: Highlighting Tasks in WPF Gantt control | Syncfusion
description: Learn about Highlighting Tasks support in Syncfusion Essential Studio WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Highlighting Tasks in WPF Gantt

Highlighting tasks allows you to highlight a specific set of tasks in the Gantt chart region. This feature will get the set of tasks as input and highlight those tasks with the specified color in the Gantt chart region. It will accept a linear set of tasks of type IList as input. You can also specify the highlighting brush through the provided API.

## Use Case Scenario

* When you like to view some specific set of tasks with a different color, you can easily achieve that by providing that set of tasks as input.
* This feature also helps the user to highlight tasks that are in a critical path of a project.

## Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
HighlightedItems</td><td>
The items that are passed through this API will be highlighted in Gantt chart region. The items should be in linear form. </td><td>
Dependency</td><td>
IList</td></tr>
<tr>
<td>
HighlightItemBrush</td><td>
Specifies the color in which items should be highlight</td><td>
Dependency</td><td>
Brush</td></tr>
</table>


## Adding Highlighting Tasks to an Application

To highlight a set of tasks in Gantt chart region:

1. Define the Gantt with initial setup.
1. Bind the tasks that need to be highlighted with Gantt’s HighlightedItems API.
2. If required, change the value of the Gantt’s HighlightItemBrush API to change the item highlight color. The default color is red.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

 <syncfusion:GanttControl x:Name="ganttControl"
                          HighlightItemBrush="{Binding Path=Brush, ElementName=HighlightBrush, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged"
                          HighlightedItems="{Binding HighlightTaskItems, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"
                          ItemsSource="{Binding TaskCollections}">
     <syncfusion:GanttControl.TaskAttributeMapping>
        <syncfusion:TaskAttributeMapping TaskIdMapping="ID"
                                         TaskNameMapping="Name"
                                         StartDateMapping="StartDate"
                                         ChildMapping="ChildCollection"
                                         FinishDateMapping="EndDate"
                                         DurationMapping="Duration"
                                         ProgressMapping="Progress"
                                         PredecessorMapping="Predecessor"   
                                         ResourceInfoMapping="Resource"
                                         CostMapping="Cost"
                                         BaselineCostMapping="BaselineCost"
                                         BaselineFinishMapping="BaselineEnd"
                                         BaselineStartMapping="BaselineStart"/>
     </syncfusion:GanttControl.TaskAttributeMapping>
     <syncfusion:GanttControl.DataContext>
        <local:ViewModel/>
    </syncfusion:GanttControl.DataContext>
 </syncfusion:GanttControl>

{% endhighlight %}

{% highlight c# %}

this.ganttControl.ItemsSource = new ViewModel().TaskCollections;

/// Task attribute mapping
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

 public class HighlightingTasksModel : NotificationObject
 {
    /// <summary>
    /// Holds the id value.
    /// </summary>
    private int id;

    /// <summary>
    /// Holds the name value.
    /// </summary>
    private string name;

    /// <summary>
    /// Holds the start date value.
    /// </summary>
    private DateTime stDate;

    /// <summary>
    /// Holds the end date value.
    /// </summary>
    private DateTime endDate;

    /// <summary>
    /// Holds the duration value.
    /// </summary>
    private TimeSpan duration;

    /// <summary>
    /// Holds the resource value.
    /// </summary>
    private ObservableCollection<Resource> resource;

    /// <summary>
    /// Holds the complete value.
    /// </summary>
    private double complete;

    /// <summary>
    /// Holds the child task value.
    /// </summary>
    private ObservableCollection<HighlightingTasksModel> childTask;

    /// <summary>
    /// Holds the predecessor value.
    /// </summary>
    private ObservableCollection<Predecessor> predecessor;

    /// <summary>
    /// Holds the cost value.
    /// </summary>
    private Double cost;

    /// <summary>
    /// Holds the baseline start value.
    /// </summary>
    private DateTime baselineStart;

    /// <summary>
    /// Holds the baseline end value.
    /// </summary>
    private DateTime baselineEnd;

    /// <summary>
    /// Holds the baseline cost value.
    /// </summary>
    private Double baselineCost;

     public HighlightingTasksModel()
     {
         this.ChildTask = new ObservableCollection<HighlightingTasksModel>();
         this.Predecessor = new ObservableCollection<Predecessor>();
         this.Resource = new ObservableCollection<Resource>();
     }

     /// <summary>
     /// Gets or sets the complete.
     /// </summary>
     /// <value>
     /// The complete.
     /// </value>
     public double Complete
     {
         get
         {
             return Math.Round(complete, 2);
         }
         set
         {
             if (value <= 100)
             {
                 if (this.childTask != null && this.childTask.Count >= 1)
                 {
                     var sum = 0d;
                     this.complete = ((this.childTask.Aggregate(sum, (cur, task) => cur + task.Complete)) / this.childTask.Count);
                 }
                 else
                     this.complete = value;
                 this.RaisePropertyChanged("Complete");
             }
         }
     }

     /// <summary>
     /// Gets or sets the resource.
     /// </summary>
     /// <value>
     /// The resource.
     /// </value>
     public ObservableCollection<Resource> Resource
     {
         get
         {
             return this.resource;
         }
         set
         {
             this.resource = value;
             this.RaisePropertyChanged("Resource");
         }
     }


     /// <summary>
     /// Gets or sets the duration.
     /// </summary>
     /// <value>
     /// The duration.
     /// </value>
     public TimeSpan Duration
     {
         get
         {
             if (this.childTask != null && this.childTask.Count >= 1)
             {
                 var sum = new TimeSpan(0, 0, 0, 0);
                 sum = this.childTask.Aggregate(sum, (current, task) => current + task.Duration);
                 return sum;
             }

             /// Finish date is having 8 working hours, the dead line will include that too. Hence one day is added in calcuation to get the exact duration.                 

             this.duration = endDate.Subtract(stDate);
             return this.duration;
         }

         set
         {
             if (this.childTask != null && this.childTask.Count >= 1)
             {
                 var sum = new TimeSpan(0, 0, 0, 0);
                 sum = this.childTask.Aggregate(sum, (current, task) => current + task.Duration);
                 this.duration = sum;
                 return;
             }

             this.duration = value;

             /// When calculating finish date from duration  we need to remove the extra date that we have added in duration to make the it fill the finish date too.
             /// End date is beeing calcuated here to make the change in endate based on duration. Duration is interlinked with start and end date, so will affect both based on the change.
             EndDate = stDate.AddDays(Double.Parse((duration.TotalDays).ToString()));

         }
     }

     /// <summary>
     /// Gets or sets the end date.
     /// </summary>
     /// <value>
     /// The end date.
     /// </value>
     public DateTime EndDate
     {
         get
         {
             return endDate;
         }
         set
         {
             if (this.childTask != null && this.childTask.Count >= 1)
             {
                 /// If this task is a parent task, then it should have the maximum end time. Hence comparing the date with maximum date of its children.

                 if (value >= this.childTask.Max(s => s.EndDate) && this.endDate != value)
                     this.endDate = value;
             }
             else
                 endDate = value;
             this.RaisePropertyChanged("EndDate");
             /// Duration changed is invoked to notify the chagne in duration based on the new end date.
             this.RaisePropertyChanged("Duration");
         }
     }

     /// <summary>
     /// Gets or sets the start date.
     /// </summary>
     /// <value>
     /// The start date.
     /// </value>
     public DateTime StDate
     {
         get
         {
             return this.stDate;
         }
         set
         {
             /// If this task is a parent task, then it should have the minimum start time. Hence comparing the date with minimum date of its children.

             if (this.childTask != null && this.childTask.Count >= 1)
             {
                 if (value <= this.childTask.Min(s => s.stDate) && this.stDate != value)
                     this.stDate = value;
             }
             else
                 this.stDate = value;
             this.RaisePropertyChanged("StDate");

             /// Duration chagned is invoked to notify the chagne in duration based on the new start date.
             this.RaisePropertyChanged("Duration");
         }
     }

     /// <summary>
     /// Gets or sets the name.
     /// </summary>
     /// <value>
     /// The name.
     /// </value>
     public string Name
     {
         get
         {
             return this.name;
         }
         set
         {
             this.name = value;
             this.RaisePropertyChanged("Name");
         }
     }

     /// <summary>
     /// Gets or sets the id.
     /// </summary>
     /// <value>
     /// The id.
     /// </value>
     public int Id
     {
         get
         {
             return this.id;
         }
         set
         {
             this.id = value;
             this.RaisePropertyChanged("Id");
         }
     }

     /// <summary>
     /// Gets or sets the predecessor.
     /// </summary>
     /// <value>
     /// The predecessor.
     /// </value>
     public ObservableCollection<Predecessor> Predecessor
     {
         get
         {
             return this.predecessor;
         }
         set
         {
             this.predecessor = value;
             this.RaisePropertyChanged("Predecessor");
         }
     }
     /// <summary>
     /// Gets or sets the cost.
     /// </summary>
     /// <value>
     /// The cost.
     /// </value>
     public Double Cost
     {
         get
         {
             return this.cost;
         }
         set
         {
             if (this.cost != value)
             {
                 if (this.childTask != null && this.childTask.Count >= 1)
                 {
                     var sum = 0d;
                     this.cost = this.childTask.Aggregate(sum, (cur, task) => cur + task.Cost);
                 }
                 else
                     this.cost = value;
                 this.RaisePropertyChanged("Cost");
             }

         }
     }

     /// <summary>
     /// Gets or sets the Baseline start.
     /// </summary>
     /// <value>
     /// The Baseline start.
     /// </value>
     public DateTime BaselineStart
     {
         get
         {
             return this.baselineStart;
         }
         set
         {
             if (this.baselineStart != value)
             {
                 if (this.childTask != null && this.childTask.Count >= 1)
                 {
                     this.baselineStart = this.childTask.Min(s => s.baselineStart);
                 }
                 else
                     this.baselineStart = value;
                 this.RaisePropertyChanged("BaselineStart");
             }
         }
     }

     /// <summary>
     /// Gets or sets the Baseline end.
     /// </summary>
     /// <value>
     /// The Baseline end.
     /// </value>
     public DateTime BaselineEnd
     {
         get
         {
             return this.baselineEnd;
         }
         set
         {
             if (this.baselineEnd != value)
             {
                 if (this.childTask != null && this.childTask.Count >= 1)
                 {
                     this.baselineEnd = childTask.Max(s => s.baselineEnd);
                 }
                 else
                     this.baselineEnd = value;
                 RaisePropertyChanged("BaselineEnd");
             }
         }
     }

     /// <summary>
     /// Gets or sets the baseline cost.
     /// </summary>
     /// <value>
     /// The baseline cost.
     /// </value>
     public Double BaselineCost
     {
         get
         {
             return this.baselineCost;
         }
         set
         {
             if (BaselineCost != value)
             {
                 if (this.childTask != null && this.childTask.Count >= 1)
                 {
                     var sum = 0d;
                     this.baselineCost = this.childTask.Aggregate(sum, (current, task) => current + task.baselineCost);
                 }
                 else
                     this.baselineCost = value;
                 this.RaisePropertyChanged("BaselineCost");
             }

         }
     }

     #region ChildTask Collection

     public ObservableCollection<HighlightingTasksModel> ChildTask
     {
         get
         {
             if (childTask == null)
             {
                 childTask = new ObservableCollection<HighlightingTasksModel>();
                 /// Collection changed of child tasks are hooked to listen and refresh the parent node based on the changes made in Child.
                 childTask.CollectionChanged += ChildNodesCollectionChanged;
             }
             return childTask;
         }
         set
         {
             childTask = value;
             ///Collection changed of child tasks are hooked to listen and refresh the parent node based on the changes made in Child.

             childTask.CollectionChanged += ChildNodesCollectionChanged;

             if (value.Count > 0)
             {
                 childTask.ToList().ForEach(n =>
                 {
                     /// To listen the changes occuring in child task.
                     n.PropertyChanged += ChildNodePropertyChanged;

                 });
                 UpdateData();
             }
             RaisePropertyChanged("ChildTask");
         }
     }
     /// <summary>
     /// The following does the calculations to update the Parent Task, when child collection property changes.
     /// </summary>
     /// <param name="sender">The source</param>
     /// <param name="e">Property changed event args</param>
     void ChildNodePropertyChanged(object sender, PropertyChangedEventArgs e)
     {
         if (e.PropertyName != null)
             if (e.PropertyName != null)
                 if (e.PropertyName == "StDate" || e.PropertyName == "EndDate" || e.PropertyName == "Cost" || e.PropertyName == "BaselineStart" ||
                     e.PropertyName == "BaselineEnd" || e.PropertyName == "BaselineCost" || e.PropertyName == "Complete")
                 {
                     UpdateData();
                 }
     }
     /// <summary>
     /// Updates the data.
     /// </summary>
     private void UpdateData()
     {
         /// Updating the Required Data based on the chagne occur in the date of child task
         if (childTask == null || childTask.Count == 0)
         {
             return;
         }

         StDate = childTask.Select(c => c.StDate).Min();
         EndDate = childTask.Select(c => c.EndDate).Max();
         BaselineStart = childTask.Select(c => c.BaselineStart).Min();
         BaselineEnd = childTask.Select(c => c.BaselineEnd).Max();
         Cost = childTask.Aggregate(0d, (cur, task) => cur + task.Cost);
         BaselineCost = childTask.Aggregate(0d, (cur, task) => cur + task.BaselineCost);
         Complete = ((childTask.Aggregate(0d, (cur, task) => cur + task.Complete)) / childTask.Count);
     }

     /// <summary>
     /// handles the child nodes collection changed.
     /// </summary>
     /// <param name="sender">The sender.</param>
     /// <param name="e">The <see cref="System.Collections.Specialized.NotifyCollectionChangedEventArgs"/> instance containing the event data.</param>
     public void ChildNodesCollectionChanged(object sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
     {
         if (e.Action == NotifyCollectionChangedAction.Add)
         {
             foreach (HighlightingTasksModel node in e.NewItems)
             {
                 node.PropertyChanged += ChildNodePropertyChanged;
             }
         }
         else
         {
             foreach (HighlightingTasksModel node in e.OldItems)
                 node.PropertyChanged -= ChildNodePropertyChanged;
         }
         UpdateData();
     }

     #endregion
 }

 public class TaskRepository : NotificationObject
 {
    /// <summary>
    /// Holds the task collections.
    /// </summary>
    private ObservableCollection<HighlightingTasksModel> _taskCollections;

     /// <summary>
     /// Initializes a new instance of the <see cref="TaskRepository"/> class.
     /// </summary>
     public TaskRepository()
     {
         this._taskCollections = GetData();
     }

     /// <summary>
     /// Gets or sets the appointment item source.
     /// </summary>
     /// <value>The appointment item source.</value>
     public ObservableCollection<HighlightingTasksModel> TaskCollections
     {
         get
         {
             return this._taskCollections;
         }
         set
         {
             this._taskCollections = value;
         }
     }

     /// <summary>
     /// Gets the data.
     /// </summary>
     /// <returns>The task details</returns>
     public ObservableCollection<HighlightingTasksModel> GetData()
     {
         var taskDetails = new ObservableCollection<HighlightingTasksModel>();

         // Collection to Strore the Required Resources.
         ObservableCollection<Resource> ResidentialConstructionResources = new ObservableCollection<Resource>();
         ResidentialConstructionResources = GetResources();

         // Adding Tasks

         taskDetails.Add(new HighlightingTasksModel() { Id = 1, Name = "Residential Construction (2500 sq.ft)", StDate = new DateTime(2012, 3, 1), EndDate = new DateTime(2012, 3, 15), Complete = 0d, Cost = 500, BaselineCost = 833d, BaselineStart = new DateTime(2012, 2, 1), BaselineEnd = new DateTime(2012, 2, 17) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 2, Name = "General Considerations", StDate = new DateTime(2012, 7, 3), EndDate = new DateTime(2012, 7, 14), Complete = 0d, Cost = 89, BaselineCost = 833d, BaselineStart = DateTime.Today, BaselineEnd = DateTime.Today });

         taskDetails[0].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 3, Name = "Finalize and Approve Plans", StDate = new DateTime(2012, 3, 1), EndDate = new DateTime(2012, 3, 15), Complete = 0d, Cost = 500, BaselineCost = 833d, BaselineStart = new DateTime(2012, 2, 1), BaselineEnd = new DateTime(2012, 2, 17) });
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 4, Name = "Review and Finalize Site Plans", StDate = new DateTime(2012, 3, 1), EndDate = new DateTime(2012, 3, 20), Complete = 0d, Cost = 500, BaselineCost = 833d, BaselineStart = new DateTime(2012, 2, 1), BaselineEnd = new DateTime(2012, 2, 17) });
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 5, Name = "Sign contract and Proceed", StDate = new DateTime(2012, 3, 20), EndDate = new DateTime(2012, 3, 22), Complete = 0d, Cost = 500, BaselineCost = 833d, BaselineStart = new DateTime(2012, 2, 1), BaselineEnd = new DateTime(2012, 2, 17) });

         taskDetails[0].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 6, Name = "Contracts and Agreements", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 20d, BaselineCost = 14 });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask.Add((new HighlightingTasksModel() { Id = 7, Name = "Lot Sale Agreement", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 20d, BaselineCost = 14 }));
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask.Add((new HighlightingTasksModel() { Id = 8, Name = "Construction Agreement", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 33d, BaselineCost = 12 }));
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask.Add((new HighlightingTasksModel() { Id = 9, Name = "Contract Specifications", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 30d, BaselineCost = 50 }));
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask.Add((new HighlightingTasksModel() { Id = 10, Name = "Contract Site Plan", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 360d, BaselineCost = 100 }));
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask.Add((new HighlightingTasksModel() { Id = 11, Name = "Financing", StDate = new DateTime(2012, 3, 22), EndDate = new DateTime(2012, 3, 22), Complete = 0d, BaselineStart = new DateTime(2012, 3, 12), BaselineEnd = new DateTime(2012, 3, 12), Cost = 39d, BaselineCost = 16 }));

         taskDetails[0].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 12, Name = "Apply Permits", StDate = new DateTime(2012, 3, 23), EndDate = new DateTime(2012, 3, 24), Complete = 0d, BaselineStart = new DateTime(2012, 3, 2), BaselineEnd = new DateTime(2012, 3, 5), Cost = 53d, BaselineCost = 65 });
         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask.Add((new HighlightingTasksModel() { Id = 13, Name = "Foundation Permit", StDate = new DateTime(2012, 3, 23), EndDate = new DateTime(2012, 3, 24), Complete = 0d, BaselineStart = new DateTime(2012, 3, 2), BaselineEnd = new DateTime(2012, 3, 5), Cost = 53d, BaselineCost = 65 }));
         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask.Add((new HighlightingTasksModel() { Id = 14, Name = "Electrical Permit", StDate = new DateTime(2012, 3, 24), EndDate = new DateTime(2012, 3, 25), Complete = 0d, BaselineStart = new DateTime(2012, 3, 4), BaselineEnd = new DateTime(2012, 3, 6), Cost = 23d, BaselineCost = 34 }));
         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask.Add((new HighlightingTasksModel() { Id = 15, Name = "Plumbing Permit", StDate = new DateTime(2012, 3, 25), EndDate = new DateTime(2012, 3, 26), Complete = 0d, BaselineStart = new DateTime(2012, 3, 5), BaselineEnd = new DateTime(2012, 3, 7), Cost = 63d, BaselineCost = 53 }));

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 16, Name = "Site Work", StDate = new DateTime(2012, 3, 26), EndDate = new DateTime(2012, 3, 27), Complete = 0d, BaselineStart = new DateTime(2012, 3, 26), BaselineEnd = new DateTime(2012, 3, 26), Cost = 2000d, BaselineCost = 1000 });
         taskDetails[0].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 17, Name = "Clear Lot", StDate = new DateTime(2012, 3, 26), EndDate = new DateTime(2012, 3, 27), Complete = 0d, BaselineStart = new DateTime(2012, 3, 26), BaselineEnd = new DateTime(2012, 3, 26), Cost = 2000d, BaselineCost = 1000 });
         taskDetails[0].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 18, Name = "Strip Topsoil", StDate = new DateTime(2012, 3, 27), EndDate = new DateTime(2012, 3, 28), Complete = 0d, BaselineStart = new DateTime(2012, 3, 26), BaselineEnd = new DateTime(2012, 3, 27), Cost = 1200d, BaselineCost = 800 });
         taskDetails[0].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 19, Name = "Installing Temporary requirements", StDate = new DateTime(2012, 3, 28), EndDate = new DateTime(2012, 3, 29), Complete = 0d, BaselineStart = new DateTime(2012, 3, 25), BaselineEnd = new DateTime(2012, 3, 28), Cost = 354d, BaselineCost = 230 });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 20, Name = "Foundation", StDate = new DateTime(2012, 3, 29), EndDate = new DateTime(2012, 4, 2), Complete = 0d, Cost = 899, BaselineCost = 833d, BaselineStart = new DateTime(2012, 4, 29), BaselineEnd = new DateTime(2012, 4, 2) });
         taskDetails[0].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 21, Name = "Excavate for foundation", StDate = new DateTime(2012, 3, 29), EndDate = new DateTime(2012, 4, 2), Complete = 0d, Cost = 899, BaselineCost = 833d, BaselineStart = new DateTime(2012, 4, 29), BaselineEnd = new DateTime(2012, 4, 2) });
         taskDetails[0].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 22, Name = "Building Basement Walls", StDate = new DateTime(2012, 4, 3), EndDate = new DateTime(2012, 4, 8), Complete = 0d, Cost = 889, BaselineCost = 803d, BaselineStart = new DateTime(2012, 4, 5), BaselineEnd = new DateTime(2012, 4, 15) });
         taskDetails[0].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 23, Name = "Foundation inspection", StDate = new DateTime(2012, 4, 8), EndDate = new DateTime(2012, 4, 10), Complete = 0d, Cost = 8, BaselineCost = 8d, BaselineStart = new DateTime(2012, 4, 14), BaselineEnd = new DateTime(2012, 4, 16) });
         taskDetails[0].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 24, Name = "Finishing Foundation", StDate = new DateTime(2012, 4, 10), EndDate = new DateTime(2012, 4, 17), Complete = 0d, Cost = 0, BaselineCost = 8d, BaselineStart = new DateTime(2012, 4, 17), BaselineEnd = new DateTime(2012, 4, 17) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 25, Name = "Framing", StDate = new DateTime(2012, 4, 18), EndDate = new DateTime(2012, 4, 24), Complete = 0d, Cost = 890, BaselineCost = 803d, BaselineStart = new DateTime(2012, 4, 18), BaselineEnd = new DateTime(2012, 5, 7) });
         taskDetails[0].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 26, Name = "First Floor Framing", StDate = new DateTime(2012, 4, 18), EndDate = new DateTime(2012, 4, 24), Complete = 0d, Cost = 890, BaselineCost = 803d, BaselineStart = new DateTime(2012, 4, 18), BaselineEnd = new DateTime(2012, 5, 7) });
         taskDetails[0].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 27, Name = "Second Floor Framing", StDate = new DateTime(2012, 4, 24), EndDate = new DateTime(2012, 5, 3), Complete = 0d, Cost = 789, BaselineCost = 898d, BaselineStart = new DateTime(2012, 5, 8), BaselineEnd = new DateTime(2012, 5, 18) });
         taskDetails[0].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 28, Name = "Framing Roof", StDate = new DateTime(2012, 5, 3), EndDate = new DateTime(2012, 5, 7), Complete = 0d, Cost = 780, BaselineCost = 833d, BaselineStart = new DateTime(2012, 5, 18), BaselineEnd = new DateTime(2012, 5, 23) });
         taskDetails[0].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 29, Name = "Framing Inspection", StDate = new DateTime(2012, 5, 7), EndDate = new DateTime(2012, 5, 8), Complete = 0d, Cost = 5, BaselineCost = 8d, BaselineStart = new DateTime(2012, 5, 18), BaselineEnd = new DateTime(2012, 5, 30) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 30, Name = "Dry In", StDate = new DateTime(2012, 5, 8), EndDate = new DateTime(2012, 5, 14), Complete = 0d, Cost = 232, BaselineCost = 323d, BaselineStart = new DateTime(2012, 5, 30), BaselineEnd = new DateTime(2012, 6, 2) });
         taskDetails[0].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 31, Name = "Installing Sheathing for floors", StDate = new DateTime(2012, 5, 8), EndDate = new DateTime(2012, 5, 14), Complete = 0d, Cost = 232, BaselineCost = 323d, BaselineStart = new DateTime(2012, 5, 30), BaselineEnd = new DateTime(2012, 6, 2) });
         taskDetails[0].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 32, Name = "Installing Windows", StDate = new DateTime(2012, 5, 14), EndDate = new DateTime(2012, 5, 25), Complete = 0d, Cost = 325, BaselineCost = 452d, BaselineStart = new DateTime(2012, 6, 4), BaselineEnd = new DateTime(2012, 6, 17) });
         taskDetails[0].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 33, Name = "Installing Sheathing for Roof", StDate = new DateTime(2012, 5, 25), EndDate = new DateTime(2012, 5, 30), Complete = 0d, Cost = 82, BaselineCost = 83d, BaselineStart = new DateTime(2012, 6, 18), BaselineEnd = new DateTime(2012, 6, 20) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 34, Name = "Exterior Finishing", StDate = new DateTime(2012, 5, 31), EndDate = new DateTime(2012, 6, 12), Complete = 0d, Cost = 463, BaselineCost = 633d, BaselineStart = new DateTime(2012, 6, 20), BaselineEnd = new DateTime(2012, 6, 25) });
         taskDetails[0].ChildTask[5].ChildTask.Add(new HighlightingTasksModel() { Id = 35, Name = "Exterior Trimming", StDate = new DateTime(2012, 5, 31), EndDate = new DateTime(2012, 6, 12), Complete = 0d, Cost = 463, BaselineCost = 633d, BaselineStart = new DateTime(2012, 6, 20), BaselineEnd = new DateTime(2012, 6, 25) });
         taskDetails[0].ChildTask[5].ChildTask.Add(new HighlightingTasksModel() { Id = 36, Name = "Completing Exterior Bricks", StDate = new DateTime(2012, 6, 12), EndDate = new DateTime(2012, 6, 17), Complete = 0d, Cost = 234, BaselineCost = 333d, BaselineStart = new DateTime(2012, 6, 26), BaselineEnd = new DateTime(2012, 6, 28) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 37, Name = "Interior Finishing", StDate = new DateTime(2012, 6, 17), EndDate = new DateTime(2012, 6, 19), Complete = 0d, Cost = 43, BaselineCost = 33d, BaselineStart = new DateTime(2012, 6, 28), BaselineEnd = new DateTime(2012, 7, 9) });

         taskDetails[0].ChildTask[6].ChildTask.Add(new HighlightingTasksModel() { Id = 38, Name = "Installing Insulation", StDate = new DateTime(2012, 6, 17), EndDate = new DateTime(2012, 6, 19), Complete = 0d, Cost = 43, BaselineCost = 33d, BaselineStart = new DateTime(2012, 6, 28), BaselineEnd = new DateTime(2012, 7, 9) });
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 39, Name = "Install Floor Insulation", StDate = new DateTime(2012, 6, 17), EndDate = new DateTime(2012, 6, 19), Complete = 0d, Cost = 43, BaselineCost = 33d, BaselineStart = new DateTime(2012, 6, 28), BaselineEnd = new DateTime(2012, 7, 9) });
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 40, Name = "Install Wall Insulation", StDate = new DateTime(2012, 6, 19), EndDate = new DateTime(2012, 6, 21), Complete = 0d, Cost = 53, BaselineCost = 83d, BaselineStart = new DateTime(2012, 7, 10), BaselineEnd = new DateTime(2012, 7, 20) });
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask.Add(new HighlightingTasksModel() { Id = 41, Name = "Install Ceiling Insulation", StDate = new DateTime(2012, 6, 21), EndDate = new DateTime(2012, 6, 22), Complete = 0d, Cost = 89, BaselineCost = 83d, BaselineStart = new DateTime(2012, 7, 20), BaselineEnd = new DateTime(2012, 7, 22) });

         taskDetails[0].ChildTask[6].ChildTask.Add(new HighlightingTasksModel() { Id = 42, Name = "Painting and Wallpaper", StDate = new DateTime(2012, 6, 22), EndDate = new DateTime(2012, 6, 23), Complete = 0d, Cost = 453, BaselineCost = 563, BaselineStart = new DateTime(2012, 7, 21), BaselineEnd = new DateTime(2012, 7, 25) });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 43, Name = "Painting all Interior", StDate = new DateTime(2012, 6, 22), EndDate = new DateTime(2012, 6, 23), Complete = 0d, Cost = 453, BaselineCost = 563, BaselineStart = new DateTime(2012, 7, 21), BaselineEnd = new DateTime(2012, 7, 25) });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 44, Name = "Painting all Exterior", StDate = new DateTime(2012, 6, 23), EndDate = new DateTime(2012, 6, 25), Complete = 0d, Cost = 352, BaselineCost = 342, BaselineStart = new DateTime(2012, 7, 26), BaselineEnd = new DateTime(2012, 7, 27) });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask.Add(new HighlightingTasksModel() { Id = 45, Name = "Additional Trimming Work", StDate = new DateTime(2012, 6, 25), EndDate = new DateTime(2012, 6, 27), Complete = 0d, Cost = 32, BaselineCost = 50, BaselineStart = new DateTime(2012, 7, 28), BaselineEnd = new DateTime(2012, 7, 29) });

         taskDetails[0].ChildTask[6].ChildTask.Add(new HighlightingTasksModel() { Id = 46, Name = "Finishing Plumbing", StDate = new DateTime(2012, 6, 27), EndDate = new DateTime(2012, 6, 29), Complete = 0d, Cost = 424, BaselineCost = 423, BaselineStart = new DateTime(2012, 7, 29), BaselineEnd = new DateTime(2012, 8, 1) });
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 47, Name = "First floor Plumbing", StDate = new DateTime(2012, 6, 27), EndDate = new DateTime(2012, 6, 29), Complete = 0d, Cost = 424, BaselineCost = 423, BaselineStart = new DateTime(2012, 7, 29), BaselineEnd = new DateTime(2012, 8, 1) });
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 48, Name = "Second floor plumbing", StDate = new DateTime(2012, 6, 29), EndDate = new DateTime(2012, 7, 1), Complete = 0d, Cost = 234, BaselineCost = 324, BaselineStart = new DateTime(2012, 8, 1), BaselineEnd = new DateTime(2012, 8, 9) });
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask.Add(new HighlightingTasksModel() { Id = 49, Name = "Inspecting Plumbing", StDate = new DateTime(2012, 7, 1), EndDate = new DateTime(2012, 7, 3), Complete = 0d, Cost = 23, BaselineCost = 33d, BaselineStart = new DateTime(2012, 8, 10), BaselineEnd = new DateTime(2012, 8, 17) });

         taskDetails[0].ChildTask[6].ChildTask.Add(new HighlightingTasksModel() { Id = 50, Name = "Finishing Electrical", StDate = new DateTime(2012, 7, 3), EndDate = new DateTime(2012, 7, 5), Complete = 0d, Cost = 432, BaselineCost = 536, BaselineStart = new DateTime(2012, 8, 17), BaselineEnd = new DateTime(2012, 8, 19) });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 51, Name = "Complete first floor connections", StDate = new DateTime(2012, 7, 3), EndDate = new DateTime(2012, 7, 5), Complete = 0d, Cost = 432, BaselineCost = 536, BaselineStart = new DateTime(2012, 8, 17), BaselineEnd = new DateTime(2012, 8, 19) });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 52, Name = "Complete second floor connections", StDate = new DateTime(2012, 7, 5), EndDate = new DateTime(2012, 7, 7), Complete = 0d, Cost = 563, BaselineCost = 463, BaselineStart = new DateTime(2012, 8, 18), BaselineEnd = new DateTime(2012, 8, 19) });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask.Add(new HighlightingTasksModel() { Id = 53, Name = "Complete non-Electrical Wiring", StDate = new DateTime(2012, 7, 7), EndDate = new DateTime(2012, 7, 8), Complete = 0d, Cost = 234, BaselineCost = 563, BaselineStart = new DateTime(2012, 8, 19), BaselineEnd = new DateTime(2012, 8, 20) });

         taskDetails[0].ChildTask[6].ChildTask.Add(new HighlightingTasksModel() { Id = 54, Name = "Carpet,Tiles and Furnishing", StDate = new DateTime(2012, 7, 8), EndDate = new DateTime(2012, 7, 10), Complete = 0d, Cost = 253, BaselineCost = 210, BaselineStart = new DateTime(2012, 8, 20), BaselineEnd = new DateTime(2012, 8, 21) });
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 55, Name = "Complete first floor carpet", StDate = new DateTime(2012, 7, 8), EndDate = new DateTime(2012, 7, 10), Complete = 0d, Cost = 253, BaselineCost = 210, BaselineStart = new DateTime(2012, 8, 20), BaselineEnd = new DateTime(2012, 8, 21) });
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 56, Name = "Complete second floor carpet", StDate = new DateTime(2012, 7, 10), EndDate = new DateTime(2012, 7, 13), Complete = 0d, Cost = 341, BaselineCost = 300, BaselineStart = new DateTime(2012, 8, 21), BaselineEnd = new DateTime(2012, 8, 22) });
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask.Add(new HighlightingTasksModel() { Id = 57, Name = "Complete Furnishing Kitchen, bath, hall", StDate = new DateTime(2012, 7, 13), EndDate = new DateTime(2012, 7, 14), Complete = 0, Cost = 4252, BaselineCost = 6033d, BaselineStart = new DateTime(2012, 8, 22), BaselineEnd = new DateTime(2012, 8, 25) });

         taskDetails[0].ChildTask.Add(new HighlightingTasksModel() { Id = 58, Name = "Final Acceptance", StDate = new DateTime(2012, 7, 14), EndDate = new DateTime(2012, 7, 16), Complete = 0d, Cost = 430, BaselineCost = 433d, BaselineStart = new DateTime(2012, 8, 25), BaselineEnd = new DateTime(2012, 8, 26) });
         taskDetails[0].ChildTask[7].ChildTask.Add(new HighlightingTasksModel() { Id = 59, Name = "Cleaning", StDate = new DateTime(2012, 7, 14), EndDate = new DateTime(2012, 7, 16), Complete = 0d, Cost = 430, BaselineCost = 433d, BaselineStart = new DateTime(2012, 8, 25), BaselineEnd = new DateTime(2012, 8, 26) });
         taskDetails[0].ChildTask[7].ChildTask.Add(new HighlightingTasksModel() { Id = 60, Name = "Final Inspection", StDate = new DateTime(2012, 7, 16), EndDate = new DateTime(2012, 7, 17), Complete = 0d, Cost = 0, BaselineCost = 5, BaselineStart = new DateTime(2012, 8, 26), BaselineEnd = new DateTime(2012, 8, 27) });
         taskDetails[0].ChildTask[7].ChildTask.Add(new HighlightingTasksModel() { Id = 61, Name = "Move In", StDate = new DateTime(2012, 7, 17), EndDate = new DateTime(2012, 7, 17), Complete = 0d, Cost = 0, BaselineCost = 0, BaselineStart = new DateTime(2012, 8, 28), BaselineEnd = new DateTime(2012, 8, 28) });

         //Adding Resources
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[0].Resource.Add(ResidentialConstructionResources[1]);
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[0].Resource.Add(ResidentialConstructionResources[0]);
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[0].Resource.Add(ResidentialConstructionResources[2]);

         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[1].Resource.Add(ResidentialConstructionResources[0]);
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[1].Resource.Add(ResidentialConstructionResources[1]);
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[1].Resource.Add(ResidentialConstructionResources[2]);

         taskDetails[0].ChildTask[1].ChildTask[0].Resource.Add(ResidentialConstructionResources[3]);
         taskDetails[0].ChildTask[1].ChildTask[1].Resource.Add(ResidentialConstructionResources[3]);
         taskDetails[0].ChildTask[1].ChildTask[2].Resource.Add(ResidentialConstructionResources[5]);
         taskDetails[0].ChildTask[1].ChildTask[2].Resource.Add(ResidentialConstructionResources[6]);
         taskDetails[0].ChildTask[1].ChildTask[2].Resource.Add(ResidentialConstructionResources[4]);

         taskDetails[0].ChildTask[2].ChildTask[0].Resource.Add(ResidentialConstructionResources[3]);
         taskDetails[0].ChildTask[2].ChildTask[1].Resource.Add(ResidentialConstructionResources[6]);
         taskDetails[0].ChildTask[2].ChildTask[2].Resource.Add(ResidentialConstructionResources[7]);
         taskDetails[0].ChildTask[2].ChildTask[3].Resource.Add(ResidentialConstructionResources[3]);

         taskDetails[0].ChildTask[3].ChildTask[0].Resource.Add(ResidentialConstructionResources[8]);
         taskDetails[0].ChildTask[3].ChildTask[1].Resource.Add(ResidentialConstructionResources[8]);
         taskDetails[0].ChildTask[3].ChildTask[2].Resource.Add(ResidentialConstructionResources[9]);
         taskDetails[0].ChildTask[3].ChildTask[3].Resource.Add(ResidentialConstructionResources[7]);

         taskDetails[0].ChildTask[4].ChildTask[0].Resource.Add(ResidentialConstructionResources[8]);
         taskDetails[0].ChildTask[4].ChildTask[1].Resource.Add(ResidentialConstructionResources[9]);
         taskDetails[0].ChildTask[4].ChildTask[2].Resource.Add(ResidentialConstructionResources[8]);

         taskDetails[0].ChildTask[5].ChildTask[0].Resource.Add(ResidentialConstructionResources[14]);
         taskDetails[0].ChildTask[5].ChildTask[1].Resource.Add(ResidentialConstructionResources[8]);

         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[0].Resource.Add(ResidentialConstructionResources[10]);
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[1].Resource.Add(ResidentialConstructionResources[10]);
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[2].Resource.Add(ResidentialConstructionResources[10]);

         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[0].Resource.Add(ResidentialConstructionResources[12]);
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[1].Resource.Add(ResidentialConstructionResources[12]);
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[2].Resource.Add(ResidentialConstructionResources[12]);

         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[0].Resource.Add(ResidentialConstructionResources[5]);
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[1].Resource.Add(ResidentialConstructionResources[5]);
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[2].Resource.Add(ResidentialConstructionResources[7]);

         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[0].Resource.Add(ResidentialConstructionResources[4]);
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[1].Resource.Add(ResidentialConstructionResources[4]);
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[2].Resource.Add(ResidentialConstructionResources[4]);

         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[0].Resource.Add(ResidentialConstructionResources[13]);
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[1].Resource.Add(ResidentialConstructionResources[13]);
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[2].Resource.Add(ResidentialConstructionResources[14]);

         taskDetails[0].ChildTask[7].ChildTask[0].Resource.Add(ResidentialConstructionResources[16]);
         taskDetails[0].ChildTask[7].ChildTask[1].Resource.Add(ResidentialConstructionResources[7]);
         taskDetails[0].ChildTask[7].ChildTask[2].Resource.Add(ResidentialConstructionResources[1]);

         //Adding Predecessors
         taskDetails[0].ChildTask[0].ChildTask[0].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 4, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[1].ChildTask[4].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });

         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });
         taskDetails[0].ChildTask[0].ChildTask[2].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 5, GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });

         taskDetails[0].ChildTask[1].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 13, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[1].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 14, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[1].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 15, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[1].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 17, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[1].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 18, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[2].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 19, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[2].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 21, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[2].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 19, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[2].ChildTask[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 23, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[3].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 24, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[3].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 26, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[3].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 27, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[3].ChildTask[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 28, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[4].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 29, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[4].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 31, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[4].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 32, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[5].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 33, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[5].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 35, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 36, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 39, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[0].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 40, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 41, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 43, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 44, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[1].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 43, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 45, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 47, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[2].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 48, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 49, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 48, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 51, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[3].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 52, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 53, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 55, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[6].ChildTask[4].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 56, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });

         taskDetails[0].ChildTask[7].ChildTask[0].Predecessor.Add(new Predecessor() { GanttTaskIndex = 57, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[7].ChildTask[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 59, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         taskDetails[0].ChildTask[7].ChildTask[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 60, GanttTaskRelationship = GanttTaskRelationship.FinishToStart });
         return taskDetails;
     }

     /// <summary>
     /// Gets the resources.
     /// </summary>
     /// <returns>The resources</returns>
     private static ObservableCollection<Resource> GetResources()
     {
         ObservableCollection<Resource> Resources = new ObservableCollection<Resource>();
         Resources.Add(new Resource() { ID = 1, Name = "General Contractor" });
         Resources.Add(new Resource() { ID = 2, Name = "Owner" });
         Resources.Add(new Resource() { ID = 3, Name = "Architect" });
         Resources.Add(new Resource() { ID = 4, Name = "Site Excavation Contractor" });
         Resources.Add(new Resource() { ID = 5, Name = "Electrical Contractor" });
         Resources.Add(new Resource() { ID = 6, Name = "Plumbing Contractor" });
         Resources.Add(new Resource() { ID = 7, Name = "Concrete Contractor" });
         Resources.Add(new Resource() { ID = 8, Name = "Inspector" });
         Resources.Add(new Resource() { ID = 9, Name = "Framing Contractor" });
         Resources.Add(new Resource() { ID = 10, Name = "Roofing Contractor" });
         Resources.Add(new Resource() { ID = 11, Name = "Insulation Contractor" });
         Resources.Add(new Resource() { ID = 12, Name = "Drywall contractor" });
         Resources.Add(new Resource() { ID = 13, Name = "Painting Contractor" });
         Resources.Add(new Resource() { ID = 14, Name = "Flooring Contractor" });
         Resources.Add(new Resource() { ID = 15, Name = "Appliance Contractor" });
         Resources.Add(new Resource() { ID = 16, Name = "Masonry Contractor" });
         Resources.Add(new Resource() { ID = 17, Name = "Maid Service" });
         return Resources;
     }
 }

{% endhighlight  %}

{% highlight c# tabtitle="ViewModel.cs" %}

public class ViewModel : TaskRepository
{
    /// <summary>
    /// Initializes a new instance of the <see cref="ViewModel"/> class.
    /// </summary>
    public ViewModel()
    {
         this.HighlightTaskItems = this.GetCriticalTasks();
        _highlightingBrush = Brushes.Red;
    }

    private List<HighlightingTasksModel> _highlightTaskItems;

    /// <summary>
    /// Gets or sets the highlight task items.
    /// </summary>
    /// <value>The highlight task items.</value>
    public List<HighlightingTasksModel> HighlightTaskItems
    {
        get
        {
            return _highlightTaskItems;
        }
        set
        {
            _highlightTaskItems = value;
            RaisePropertyChanged("HighlightTaskItems");
        }
    }

    private DateTime _startTime = new DateTime(2012, 2, 16);

    /// <summary>
    /// Gets or sets the start time.
    /// </summary>
    /// <value>The start time.</value>
    public DateTime StartTime
    {
        get
        {
            return _startTime;
        }
        set
        {
            if (value <= _endTime || this._endTime.Equals(DateTime.MinValue))
            {
                _startTime = value;
            }
            RaisePropertyChanged("StartTime");
        }
    }

    private DateTime _endTime = new DateTime(2012, 8, 1);

    /// <summary>
    /// Gets or sets the end time.
    /// </summary>
    /// <value>The end time.</value>
    public DateTime EndTime
    {
        get
        {
            return _endTime;
        }
        set
        {
            _endTime = value;
            RaisePropertyChanged("EndTime");
        }
    }

    private Brush _highlightingBrush;

    /// <summary>
    /// Gets or sets the highlighting brush.
    /// </summary>
    /// <value>The highlighting brush.</value>
    public Brush HighlightingBrush
    {
        get
        {
            return _highlightingBrush;
        }
        set
        {
            _highlightingBrush = value;
            RaisePropertyChanged("HighlightingBrush");
        }
    }

    #region Delegate Commands

    private DelegateCommand<object> _highlightTaskBetween;

    /// <summary>
    /// Gets the highlight task between.
    /// </summary>
    /// <value>The highlight task between.</value>
    public DelegateCommand<object> HighlightTaskBetween
    {
        get
        {
            return _highlightTaskBetween;
        }
    }

    private DelegateCommand<object> _highlightCriticalTask;

    /// <summary>
    /// Gets the highlight critical task.
    /// </summary>
    /// <value>The highlight critical task.</value>
    public DelegateCommand<object> HighlightCriticalTask
    {
        get
        {
            return _highlightCriticalTask;
        }
    }

    #endregion

    /// <summary>
    /// Gets the critical tasks.
    /// </summary>
    /// <returns></returns>
    internal List<HighlightingTasksModel> GetCriticalTasks()
    {
        List<HighlightingTasksModel> criticalTasks = new List<HighlightingTasksModel>();

        criticalTasks.AddRange(this.TaskCollections[0].ChildTask[0].ChildTask[2].ChildTask);
        criticalTasks.AddRange(this.TaskCollections[0].ChildTask[1].ChildTask);
        criticalTasks.AddRange(this.TaskCollections[0].ChildTask[2].ChildTask);

        return criticalTasks;
    }
}
 
{% endhighlight  %}
{% endtabs  %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

The following image shows the Gantt with Highlighted Tasks:

![gantt-control-highlighting-tasks](Highlighting-Tasks_images/gantt-control-highlighting-tasks.png)

Gantt with Highlighted Tasks
{:.caption}

## Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel
4. Select Gantt
5. Expand the Interactive Features item in the Sample Browser
6. Choose Highlighting Tasks to launch the sample.

## see also

[How to view the gantt control with the desired date tasks at load time in WPF](https://www.syncfusion.com/kb/7728/how-to-view-the-gantt-control-with-the-desired-date-tasks-at-load-time-in-wpf)
