---
layout: post
title: Date Selection in WPF Calendar | Syncfusion
description: Learn how to select dates and customize the date selection user interface in WPF Calendar control easily.
platform: scheduler-sdk
control: CalendarEdit
documentation: ug
---

# Date Selection in WPF Calendar

This section explains how to select a date and custom UI of the WPF [CalendarEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html) control.

## Select a date

You can select a date in the `CalendarEdit` control by mouse click on the specific date. You can get the selected date by using the `Date` property.

{% tabs %}
{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" />
</Window>
{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

CalendarEdit calendarEdit = new CalendarEdit();
{% endhighlight %}
{% endtabs %}

![Date selected from the CalendarEdit](Getting-Started_images/wpf-calendar-control-date-selection.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

### Select a date programmatically

You can set selected date programmatically by setting the date value to the [Date](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_Date) property.

{% tabs %}
{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Date="25/08/2020"
                         Name="calendarEdit"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting date programmatically
this.calendarEdit.Date = new DateTime(2020, 08, 25);

{% endhighlight %}
{% endtabs %}

![Date selected programmatically from the CalendarEdit](Getting-Started_images/Date_programmatically.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Select multiple dates

You can select multiple dates by drag and move the mouse from required start date to end date.
You can get the selected dates from the [SelectedDates](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectedDates) property. You can restrict the multiple date selection by setting [AllowMultiplySelection](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_AllowMultiplySelection) property as `false`. The default value of `AllowMultiplySelection` property is `true`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                            AllowMultiplySelection="True"/>
</Window>
{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting multiple dates
this.calendarEdit.AllowMultiplySelection = true;

{% endhighlight %}
{% endtabs %}

![CalendarEdit control displaying multiple selected dates](Getting-Started_images/wpf-calendar-control-multiple-date-selection.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

### Select specific multiple dates

You can select specific multiple dates by pressing the `Ctrl` key and select required dates using mouse click.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                            AllowMultiplySelection="True"/>
</Window>>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting multiple dates
this.calendarEdit.AllowMultiplySelection = true;

{% endhighlight %}
{% endtabs %}

![CalendarEdit control displaying specifically selected multiple dates](Getting-Started_images/multiple-date-selection_mouse.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

### Select multiple dates programmatically

You can select a multiple dates programmatically by setting the dates to the [SelectedDatesList](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectedDatesList) property.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Date="08/25/2020" 
                         AllowMultiplySelection="True"
                         Name="calendarEdit">
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting multiple date programmatically
this.calendarEdit.AllowMultiplySelection = true;
this.calendarEdit.SelectedDatesList = new List<Date>();
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 01));
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 05));
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 10));
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 15));
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 20));
this.calendarEdit.SelectedDatesList.Add(new Date(2020, 08, 29));

{% endhighlight %}
{% endtabs %}

![Multiple dates selected programmatically from the CalendarEdit](Getting-Started_images/MultipleDate_programmatically.png)

## Select multiple dates using key navigation

You can select a multiple dates by pressing the `Shift` with `Arrow` keys. If you want to select multiple dates in forward direction, press the `Shift + Down` or  `Shift + Right` keys. If you want to select a date in backward direction, press the `Shift + UP` or  `Shift + Left` keys. You can get the selected dates from the `SelectedDates` property.

For example, if you start selecting the date from `18 Nov 2020` using key navigation, it will select the dates as follows,

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                         AllowMultiplySelection="True"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting multiple dates
this.calendarEdit.AllowMultiplySelection = true;

{% endhighlight %}
{% endtabs %}

![Multiple dates selected by key navigation in CalendarEdit](Working-with-Calendar_images/Multipledates_keynavigation.png)

### Select specific multiple dates using key navigation

You can select or unselect the specific multiple dates by using the `Ctrl`, `Arrow` keys and `Space` bar.

