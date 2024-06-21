---
layout: post
title: Custom Schedule in WPF Gantt control | Syncfusion
description: Learn about Custom Schedule support in Syncfusion Essential Studio WPF Gantt control, its elements and more details.
platform: wpf
control: Gantt
documentation: ug
---

# Custom Schedule in WPF Gantt

Essential Gantt provides the custom schedule support that allows you to define your own schedule for Gantt to track the progress of projects. You can define the schedule for any measurement unit or for different types of date time formats namely quarterly basis scale and so on.

This feature will get the information from you and will draw the Gantt schedule with that information. Custom schedule is categorized into two types namely: 

* Custom Numeric 
* Custom DateTime

These types are included in the existing ScheduleType enum.

## Custom Numeric

Custom Numeric schedule is used to define your own schedule with any numeric measurement unit other than date time. With this schedule, you can track the progress based on your own measurement and there is no need to depend on Date Time. Two new API’s are added to the Mapping attributes to support this schedule in GanttChart and GanttGrid.

## Custom DateTime

Custom DateTime schedule is used to define your own date time schedule, which can match your current financial calendar. By using schedule type as custom schedule, you can define your schedule on quarterly basis.

In both the custom schedules, Gantt will get the information from the application to render the schedule. Gantt will accept the custom schedule information in the form of a collection of GanttScheduleRowInfo object, and process it to draw the schedule. 

GanttScheduleRowInfo class will have following fields:

1. PixelsPerUnit—Gets the information of the pixel value equivalent to one unit in custom measurement.
2. CellsPerUnit—Gets the information of a cell size of preceding row in the schedule based on the immediate next row. In CustomDateTime Schedule, the CellsPerUnit will be used to customize the cell. For example, in quarterly basis month cell, You need to draw a schedule by consolidating three months. For this, you need to define the CellsPerUnit of that corresponding row as 3.
3. TimeUnit—Gets the information about the type of row, when the schedule type is CustomDateTime. The Time unit can be any one of the following:

    * Seconds-represents the corresponding row as second's row.
    * Minutes—represents the corresponding row as minute’s row.
    * Hours—represents the corresponding row as hour’s row.
    * Days—represents the corresponding row as day’s row.
    * Weeks—represents the corresponding row as week’s row.
    * Months—represents the corresponding row as month’s row.
    * Years—represents the corresponding row as year’s row.

#### Use Case Scenario

This will be useful when you like to define your own schedules with your own measurements/calendars.

Example 1: The Research organizations may follow different measurements to track their work progress and the measurement will depend on their products. In this case, they can use CustomNumeric schedule to define the schedule with their own measure.

Example 2: A very big construction project many have the time period of many years or months. They need some customized way of date time schedule to track their progress. In this scenario, they can use the CustomDateTime schedule to form the custom schedule like the schedule that has the time scale on quarterly basis to track their progress.

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
CustomScheduleSource</td><td>
Gets/Sets the custom schedule items Source of the Gantt.</td><td>
DependencyProperty </td><td>
IList&lt;GanttScheduleRowInfo&gt;</td></tr>
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
ScheduleCellCreated </td><td>
Event will be triggered whenever a schedule cell is created. The handler of the event will have the newly created cell (GanttScheduleCell) in the argument.By handling this event, you can customize the appearance of the cell. </td><td>
ScheduleCellCreated (object sender, ScheduleCellCreatedEventArgs args)</td><td>
Routed Event </td></tr>
</table>

## GanttScheduleCell Class

The properties of the GanttScheduleCell class are as follows:

#### Properties

<table>
<tr>
<th>
Property</th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
CellDate</td><td>
Gets/Sets the current schedule cell date in the datetime schedule. </td><td>
Dependency Property </td><td>
DateTime</td></tr>
<tr>
<td>
CellToolTip</td><td>
Gets/Sets the current schedule cell tool tip.</td><td>
Dependency Property</td><td>
Object</td></tr>
<tr>
<td>
CellTimeUnit</td><td>
Gets/Sets the current schedule row time unit (like weeks, months and so on).</td><td>
Dependency Property</td><td>
TimeUnit (Enum)</td></tr>
<tr>
<td>
Content</td><td>
Gets/Sets the current schedule cell content.</td><td>
Dependency Property</td><td>
Object</td></tr>
</table>

