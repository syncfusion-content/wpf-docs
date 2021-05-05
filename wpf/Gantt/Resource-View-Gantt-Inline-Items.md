---
layout: post
title: Resource View Gantt Inline Items in WPF Gantt control | Syncfusion
description: Learn about Resource View Gantt Inline Items support in Syncfusion WPF Gantt control and more.
platform: wpf
control: Gantt
documentation: ug
---

# Resource View Gantt Inline Items in WPF Gantt

By default, the Gantt chart will display a single node in a row. This helps you to manage the project. When you want to manage the resources in a project, you need multiple nodes in a single row. A Resource view Gantt enables you to manage the resources involved in a project.

In a normal Gantt, a node represents a task or activity of the project. In a resource view Gantt, the node represents task assigned to a resource. Multiple tasks assigned to a resource can be displayed in a single row. You can achieve this by using the mapping attribute of the InLineTaskMapping. 

Essential Gantt will listen to the dynamic inclusion of inline items and refresh the chart region.

The following code illustrates how to add inline items dynamically to the underlying collection.


{% highlight c# %}


//To add dynamic inline items
Item item = new Item() 
{ 
    StartDate = new DateTime(2012, 01, 19), 
    FinishDate = new DateTime(2012, 01, 25) 
};

viewModel.GanttItemSource[0].SubItems[0].InLineItems.Add(item);

{% endhighlight  %}



## Use Case Scenarios

A resource view is very useful when you need to manage the resources in a project.

Example: A very big development project that contains multiple phases to complete the project. The management needs to track the status of the project. In this scenario, they can manage the project with a Resource view Gantt easily. The Resource view Gantt will show all the tasks in a single row that are assigned to a particular resource.

## Adding Inline Items to an Application 

You can populate a resource view Gantt by populating the collection of tasks in a single row by mapping the corresponding field in the underlying source to the InLineTaskMapping. 

You can populate a Resource view Gantt for both date-time schedules and numeric schedules. 

### Resource View Gantt in a Custom Numeric Schedule

To populate a Resource view Gantt in a Custom Numeric Schedule:

1. Define the Gantt with a custom numeric schedule source. For more information about custom numeric schedules, visit the following link: <http://help.syncfusion.com/wpf/gantt/custom-schedule#custom-numeric>
2. You can populate the collection of tasks in a single row by mapping the corresponding field in the underlying source to the InLineTaskMapping.

The following code illustrates this.


{% highlight xaml %}

<gantt:GanttControl x:Name="Gantt"
                    Grid.Row="1"
                    ScheduleType="CustomNumeric"
                    CustomScheduleSource="{Binding CustomScheduleInfo}"
                    ItemsSource="{Binding TeamDetails}">
    <gantt:GanttControl.TaskAttributeMapping>
        <gantt:TaskAttributeMapping TaskNameMapping="Name"
                                    ChildMapping="SubItems"
                                    StartPointMapping="Start"
                                    FinishPointMapping="End"
                                    InLineTaskMapping="InLineItems"/>
    </gantt:GanttControl.TaskAttributeMapping>
</gantt:GanttControl>

{% endhighlight  %}

The following code is the sample data source of a resource view Gantt in a custom numeric schedule.


{% highlight c# %}


ObservableCollection<Item> teams = new ObservableCollection<Item>();
teams.Add(new Item() { Name = "RDU Team" });

Item Person = new Item() { Name = "Robert" };
Person.InLineItems.Add(new Item() { Start =0, End=2, Name = "Market Analysis", Progress = 50d });
Person.InLineItems.Add(new Item() { Start =2, End=4, Name = "Competitor Analysis", Progress = 20d });
Person.InLineItems.Add(new Item() { Start = 3, End = 6,Name = "Design Spec" });
teams[0].SubItems.Add(Person);

Person = new Item() { Name = "Michael" };
Person.InLineItems.Add(new Item() { Start = 2, End = 4, Name = "Basic Requirement Analysis", Progress = 40 });
Person.InLineItems.Add(new Item() { Start = 5, End = 7, Name = "Requirement Spec" });
teams[0].SubItems.Add(Person);

Person = new Item() { Name = "Anne" };
Person.InLineItems.Add(new Item() { Start = 0, End = 2, Name = "Estimation", Progress = 30 });
Person.InLineItems.Add(new Item() { Start = 3, End = 6, Name = "Budget & Plan Spec" });
teams[0].SubItems.Add(Person);

teams.Add(new Item() { Name = "Graphics Team" });

Person = new Item() { Name = "Madhan" };
Person.InLineItems.Add(new Item() { Start = 0, End = 3, Name = "Identifying UI modules", Progress = 40 });
Person.InLineItems.Add(new Item() { Start = 2, End = 5, Name = "Defining UI Design" });
teams[1].SubItems.Add(Person);

{% endhighlight  %}

The following shows the Resultant output:



![Resource-View-Gantt-Inline-Items_img1](Resource-View-Gantt-Inline-Items_images/Resource-View-Gantt-Inline-Items_img1.png)



### Resource View Gantt with a Date-Time Schedule

To populate the Resource view Gantt with a date-time schedule:

1. Define the Gantt with DateTime values.
2. Populate the collection of tasks in a single row by mapping the corresponding field in the underlying source to the InLineTaskMapping.

The following code sample illustrates this:


{% highlight xaml %}




 <gantt:GanttControl Grid.Row="1" x:Name="Gantt">
                <gantt:GanttControl.TaskAttributeMapping>
                    <gantt:TaskAttributeMapping       
                     TaskNameMapping="Name"      
                     StartDateMapping="StartDate"   
                     ChildMapping="SubItems"   
                      FinishDateMapping="FinishDate"   
                     InLineTaskMapping="InLineItems">

                    </gantt:TaskAttributeMapping>
                </gantt:GanttControl.TaskAttributeMapping>
 </gantt:GanttControl>


{% endhighlight  %}
The following is the sample data source for the resource view Gantt:

{% highlight c# %}





ObservableCollection<Item> teams = new ObservableCollection<Item>();
teams.Add(new Item() { Name = "RDU Team" });
Item Person = new Item() { Name = "Robert" };
Person.InLineItems.Add(new Item(){ StartDate = new DateTime(2012, 01, 07), FinishDate = new DateTime(2012, 01, 11), Name = "Market Analysis", Progress = 50d });
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 11), FinishDate = new DateTime(2012, 01, 15), Name = "Competitor Analysis", Progress = 20d });
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 13), FinishDate = new DateTime(2012, 01, 19), Name = "Design Spec" });
teams[0].SubItems.Add(Person);
Person = new Item() { Name = "Michael" };
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 18), FinishDate = new DateTime(2012, 01, 19), Name = "Basic Requirement Analysis", Progress = 40 });
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 19), FinishDate = new DateTime(2012, 01, 21), Name = "Requirement Spec" });
teams[0].SubItems.Add(Person);
Person = new Item() { Name = "Anne" };
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 21), FinishDate = new DateTime(2012, 01, 24), Name = "Estimation", Progress = 30 });
Person.InLineItems.Add(new Item() { StartDate = new DateTime(2012, 01, 24), FinishDate = new DateTime(2012, 01, 26), Name = "Budget & Plan Spec" });
teams[0].SubItems.Add(Person);

{% endhighlight  %}

Output

The following image shows the resultant output:



![Resource-View-Gantt-Inline-Items_img2](Resource-View-Gantt-Inline-Items_images/Resource-View-Gantt-Inline-Items_img2.png)





## Data Structure

The following is the data structure used to build a Resource view Gantt: 



![Resource-View-Gantt-Inline-Items_img3](Resource-View-Gantt-Inline-Items_images/Resource-View-Gantt-Inline-Items_img3.png)



* team holds information about the team. 
* SubItems of Team will hold the list of Resources in that particular team.
* InLineItems of each Resource will hold the tasks assigned to the particular resource.

## Information Displayed in Gantt

Grid Region:The grid will display only the information about the team and its resources (SubItems). It will not display the information about assigned tasks (InLineItems).

Chart Region: The chart will display only the information about the team and the tasks assigned to each resource in the team (InLineItems). It will not display the information about resources (SubItems).

## Sample Link

To view samples: 

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under User Interface Edition panel.
4. Select Gantt.
5. Expand the Data Binding item in the Sample Browser.
6. Choose the Resource View Gantt sample to launch. 



