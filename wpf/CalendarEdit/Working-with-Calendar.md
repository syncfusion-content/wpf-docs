---
layout: post
title: Working with Calendar | CalendarEdit | WPF | Syncfusion
description: working with calendar
platform: wpf
control: CalendarEdit
documentation: ug
---

# Working with Calendar

This section contains the following topics:

## Setting the Date

You can explicitly set the date for the CalendarEdit control, using the Date property. This dependency property sets the date explicitly to the CalendarEdit control. It returns the current date of the CalendarEdit control.

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with date as 12/12/2009 -->
<syncfusion:CalendarEdit Name="calendarEdit" Date="12/12/2009"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Sets the Date
calendarEdit.Date = DateTime.Now.Date;  

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

![](Working-with-Calendar_images/Working-with-Calendar_img1.jpeg)



## Settings the Days

It is possible to hide the days of the next month and the previous month in the calendar, to enhance the appearance of the Calendar. This is done by disabling the ShowNextMonthDays and ShowPreviousMonthDays properties. 

For setting these properties, use the following code.

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with next month day and previous month day Set to false -->
<syncfusion:CalendarEdit Name="calendarEdit" ShowNextMonthDays="False" ShowPreviousMonthDays="False"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Hide the next month days
calendarEdit.ShowNextMonthDays = false;

//Hide the previous month days
calendarEdit.ShowPreviousMonthDays = false;

//Adding CalendarEdit as window content
this.Content = calendarEdit;
 
{% endhighlight %}
{% endtabs %}

![](Working-with-Calendar_images/Working-with-Calendar_img2.jpeg)



## Today Row

To know the details of current date in a CalendarEdit control, you need to enable Today Row. Set the TodayRowIsVisible property to true to display today's details. This dependency property indicates whether the today bar is visible or collapsed.

For setting this property, use the following code example.

{% tabs %}
{% highlight xaml %}

<!-- Adding Calendar with today row -->
<syncfusion:CalendarEdit Name="calendarEdit" TodayRowIsVisible="True"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Enable the today row
calendarEdit.TodayRowIsVisible = true; 

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}


![](Working-with-Calendar_images/Working-with-Calendar_img3.jpeg)



## Week Number

Enhance the usability of the CalendarEdit control, by showing week numbers near the left margin. To show week numbers, set IsShowWeekNumbers property to true as follows.

{% tabs %}
{% highlight xaml %}

<!-- Adding calendar with week numbers -->
<syncfusion:CalendarEdit Name="calendarEdit" IsShowWeekNumbers="True"/>

{% endhighlight %}

