---
layout: post
title: Dependency Relationship in WPF Gantt control | Syncfusion
description: Learn about Dependency Relationship support in Syncfusion WPF Gantt control and more.
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
Predecessor</td><td>
This enables you to set the relationship between the tasks.</td><td>
Object</td><td>
Object</td><td>
NA</td></tr>
<tr>
<td>
GanttTaskRelationship</td><td>
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


{% highlight c# %}


 // Adding dependency relationship.
task[0].ChildCollection[1].Predecessors = new ObservableCollection<Predecessor>(
task[0].ChildCollection[1].Predecessors.Add(new Predecessor()
                                     {
                                         GanttTaskIndex = 
                                         GanttTaskRelationship = GanttTaskRelationship.StartToStart
                                     });

task[0].ChildCollection[2].Predecessors = new ObservableCollection<Predecessor>();
task[0].ChildCollection[2].Predecessors.Add(new Predecessor()
                                     {
                                         GanttTaskIndex = 
                                         GanttTaskRelationship = GanttTaskRelationship.StartToFinish
                                     });

task[0].ChildCollection[3].Predecessors = new ObservableCollection<Predecessor>();
task[0].ChildCollection[3].Predecessors.Add(new Predecessor()
                                     {
                                         GanttTaskIndex = 
                                         GanttTaskRelationship = GanttTaskRelationship.FinishToFinish
                                     });

{% endhighlight  %}

The following image shows the Dependency Relationship:



![Dependency-Relationship_img5](Dependency-Relationship_images/Dependency-Relationship_img5.png)



### Samples Link

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

You can edit the predecessor information from the GanttGrid. For resource, you can edit in the underlying source, Gantt will listen to the change in the underlying source and reflect it in both GanttGrid and GanttChart.

## Predecessor Validation

There are two predecessor validation modes in Gantt Control. 

* Auto - Successor nodes will adjust its position based on its predecessor nodes automatically.
* Manual - Successor nodes need to adjust manually with respect to predecessor.

### Properties

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
ValidationMode</td><td>
This contains two modes.<ul><li>
Manual,</li><li>
Auto.</li></ul>
Default value is Manual.</td><td>
DependencyProperty</td><td>
Enum</td><td>
NA</td></tr>
</table>

The following image shows the Predecessor in Manual Mode:

![Predecessors ManualMode](Dependency-Relationship_images/Predecessors ManualMode.png)

The following image shows the Predecessor in Auto Mode:

![Predecessors AutoMode](Dependency-Relationship_images/Predecessors AutoMode.png)

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



![Dependency-Relationship_img6](Dependency-Relationship_images/Dependency-Relationship_img6.png)



Adding Dynamic Predecessors and Resources to an Application

The dynamic editing of predecessor will be automatically included in the Gantt by default. There is no need to provide any additional data for that. The following codes illustrate this:

{% highlight xaml %}

<Sync:GanttControl ItemsSource="{Binding TaskCollection}" >
    <Sync:GanttControl.TaskAttributeMapping>
        <Sync:TaskAttributeMapping TaskIdMapping="Id"
                                    TaskNameMapping="Name"
                                    DurationMapping="Duration"
                                    StartDateMapping="StDate"                                           
                                    FinishDateMapping="EndDate"
                                    ChildMapping="ChildTask"  
                                    ProgressMapping="Complete"
                                    PredecessorMapping="Predecessors"  
                                    ResourceInfoMapping="Resource">
        </Sync:TaskAttributeMapping>
    </Sync:GanttControl.TaskAttributeMapping>
</Sync:GanttControl>
 
{% endhighlight  %}


The following code will illustrate how to dynamically add resource and predecessor in the underlying collection:


{% highlight c# %}


// To Add the Dynamic Predecessors

this.viewModel.GanttItemSource[0].ChildCollection[2].Predecessors.Add(new Predecessor()
                                                 {
                                                     GanttTaskIndex = 3,
                                                     GanttTaskRelationship = GanttTaskRelationship.StartToFinish
                                                 });

//To Add the Dynamic Resources   
this.viewModel.GanttItemSource[0].ChildTask[2].Resource.Add(new Resource { ID = 3, Name = "Resource3" });

{% endhighlight %}
