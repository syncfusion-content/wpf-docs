---
layout: post
title: Adjusting the GroupBar width in WPF Navigation Pane | Syncfusion
description: Learn here all about Adjusting the GroupBar width support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
 documentation: ug
---

# Adjusting the GroupBar width in WPF Navigation Pane (GroupBar)

Set the width of the GroupBar while it is collapsed by using the CollapsedWidth property. This dependency property sets the width of the collapsed groupbar. 

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar with  AllowCollapse property = true -->
<syncfusion:GroupBar Height="300" Width="230" Name="groupBar" CollapsedWidth="100" AllowCollapse="True" VisualMode="StackMode">  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView Name="groupView" IsListViewMode="True">      <syncfusion:GroupViewItem Text="List View"/>      <syncfusion:GroupViewItem Text="Show ContextMenu"/>      <syncfusion:GroupViewItem Text="Show ToolTip"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView>      <syncfusion:GroupViewItem Text="Default"/>      <syncfusion:GroupViewItem Text="Multiple Expansion"/>      <syncfusion:GroupViewItem Text="StackMode"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView>      <syncfusion:GroupViewItem Text="Save State"/>      <syncfusion:GroupViewItem Text="Load State"/>      <syncfusion:GroupViewItem Text="Reset State"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem></syncfusion:GroupBar> {% endhighlight %} 

{% highlight C# %} 
//Enable AllowCollapse property for GroupBar
groupBar.AllowCollapse = true;
//Setting the width of Collapse button
groupBar.CollapsedWidth = 100; 
{% endhighlight %} 
{% endtabs %}


{% seealso %}

Collapsing the GroupBar

{% endseealso %}