## Adding Custom Schedule to an Application

To Add CustomNumeric Schedule to an application:

1. Define the Mapping for StartPointMapping and FinishPointMapping in TaskAttributeMapping.
1. Set the Gantt Schedule type as CustomNumeric.
2. Bind the GanttScheduleRowInfo collection to the CustomScheduleSource property of the Gantt.

The following code illustrates Adding Custom Schedule to an Application:

{% tabs  %}
{% highlight xaml %}

<!--Gantt node style-->
 <Style x:Key="TopCountriesNode" TargetType="{x:Type gantt:GanttNode}">
     <Setter Property="Template">
         <Setter.Value>
             <ControlTemplate TargetType="{x:Type gantt:GanttNode}">
                 <Border
                     Name="PART_Border"
                     Height="21"
                     VerticalAlignment="Center"
                     BorderThickness="0.5"
                     Opacity="0.8">
                     <interact:Interaction.Behaviors>
                         <local:NumericGanttNodeCustomizationBehavior />
                     </interact:Interaction.Behaviors>
                     <Grid>
                         <Grid.ColumnDefinitions>
                             <ColumnDefinition Width="Auto" />
                             <ColumnDefinition Width="*" />
                             <ColumnDefinition Width="Auto" />
                         </Grid.ColumnDefinitions>

                         <Thumb
                             x:Name="PART_DragDropThumb"
                             Grid.Column="0"
                             Grid.ColumnSpan="3"
                             Cursor="SizeAll">
                             <Thumb.Template>
                                 <ControlTemplate>
                                     <Border Background="Transparent" />
                                 </ControlTemplate>
                             </Thumb.Template>
                         </Thumb>
                         <Grid
                             Grid.Column="0"
                             Grid.ColumnSpan="3"
                             Width="{TemplateBinding Width}"
                             HorizontalAlignment="Stretch"
                             VerticalAlignment="Center">
                             <TextBlock
                                 Margin="0,0,20,0"
                                 HorizontalAlignment="Right"
                                 Foreground="White"
                                 IsHitTestVisible="False"
                                 Text="{Binding End, StringFormat='\{0\}%'}" />
                         </Grid>
                         <Thumb
                             x:Name="PART_RightThumb"
                             Grid.Column="2"
                             HorizontalAlignment="Right"
                             Cursor="ScrollE">
                             <Thumb.Template>
                                 <ControlTemplate>
                                     <Rectangle
                                         Width="6"
                                         Height="20"
                                         HorizontalAlignment="Right"
                                         VerticalAlignment="Center"
                                         Fill="Transparent" />
                                 </ControlTemplate>
                             </Thumb.Template>
                         </Thumb>
                         <Thumb
                             x:Name="PART_LeftThumb"
                             Grid.Column="0"
                             HorizontalAlignment="Left"
                             Cursor="ScrollW">
                             <Thumb.Template>
                                 <ControlTemplate>
                                     <Border
                                         Width="4"
                                         Height="20"
                                         Background="Transparent"
                                         BorderBrush="Transparent"
                                         BorderThickness="0" />
                                 </ControlTemplate>
                             </Thumb.Template>
                         </Thumb>
                     </Grid>
                 </Border>
             </ControlTemplate>
         </Setter.Value>
     </Setter>
 </Style>

<!--Milestone style-->
 <Style x:Key="MileStone" TargetType="gantt:MileStone">
     <Setter Property="Template">
         <Setter.Value>
             <ControlTemplate TargetType="gantt:MileStone">
                 <Grid>
                     <Path
                         Width="17"
                         Height="19"
                         HorizontalAlignment="Left"
                         VerticalAlignment="Center"
                         Data="F1 M 551.156,416.878L 552.734,419.766L 555.621,421.344L 552.734,422.922L 551.156,425.81L 549.577,422.922L 546.69,421.344L 549.577,419.766L 551.156,416.878 Z "
                         Fill="#FFE71400"
                         Stretch="Fill"
                         Stroke="#FFE71400" />
                 </Grid>
             </ControlTemplate>
         </Setter.Value>
     </Setter>
 </Style>
 
