---
layout: post
title: Edit Mode| Hierarchical Navigator | Wpf | Syncfusion
description: edit mode
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Edit Mode

This feature allows you to easily edit a navigation path by setting the [IsEnableEditMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.HierarchyNavigator.html#Syncfusion_Windows_Tools_Controls_HierarchyNavigator_IsEnableEditMode) property to `true`. AutoComplete support is available in edit mode, which suggests matching nodes based on the path entered in the editor like the Windows Explorer.

In edit mode provides the following capabilities, 

1. To start the edit mode, click 'HierarchyNavigatorItemsControl' to enable the AutoComplete feature. 

2. In Edit mode, you can type a navigation path to show a list of navigation items you can select from under `HierarchyNavigatorItemsControl`.

3. You can use the 'Tab' key to navigate from editing to select drop-down suggestions from top to bottom order. Using the 'Shift + Tab' key to select items from the bottom to top order.

4. When pressing the 'Escape' key when editing, the popup will close with the selected item or edited text in the `HierarchyNavigator` control. After that, the editor is closed and the control is switched back to select mode with the previous item selected, if the escape key is pressed again.

5. You can paste the text into editor instead of typing and the `HierarchyNavigator` control checks for possible matching items and will be shown in the popup.

7. The popup will be closed if you enter an invalid path or text in the textbox.

{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
		xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
		x:Class="HierarchicalNavigatorSample.MainWindow"
		Title="HierarchicalNavigator Sample" Height="350" Width="525">
	<Grid>
		<!--Adding HierarchicalNavigator control -->
		<syncfusion:HierarchicalNavigator x:Name="hierarchicalNavigator" Width="100" Height="100" IsEnableEditMode="true" VerticalAlignment="Center" HorizontalAlignment="Center"/>
	</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Tools;
namespace HierarchicalNavigatorSample
{
	/// <summary>
	/// Interaction logic for MainWindow.xaml
	/// </summary>
	public partial class MainWindow : Window
	{
		public MainWindow()
		{
			InitializeComponent();
			//Creating an instance of HierarchicalNavigator control
			HierarchicalNavigator hierarchicalNavigator = new HierarchicalNavigator();
			hierarchyNavigator.IsEnableEditMode = true;
			
			//Adding HierarchicalNavigator as window content
			this.Content = hierarchicalNavigator;
		}
	}
}

{% endhighlight %}
{% endtabs %}

![Hierarchy Naviagtor with AutoComplete](Edit-Mode_images/AutoComplete_image.png)



