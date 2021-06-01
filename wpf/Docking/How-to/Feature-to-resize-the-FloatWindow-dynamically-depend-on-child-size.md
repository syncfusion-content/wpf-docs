---
layout: post
title: Feature to resize the FloatWindow in WPF DockingManager | Syncfusion
description: Feature to resize the floatwindow dynamically depend on child size in Syncfusion Essential Studio WPF DockingManager control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# Feature to resize the FloatWindow dynamically depend on child size

Normally SizetoContentInFloat property can be used to resize the FloatWindow to its child size while initializing the FloatWindow. But when Float child of DockingManager is resized,dynamically it doesn’t have any options to resize the FloatWindow to that content size. FloatWindowHeight and FloatWindowWidth are introduced for this purpose.. The usage has been shown below.

{% tabs %}

{% highlight xaml %}

<Grid>
   
	<Grid.RowDefinitions>  
	
		<RowDefinition Height="0.08*"/>
		
		<RowDefinition Height="*"/>  
		
	</Grid.RowDefinitions>  
	
	<Button Content="click" Click="Button_Click"/>  
	
	<syncfusion:DockingManager Name="dockingmanager" Grid.Row="1">
    
		<Grid Name="grid1" Width="300" Height="300" syncfusion:DockingManager.FloatWindowWidth="{Binding Width, RelativeSource={RelativeSource Self},Mode=OneWay}" syncfusion:DockingManager.FloatWindowHeight="{Binding Height,RelativeSource={RelativeSource Self},Mode=OneWay}" syncfusion:DockingManager.DesiredWidthInFloatingMode="300" syncfusion:DockingManager.DesiredHeightInFloatingMode="300"  syncfusion:DockingManager.State="Float"/>  
	
	</syncfusion:DockingManager>
	
</Grid>

{% endhighlight  %}

{% highlight c# %}

private void Button_Click(object sender, RoutedEventArgs e)
{    
 grid1.Width += 50;    
 grid1.Height + = 50;
}

{% endhighlight  %}

{% endtabs %}

When the button is clicked width and height of the controls changes dynamically so that the binded FloatWindowWidth and FloatWindowHeight gets reflected dynamically. Similarly we can use FloatWindowSize property to set size of float window dynamically.