<syncfusion:GanttControl x:Name="ganttControl"
                         CustomScheduleSource="{Binding CustomScheduleInfo}"
                         ItemsSource="{Binding TopCountriesCollection}"
                         ScheduleType="CustomNumeric"
                         UseAutoUpdateHierarchy="False">
    <syncfusion:GanttControl.TaskAttributeMapping>
        <syncfusion:TaskAttributeMapping TaskIdMapping="Id"                    
                                         TaskNameMapping="Name"                
                                         StartPointMapping="Start" 
                                         FinishPointMapping="End"              
                                         ChildMapping="ChildTask"              
                                         ProgressMapping="Complete"
                                         ResourceInfoMapping="Resource">
        </syncfusion:TaskAttributeMapping>
    </syncfusion:GanttControl.TaskAttributeMapping>
 <syncfusion:GanttControl.Resources>
    <Style BasedOn="{StaticResource TopCountriesNode}" TargetType="gantt:GanttNode" />
    <Style BasedOn="{StaticResource MileStone}" TargetType="gantt:MileStone" />
 </syncfusion:GanttControl.Resources>
    <syncfusion:GanttControl.DataContext>
        <local:ViewModel/>
    </syncfusion:GanttControl.DataContext>
</syncfusion:GanttControl>

{% endhighlight  %}
{% highlight c# %}

//Initializing Gantt
this.ganttControl.ItemsSource = new ViewModel().TaskCollections;
this.ganttControl.ScheduleType= ScheduleType.CustomNumeric;
this.ganttControl.UseAutoUpdateHierarchy = false;

// Task attribute mapping
TaskAttributeMapping taskAttributeMapping = new TaskAttributeMapping();
taskAttributeMapping.TaskIdMapping = "Id";
taskAttributeMapping.TaskNameMapping = "Name";
taskAttributeMapping.StartDateMapping = "Start";
taskAttributeMapping.ChildMapping = "ChildTask";
taskAttributeMapping.FinishDateMapping = "End";
taskAttributeMapping.ProgressMapping = "Complete";
taskAttributeMapping.ResourceInfoMapping = "Resource";
this.ganttControl.TaskAttributeMapping = taskAttributeMapping;

{% endhighlight  %}

{% highlight c# tabtitle="ViewModel.cs" %}

 public class ViewModel
 {
    /// <summary>
    /// Holds the custom schedule information.
    /// </summary>
    private ObservableCollection<GanttScheduleRowInfo> _customScheduleInfo;

    /// <summary>
    /// Holds the top countries collections.
    /// </summary>
    private ObservableCollection<TopCountries> _topCountriesCollection;

     public ViewModel()
     {
         this.CreateCountryCollection();
         this._topCountriesCollection = GetData();
         this._customScheduleInfo = GetCustomScheduleInfo();
     }

     /// <summary>
     /// Collection which is used to store the CountryNamesWith their Flags
     /// </summary>
     internal static Dictionary<string, string> CountryNamesandFlags = new Dictionary<string, string>();

     /// <summary>
     /// Gets or sets the custom schedule info.
     /// </summary>
     /// <value>The custom schedule info.</value>
     public ObservableCollection<GanttScheduleRowInfo> CustomScheduleInfo
     {
         get
         {
             return this._customScheduleInfo;
         }
         set
         {
             this._customScheduleInfo = value;
         }
     }
     
     /// <summary>
     /// Gets or sets the appointment item source.
     /// </summary>
     /// <value>The appointment item source.</value>
     public ObservableCollection<TopCountries> TopCountriesCollection
     {
         get
         {
             return this._topCountriesCollection;
         }
         set
         {
             this._topCountriesCollection = value;
         }
     }


     /// <summary>
     /// Gets the Numeric Schedule Items Info
     /// </summary>
     /// <returns></returns>
     private ObservableCollection<GanttScheduleRowInfo> GetCustomScheduleInfo()
     {
         ObservableCollection<GanttScheduleRowInfo> RowInfo = new ObservableCollection<GanttScheduleRowInfo>();
         RowInfo.Add(new GanttScheduleRowInfo() { CellsPerUnit = 5 });
         RowInfo.Add(new GanttScheduleRowInfo() { CellsPerUnit = 2, PixelsPerUnit = 30d });
         return RowInfo;
     }

     /// <summary>
     /// Gets the data.
     /// </summary>
     /// <returns></returns>
     public ObservableCollection<TopCountries> GetData()
     {
         var taskDetails = new ObservableCollection<TopCountries>();

         taskDetails.Add(new TopCountries() { Id = 1, Name = "Afghanistan", Start = 0, End = 8.227, Rank = 17 });
         taskDetails.Add(new TopCountries() { Id = 2, Name = "Argentina", Start = 0, End = 9.161, Rank = 8 });
         taskDetails.Add(new TopCountries() { Id = 3, Name = "Belarus", Start = 0, End = 7.6, Rank = 27 });
         taskDetails.Add(new TopCountries() { Id = 4, Name = "Botswana", Start = 0, End = 8.562, Rank = 13 });
         taskDetails.Add(new TopCountries() { Id = 5, Name = "Brazil", Start = 0, End = 7.49, Rank = 31 });
         taskDetails.Add(new TopCountries() { Id = 6, Name = "Democratic Republic of the Congo", Start = 0, End = 7.245, Rank = 32 });
         taskDetails.Add(new TopCountries() { Id = 7, Name = "Dominican Republic", Start = 0, End = 7.751, Rank = 23 });
         taskDetails.Add((new TopCountries() { Id = 8, Name = "Ethiopia", Start = 0, End = 8.008, Rank = 20 }));
         taskDetails.Add((new TopCountries() { Id = 9, Name = "India", Start = 0, End = 11.1, Rank = 4 }));
         taskDetails.Add((new TopCountries() { Id = 10, Name = "Laos", Start = 0, End = 7.747, Rank = 24 }));
         taskDetails.Add((new TopCountries() { Id = 11, Name = "Lebanon", Start = 0, End = 7.5, Rank = 30, }));
         taskDetails.Add((new TopCountries() { Id = 12, Name = "Malaysia", Start = 0, End = 7.156, Rank = 33 }));
         taskDetails.Add(new TopCountries() { Id = 13, Name = "Maldives", Start = 0, End = 7.969, Rank = 21, });
         taskDetails.Add((new TopCountries() { Id = 14, Name = "Mozambique", Start = 0, End = 7.009, Rank = 35 }));
         taskDetails.Add((new TopCountries() { Id = 15, Name = "Niger", Start = 0, End = 7.53, Rank = 28, }));
         taskDetails.Add((new TopCountries() { Id = 16, Name = "Nigeria", Start = 0, End = 8.394, Rank = 16, }));
         taskDetails.Add((new TopCountries() { Id = 17, Name = "Panama", Start = 0, End = 7.505, Rank = 29, }));
         taskDetails.Add(new TopCountries() { Id = 18, Name = "Papua New Guinea", Start = 0, End = 7.03, Rank = 34 });
         taskDetails.Add((new TopCountries() { Id = 19, Name = "Paraguay", Start = 0, End = 14.40, Rank = 3 }));
         taskDetails.Add((new TopCountries() { Id = 20, Name = "People's Republic of China", Start = 0, End = 10.3, Rank = 6 }));
         taskDetails.Add((new TopCountries() { Id = 21, Name = "Peru", Start = 0, End = 8.795, Rank = 12 }));
         taskDetails.Add((new TopCountries() { Id = 22, Name = "Philippines", Start = 0, End = 7.6, Rank = 26 }));
         taskDetails.Add((new TopCountries() { Id = 23, Name = "Qatar", Start = 0, End = 16.272, Rank = 1 }));
         taskDetails.Add(new TopCountries() { Id = 24, Name = "Republic of China(Taiwan)", Start = 0, End = 10.8, Rank = 6 });
         taskDetails.Add((new TopCountries() { Id = 25, Name = "Republic of the Congo", Start = 0, End = 9.09, Rank = 10 }));
         taskDetails.Add((new TopCountries() { Id = 26, Name = "Singapore", Start = 0, End = 15.27, Rank = 2 }));
         taskDetails.Add((new TopCountries() { Id = 27, Name = "Sri Lanka", Start = 0, End = 9.134, Rank = 9 }));
         taskDetails.Add((new TopCountries() { Id = 28, Name = "Thailand", Start = 0, End = 7.803, Rank = 22 }));
         taskDetails.Add(new TopCountries() { Id = 29, Name = "Turkey", Start = 0, End = 8.2, Rank = 18 });
         taskDetails.Add((new TopCountries() { Id = 30, Name = "Turkmenistan", Start = 0, End = 9.222, Rank = 7 }));
         taskDetails.Add((new TopCountries() { Id = 31, Name = "Uruguay", Start = 0, End = 8.468, Rank = 15 }));
         taskDetails.Add((new TopCountries() { Id = 32, Name = "Uzbekistan", Start = 0, End = 8.5, Rank = 14 }));
         taskDetails.Add((new TopCountries() { Id = 33, Name = "Yemen", Start = 0, End = 8.016, Rank = 19 }));
         taskDetails.Add(new TopCountries() { Id = 34, Name = "Zambia", Start = 0, End = 7.601, Rank = 25 });
         taskDetails.Add((new TopCountries() { Id = 35, Name = "Zimbabwe", Start = 0, End = 9.006, Rank = 11 }));

         return taskDetails;
     }

     #region Image and Country Collection
     /// <summary>
     /// Creates the country collection with the corresponding Image.
     /// </summary>
     void CreateCountryCollection()
     {
         CountryNamesandFlags.Add("Afghanistan", "Flag_Afghanistan.png");
         CountryNamesandFlags.Add("Argentina", "Flag_Argentina.png");
         CountryNamesandFlags.Add("Belarus", "Flag_Belarus.png");
         CountryNamesandFlags.Add("Botswana", "Flag_Botswana.png");
         CountryNamesandFlags.Add("Brazil", "Flag_Brazil.png");
         CountryNamesandFlags.Add("Democratic Republic of the Congo", "Flag_Democratic_Republic_of_the_Congo.png");
         CountryNamesandFlags.Add("Dominican Republic", "Flag_Dominican_Republic.png");
         CountryNamesandFlags.Add("Ethiopia", "Flag_Ethiopia.png");
         CountryNamesandFlags.Add("India", "Flag_India.png");
         CountryNamesandFlags.Add("Laos", "Flag_Laos.png");
         CountryNamesandFlags.Add("Lebanon", "Flag_Lebanon.png");
         CountryNamesandFlags.Add("Malaysia", "Flag_Malaysia.png");
         CountryNamesandFlags.Add("Maldives", "Flag_Maldives.png");
         CountryNamesandFlags.Add("Mozambique", "Flag_Mozambique.png");
         CountryNamesandFlags.Add("Niger", "Flag_Niger.png");
         CountryNamesandFlags.Add("Nigeria", "Flag_Nigeria.png");
         CountryNamesandFlags.Add("Panama", "Flag_Panama.png");
         CountryNamesandFlags.Add("Papua New Guinea", "Flag_Papua_New_Guinea.png");
         CountryNamesandFlags.Add("Paraguay", "Flag_Paraguay.png");
         CountryNamesandFlags.Add("People's Republic of China", "Flag_People's_Republic_of_China.png");
         CountryNamesandFlags.Add("Peru", "Flag_Peru.png");
         CountryNamesandFlags.Add("Philippines", "Flag_Philippines.png");
         CountryNamesandFlags.Add("Qatar", "Flag_Qatar.png");
         CountryNamesandFlags.Add("Republic of China(Taiwan)", "Flag_Republic_of_China.png");
         CountryNamesandFlags.Add("Republic of the Congo", "Flag_Republic_of_the_Congo.png");
         CountryNamesandFlags.Add("Singapore", "Flag_Singapore.png");
         CountryNamesandFlags.Add("Sri Lanka", "Flag_Sri_Lanka.png");
         CountryNamesandFlags.Add("Thailand", "Flag_Thailand.png");
         CountryNamesandFlags.Add("Turkey", "Flag_Turke.png");
         CountryNamesandFlags.Add("Turkmenistan", "Flag_Turkmenistan.png");
         CountryNamesandFlags.Add("Uruguay", "Flag_Uruguay.png");
         CountryNamesandFlags.Add("Uzbekistan", "Flag_Uzbekistan.png");
         CountryNamesandFlags.Add("Yemen", "Flag_Yemen.png");
         CountryNamesandFlags.Add("Zambia", "Flag_Zambia.png");
         CountryNamesandFlags.Add("Zimbabwe", "Flag_Zimbabwe.png");

     }
     #endregion
 }

{% endhighlight  %}
{% endtabs %}

The following image shows Custom Schedule:

![gantt-control-custom-numeric-schedule](Custom-Schedule_images/gantt-control-custom-numeric-schedule.png)

Custom Schedule
{:.caption}

## Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under the User Interface Edition panel.
4. Select Gantt.
5. Expand the Custom Schedule item in the Sample Browser.
6. Choose the Custom Numeric Schedule sample to launch.

## Adding CustomDateTime Schedule to an Application

To Add CustomDateTime Schedule to an application:

1. Define the Gantt Schedule type as CustomDateTime.
2. Bind the GanttScheduleRowInfo collection to the CustomScheduleSource property of the Gantt.

The following code illustrates this:

{% tabs %}
{% highlight xaml %}

<syncfusion:GanttControl x:Name="ganttControl"
                         ScheduleType="CustomDateTime"
                         ShowChartLines="False"
                         ShowNonWorkingHoursBackground="False"
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

this.ganttControl.ItemsSource = new ViewModel().TaskCollections;
this.ganttControl.ScheduleType= ScheduleType.CustomDateTime;
this.ganttControl.ShowChartLines = false;
this.ganttControl.ShowNonWorkingHoursBackground = false;

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

// Assigning the custom schedule Items Source.
this.ganttControl.CustomScheduleSource = this.GetCustomScheduleSource();

// Hooks the schedule cell created event to customize the schedule cell appearance.
this.ganttControl.ScheduleCellCreated += this.OnGanttScheduleCellCreated;

// Gets the Custom Schedule Items Info
public IList<GanttScheduleRowInfo> GetCustomScheduleSource()
{
    List<GanttScheduleRowInfo> RowInfo = new List<GanttScheduleRowInfo>();

    // Defining the top most row of the schedule
    // Here we need the Year Schedule in this row. So we are defining  the TimeUnit as years
    RowInfo.Add(new GanttScheduleRowInfo()
    {
        TimeUnit = TimeUnit.Years,
        CellsPerUnit = 1,
        HorizontalAlignment = HorizontalAlignment.Left
    });

    // Defining the bottom most row of the schedule
    // Here we need to display the three months in a cell so we are defining TimeUnit in months, and cells per Unit as 3 
    // Bottom Most row should consist information about the pixels per Unit, so we define the pixels per unit as 15 (here this is a one month width).
    RowInfo.Add(new GanttScheduleRowInfo()
    {
        TimeUnit = TimeUnit.Months,
        CellsPerUnit = 3,
        PixelsPerUnit = 15
    });

    return RowInfo;
}

/// Handles the Schedule cell Created Event of the Gantt 

void Gantt_ScheduleCellCreated(object sender, ScheduleCellCreatedEventArgs args)
{
    DateTime currentDate = args.CurrentCell.CellDate;
    if (args.CurrentCell.CellTimeUnit == TimeUnit.Months)
    {
        args.CurrentCell.Foreground = new SolidColorBrush(Colors.White);
        // Quarter 1 dates contain months below 3 as we are checking the cell date and changing the content of the cell.
        if (currentDate.Month <= 3)
        {
            args.CurrentCell.Content = "Q 1";
            args.CurrentCell.CellToolTip = "Quarter 1";
            args.CurrentCell.Background = new SolidColorBrush(Colors.DarkGray);
        }

        // Quarter 2 dates contain months between 4 – 6 as we are checking the cell dates and changing the content of the cell.
        else if (currentDate.Month > 3 && currentDate.Month <= 6)
        {
            args.CurrentCell.Content = "Q 2";
            args.CurrentCell.CellToolTip = "Quarter 2";
            args.CurrentCell.Background = new SolidColorBrush(Colors.LightGray);
        }

        // Quarter 3 dates contains months between 6 - 9 as we are checking the cell date and changing the Content of the cell.
        else if (currentDate.Month > 6 && currentDate.Month <= 9)
        {
            args.CurrentCell.Content = "Q 3";
            args.CurrentCell.CellToolTip = "Quarter 3";
            args.CurrentCell.Background = new SolidColorBrush(Colors.DarkGray);
        }

        // Quarter 4 dates contains months between 9 - 12. So we are checking the cell date and changing the content of the cell.
        else if (currentDate.Month > 9 && currentDate.Month <= 12)
        {
            args.CurrentCell.Content = "Q 4";
            args.CurrentCell.CellToolTip = "Quarter 4";
            args.CurrentCell.Background = new SolidColorBrush(Colors.LightGray);
        }
    }

}

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
    /// Gets or sets the id value.
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
    /// Gets or sets name.
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
    /// Gets or sets the progress.
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
    ///  Gets or sets the child collection.
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
    TaskCollection = this.GetDataSource();
    }

    /// <summary>
    /// Gets the data.
    /// </summary>
    /// <returns></returns>
    private ObservableCollection<Task> GetDataSource()
    {
        var taskDetails = new ObservableCollection<Task>();
        taskDetails.Add(new Task() { ID = 1, Name = "Scope", StartDate = new DateTime(2011, 8, 9), EndDate = new DateTime(2012, 6, 20), Progress = 40d });
        taskDetails[0].ChildCollection.Add((new Task() { ID = 2, Name = "Determine project office scope", StartDate = new DateTime(2011, 8, 9), EndDate = new DateTime(2012, 2, 20), Progress = 20d, }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 3, Name = "Justify Project Offfice via business model", StartDate = new DateTime(2011, 11, 6), EndDate = new DateTime(2012, 4, 7), Progress = 20d, }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 4, Name = "Secure executive sponsorship", StartDate = new DateTime(2012, 2, 10), EndDate = new DateTime(2012, 6, 14), Progress = 10d, }));
        taskDetails[0].ChildCollection.Add((new Task() { ID = 5, Name = "Secure Progress", StartDate = new DateTime(2012, 6, 14), EndDate = new DateTime(2012, 9, 14), Progress = 10d }));

        taskDetails.Add(new Task() { ID = 6, Name = "Risk Assessment", StartDate = new DateTime(2012, 7, 15), EndDate = new DateTime(2011, 7, 24) });
        taskDetails[1].ChildCollection.Add((new Task() { ID = 7, Name = "Perform risk assessment", StartDate = new DateTime(2012, 2, 15), EndDate = new DateTime(2012, 8, 21), Progress = 20d, }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 8, Name = "Evaluate risk assessment", StartDate = new DateTime(2012, 5, 21), EndDate = new DateTime(2012, 7, 23), Progress = 20d, }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 9, Name = "Prepare contingency plans", StartDate = new DateTime(2012, 8, 21), EndDate = new DateTime(2013, 2, 24), Progress = 20d, }));
        taskDetails[1].ChildCollection.Add((new Task() { ID = 10, Name = "Risk Assessment Progress", StartDate = new DateTime(2012, 4, 24), EndDate = new DateTime(2012, 9, 24), Progress = 30d }));

        taskDetails.Add(new Task() { ID = 11, Name = "Monitoring", StartDate = new DateTime(2012, 7, 25), EndDate = new DateTime(2012, 8, 6), Duration = new TimeSpan(1, 0, 0, 0) });
        taskDetails[2].ChildCollection.Add((new Task() { ID = 12, Name = "Prepare Meeting agenda", StartDate = new DateTime(2012, 9, 25), EndDate = new DateTime(2012, 12, 26), Progress = 20d, }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 13, Name = "Conduct review meeting", StartDate = new DateTime(2013, 1, 27), EndDate = new DateTime(2013, 7, 30), Progress = 20d, }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 14, Name = "Migrate critical issues", StartDate = new DateTime(2013, 3, 30), EndDate = new DateTime(2013, 7, 2), Progress = 20d, }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 15, Name = "Estabilish change mgmt Control", StartDate = new DateTime(2013, 5, 3), EndDate = new DateTime(2013, 9, 6), Progress = 30d, }));
        taskDetails[2].ChildCollection.Add((new Task() { ID = 16, Name = "Monitoring Progress", StartDate = new DateTime(2013, 7, 6), EndDate = new DateTime(2013, 12, 6), Progress = 30d }));

        taskDetails.Add(new Task() { ID = 17, Name = "Post Implementation", StartDate = new DateTime(2013, 7, 25), EndDate = new DateTime(2012, 3, 12) });
        taskDetails[3].ChildCollection.Add((new Task() { ID = 18, Name = "Obtain User feedback", StartDate = new DateTime(2013, 7, 25), EndDate = new DateTime(2014, 4, 29), Progress = 20d, }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 19, Name = "Evaluate lessons learned", StartDate = new DateTime(2013, 10, 29), EndDate = new DateTime(2014, 7, 5), Progress = 20d, }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 20, Name = "Modify items as necessary", StartDate = new DateTime(2014, 1, 2), EndDate = new DateTime(2014, 9, 8), Progress = 20d, }));
        taskDetails[3].ChildCollection.Add((new Task() { ID = 21, Name = "Post Implementation Progress", StartDate = new DateTime(2014, 4, 8), EndDate = new DateTime(2014, 9, 12), Progress = 30d }));

        taskDetails[0].ChildCollection[0].Resource.Add(new Resource() { ID = 1, Name = "Leslie" });
        taskDetails[0].ChildCollection[1].Resource.Add(new Resource() { ID = 2, Name = "John" });
        taskDetails[0].ChildCollection[2].Resource.Add(new Resource() { ID = 3, Name = "DavID" });
        taskDetails[0].ChildCollection[3].Resource.Add(new Resource() { ID = 4, Name = "Peter" });

        taskDetails[1].ChildCollection[0].Resource.Add(new Resource() { ID = 5, Name = "Neil" });
        taskDetails[1].ChildCollection[1].Resource.Add(new Resource() { ID = 7, Name = "Johnson" });
        taskDetails[1].ChildCollection[1].Resource.Add(new Resource() { ID = 8, Name = "Julie" });
        taskDetails[1].ChildCollection[2].Resource.Add(new Resource() { ID = 9, Name = "Peterson" });
        taskDetails[1].ChildCollection[3].Resource.Add(new Resource() { ID = 10, Name = "Thomas" });

        taskDetails[3].ChildCollection[1].Resource.Add(new Resource() { ID = 5, Name = "DavID" });
        taskDetails[3].ChildCollection[2].Resource.Add(new Resource() { ID = 7, Name = "Peter" });
        taskDetails[3].ChildCollection[3].Resource.Add(new Resource() { ID = 8, Name = "Thomas" });

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
        return taskDetails;
    }
}

{% endhighlight  %}
{% endtabs %}


The following image shows Custom DateTime Schedule:

![gantt-control-custom-datetime-schedule](Custom-Schedule_images/gantt-control-custom-datetime-schedule.png)

Custom DateTime Schedule
{:.caption}

## Samples Link

To view samples:

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under User Interface Edition panel.
4. Select Gantt.
5. Expand the Custom Schedule item in the Sample Browser.
6. Choose the Customized Schedule Appearance sample to launch.

## ScheduleCellCreatedEventArgs Class

The ScheduleCellCreatedEventArgs consists of the current schedule cell in the name of CurrentCell. It is the GanttScheduleCell type. 

