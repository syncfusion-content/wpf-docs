---
layout: post
title: Strip Lines| Gantt | Wpf | Syncfusion
description: strip lines
platform: wpf
control: Gantt
documentation: ug
---

# Strip Lines

The Gantt provides support to add strip lines in the Gantt chart region that denotes an important event in a sequential timeline. By using this feature, you can add strip lines to highlight the important days in your project. You can add a collection of strip lines using the provided API.

## Strip lines in Essential Gantt support the following features:

Strip lines can be repeatable in the Gantt chart region based on repeat behavior and repeat interval.

* You can modify the content or appearance of the strip lines at run time by changing the values of the underlying collection source.
* The visibility of strip lines can be toggled using the [`ShowStripLines`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_ShowStripLines) property in the Gantt control.

The Gantt control will get the information from the application to draw the strip lines. Gantt will accept the strip line information in the form of a collection of StripLineInfo objects and process it to draw the strip lines.

### Repeat behavior

The available repeat behaviors are as follows:

* Year
* Month
* Week
* Day
* Hour
* Minute

### Style selector
It used to pass the style of the strip lines dynamically. Based on constraints.
### Template selector
It used to pass the content template of the strip lines dynamically based on constraints.

## Types of strip lines

There are two types of strip lines available in Essential Gantt. They are:

* Regular
* Absolute—Absolute type will place the strip line at any user-defined point. 

## Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
Background</td><td>
Gets/sets background color of strip line.</td><td>
CLR</td><td>
Brush</td></tr>
<tr>
<td>
Content</td><td>
Gets/sets the content of the strip line.</td><td>
CLR</td><td>
Object</td></tr>
<tr>
<td>
ContentTemplate</td><td>
Gets/sets the content template of the strip line.</td><td>
CLR</td><td>
DataTemplate</td></tr>
<tr>
<td>
ContentTemplateSelector</td><td>
Gets/sets the TemplateSelector of the strip line.</td><td>
CLR</td><td>
DataTemplateSelector</td></tr>
<tr>
<td>
StartDate</td><td>
Gets/sets the start date of the strip line.</td><td>
CLR</td><td>
DateTime</td></tr>
<tr>
<td>
EndDate</td><td>
Gets/sets the end date of the strip line.</td><td>
CLR</td><td>
DateTime</td></tr>
<tr>
<td>
RepeatBehavior</td><td>
Gets/sets the repeat behavior of the strip line.</td><td>
CLR</td><td>
Repeat (Enum)</td></tr>
<tr>
<td>
RepeatFor</td><td>
Gets/sets the intervals between the repeating strip lines.</td><td>
CLR</td><td>
Integer</td></tr>
<tr>
<td>
RepeatUpto</td><td>
Gets/sets DateTime value. The strip line will be repeated up to this value.</td><td>
CLR</td><td>
DateTime</td></tr>
<tr>
<td>
Style</td><td>
Gets/sets the style for the strip line.</td><td>
CLR</td><td>
Style</td></tr>
<tr>
<td>
StyleSelector</td><td>
Gets/sets the style selector of the strip line.</td><td>
CLR</td><td>
StyleSelector</td></tr>
<tr>
<td>
VerticalContentAlignment</td><td>
Gets/sets the vertical alignment of the content present in the strip line.</td><td>
CLR</td><td>
VerticalAlignment</td></tr>
<tr>
<td>
HorizontalContentAlignment</td><td>
Gets/sets the horizontal alignment of the content present in the strip line.</td><td>
CLR</td><td>
Horizontal Alignment</td></tr>
<tr>
<td>
Type</td><td>
Gets/sets the type of the strip line.</td><td>
CLR</td><td>
StriplineType(Enum)</td></tr>
<tr>
<td>
Position</td><td>
Gets/sets the absolute position of the strip line for Absolute strip line type.</td><td>
CLR</td><td>
Point</td></tr>
<tr>
<td>
Height</td><td>
Gets/sets the absolute height of the strip line for Absolute strip line type.</td><td>
CLR</td><td>
Double</td></tr>
<tr>
<td>
Width</td><td>
Get/sets the absolute width of the strip line for Absolute strip line type.</td><td>
CLR</td><td>
Double</td></tr>
</table>


### Use Case Scenarios

* You can mark the important dates and meetings in the scheduled time line.
* Strip lines help you to avoid missing important events.

### Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
ShowStripLines</td><td>
Get the user option to show the strip lines.</td><td>
Dependency Property</td><td>
Bool</td></tr>
<tr>
<td>
StripLines</td><td>
Get/sets the collection of StripLineInfo from the user.</td><td>
Dependency Property</td><td>
IEnumerable</td></tr>
</table>


### Enums



