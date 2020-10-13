---
layout: post
title: Visualize graphical object using BPMNNode Activity | Syncfusion 
description: BPMNNode Activity is the task that is performed in a business process and shows how to customize their appearance.
platform: wpf
control: SfDiagram
documentation: ug
---

# BPMNNode Activity and its customization

The [`Activity`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.BpmnShapeType.html#fields#Activity) is the task that is performed in a business process. It is represented by a rounded rectangle.

There are two types of activities. They are listed as follows:

* [Task](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.ActivityType.html#fields#Task): Occurs within a process and it is not broken down to a finer level of detail.
* [CollapsedSubProcess](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.ActivityType.html#fields#CollapsedSubProcess): Occurs within a process and it is broken down to a finer level of detail.

You can specify the any one of the above activity type using the [ActivityType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_ActivityType) property of `BpmnNodeViewModel`.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="Task"> 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType=ActivityType.Task,
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Activity](BPMN-Shapes-Images/Activity-Task.png)

## BPMN activity task

The [`TaskType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_TaskType) property of the `BpmnNodeViewModel` allows you to define the type of task such as sending, receiving, user-based task, etc. By default, the TaskType property of task is set to **None**. This is shown by a small event symbol in the top of the corner. The following code explains how to create different types of BPMN tasks.


{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="Task" TaskType="Send"> 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType=ActivityType.Task,
  TaskType = TaskType.Send
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create TaskActivity](BPMN-Shapes-Images/Send.png)

The various types of BPMN tasks are tabulated as follows.

| Task type | Symbol | Description |
| -------- | -------- | -------- |
| Service | ![Service Task BPMN Shape](BPMN-Shapes-Images/Service.png) |A Service Task is a Task that uses a Web service, an automated application, or other kinds of service in completing the task|
| Send | ![Send Task BPMN Shape](BPMN-Shapes-Images/Send.png) |A Send Task is represents a task that sends a Message from one to another. The Task is completed once the Message has been sent|
| Receive | ![Receive Task BPMN Shape](BPMN-Shapes-Images/Receive.png) |A Receive Task indicates that waits for the arrival of a certain message. The Task is completed once the message has received|
| Instantiating Receive | ![Instantiating Receive Task BPMN Shape](BPMN-Shapes-Images/InsService.png) |If a receive task is to instantiate a process, that is, the receive tasks replace message start event |
| Manual |![Manual Task BPMN Shape](BPMN-Shapes-Images/Manual.png) |A Manual Task is a Task that is performed without the aid of any business process execution engine or any application|
| Business Rule | ![Business Rule  Task BPMN Shape](BPMN-Shapes-Images/Bussiness.png) |A Business Rule Task is used to synchronously execute one or more rules|
| User | ![User Task BPMN Shape](BPMN-Shapes-Images/User.png) |A User Task represents that a human performer performs the Task with the use of a software application|
| Script | ![Script Task BPMN Shape](BPMN-Shapes-Images/Script.png) |A Script Task is an automated activity. When a process execution arrives at the Script Task, the corresponding script is executed|

## BPMN activity sub process

A [`CollapsedSubProcess`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.ActivityType.html#fields#CollapsedSubProcess) is a group of tasks that is used to hide or reveal details of additional levels. The following code explains how to create CollapsedSubProcess.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="CollapsedSubProcess" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType=ActivityType.CollapsedSubProcess,
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create CollapsedSubProcess](BPMN-Shapes-Images/CollapsedSubProcess.png)

### Loop

[`LoopActivity`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_LoopActivity) is a task that is internally being looped. The LoopActivity property of BpmnNodeViewModel allows you to define the type of loop. The default value for `LoopActivity` is **None**.

You can define the LoopActivity in both task and collapsed subprocess of the Activity.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="Task" LoopActivity="Standard" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType = ActivityType.Task,
  LoopActivity = LoopCharacteristic.Standard
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Standard](BPMN-Shapes-Images/Loop-Standard.png)

The following table contains various types of BPMN loops.

| LoopActivity | Task | CollapsedSubProcess | Description |
| -------- | -------- | -------- | -------- |
| None | ![None Task BPMN Shape](BPMN-Shapes-Images/Loop-None.png)  | ![None CollapsedSubProcess BPMN Shape](BPMN-Shapes-Images/BPMN-Loop-None.png) |None of the shape shows in the sub-process | 
| Standard | ![Standard Task BPMN Shape](BPMN-Shapes-Images/Loop-Standard.png)  | ![Standard CollapsedSubProcess BPMN Shape](BPMN-Shapes-Images/CollapsedSubProcess-Standard.png) |Loop marker indicates that the sub-process repeats itself in sequence|
| SequenceMultiInstance | ![Sequence MultiInstance Task BPMN Shape](BPMN-Shapes-Images/Loop-SequenceMultiInstance.png) |  ![SequenceMultiInstance CollapsedSubProcess BPMN Shape](BPMN-Shapes-Images/CollapsedSubProcess-SequenceMultiInstance.png) |Multi-Instance marker indicates that the sub-process can run with other identical sub-processes simultaneously.Three horizontal lines indicate sequential execution|
| ParallelMultiInstance | ![ParallelMultiInstance Task BPMNShape](BPMN-Shapes-Images/Loop-ParallelMultiInstance.png) | ![ParallelMultiInstance Task BPMN Shape](BPMN-Shapes-Images/CollapsedSubProcess-ParallelMultiInstance.png) |Multi-Instance marker indicates that the sub-process can run with other identical sub-processes simultaneously.Three vertical lines indicate that the instances will be executed in parallel|

### Compensation

Compensation is triggered when the operation is partially failed and enabled it with the compensation property in both task and the collapsed subprocess. To create a Compensation, you have to enable the [IsCompensationActivity](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_IsCompensationActivity) property of the BPMNNodeViewModel.

>Note: By default, IsCompensationActivity property is false.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="Task" IsCompensationActivity="True" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType = ActivityType.Task,
  IsCompensationActivity = true
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Compensation](BPMN-Shapes-Images/Task-Compensation.png)

### Call

A Call activity is a global subprocess that is reused at various points of the business flow. To create a Call activity, you have to enable the [IsCallActivity](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_IsCallActivity) property of the BPMNNodeViewModel.

>Note: By default, IsCallActivity property is false.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="Task" IsCallActivity="True" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 70,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType = ActivityType.Task,
  IsCallActivity = true
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![Create Call](BPMN-Shapes-Images/Task-Call.png)

### Ad-Hoc

An ad-hoc subprocess is a group of tasks that are executed in any order or skipped in order to fulfill the end condition. To create a ad-hoc activity, you have to enable the [`IsAdhocActivity`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_IsAdhocActivity) property of the BPMNNodeViewModel. 

>Note: By default, IsAdhocActivity property is false.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="100" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="CollapsedSubProcess" IsAdhocActivity="True" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 100,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType = ActivityType.CollapsedSubProcess,
  IsAdhocActivity = true
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![BPMN IsAdhocActivity](BPMN-Shapes-Images/BPMN-IsAdhocActivity.png)

### SubProcessType

SubProcessType represents the type of task that is being processed. The [`SubProcessType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.BpmnNodeViewModel.html#Syncfusion_UI_Xaml_Diagram_BpmnNodeViewModel_SubProcessType) property of BpmnNodeViewModel allows you to define the type of SubProcess. By default, it is set to **Default**.

{% tabs %}
{% highlight xaml %}
<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the Node-->
    <syncfusion:SfDiagram.Nodes>
        <!--Initialize the Node Collection-->
        <syncfusion:NodeCollection>
            <!--Initialize the BpmnNodeViewModel-->
            <syncfusion:BpmnNodeViewModel UnitHeight="100" UnitWidth="100" OffsetX="100" OffsetY="100" Type="Activity" ActivityType="CollapsedSubProcess" SubProcessType="Event" > 
            </syncfusion:BpmnNodeViewModel>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the BpmnNodeViewModel
BpmnNodeViewModel node = new BpmnNodeViewModel()
{
  OffsetX = 100,
  OffsetY = 100,
  UnitHeight = 100,
  UnitWidth = 100,
  Type = BpmnShapeType.Activity,
  ActivityType = ActivityType.CollapsedSubProcess,
  SubProcessType = SubProcessType.Event
};

// Add the node into Node's collection
(Diagram.Nodes as NodeCollection).Add(node);

{% endhighlight %}
{%  endtabs %}

![BPMN SubProcessType](BPMN-Shapes-Images/BPMN-SubProcessType-Event.png)

The following table contains various types of BPMN boundaries.

| SubProcessType | Symbol | Description |
| -------- | -------- | -------- |
| Call | ![Call Boundary BPMN Shape](BPMN-Shapes-Images/BPMN-SubProcessType-Call.png) |It is a global sub-process that is reused at various points in the business flow|
| Event | ![Event Boundary BPMN Shape](BPMN-Shapes-Images/BPMN-SubProcessType-Event.png) |The event subprocess is a subprocess that is triggered by an event.An event subprocess can be added at the process level or at any subprocess level|
| Default | ![Default Boundary BPMN Shape](BPMN-Shapes-Images/BPMN-Loop-None.png) |The task that is performed in a business process. It is represented by a rounded rectangle|
| Transaction | ![Transaction Boundary BPMN Shape](BPMN-Shapes-Images/BPMN-SubProcessType-Transaction.png) |It is a specialized sub-process that involves payment|