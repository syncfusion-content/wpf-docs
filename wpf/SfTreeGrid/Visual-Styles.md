---
layout: post
title: Visual Styles in SfTreeGrid
description: How to apply visual styles in SfTreeGrid
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Visual Styles of SfTreeGrid

The appearance of the SfTreeGrid control is customized by using the [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/sfskinmanager/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.VisualStyles.html) property of `SfSkinManager`. Refer the following built in themes and its available assemblies.

<table>
<tr>
<td>
{{'**Style**'| markdownify }}
</td>
<td>
{{'**Assemblies**'| markdownify }}
</td>
</tr>
<tr>
<td>
Metro
</td>
<td>
Syncfusion.Themes.Metro.Wpf.dll
</td>
</tr>
<tr>
<td>
Lime
</td>
<td>
Syncfusion.Themes.Lime.Wpf.dll
</td>
</tr>
<tr>
<td>
Saffron
</td>
<td>
Syncfusion.Themes.Saffron.Wpf.dll
</td>
</tr>
<tr>
<td>
Blend
</td>
<td>
Syncfusion.Themes.Blend.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2013White
</td>
<td>
Syncfusion.Themes.Office2013White.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2013LightGray
</td>
<td>
Syncfusion.Themes.Office2013LightGray.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2013DarkGray
</td>
<td>
Syncfusion.Themes.Office2013DarkGray.Wpf.dll
</td>
</tr>
<tr>
<td>
VisualStudio2013
</td>
<td>
Syncfusion.Themes.VisualStudio2013.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2010Black
</td>
<td>
Syncfusion.Themes.Office2010Black.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2010Blue
</td>
<td>
Syncfusion.Themes.Office2010Blue.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2010Silver
</td>
<td>
Syncfusion.Themes.Office2010Silver.Wpf.dll
</td>
</tr>
<tr>
<td>
Office365
</td>
<td>
Syncfusion.Themes.Office365.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2016Colorful
</td>
<td>
Syncfusion.Themes.Office2016Colorful.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2016White
</td>
<td>
Syncfusion.Themes.Office2016White.Wpf.dll
</td>
</tr>
<tr>
<td>
Office2016DarkGray
</td>
<td>
Syncfusion.Themes.Office2016DarkGray.Wpf.dll
</td>
</tr>
<tr>
<td>
VisualStudio2015
</td>
<td>
Syncfusion.Themes.VisualStudio2015.Wpf.dll
</td>
</tr>
</table>

### Apply Visual Style to SfTreeGrid

Any built-in themes can applied to the SfTreeGrid by setting VisualStyle attached property of the SfSkinManager. In the below code example shows how to apply the theme for SfTreeGrid control

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfTreeGrid Name="treeGrid"                            
						AutoExpandMode="RootNodesExpanded"
						AutoGenerateColumns="False"
						sfSkin:SfSkinManager.VisualStyle="Office2016Colorful"
						ChildPropertyName="Children"
						ColumnSizer="Star"
						ExpanderColumn="FirstName"
						ItemsSource="{Binding PersonDetails}"
						ShowRowHeader="True">
						
