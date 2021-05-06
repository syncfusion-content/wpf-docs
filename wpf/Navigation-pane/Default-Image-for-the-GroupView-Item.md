---
layout: post
title: Default Image for the GroupView Item in WPF Navigation Pane control | Syncfusion
description: Learn here all about Default Image for the GroupView Item support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# Default Image for the GroupView Item in WPF Navigation Pane (GroupBar)

You can set the default item image for the GroupView item using the DefaultItemImage property. This dependency property sets the default image for GroupView item. It returns the default image of GroupView item.

Use the below code snippet to set this property.



{% highlight xaml %}



<!-- Adding GroupBar -->

<syncfusion:GroupBar Height="200" DefaultItemImage="App.ico" Width="230" Name="groupBar">



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
