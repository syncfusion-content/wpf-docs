---
layout: post
title: Print in WPF Wizard Control control | Syncfusion
description: Learn here all about Print support in Syncfusion WPF Chart (Classic) control and more.
platform: wpf
control: Chart (Classic)
documentation: ug
---
# Print in WPF Chart (Classic)

Essential Chart for WPF now comes with support to print the chart and printing options such as page orientation, print preview, color mode, and more.

![C:/Users/michaelprabhu/Desktop/print.png](Chart-Controls_images/Chart-Controls_img237.png)


## Use Case Scenarios

Printing the chart is useful for visual representation in organizational meetings.

![C:/Users/michaelprabhu/Desktop/print.png](Chart-Controls_images/Chart-Controls_img238.png)



## Methods


<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<td>
Print()</td><td>
Used to print tde Chart control. tdis opens tde printing dialog box. tdis metdod returns a bool value after printing.</td><td>
Overloads: (Rect  printArea) </td><td>
N/A</td><td>
Bool</td></tr>
<tr>
<td>
PrintSwitchMode()</td><td>
To select a particular area for printing.</td><td>
N/A</td><td>
N/A</td><td>
Void</td></tr>
</table>

## Sample Link

..My Documents\Syncfusion\EssentialStudio\<Version Number>\WPF\Chart.WPF\Samples\3.5\WindowsSamples\Export and Print\Printing Chart Demo

## Print in WPF Chart (Classic)ing a Chart

Charts can be printed by using the following code example.

{% tabs %}
{% highlight xaml %}


<!--Button when clicked executes the Print command-->

<Button Grid.Row="0" Content="Print"						Command="{x:Static ApplicationCommands.Print}"						CommandTarget="{Binding ElementName=Chart1}" x:Name="button"/>            <!--Button when clicked executes the SwitchPrinting command-->            <Button Grid.Row="0" Grid.Column="1" Content="Printing Mode" 						Command="{x:Static syncfusion:ChartCommands.SwitchPrinting}"						CommandTarget="{Binding ElementName=Chart1}" x:Name="button1" />

{% endhighlight  %}
{% highlight c# %}


Chart1.Print();

Chart1.PrintSwitchMode();
{% endhighlight  %}
{% endtabs %}