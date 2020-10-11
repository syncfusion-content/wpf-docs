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

1. Click the `HierarchyNavigatorItemsControl`, to start the edit mode and which enables the AutoComplete function. 

2. In Edit mode, you can type a navigation path to display a list of navigation items below the HierarchyNavigatorItemsControl from which you can select.

3. Using the `Tab` key, you can navigate from editing to select the drop-down suggestions from Top to bottom order. using `Shift + Tab` key to select the items from bottom to top order.

4. When press the escape key while editing, the popup will be closed with the selected item or text edited in the HierarchyNavigator control. After that if we press escape key again, the editor will be closed and control will turn back to select mode with the previous selected item.  

5. using the Enter key after selecting the dropdown item using the arrow keys or tab key, the item must be selected based on the matched item and the control turn back to select mode. 

6. You can paste the text into editor instead of typing. The control checks for possible matching items and should be shown in the popup.

7. If enter the invalid path or text in the textbox, the popup should be closed. 

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



