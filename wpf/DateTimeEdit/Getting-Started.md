---
layout: post
title: Getting Started | DateTimeEdit | wpf | Syncfusion
description: getting started
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Getting Started

## Creating a DateTimeEdit control

DateTimeEdit control can be added to the application by using Visual Studio and Microsoft Expression Blend.

### Creating a DateTimeEdit control in C#

The steps to create a DateTimeEdit control by using Visual Studio in C# are as follows:

1. Open Visual Studio.

2. On the File menu, select New -> Project. This opens the New Project Dialog box.

   ![](Getting-Started_images/Getting-Started_img1.png)

3. On the Project Dialog window, select WPF Application, in the name field, type the name of the project, and then click OK.

   ![](Getting-Started_images/Getting-Started_img2.png)

4. Add the following reference with the sample project:

   1. Syncfusion.Shared.WPF.dll

   ![](Getting-Started_images/Getting-Started_img3.png)

5. Click the C# file, to open the C# file and add the DateTimeEdit control to the application. Here is the code to create the DateTimeEdit control in C#:

{% tabs %}
{% highlight c# %}

namespace WpfApp{ 
public partial class MainWindow : Window
{        
	public MainWindow()     
	{            
		InitializeComponent();   
		
//Adding DateTimeEdit control to application from Syncfusion.Windows.Shared 
		Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();            
		dateTimeEdit.Width = 200; 
        dateTimeEdit.Height = 25;
        this.LayoutRoot.Children.Add(dateTimeEdit); 
    }    
}}

{% endhiglight %}
{% endtabs %}

   ![](Getting-Started_images/Getting-Started_img4.png)



### Creating a DateTimeEdit control in XAML

The steps to create a DateTimeEdit control by using VisualStudio in XAML are as follows:

1. Create a new application in VisualStudio.
2. In the VisualStudio ToolBox, click the Syncfusion WPF Toolbox tab and select DateTimeEdit.
3. Drag and drop the DateTimeEdit control to Design View, to add the DateTimeEdit control to the application.

   ![](Getting-Started_images/Getting-Started_img5.png)

4. On the Properties window, customize the properties of the DateTimeEdit control.

{% tabs %}
{% highlight xaml %}

<Window x:Class="WpfApp.MainWindow"  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" Title="DateTimeEdit Demo" Height="280" Width="365"  xmlns:syncfusion=" clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.Wpf" xmlns:local="clr-namespace:WpfApp">    
<Grid x:Name="LayoutRoot">
<syncfusion:DateTimeEdit Height="29" Margin="75,71,50,0"  VerticalAlignment="Top"/>    
</Grid>
</Window>

{% endhighlight %}
{% endtabs %}

   ![](Getting-Started_images/Getting-Started_img6.png)


### Creating a DateTimeEdit control by using expression blend

The steps to create a DateTimeEdit control in the application by using Expression Blend are as follows:

1. Open Expression Blend.

2. On the File menu, select New Project. This opens the New Project dialog box.

   ![](Getting-Started_images/Getting-Started_img7.png)

3. In the Project types panel, select WPF Application and then click OK.

   ![](Getting-Started_images/Getting-Started_img8.png)

4. Add the following reference with the sample project:
   1. Syncfusion.Shared.WPF.dll
   
5. On the Window menu, select Assets. This opens the Assets Library dialog box.

6. In the Search box, type DateTimeEdit. This displays the search results.

   ![](Getting-Started_images/Getting-Started_img9.png)

7. Drag the DateTimeEdit control to Design View.

   ![](Getting-Started_images/Getting-Started_img10.png)

{% tabs %}
{% highlight xaml %}

<Window x:Class="WpfApp.MainWindow" xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" Title="DateTimeEdit Demo" Height="280" Width="365" xmlns:syncfusion=" clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.Wpf" xmlns:local="clr-namespace:WpfApp">    
<Grid x:Name="LayoutRoot">
<syncfusion:DateTimeEdit Height="29" Margin="75,71,50,0"  VerticalAlignment="Top"/>    
</Grid>
</Window>

{% endhighlight %}
{% endtabs %}

   ![](Getting-Started_images/Getting-Started_img11.png)


## Setting date

You have to use the DateTime property to set the date for the DateTimeEdit control.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"  DateTime="07/05/2010" Pattern="LongDate"/>

{% endhighlight %}

{% highlight c# %}

dateTimeEdit.DateTime = new DateTime(2010, 07, 05);

{% endhighlight  %}

{% endtabs %}

N> Use the DateTime property for Binding and Setting the date to the control. Do not use the Text property. If you do not set any value to the DateTimeEdit then the default value will be as follows: If the IsEmptyDateEnabled is set to true then, Value of the NullValue property will be the default value. Otherwise  DateTime.Today will be the default value (based on the MinValue and MaxValue the default value will change).

{% seealso %}

[Culture support](/wpf/datetimeedit/culture-support)

[DateTime Patterns](/wpf/datetimeedit/datetime-patterns)

[Minimum and Maximum Value](/wpf/datetimeedit/maximum-and-minimum-value)

{% endseealso %}

## Setting minimum and maximum value

The Minimum and Maximum values of the DateTimeEdit can be specified by the MinDateTime and MaxDateTime properties respectively.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"  DateTime="07/05/2010" Pattern="LongDate"  MinDateTime="01/01/2010" MaxDateTime="07/15/2010"/>

{% endhighlight  %}

{% highlight c# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new  Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2010, 07, 05);
dateTimeEdit.MinDateTime = new DateTime(2010, 01, 01);
dateTimeEdit.MaxDateTime = new DateTime(2010, 07, 15);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
this.LayoutRoot.Children.Add(dateTimeEdit);

{% endhighlight  %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img12.png)

{% seealso %}

[Minimum and Maximum Value](/wpf/datetimeedit/maximum-and-minimum-value)

[NullValue support](/wpf/datetimeedit/null-value-support)

{% endseealso %}