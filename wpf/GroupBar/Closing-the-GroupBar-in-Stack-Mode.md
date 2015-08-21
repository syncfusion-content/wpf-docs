---
layout: post
title: Closing-the-GroupBar-in-Stack-Mode
description: closing the groupbar in stack mode
platform: wpf
control: GroupBar
documentation: ug
---

# Closing the GroupBar in Stack Mode

You can close the GroupBar in stack mode by enabling the close button. This is done by using the IsCloseButtonEnabled property. This dependency property sets the value indicating whether the close button is visible on the header of the item in stack mode when IsToolBarEnabled property is set to _false_. That is close button is visible only if toolbar is disabled. This property can work only in stack mode.

Use the below code snippet to set this property. 



{% highlight xml %}<!-- Adding GroupBar --><syncfusion:GroupBar Height="200" Width="230" IsCloseButtonEnabled="True" 	IsToolBarEnabled="False" VisualMode="StackMode" Name="groupBar">  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True">    <!-- Adding content for groupbar item using panel -->    <StackPanel Orientation="Vertical">      <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2"  >Vertical</RadioButton>      <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    </StackPanel>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">    <!-- Adding content for GroupBar item using GroupView -->    <syncfusion:GroupView Name="groupView" IsListViewMode="True">      <syncfusion:GroupViewItem Text="List View"/>      <syncfusion:GroupViewItem Text="Show ContextMenu"/>      <syncfusion:GroupViewItem Text="Show ToolTip"/>    </syncfusion:GroupView>  </syncfusion:GroupBarItem></syncfusion:GroupBar>{% endhighlight %}

{% highlight C# %}//Setting the visual mode as stack modegroupBar.VisualMode = VisualMode.StackMode;//Enabling the close buttongroupBar.IsCloseButtonEnabled = true;//Disabling the toolbargroupBar.IsToolBarEnabled = false;{% endhighlight %}


