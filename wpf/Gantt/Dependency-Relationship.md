---
layout: post
title: Dependency Relationship| Gantt | Wpf | Syncfusion
description: dependency relationship
platform: wpf
control: Gantt
documentation: ug
---

# Dependency Relationship

Dependency relationship is the relationship between two tasks. These relationship has been caterogrised into four types based on the start and finish date of the task. They are:

* FinishToStart 
* FinishToFinish
* StartToStart
* StartToFinish

Finish-to-start—You cannot start a task until the other task is completed.



![](Dependency-Relationship_images/Dependency-Relationship_img1.png)



Finish-to-finish—You cannot finish a task until the other task is completed.



![](Dependency-Relationship_images/Dependency-Relationship_img2.png)



Start-to-start—You cannot start a task until the other task is also started.



![](Dependency-Relationship_images/Dependency-Relationship_img3.png)



Start-to-Finish—You cannot finish a task until another the other task is started.



![](Dependency-Relationship_images/Dependency-Relationship_img4.png)



### Properties

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
Prodecessor</td><td>
This enables you to set the relationship between the tasks.</td><td>
Object</td><td>
Object</td><td>
NA</td></tr>
<tr>
<td>
GanttTaskRelationship</td><td>
This contains four relationships. They are:* StartToStart* StartToFinish* FinishToFinish* FinishToStart<br>You can asign this to the {{ '_TaskDetails_' | markdownify }} to set the relationship between tasks.</td><td>
Predecessor</td><td>
Enum</td><td>
NA</td></tr>
</table>


Specifing the Relationship between Tasks 

The following code illustrates how to add the Dependency Relationship between tasks:


{% highlight c# %}


GanttItemSource = new ObservableCollection<TaskDetails>();

GanttItemSource = GetDataSourceStartToStart();

ObservableCollection<TaskDetails> GetDataSourceStartToStart()
{
ObservableCollection<TaskDetails> task = ObservableCollection<TaskDetails>();
task.Add(new TaskDetails { TaskId = 1, 

TaskName = "Scope", 

StartDate = new DateTime(2011, 1, 3), 

FinishDate = new DateTime(2011, 1, 14),  

Progress = 40d });
task[0].Child.Add(new TaskDetails { TaskId = 2, 

TaskName = "Determine project office scope", 

StartDate = new DateTime(2011, 1, 3), 

FinishDate = new DateTime(2011, 1, 5), 

Progress = 20d });
task[0].Child.Add(new TaskDetails { TaskId = 3, 

TaskName = "Justify Project Offfice via business model", 

StartDate = new DateTime(2011, 1, 6), 

FinishDate = new DateTime(2011, 1, 7), 

Progress = 20d });
task[0].Child.Add(new TaskDetails { TaskId = 4, 

TaskName = "Secure executive sponsorship", 

StartDate = new DateTime(2011, 1, 10), 

FinishDate = new DateTime(2011, 1, 14), 

 Progress = 20d });

task[0].Child.Add(new TaskDetails { TaskId = 5, 

TaskName = "Secure complete", 

StartDate = new DateTime(2011, 1, 14), 

FinishDate = new DateTime(2011, 1, 14), 

Progress = 20d });

//Adding dependency relationShip 
task[0].Child[1].Predecessor.Add(new Predecessor() { GanttTaskIndex = 2, 

GanttTaskRelationship = GanttTaskRelationship.StartToStart });


task[0].Child[2].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, 

GanttTaskRelationship = GanttTaskRelationship.StartToFinish });


task[0].Child[3].Predecessor.Add(new Predecessor() { GanttTaskIndex = 3, 

GanttTaskRelationship = GanttTaskRelationship.FinishToFinish });

return task;

}

{% endhighlight  %}

The following image shows the Dependency Relationship:



![](Dependency-Relationship_images/Dependency-Relationship_img5.png)



### Samples Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
2. Click Run Samples for WPF under User Interface Edition panel .
3. Select Gantt.
4. Expand the Connectors Features item in the Sample Browser.
5. Choose the Predecessor samples to launch. 

## Dynamic Predecessors and Resources


Essential Gantt provides support for dynamic editing of predecessors in the Grid area. Using this feature, you can dynamically add the predecessor on-demand basis to Gantt. You can add/remove the predecessor in the corresponding cell in the GanttGrid.

You can add/remove/update the predecessors and resources of tasks at run time. Initially, the Gantt is loaded with the Predecessor/Resource information in the underlying collection and you can update this information if required.

You can edit the predecessor information from the GanttGrid. For resource, you can edit in the underlying source, Gantt will listen to the change in the underlying source and reflect it in both GanttGrid and GanttChart.

### Editing Predecessors

While creating a new predecessor in Grid, it should be in the following format:

{% highlight c# %}

	{Task ID}{GanttTaskRelationship} 
	
	{% endhighlight  %}

Here the {GanttTaskRelationship} is any one of the following:

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

### Editing Resources

As of now, resources cannot be edited in Grid. You can update the resource collection in the underlying source whenever you need. Gantt will listen to the changes in the collection and will update the GanttGrid and GanttChart accordingly.

### Use Case Scenario

This helps to change the dependency relationships and resources of the tasks dynamically.



![](Dependency-Relationship_images/Dependency-Relationship_img6.png)



Adding Dynamic Predecessors and Resources to an Application

The dynamic editing of predecessor will be automatically included in the Gantt by default. There is no need to provide any additional data for that. The following codes illustrate this:

{% highlight xml %}

 

<gantt:GanttControl Grid.Row="1" x:Name="Gantt"  

ItemsSource="{Binding GanttItemSource}" 

ToolTipTemplate="{StaticResource toolTipTemplate}"> 

<gantt:GanttControl.TaskAttributeMapping>

<gantt:TaskAttributeMapping TaskIdMapping="Id"

TaskNameMapping="Name"

DurationMapping="Duration"

StartDateMapping="StDate"                                           

FinishDateMapping="EndDate"

ChildMapping="ChildTask"  

ProgressMapping="Complete"

PredecessorMapping="Predecessor"  

ResourceInfoMapping="Resource">

</gantt:TaskAttributeMapping>

</gantt:GanttControl.TaskAttributeMapping>

</gantt:GanttControl>




{% endhighlight  %}


The following code will illustrate how to dynamically add resource and predecessor in the underlying collection:


{% highlight c# %}


// To Add the Dynamic Predecessors

this.viewModel.GanttItemSource[0].ChildTask[2].Predecessor.Add(new Predecessor() 
{   GanttTaskIndex = 4,    GanttTaskRelationship = GanttTaskRelationship.FinishToStart 
});

//To Add the Dynamic Resources   
this.viewModel.GanttItemSource[0].ChildTask[2].Resource.Add(new Resource { ID = 3, Name = "Resource3" });


{% endhighlight %}


