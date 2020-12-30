---
layout: post
title: Getting Started | SfSunburstChart | WPF | Syncfusion 
description: This section explains the steps required to populate the sunburst chart with data, add data labels, legends and header.
platform: wpf
control: SfSunburstChart
documentation: ug
---

# Getting Started with WPF Sunburst Chart (SfSunburstChart)

This section explains you the steps required to populate the sunburst chart with data, add data labels, legends and header. This section covers only the minimal features that you need to know to get started with the Sunburst chart.

## Adding assembly reference

1. Open the Add Reference window from your project
2. Choose Assemblies -> Extensions -> Syncfusion.SfSunburstChart.WPF

![Reference Manager Dialog Windows in Visual Studio](Getting-Started_images/gettingstarted1.png)

N> This window differs for the Visual Basic project.

## Adding SfSunburstChart from Toolbox

Drag and drop the SfSunburstChart control from the Toolbox to your application,

![Visual Studio Toolbox](Getting-Started_images/gettingstarted2.png)

Now the Syncfusion.SfSunburstChart.WPF reference is added to the application references and the namespace code is generated in MainWindow.xaml as below.

![Project Solution Window contains SfSunburstChart reference](Getting-Started_images/gettingstarted3.png)

![Added xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.SunburstChart;assembly=Syncfusion.SfSunburstChart.WPF" in MainWindow](Getting-Started_images/gettingstarted4.png)

## Initialize view model

In this section, the data in the following table is used for demonstration,

<table>
<tr>
<th>
Country
</th>
<th>
Job Description
</th>
<th>
Job Group
</th>
<th>
Job Role
</th>
<th>
Employees Count
</th>
</tr>
<tr>
<td>
America
</td>
<td>
Sales
</td>
<td>
</td>
<td>
</td>
<td>
70
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Testers
</td>
<td>
</td>
<td>
35
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
105
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
40
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Management
</td>
<td>
</td>
<td>
</td>
<td>
40
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Accounts
</td>
<td>
</td>
<td>
</td>
<td>
60
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Testers
</td>
<td>
</td>
<td>
25
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
155
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
60
</td>
</tr>
<tr>
<td>
Germany
</td>
<td>
Sales
</td>
<td>
Executive
</td>
<td>
</td>
<td>
30
</td>
</tr>
<tr>
<td>
Germany
</td>
<td>
Sales
</td>
<td>
Analyst
</td>
<td>
</td>
<td>
40
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
100
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
30
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
HR Executives
</td>
<td>
</td>
<td>
</td>
<td>
60
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Marketing
</td>
<td>
</td>
<td>
</td>
<td>
40
</td>
</tr>
</table>

Now, let us define a data model that represents the above data in sunburst chart.

{% highlight C# %}
    public class Model
    {
        public string Category { get; set; }
        public string Country { get; set; }
        public string JobDescription { get; set; }
        public string JobGroup { get; set; }
        public string JobRole { get; set; }
        public double EmployeesCount { get; set; }
    }
{% endhighlight %}

Next, create a view model class and initialize a list of Model objects as shown below,

{% highlight C# %}
    public class ViewModel
    {
        public ObservableCollection<Model> Data { get; set; }
        public ViewModel()
        {
            Data = new ObservableCollection<Model>
            {
                new Model
                {
                    Country = "America", JobDescription = "Sales",
                    EmployeesCount = 70
                },
                new Model
                {
                    Country = "America", JobDescription = "Technical",
                    JobGroup = "Testers", EmployeesCount = 35
                },
                new Model
                {
                    Country = "America", JobDescription = "Technical",
                    JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 105
                },
                new Model
                {
                    Country = "America", JobDescription = "Technical",
                    JobGroup = "Developers", JobRole = "Web", EmployeesCount = 40
                },
                new Model
                {
                    Country = "America", JobDescription = "Management",
                    EmployeesCount = 40
                },
                new Model
                {
                    Country = "America", JobDescription = "Accounts",
                    EmployeesCount = 60
                },
                new Model
                {
                    Country = "India", JobDescription = "Technical",
                    JobGroup = "Testers", EmployeesCount = 25
                },
                new Model
                {
                    Country = "India", JobDescription = "Technical", JobGroup = "Developers",
                    JobRole = "Windows", EmployeesCount = 155
                },
                new Model
                {
                    Country = "India", JobDescription = "Technical", JobGroup = "Developers",
                    JobRole = "Web", EmployeesCount = 60
                },
                new Model
                {
                    Country = "Germany", JobDescription = "Sales", JobGroup = "Executive",
                    EmployeesCount = 30
                },
                new Model
                {
                    Country = "Germany", JobDescription = "Sales", JobGroup = "Analyst",
                    EmployeesCount = 40
                },
                new Model
                {
                    Country = "UK", JobDescription = "Technical", JobGroup = "Developers",
                    JobRole = "Windows", EmployeesCount = 100
                },
                new Model
                {
                    Country = "UK", JobDescription = "Technical", JobGroup = "Developers",
                    JobRole = "Web", EmployeesCount = 30
                },
                new Model
                {
                    Country = "UK", JobDescription = "HR Executives", EmployeesCount = 60
                },
                new Model
                {
                    Country = "UK", JobDescription = "Marketing", EmployeesCount = 40
                }
            };
        }
    }
{% endhighlight %}

Set the ViewModel instance as the DataContext of your window; this is done to bind properties of ViewModel to Sunburst chart.

N> Add namespace of ViewModel class in your XAML page if you prefer to set DataContext in XAML.

{% tabs %}

{% highlight xaml %}
    <Window x:Class="GettingStarted.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:GettingStarted">
    <Window.DataContext>
         <local:ViewModel/>
    </Window.DataContext>
{% endhighlight %}

{% highlight C# %}
this.DataContext = new ViewModel();
{% endhighlight %}
    
{% endtabs %}

## Populate Sunburst chart with data

Now, bind the Data property of the above ViewModel to the `ItemsSource` property. 
Add `SunburstHierarchicalLevel` to `Levels` property. Each hierarchy level is formed based on the property specified in `GroupMemberPath` property, and each arc segment size is calculated using `ValueMemberPath`.

{% tabs %}

{% highlight xaml %}
<sunburst:SfSunburstChart ItemsSource="{Binding Data}" ValueMemberPath="EmployeesCount">
    <sunburst:SfSunburstChart.Levels>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="Country"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobDescription"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobGroup"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobRole"/>
    </sunburst:SfSunburstChart.Levels>
</sunburst:SfSunburstChart>
{% endhighlight %}

{% highlight C# %}
SfSunburstChart sunburst = new SfSunburstChart();
sunburst.ValueMemberPath = "EmployeesCount";
sunburst.SetBinding(SfSunburstChart.ItemsSourceProperty, "Data");
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "Country"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobDescription"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobGroup"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobRole"});
{% endhighlight %}
    
{% endtabs %}

## Add header 

You can add header to Sunburst chart to provide quick information to the user about the data being plotted in the chart. You can set title using `Header` property as shown below.

{% tabs %}

{% highlight xaml %}
<sunburst:SfSunburstChart Header="Employees Count" FontSize="22" />
{% endhighlight %}

{% highlight C# %}
sunburst.Header = "Employees Count";
sunburst.FontSize = 22d;
{% endhighlight %}
    
{% endtabs %}

## Add legend

You can enable legend using `Legend` property as shown below,

{% tabs %}

{% highlight xaml %}
<sunburst:SfSunburstChart.Legend>
    <sunburst:SunburstLegend DockPosition="Left"/>
</sunburst:SfSunburstChart.Legend>
{% endhighlight %}

{% highlight C# %}
SunburstLegend legend = new SunburstLegend();
legend.DockPosition= ChartDock.Left;
{% endhighlight %}
    
{% endtabs %}

## Add data labels

You can add data labels to improve the readability of the Sunburst chart. This can be achieved using `DataLabelInfo` property as shown below,

{% tabs %}

{% highlight xaml %}
<sunburst:SfSunburstChart.DataLabelInfo>
    <sunburst:SunburstDataLabelInfo />
</sunburst:SfSunburstChart.DataLabelInfo>
{% endhighlight %}

{% highlight C# %}
SunburstDataLabelInfo dataLabel= new SunburstDataLabelInfo();
sunburst.DataLabelInfo = dataLabel;
{% endhighlight %}
    
{% endtabs %}

Following is the final output screenshot,

![SfSunburstChart with data label and legend](Getting-Started_images/gettingstarted5.png)

You can find the complete getting started sample from this [`link.`](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Getting_Started2023483097)

## Theme

Sunburst chart supports various built-in themes. Refer to the below links to apply themes for the Sunburst chart,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)