{% highlight c# %}

//Creating an instance of CalendarEdit control
CalendarEdit calendarEdit = new CalendarEdit();

//Show week numbers
calendarEdit.IsShowWeekNumbers = true;

//Adding CalendarEdit as window content
this.Content = calendarEdit;

{% endhighlight %}
{% endtabs %}

![](Working-with-Calendar_images/Working-with-Calendar_img4.jpeg)





## Week Numbers Grid

It is now possible to edit weekly date in CalendarEdit control. This is achieved by using the IsShowWeekNumbersGrid property.

The following code example illustrates this.

{% tabs %}
{% highlight xaml %}
<!--Calendar Edit-->
<syncfusion:CalendarEdit Name="calendar"  IsShowWeekNumbersGrid="{Binding ElementName = cbShowWeekNumbersGrid, Path=IsChecked, Mode=TwoWay}/>
<CheckBox Name="cbShowWeekNumbersGrid" IsChecked="False" IsEnabled="False">Show Week Numbers Grid</CheckBox>

{% endhighlight %}

{% highlight c# %}

//Binding IsShowWeekNumbersGrid property to CheckBox
Binding b = new Binding();
b.Source = calendar;b.Mode = BindingMode.TwoWay;b.Path = new PropertyPath("IsShowWeekNumbersGrid");
BindingOperations.SetBinding(cbShowWeekNumbersGrid, CheckBox.IsCheckedProperty, b);

{% endhighlight %}
{% endtabs %}

Run the code. The output is as follows:

![](Working-with-Calendar_images/Working-with-Calendar_img5.jpeg)





### Changing Week Number Grid’s Default Properties

You can set the color for the border brush, background and foreground for the cells in the Week Numbers Grid. You can also set the corner radius and thickness for the border of the cells in the Week Numbers Grid.

The following code example illustrates this.

{% tabs %}
{% highlight xaml %}

<!--Calendar Edit with Week Number Default Properties-->
<syncfusion:CalendarEdit  WeekNumberBackground="DodgerBlue" WeekNumberBorderBrush="Cyan" WeekNumberForeground="White" WeekNumberBorderThickness="1" WeekNumberCornerRadius="2"/>

{% endhighlight %}

{% highlight c# %}

//Calendar Edit with Week Number Default Properties
CalendarEdit calendar = new CalendarEdit();
calendar.WeekNumberBorderBrush = Brushes.Cyan;calendar.WeekNumberCornerRadius = new CornerRadius(2);
calendar.WeekNumberBorderThickness = new Thickness(1);calendar.WeekNumberBackground = Brushes.DodgerBlue;
calendar.WeekNumberForeground = Brushes.White;

{% endhighlight %}
{% endtabs %}

Run the code. The output is as follows:

![](Working-with-Calendar_images/Working-with-Calendar_img6.jpeg)





### Changing Week Number Grid’s Selection Properties

You can set the border brush, background and foreground color for the required cell in the Week Numbers Grid. You can also set the corner radius and thickness for the border of the selected cell in the Week Numbers Grid.

The following code example illustrates this.


{% tabs %}
{% highlight xaml %}

<!--Calendar Edit with Week Number Selection Properties-->
<syncfusion:CalendarEdit WeekNumberSelectionBackground="AntiqueWhite" WeekNumberSelectionBorderBrush="Blue" WeekNumberSelectionForeground="Brown" WeekNumberSelectionBorderThickness="2" WeekNumberSelectionBorderCornerRadius="2"/>

{% endhighlight %}

{% highlight c# %}

//Calendar Edit with Week Number Selection Properties
CalendarEdit calendar = new CalendarEdit();
calendar.WeekNumberSelectionBorderBrush = Brushes.Blue;calendar.WeekNumberSelectionBorderCornerRadius = new CornerRadius(2);
calendar.WeekNumberSelectionBorderThickness = new Thickness(2);
calendar.WeekNumberSelectionBackground = Brushes.AntiqueWhite;calendar.WeekNumberSelectionForeground = Brushes.Brown;

{% endhighlight %}
{% endtabs %}

Run the code. The output is as follows:

![](Working-with-Calendar_images/Working-with-Calendar_img7.jpeg)





### Changing Week Number Mouse Over Properties

You can set the border brush, background and foreground color for the cell focused in the Week Numbers Grid.

The following code example illustrates this.

{% tabs %}
{% highlight xaml %}

<!--Calendar Edit with Week Number Mouse Over Properties-->
<syncfusion:CalendarEdit WeekNumberHoverBackground="Gold"  WeekNumberHoverBorderBrush="DarkOrange" WeekNumberHoverForeground="Indigo" />

{% endhighlight %}

{% highlight c# %}

//Calendar Edit with Week Number Mouse Over Properties
CalendarEdit calendar = new CalendarEdit();
calendar.WeekNumberHoverBorderBrush = Brushes.DarkOrange;
calendar.WeekNumberHoverBackground = Brushes.Gold;
calendar.WeekNumberHoverForeground = Brushes.Indigo;

{% endhighlight %}
{% endtabs %}

Run the code. The output is as follows:

![](Working-with-Calendar_images/Working-with-Calendar_img8.jpeg)



## Customizing the Display of Minimum and Maximum Dates

Minimum dates and Maximum dates display in CalendarEdit can be customized with two states-True and False. The states can be set by using the property MinMaxHidden:

* When this property is set to True, the minimum dates and maximum dates are hidden. 
* When this property is set to False, the display minimum dates and maximum dates are disabled. 
* The default value for this property is true. It returns the Boolean value.

The following code example illustrates how to set the MinMaxHidden property to the control programmatically.

{% tabs %}
{% highlight xaml %}
<!-- CalendarEdit with MinMaxHidden has false -->
<syncfusion:CalendarEdit Height ="250" Width ="250" Name="calendar" MinMaxHidden="False" MinDate="11/30/2009" MaxDate="1/4/2010"/>

{% endhighlight %}

{% highlight c# %}

//Create an instance of CalendarEdit
CalendarEdit calendarEdit = new CalendarEdit();

//CalendarEdit with MinMaxHidden as false
calendarEdit.MinMaxHidden = false;

{% endhighlight %}
{% endtabs %}


Run the code. The output is as follows:

![](Working-with-Calendar_images/Working-with-Calendar_img9.jpeg)





![](Working-with-Calendar_images/Working-with-Calendar_img10.jpeg)



