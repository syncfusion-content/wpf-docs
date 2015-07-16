---
layout: post
title: Feature-to-resize-the-FloatWindow-dynamically-depend-on-child-size
description: feature to resize the floatwindow dynamically depend on child size
platform: wpf
control: DockingManager
documentation: ug
---

### Feature to resize the FloatWindow dynamically depend on child size

Normally SizetoContentInFloat property can be used to resize the FloatWindow to its child size while initializing the FloatWindow. But when Float child of DockingManager is resized,dynamically it doesn’t have any options to resize the FloatWindow to that content size. FloatWindowHeight and FloatWindowWidth are introduced for this purpose.. The usage has been shown below.



<table>
<tr>
<td>
XAML&lt;Grid&gt;   &lt;Grid.RowDefinitions&gt;     &lt;RowDefinition Height="0.08*"/&gt;     &lt;RowDefinition Height="*"/&gt;   &lt;/Grid.RowDefinitions&gt;  &lt;Button Content="click" Click="Button_Click"/&gt;  &lt;syncfusion:DockingManager Name="dockingmanager" Grid.Row="1"&gt;    &lt;Grid Name="grid1" Width="300" Height="300" syncfusion:DockingManager.FloatWindowWidth="{Binding Width, RelativeSource={RelativeSource Self},Mode=OneWay}" syncfusion:DockingManager.FloatWindowHeight="{Binding Height,RelativeSource={RelativeSource Self},Mode=OneWay}" syncfusion:DockingManager.DesiredWidthInFloatingMode="300" syncfusion:DockingManager.DesiredHeightInFloatingMode="300"  syncfusion:DockingManager.State="Float"/&gt;  &lt;/syncfusion:DockingManager&gt;&lt;/Grid&gt;</td></tr>
<tr>
<td>
C#:private void Button_Click(object sender, RoutedEventArgs e){    grid1.Width += 50;    grid1.Height + = 50;}</td></tr>
</table>


When the button is clicked width and height of the controls changes dynamically so that the binded FloatWindowWidth and FloatWindowHeight gets reflected dynamically. Similarly we can use FloatWindowSize property to set size of floatwindow dynamically.