* `Ctrl + Arrow` keys → To move the focus to the top, left, bottom and right cells with maintaining the old selection.
* `Space` bar → To select the currently focused item.
* `Ctrl + Space` bar → To remove an item from multiple selection that is already selected.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                         AllowMultiplySelection="True"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Selecting multiple dates
this.calendarEdit.AllowMultiplySelection = true;

{% endhighlight %}
{% endtabs %}

![CalendarEdit control displaying specifically selected multiple dates](Getting-Started_images/multiple-date-selection_keys.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Highlight selected date

If you want to highlight the selected date, change its foreground, background or border brush by using the [SelectionForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectionForeground), [SelectedDayCellBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectedDayCellBackground) and [SelectedDayCellBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectedDayCellBorderBrush) and  properties. You can also change the mouse hover background and border brush for the selected day cell by using the [SelectedDayCellHoverBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectedDayCellHoverBackground) and [SelectionBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SelectionBorderBrush) properties.

![Changed selected date appearance](Working-with-Calendar_images/SelectionApperance.png)

{% tabs %}
{% highlight xaml %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit SelectedDayCellBackground="Yellow" 
                         SelectedDayCellBorderBrush="Blue"
                         SelectionForeground="Red"
                         SelectedDayCellHoverBackground="Green"
                         SelectionBorderBrush="Red"
                         Name="calendarEdit" />
</Window>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.Windows.Shared;

this.calendarEdit.SelectedDayCellBackground = Brushes.Yellow;
this.calendarEdit.SelectedDayCellBorderBrush = Brushes.Blue;
this.calendarEdit.SelectionForeground = Brushes.Red;
this.calendarEdit.SelectedDayCellHoverBackground = Brushes.Green;
this.calendarEdit.SelectionBorderBrush = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![Selected date background and foreground changed in CalendarEdit](Working-with-Calendar_images/SelectionCustomUI.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Get today date

If you want to know the today date, use the [TodayDate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayDate) property. It contains the today date of the `CalendarEdit` control.

{% tabs %}
{% highlight c# %}
using Syncfusion.Windows.Shared;

CalendarEdit calendarEdit = new CalendarEdit();

//get the today date
 var today_Date= calendarEdit.TodayDate;

{% endhighlight %}
{% endtabs %}

## Display today date

If you want to display the today date in the `CalendarEdit` control, use the [TodayRowIsVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayRowIsVisible) property value as `true`. It will display the today date in the bottom-left corner of the `CalendarEdit` control. The default value of `TodayRowIsVisible` property is `false`.

{% tabs %}
{% highlight xaml %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <syncfusion:CalendarEdit TodayRowIsVisible="True"
                         Name="calendarEdit" />
</Window>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.Windows.Shared;

//Enable the today row
this.calendarEdit.TodayRowIsVisible = true; 

{% endhighlight %}
{% endtabs %}

![Display today date](Working-with-Calendar_images/Working-with-Calendar_img3.jpeg)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

### Highlight today date

If you want to highlight the today date, change its foreground, background or border brush by using [TodayCellForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayCellForeground), [TodayCellBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayCellBackground) and [TodayCellBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayCellBorderBrush) properties. You can also change the selected border brush and background of the today date by using the [TodayCellSelectedBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayCellSelectedBorderBrush) and [TodayCellSelectedBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_TodayCellSelectedBackground) properties.

![Changing today dates foreground and background to highlight](Working-with-Calendar_images/Highlight_todaydate.png)

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <syncfusion:CalendarEdit TodayCellSelectedBorderBrush="Red" 
                         TodayCellSelectedBackground="Green"
                         TodayCellForeground="Yellow"
                         Name="calendarEdit" />
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

this.calendarEdit.TodayCellSelectedBorderBrush = Brushes.Red;
this.calendarEdit.TodayCellSelectedBackground = Brushes.Green;
this.calendarEdit.TodayCellForeground = Brushes.Yellow;

{% endhighlight %}
{% endtabs %}

![Changing today dates selected foreground and background to highlight](Working-with-Calendar_images/HighlightTodaydate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Differentiate current month days from other days

If you want to differentiate currently selected month days from previous or next month days, change the previous and next month days foreground by using the [NotCurrentMonthForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_NotCurrentMonthForeground) property. The default value of `NotCurrentMonthForeground` property is `Gray`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit NotCurrentMonthForeground="Red"
                            Name="calendarEdit" />
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

this.calendarEdit.NotCurrentMonthForeground = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![Changing previous and next month days foreground to differentiate current month days](Working-with-Calendar_images/NotCurrentMonthForeground.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Change default view (Month, Year, Decade)

By default, the days are displayed in the `CalendarEdit`.
You can change the default calendar view as week numbers, month, years or years range mode by setting the respective value to the [VisualMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_VisualMode) property. The default value of `VisualMode` property is `Days`.

![Various initial display mode for CalendarEdit](Working-with-Calendar_images/VisualMode.png)

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                         VisualMode="YearsRange"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

this.calendarEdit.VisualMode = CalendarVisualMode.YearsRange;

{% endhighlight %}
{% endtabs %}

![Changed initial display mode as years range](Working-with-Calendar_images/YearVisualMode.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Display week numbers

If you want to know the week number of the currently displayed dates, use the [ShowWeekNumbers](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_ShowWeekNumbers) property as `true`. It will display the respective week numbers in the left side of the `CalendarEdit` control.The default value of `ShowWeekNumbers` property is `false`.   

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                         ShowWeekNumbers="True"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Shows week numbers
this.calendarEdit.ShowWeekNumbers = true;

{% endhighlight %}
{% endtabs %}

![wpf calendar control shows week numbers](Getting-Started_images/wpf-calendar-control-week-numbers.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Highlight week numbers

If you want to highlight the week numbers, change it's foreground, background or border brush by using the [WeekNumberBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberBackground), [WeekNumberForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberForeground) and [WeekNumberBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberBorderBrush) properties. You can also change the mouse hover background, foreground and border brush for the selected day cell by using the [WeekNumberHoverBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberHoverBackground), [WeekNumberHoverForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberHoverForeground) and [WeekNumberHoverBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_WeekNumberHoverBorderBrush) properties.

{% tabs %}
{% highlight xaml %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit"                   
                         WeekNumberBackground="Green" 
                         WeekNumberBorderBrush="Red"
                         WeekNumberForeground="Yellow"
                         WeekNumberHoverBackground="Yellow"
                         WeekNumberHoverBorderBrush="Blue"
                         WeekNumberHoverForeground="Green"
                         ShowWeekNumbers="True"
                         VisualMode="WeekNumbers" />
</Window>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.Windows.Shared;

this.calendarEdit.WeekNumberBackground = Brushes.Green;
this.calendarEdit.WeekNumberBorderBrush = Brushes.Red;
this.calendarEdit.WeekNumberForeground = Brushes.Yellow;
this.calendarEdit.WeekNumberHoverBackground = Brushes.Yellow;
this.calendarEdit.WeekNumberHoverBorderBrush = Brushes.Blue;
this.calendarEdit.WeekNumberHoverForeground = Brushes.Green;
this.calendarEdit.ShowWeekNumbers = true;
this.calendarEdit.VisualMode = CalendarVisualMode.WeekNumbers;

{% endhighlight %}
{% endtabs %}

![Week number cells background and foreground changed in CalendarEdit](Working-with-Calendar_images/WeekNumberCustomUI.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Special days

You can differentiate the special day from other days by setting that date value to the [SpecialDate.Date](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SpecialDate.html#Syncfusion_Windows_Shared_SpecialDate_Date) property and adding `SpecialDate.Date` into the [SpecialDates](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SpecialDates) collection. You can use the [SpecialDate.CellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SpecialDate.html#Syncfusion_Windows_Shared_SpecialDate_CellTemplate) property to customize the `SpecialDate` day cell appearance. 

{% tabs %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//ViewModel.cs
public class ViewModel {
	private SpecialDatesCollection specialDates;
	public SpecialDatesCollection SpecialDates {
		get { return specialDates; }
		set { specialDates = value; }
	}
	public ViewModel() {
		SpecialDates = new SpecialDatesCollection();
	}
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <Window.Resources>
        <DataTemplate x:Key="WorldEnvironmentDay" >
            <Image Source="Resources\Icon_Environmental day.png" />
        </DataTemplate>
        <DataTemplate x:Key="EngineersDay" >
            <Image Source="Resources\Icon_Engineer day.png" />
        </DataTemplate>
        <DataTemplate x:Key="PollutionPreventionDay" >
            <Image Source="Resources\Icon_Pollution day.png" />
        </DataTemplate>
        <DataTemplate x:Key="NationalMathematicsDay" >
            <Image Source="Resources\Icon_Mathematics day.png" />
        </DataTemplate>
        <DataTemplate x:Key="Christmas" >
            <Image Source="Resources\Christmas.png" />
        </DataTemplate>

        <local:ViewModel x:Key="viewModel">
            <local:ViewModel.SpecialDates>
                <syncfusion:SpecialDate Date="06/05/2020" CellTemplate="{StaticResource WorldEnvironmentDay }"/>
                <syncfusion:SpecialDate Date="09/15/2020" CellTemplate="{StaticResource EngineersDay }"/>
                <syncfusion:SpecialDate Date="12/02/2020" CellTemplate="{StaticResource PollutionPreventionDay }"/>
                <syncfusion:SpecialDate Date="12/22/2020" CellTemplate="{StaticResource NationalMathematicsDay }"/>
                <syncfusion:SpecialDate Date="12/25/2020" CellTemplate="{StaticResource Christmas }"/>
            </local:ViewModel.SpecialDates>
        </local:ViewModel>
    </Window.Resources>
    
    <Grid>
        <syncfusion:CalendarEdit DataContext="{StaticResource viewModel}"                         
                                 SpecialDates="{Binding SpecialDates}"
                                 Name="calendarEdit" />
    </Grid>
</Window>
    
{% endhighlight %}
{% endtabs %}

![Custom appearance for the special Day cell](Working-with-Calendar_images/SpecialDays.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendaredit-examples/tree/master/Samples/SpecialDays)

## Setting Culture

You can change the culture for `CalendarEdit` control by setting the required culture to the `Culture` property.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:CalendarEdit Name="calendarEdit" 
                         Culture="fr-FR"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

//Setting french culture
this.calendarEdit.Culture = new CultureInfo("fr-FR");

{% endhighlight %}
{% endtabs %}

![wpf calendar control with french culture](Getting-Started_images/Culture.png)

## Show full month and week name

You can display full month names and week day names by setting the [ShowAbbreviatedDayNames](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_ShowAbbreviatedDayNames) and [ShowAbbreviatedDayNames](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_ShowAbbreviatedDayNames) properties as `false`. The default value of `ShowAbbreviatedDayNames` and `ShowAbbreviatedDayNames` property is `true`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <syncfusion:CalendarEdit ShowAbbreviatedDayNames="False"
                         ShowAbbreviatedMonthNames="False"
                         Name="calendarEdit"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

this.CalendarEdit calendarEdit = new CalendarEdit();
this.calendarEdit.ShowAbbreviatedDayNames = false;
this.calendarEdit.ShowAbbreviatedMonthNames = false;

{% endhighlight %}
{% endtabs %}

![CalendarEdit shows full month and week name](Getting-Started_images/FullDayNames.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Select-Date)

## Tooltip for particular days

You can set tooltip for particular days in the `CalendarEdit` control by using the [SetToolTip(Date,ToolTip)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_SetToolTip_Syncfusion_Windows_Shared_Date_System_Windows_Controls_ToolTip_) method. You can pass the specific date and tooltip to the `SetToolTip(Date,ToolTip)` method.

{% tabs %}
{% highlight C# %}

Date yesterday = new Date(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day-1);
Date today = new Date(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day);
CalendarEdit calendarEdit = new CalendarEdit();

//Setting tooltip for yesterday and today dates
calendarEdit.SetToolTip(yesterday, new ToolTip() { Content = "Yesterday" });
calendarEdit.SetToolTip(today, new ToolTip() { Content = "Today" });

{% endhighlight %}
{% endtabs %}

![Tooltip for today and yesterday](Working-with-Calendar_images/Tooltip.png)

## Custom appearance of day cell

You can customize the appearance of day cell by using styles and templates in the `CalendarEdit` control.

### Custom UI for day cell using style

You can customize the appearance of day cell by using the [DayCellsStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_DayCellsStyle) property. The `DataContext` of the `DayCellsStyle` is `DayCell`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <Window.Resources>    
        <!-- day cell style -->
        <Style x:Key="dayCell" 
            TargetType="{x:Type syncfusion:DayCell}">
            <Setter Property="CornerRadius" Value="0"/>
            <Setter Property="Background" Value="Pink"/>
        </Style>
    </Window.Resources>
    <Grid>
        <syncfusion:CalendarEdit DayCellsStyle="{StaticResource dayCell}" 
                                Name="calendarEdit" />
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![Custom UI for the day cell by using DayCellsStyle](Working-with-Calendar_images/DayCellsStyle.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Style)

### Custom UI for day cell using template

You can customize the appearance of day cell by using the [DayCellsDataTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_DayCellsStyle) property. The `DataContext` of the `DayCellsDataTemplate` is `DayCell`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <Window.Resources>    
        <!-- day cell template -->
        <DataTemplate x:Key="dayCelltemplate"
                    DataType="syncfusion:DayCell">
            <TextBlock TextAlignment="Center"
                    Foreground="Yellow"
                    Background="Green"
                    FontFamily="Tahoma"
                    FontStyle="Normal"
                    Text="{Binding Day}"/>
        </DataTemplate>
    </Window.Resources>
    <Grid>
        <syncfusion:CalendarEdit DayCellsDataTemplate="{StaticResource dayCelltemplate}"  
                                Name="calendarEdit" />
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![Custom UI for the day cell by using DayCellsStyle](Working-with-Calendar_images/DayCellsDataTemplate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Template)

## Custom UI for day name cell using style

You can customize the appearance of day name cell by using the [DayNameCellsStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html#Syncfusion_Windows_Shared_CalendarEdit_DayNameCellsStyle) property. The `DataContext` of the `DayNameCellsStyle` is `DayNameCell`.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <Window.Resources>    
        <!-- day name cell style -->
        <Style x:Key="daynameCellStyle" 
            TargetType="{x:Type syncfusion:DayNameCell}">
            <Setter Property="Background" Value="Yellow"/>
            <Setter Property="Foreground" Value="Yellow"/>
        </Style>
    </Window.Resources>
    <Grid>
        <syncfusion:CalendarEdit DayNameCellsStyle="{StaticResource daynameCellStyle}" 
                                Name="calendarEdit" />
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

![Custom UI for the day name cell by using DayNameCellsStyle](Working-with-Calendar_images/DayNameCellsStyle.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusin-wpf-calendar-examples/tree/master/Samples/Style)

## Selected date changed notification

The selected date changed in `CalendarEdit` can be examined using [DateChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CalendarEdit.html) event. The `DateChanged` event contains the old and newly selected date time values in the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight XAML %}
<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
   <syncfusion:CalendarEdit DateChanged="CalendarEdit_DateChanged" 
                          Name="calendarEdit"/>
</Window>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.Windows.Shared;

this.CalendarEdit calendarEdit = new CalendarEdit();
this.calendarEdit.DateChanged += CalendarEdit_DateChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight C# %}

private void CalendarEdit_DateChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Get old and new selected date values
    var oldValue = e.OldValue;
    var newValue = e.NewValue;
}

{% endhighlight %}
{% endtabs %}
