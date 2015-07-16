---
layout: post
title: Default-Image-for-the-GroupView-Item
description: default image for the groupview item
platform: wpf
control: GroupBar
documentation: ug
---

# Default Image for the GroupView Item

You can set the default item image for the GroupView item using the DefaultItemImage property. This dependency property sets the default image for GroupView item. It returns the default image of GroupView item.

Use the below code snippet to set this property.



[XAML]



&lt;!-- Adding GroupBar --&gt;

&lt;syncfusion:GroupBar Height="200" DefaultItemImage="App.ico" Width="230" Name="groupBar"&gt;



  &lt;!-- Adding GroupBarItem --&gt;

  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"&gt;



    &lt;!-- Adding content for GroupBar item using panel --&gt;

    &lt;StackPanel Orientation="Vertical"&gt;

      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;

      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>

      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>

      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;

      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>

      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>

    &lt;/StackPanel&gt;

  &lt;/syncfusion:GroupBarItem&gt;



  &lt;!-- Adding GroupBarItem --&gt;

  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;



    &lt;!-- Adding content for GroupBar item using GroupView --&gt;

    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;

      &lt;syncfusion:GroupViewItem Text="List View"/&gt;

      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;

      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;

    &lt;/syncfusion:GroupView&gt;

  &lt;/syncfusion:GroupBarItem&gt;

&lt;/syncfusion:GroupBar&gt;