{% endhighlight %}
{% highlight c# %}

SfSkinManager.SetVisualStyle(treeGrid, VisualStyles.Office2016Colorful);

{% endhighlight %}
{% endtabs %}

![](Visual-Styles_images/Visual-Styles_img1.png)

### Apply themes at run time

To apply the built-in themes can be changed at runtime by VisualStyle property. Here, a ComboBox control is used to switch various built-in themes that are referred in the assembly references. 

![](Visual-Styles_images/Visual-Styles_img2.png)

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfTreeGrid Name="treeGrid"                            
						AutoExpandMode="RootNodesExpanded"
						AutoGenerateColumns="False"
						sfSkin:SfSkinManager.VisualStyle="Office2016Colorful"
						ChildPropertyName="Children"
						ColumnSizer="Star"
						ExpanderColumn="FirstName"
						ItemsSource="{Binding PersonDetails}"
						ShowRowHeader="True">
							
	<StackPanel Margin="5">
		<TextBlock Margin="5" FontSize="12" FontWeight="Bold" Text="Visual Styles:" />
							
		<ComboBox x:Name="StylesComboBox" ItemsSource="{Binding Path=ComboBoxItemsSource}" FocusVisualStyle="{x:Null}" 
					SelectedIndex="1" Height="30" VerticalContentAlignment="Center" Margin="5">
			<interactivity:Interaction.Triggers>
				<interactivity:EventTrigger EventName="SelectionChanged">
					<local:VisualThemesTriggerAction TargetName="treeGrid" />
				</interactivity:EventTrigger>
			</interactivity:Interaction.Triggers>
		</ComboBox>                        
	</StackPanel>

{% endhighlight %}
{% highlight c# %}

	public class VisualThemesTriggerAction : TargetedTriggerAction<ComboBox>
	{
		SfTreeGrid grid = (Application.Current.MainWindow as VisualStylesDemo.MainWindow).treeGrid;

		/// <summary>
		/// Invokes the specified parameter.
		/// </summary>
		/// <param name="parameter">The parameter.</param>
		protected override void Invoke(object parameter)
		{
			var cb = this.AssociatedObject as ComboBox;
			// Apply Visual Style based on the selected theme
			switch (cb.SelectedItem.ToString())
			{
				case "Metro":
					SfSkinManager.SetVisualStyle(grid, VisualStyles.Metro);
					break;           
				case "Office2016Colorful":
					SfSkinManager.SetVisualStyle(grid, VisualStyles.Office2016Colorful);
					break;
				case "VisualStudio2015":
					SfSkinManager.SetVisualStyle(grid, VisualStyles.VisualStudio2015);
					break;
				default:
					SfSkinManager.SetVisualStyle(grid, VisualStyles.Default);
					break;
			}
		}
	}

{% endhighlight %}
{% endtabs %}

## ThemeStudio 

### Applying themes in Theme Studio
To apply predefined themes, we need to choose the needed themes from Themes List. Its available in drop down near Personalize Heading. Refer to the following link, to apply the theme in [ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#applying-predefined-themes-in-theme-studio) for syncfusion controls.

### Applying the custom theme in SfTreeGrid application
To apply the custom theme for SfTreeGrid control, you need to generate the resource dictionary xaml file from the ThemeStudio. Refer to the following link, to generate the resource dictionary file and then apply the [custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#applying-generated-resource-xaml-in-application) to SfTreeGrid control. 

#### Adding the XAML files to WPF Application
<ul>
<li> Open Visual Studio 20xx and create a WPF project. </li>

<li> Add the necessary dll’s for the controls used. For example, add SfTreeGrid control to the application. The SfTreeGrid control requires Syncfusion.SfGrid.WPF, Syncfusion.Data.WPF and Syncfusion.Shared.WPF assembly in the application. </li>

<li> The exported XAML file of controls can be obtained from the Output folder as described in the export topic. </li>

<li> From the Output folder, browse the Syncfusion Controls folder and add the required XAML file to the project. </li>

![](Visual-Styles_images/Visual-Styles_img4.png)

<li> Now, initialize the SfTreeGrid control in the MainWindow.xaml as below: </li>

{% tabs %}
{% highlight xaml %}

	<syncfusion:SfTreeGrid Name="treeGrid"
                    AutoExpandMode="RootNodesExpanded"
                    AutoGenerateColumns="False"
                    ChildPropertyName="Children"
                    ColumnSizer="Star"
                    ExpanderColumn="FirstName"
                    ItemsSource="{Binding PersonDetails}"
                    ShowRowHeader="True">

{% endhighlight %}
{% endtabs %}					

<li> Merge the SfTreeGrid.xaml in the application resources using MergedDictionaries.</li>

{% tabs %}
{% highlight xaml %}

	<Application.Resources>
		<ResourceDictionary>
			<ResourceDictionary.MergedDictionaries>
				<ResourceDictionary Source="..\VisualStudioDemos\CS\SfTreeGrid.xaml"/>
			</ResourceDictionary.MergedDictionaries>
		</ResourceDictionary>
	</Application.Resources>

{% endhighlight %}
{% endtabs %}

<li> Run the sample and the below output will be obtained: </li>

![](Visual-Styles_images/Visual-Styles_img3.png)

</ul>

### Importing and Exporting the custom theme in Theme Studio

#### Import the custom theme
To import custom theme in ThemeStudio, click Import button for choosing *.wpft file containing customized skin color values. After importing, we can visualize the loaded custom skin color applied to controls. Refer to the following link to [import the custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#importing-custom-theme-to-theme-studio)

#### Export the custom theme
To export the custom theme in ThemeStudio, click Export button to display a popup containing option to select the controls to be exported. Refer to the following link to [export the custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#exporting-custom-theme-from-theme-studio).