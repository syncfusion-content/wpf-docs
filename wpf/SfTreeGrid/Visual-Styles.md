---
layout: post
title: Visual Styles in SfTreeGrid
description: How to apply visual styles in SfTreeGrid
platform: wpf
control: SfTreeGrid
documentation: ug
---

# VisualStyle

The appearance of the SfTreeGrid control is customized using the [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/sfskinmanager/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.VisualStyles.html) property of `SfSkinManager`. Refer to the following built-in themes and available assemblies:

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

### Apply VisualStyle to SfTreeGrid

Any built-in themes can be applied to SfTreeGrid by setting the VisualStyle attached property of SfSkinManager. To apply theme for the SfTreeGrid control, follow the code example:

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

### Apply themes at runtime

To apply built-in themes at runtime, use the VisualStyle property. Here the ComboBox control is used to switch various built-in themes that are referred in assembly references. 

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

### Applying themes in ThemeStudio

Predefined themes can be applied by choosing themes from the theme list. It is available in the DropDown option near the Personalize heading. Refer to the following link to apply the theme in the [ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#applying-predefined-themes-in-theme-studio) for the Syncfusion controls.

### Applying the custom theme in SfTreeGrid application

To apply the custom theme, generate the resource dictionary xaml file from ThemeStudio. Refer to the following link to generate the resource dictionary file and then apply the [custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#applying-generated-resource-xaml-in-application) to the SfTreeGrid control. 

#### Adding XAML files to WPF application

<ul>
<li> Open Visual Studio 20xx and create WPF project. </li>

<li> Add the necessary dll for the controls used. For example, add the SfTreeGrid control to the application. The SfTreeGrid control requires Syncfusion.SfGrid.WPF, Syncfusion.Data.WPF, and Syncfusion.Shared.WPF assembly in the application. </li>

<li> In ThemeStudio, you can get the customized style of SfDataGrid from the Output folder as described in the export topic. </li>

<li> From the Output folder, browse the Syncfusion controls folder and add the required XAML file to the project. </li>

![](Visual-Styles_images/Visual-Styles_img4.png)

<li> Now initialize the SfTreeGrid control in the MainWindow.xaml as follows: </li>

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

<li> Run the sample and the following output will be obtained: </li>

![](Visual-Styles_images/Visual-Styles_img3.png)

</ul>

### Importing and exporting the custom theme in ThemeStudio

#### Import the custom theme

To import the custom theme in ThemeStudio, click Import button for choosing *.wpft file containing customized skin color values. After importing custom theme, the loaded custom skin color applied to controls can be visualized. Refer to the following link to [import the custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#importing-custom-theme-to-theme-studio).

#### Export the custom theme

To export the custom theme in ThemeStudio, click Export button to display a popup that contains option to select the controls to be exported. Refer to the following link to [export the custom theme](https://help.syncfusion.com/wpf/themes/theme-studio#exporting-custom-theme-from-theme-studio).