<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
Repeat</td><td>
This property contains the following values:Year: Repeating the strip line on a yearly basis depends on the RepeatFor value in StripLineInfo.Month: Repeating the strip line on a monthly basis depends on the RepeatFor value in StripLineInfo.Week: Repeating the strip line on a weekly basis depends on the RepeatFor value in StripLineInfo.Day: Repeating the strip line on a daily basis depends on the RepeatFor value in StripLineInfo.Hour: Repeating the strip line on an hourly basis depends on the RepeatFor value in StripLineInfo.Minute: Repeating the strip line on per-minute basis depends on the RepeatFor value in StripLineInfo.</td></tr>
<tr>
<td>
StriplineType</td><td>
This property contains the following values:Regular: This denotes the normal strip line.Absolute: This denotes the absolute strip line. You can customize the position, size, and appearance of the strip line in this type.</td></tr>
</table>


### Events

By handling its event, you can customize the strip lines dynamically.

<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th><th>
Type</th></tr>
<tr>
<td>
StripLineCreated </td><td>
Whenever a strip line is created, this event will be triggered. the handler of the event will have the newly created strip line (StripLineInfo) in the argument.By handling this event, you can customize the appearance of the strip line.</td><td>
StripLineCreated(object sender, StriplineCreatedEventArgs args)</td><td>
Event </td></tr>
</table>

## Adding strip lines to application

### Regular strip lines

The following code sample demonstrates how to define a collection of regular strip lines.

{% highlight c# %}


StripCollection =  new List<StripLineInfo>();

//Getting the collection of StripLineInfo
StripCollection = GetStripCollection();

//Method will return the collection StripLineInfo
private List<StripLineInfo> GetStripCollection()

{
    List<StripLineInfo> stripCollection = new List<StripLineInfo>();
    stripCollection.Add(new StripLineInfo() 
    { 
        Content =  "Weekly Team Meeting", 
        StartDate = new DateTime(2012, 6, 4), 
        EndDate = new DateTime(2012, 6, 4), 
        HorizontalContentAlignment = HorizontalAlignment.Center, 
        VerticalContentAlignment = VerticalAlignment.Center, 
        Background =  Brushes.Gold, RepeatBehavior = Repeat.Week, RepeatFor = 1,
        RepeatUpto = new DateTime(2012, 12, 10),
    });

    return stripCollection;
}


{% endhighlight  %}

The following code sample demonstrates how to bind the regular strip line collection to strip lines.

{% highlight xaml %}


<sync:GanttControl x:Name="Gantt"
                   Grid.Row="1"
                   ShowStripLines="True"
                   StripLines="{Binding StripCollection}">
    <sync:GanttControl.TaskAttributeMapping>
        <sync:TaskAttributeMapping TaskIdMapping="TaskId"
                                   TaskNameMapping="TaskName"
                                   StartDateMapping="StartDate"
                                   FinishDateMapping="FinishDate"
                                   ChildMapping="Child"
                                   DurationMapping="Duration"
                                   ProgressMapping="Progress"
                                   PredecessorMapping="Predecessor"
                                   ResourceInfoMapping="Resources"/>
    </sync:GanttControl.TaskAttributeMapping>
</sync:GanttControl>                                                

{% endhighlight  %}

### Output

The following screenshot illustrates how to render the regular strip lines.


![WPF Gantt with regular strip line](Strip-Lines_images/Strip-Lines_img1.png)

Strip lines in the Gantt chart
{:.caption}

### Absolute Strip lines

The following code sample demonstrates how to define a collection of absolute strip lines.

{% highlight c# %}


StripCollection =  new List<StripLineInfo>();

//Getting the collection of StripLineInfo
StripCollection = GetStripCollection();

//Method will return the collection StripLineInfo
private List<StripLineInfo> GetStripCollection()

{
    List<StripLineInfo> stripCollection = new List<StripLineInfo>();
    stripCollection.Add(new StripLineInfo()
    {
        Type = StriplineType.Absolute,
        Height = 1500,
        Width = 200,
        Position = new System.Windows.Point(300, 5),
        Background = new SolidColorBrush(Colors.LightGray)
    });
    return stripCollection;
}


{% endhighlight  %}

The following code sample demonstrates how to bind the absolute strip line collection to strip lines.

{% highlight xaml %}


<sync:GanttControl x:Name="Gantt"
                   Grid.Row="1"
                   ShowStripLines="True"
                   StripLines="{Binding StripCollection}">
    <sync:GanttControl.TaskAttributeMapping>
        <sync:TaskAttributeMapping TaskIdMapping="TaskId"
                                   TaskNameMapping="TaskName"
                                   StartDateMapping="StartDate"
                                   FinishDateMapping="FinishDate"
                                   ChildMapping="Child"
                                   DurationMapping="Duration"
                                   ProgressMapping="Progress"
                                   PredecessorMapping="Predecessor"
                                   ResourceInfoMapping="Resources"/>
    </sync:GanttControl.TaskAttributeMapping>
</sync:GanttControl>                                                

{% endhighlight  %}

### Output

The following screenshot illustrates how to render the absolute strip lines.

![WPF Gantt with absolute strip line](Strip-Lines_images/Strip-Lines_absolute.png)


Strip lines in the Gantt chart
{:.caption}

### Sample Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel.
4. Select Gantt.
5. Expand the Interactive Features item in the Sample Browser.
6. Choose the Strip Lines sample to launch.



