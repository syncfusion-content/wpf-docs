---
layout: post
title: Navigation Pane in GroupBar in WPF Navigation Pane control | Syncfusion
description: Learn here all about Navigation Pane in GroupBar support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# Navigation Pane in GroupBar in WPF Navigation Pane (GroupBar)

Resizing the Navigation Pane Pop-up

You can resize the navigation pane pop-up in any direction using the PopupResizeDirection property. This dependency property sets the value indicating the resize directions of the navigation pane's pop-up. There are four built-in resize directions.

* Both - navigation pane pop-up is resized in both directions, i.e., vertically and horizontally
* Horizontal – navigation pane pop-up is resized in the horizontal direction only
* None – navigation pane pop-up is not resized
* Vertical – navigation pane pop-up is resized in the vertical direction only

Use the below code to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" PopupResizeDirection="Both" Name="groupBar">  
<!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True">
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
//Resize the navigation pane pop-up in both direction
groupBar.PopupResizeDirection = PopupResizeDirection.Both;
{% endhighlight %}
{% endtabs %}


## Navigation Pane Gripper

Gripper is available in navigation pane. Using the gripper we can increase or decrease the size of the GroupBar items. You can enable the gripper in GroupBar by setting ShowGripper property to true. This property works only in stacked mode. Default value is true.

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" VisualMode="StackMode" ShowGripper="True" Name="groupBar">
  <!-- Adding GroupBarItem --> 
  <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">   
  <!-- Adding content for GroupBar item using panel --> 
  <StackPanel Orientation="Vertical">   
  <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>   
  <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>     
  <RadioButton Margin="4,2,2,2">Vertical</RadioButton>  
  <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>   
  <RadioButton Margin="4,2,2,2">Horizontal
  </RadioButton>     
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
//Enable the gripper in navigation pane
groupBar.ShowGripper = true;
{% endhighlight %} 
{% endtabs %}


