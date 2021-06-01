---
layout: post
title: Setting ToolTip for GroupBar in WPF Navigation Pane | Syncfusion
description: Learn here all about Setting ToolTip for GroupBar support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
documentation: ug
---

# Setting ToolTip for GroupBar in WPF Navigation Pane (GroupBar)

ToolTip is one of the important user interactive feature available in GroupBar control. You can set the tooltip for the collapse button and expand button using the properties listed below.

### Property table

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
CollapseButtonToolTip</td><td>
Gets or sets the tooltip to be displayed when mouse is hovered over the collapse button.</td></tr>
<tr>
<td>
ExpandButtonToolTip</td><td>
Gets or sets the tooltip to be displayed when mouse is hovered over the expand button.</td></tr>
</table>


Use the below code snippet to set this property.



{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" CollapseButtonToolTip="Expand"  VisualMode="StackMode" AllowCollapse="True"  ExpandButtonToolTip="Collapse" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">
 <!-- Adding content for GroupBar item using panel -->   
 <StackPanel Orientation="Vertical">   
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/> 
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>  
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>   
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>  
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>  
 </StackPanel>  
 </syncfusion:GroupBarItem> 

 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">   
 <!-- Adding content for GroupBar item using GroupView -->
 <syncfusion:GroupView Name="groupView" IsListViewMode="True">  
 <syncfusion:GroupViewItem Text="List View"/>     
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>    
 <syncfusion:GroupViewItem Text="Show ToolTip"/>   

 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar>
 {% endhighlight %}

{% highlight C# %}
//Setting the visual mode as StackMode
groupBar.VisualMode = VisualMode.StackMode;  
//Setting AllowCollapse property
groupBar.AllowCollapse = true;
//Setting the tooltip for Expand button
groupBar.ExpandButtonToolTip = "Collapse";
//Setting the tooltip for Collapse button
groupBar.CollapseButtonToolTip = "Expand";
{% endhighlight %}
{% endtabs %}


