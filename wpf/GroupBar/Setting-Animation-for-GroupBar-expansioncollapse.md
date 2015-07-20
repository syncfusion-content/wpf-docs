---
layout: post
title: Setting-Animation-for-GroupBar-expansioncollapse
description: setting animation for groupbar expansion/collapse
platform: wpf
control: GroupBar
documentation: ug
---

# Setting Animation for GroupBar expansion/collapse

Animation Speed

The expanding and collapsing operation in a GroupBar leads to an animated action. This animation is controlled using the AnimationSpeed property, which sets the speed of animation. This dependency property will be activated when the user expands or collapses the GroupBar Item of the GroupBar control. Using this property, you can control the animation speed of GroupBarItem while expanding / collapsing. It returns the speed of animation.

Use the following code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar that have animation speed --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar" AnimationSpeed="5" AnimationType="Fade"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Default"/&gt;      &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;      &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Save State"/&gt;      &lt;syncfusion:GroupViewItem Text="Load State"/&gt;      &lt;syncfusion:GroupViewItem Text="Reset State"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Getting the speed of animationgroupBar.AnimationSpeed = 5;   </td></tr>
</table>


Animation Type

When the GroupBar is collapsed or expanded, it gives an animation effect. There are three types of animation, defined for the GroupBar control using AnimationType property. This dependency property sets the animation type to be applied when GroupBar is collapsed or expanded. It provides the following options.

* Fade - Animation fades out when the GroupBar is collapsed or expanded
* None - No animation when the GroupBar is collapsed or expanded
* Slide - Animation slides when the GroupBar is collapsed or expanded

Use the following code snippet to set AnimationType property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar that have AnimationType as Fade --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" AnimationType="Fade" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Default"/&gt;      &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;      &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Save State"/&gt;      &lt;syncfusion:GroupViewItem Text="Load State"/&gt;      &lt;syncfusion:GroupViewItem Text="Reset State"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//To set animation type as FadegroupBar.AnimationType = AnimationsType.Fade;//To set animation type as NonegroupBar.AnimationType = AnimationsType.None;//To set animation type as SlidegroupBar.AnimationType = AnimationsType.Slide;</td></tr>
</table>


