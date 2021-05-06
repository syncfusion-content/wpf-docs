---
layout: post
title: Toolbars in GroupBar in WPF Navigation Pane control | Syncfusion
description: Learn here all about Toolbars in GroupBar support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# Toolbars in GroupBar in WPF Navigation Pane (GroupBar)

We can hide the toolbar that is displayed in the GroupBar using the IsToolBarEnabled property. This dependency property sets the value indicating whether to hide the toolbar and items in stacked mode. It returns the bool value that indicates the state of toolbar that is hidden or visible. This property works only in stacked mode. 

The following code snippet will help you to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" IsToolBarEnabled="True" VisualMode="StackMode" Name="groupBar">
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
  </StackPanel></syncfusion:GroupBarItem>
  <!-- Adding GroupBarItem -->
  <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"> 
  <!-- Adding content for GroupBar item using GroupView -->
  <syncfusion:GroupView Name="groupView" IsListViewMode="True">  
  <syncfusion:GroupViewItem Text="List View"/>  
  <syncfusion:GroupViewItem Text="Show ContextMenu"/>  
  <syncfusion:GroupViewItem Text="Show ToolTip"/>  
  </syncfusion:GroupView>
  </syncfusion:GroupBarItem>
  </syncfusion:GroupBar>{% endhighlight %}

{% highlight C# %}
//Enable the ToolBar
groupBar.IsToolBarEnabled = true;
{% endhighlight %}
{% endtabs %}


