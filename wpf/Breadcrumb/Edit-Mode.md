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

1. Click the `HierarchyNavigatorItemsControl`, to start the edit mode and which enables the AutoComplete function. 

2. You can type a navigation path in Edit mode to display a list of navigation items under HierarchyNavigatorItemsControl which you can select from.

3. You can navigate from editing using the `Tab` key to select drop-down suggestions from the top to bottom order. To select items from the bottom to top order, use the `Shift + Tab` key.

4. The popup will be closed with the selected item or edited text in the HierarchyNavigator control when pressing the `Escape` key when editing. After that, if the escape key is pressed again, the editor is closed and the control is switched back to select mode with the previous item selected.

5. Using the `Enter` key, after using the arrow keys or the tab key to select the drop-down item, the item must be selected based on the matched item and the control switches back to select mode.

6. You can paste the text into editor instead of typing. The control checks for possible matching items and should be shown in the popup.

7. The popup should be closed if you enter an invalid path or text in the textbox.

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



