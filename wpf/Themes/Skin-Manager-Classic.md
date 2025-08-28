---
layout: post
title: WPF Skin Manager (Classic) | Apply Themes for Syncfusion WPF controls
description: Learn about how to apply the themes for Syncfusion WPF controls and Framework controls using the skin manager (Classic).
platform: wpf
control: Themes
documentation: ug
---
# WPF Skin Manager Classic 

The Classic Skin Manager in WPF applies themes by merging style definitions from theme assemblies into the application's visual tree. Each theme assembly contains resource dictionaries with styles for controls. When the `Theme` property is set, the Skin Manager merges the appropriate theme resources into the resource dictionary of the target element or into `Application.Current.Resources`, ensuring consistent styling across the element and its descendants. 

N> Theme Studio-based themes provide improved consistency and uniqueness among various controls when compared to other themes. It is preferable to use Theme Studio-based themes in the application over other themes. 

## Themes list

The following table lists the available themes as well as the assembly or NuGet reference to be used in the application. 

<table>
<tr>
<th>
Styles</th><th>
Assembly</th><th>
NuGet package</th></tr>
<tr>
<td>
Metro</td><td>
Syncfusion.Themes.Metro.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Metro.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Metro.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Lime</td><td>
Syncfusion.Themes.Lime.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Lime.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Lime.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Saffron</td><td>
Syncfusion.Themes.Saffron.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Saffron.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Saffron.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Blend</td><td>
Syncfusion.Themes.Blend.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Blend.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Blend.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013White</td><td>
Syncfusion.Themes.Office2013White.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013White.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013White.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013LightGray</td><td>
Syncfusion.Themes.Office2013LightGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013LightGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013LightGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2013DarkGray</td><td>
Syncfusion.Themes.Office2013DarkGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2013DarkGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2013DarkGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
VisualStudio2013</td><td>
Syncfusion.Themes.VisualStudio2013.Wpf.dll</td><td>
{{'[Syncfusion.Themes.VisualStudio2013.WPF](https://www.nuget.org/packages/Syncfusion.Themes.VisualStudio2013.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Black</td><td>
Syncfusion.Themes.Office2010Black.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Black.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Black.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Blue</td><td>
Syncfusion.Themes.Office2010Blue.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Blue.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Blue.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2010Silver</td><td>
Syncfusion.Themes.Office2010Silver.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2010Silver.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2010Silver.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office365</td><td>
Syncfusion.Themes.Office365.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office365.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office365.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016Colorful</td><td>
Syncfusion.Themes.Office2016Colorful.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016Colorful.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016Colorful.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016White</td><td>
Syncfusion.Themes.Office2016White.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016White.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016White.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
Office2016DarkGray</td><td>
Syncfusion.Themes.Office2016DarkGray.Wpf.dll</td><td>
{{'[Syncfusion.Themes.Office2016DarkGray.WPF](https://www.nuget.org/packages/Syncfusion.Themes.Office2016DarkGray.WPF/)'| markdownify }}
</td></tr>
<tr>
<td>
VisualStudio2015</td><td>
Syncfusion.Themes.VisualStudio2015.Wpf.dll</td><td>
{{'[Syncfusion.Themes.VisualStudio2015.WPF](https://www.nuget.org/packages/Syncfusion.Themes.VisualStudio2015.WPF/)'| markdownify }}
</td></tr>
</table>

The following table lists alternative theme studio themes suggestions to be used in the application. 

<table>
<tr>
<th>
Styles</th><th>
Alternative theme studio themes suggestion to use</th></tr>
<tr>
<td>
Metro</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Lime</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Saffron</td><td>
FluentLight, Office2019Colorful</td></tr>
<tr>
<td>
Blend</td><td>
FluentDark, MaterialDark, Office2019Black</td></tr>
<tr>
<td>
Office2013White</td><td>
Office2019White</td></tr>
<tr>
<td>
Office2013LightGray</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2013DarkGray</td><td>
Office2019DarkGray</td></tr>
<tr>
<td>
VisualStudio2013</td><td>
-</td></tr>
<tr>
<td>
Office2010Black</td><td>
-</td></tr>
<tr>
<td>
Office2010Blue</td><td>
-</td></tr>
<tr>
<td>
Office2010Silver</td><td>
-</td></tr>
<tr>
<td>
Office365</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2016Colorful</td><td>
Office2019Colorful</td></tr>
<tr>
<td>
Office2016White</td><td>
Office2019White</td></tr>
<tr>
<td>
Office2016DarkGray</td><td>
Office2019DarkGray</td></tr>
<tr>
<td>
VisualStudio2015</td><td>
-</td></tr>
</table>

### Set theme

Themes will be applied to both Syncfusion<sup>&reg;</sup> and Framework controls by using [Theme](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html#Syncfusion_SfSkinManager_SfSkinManager_ThemeProperty) attached property of the [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html).

{% tabs %}

{% highlight XAML %}

<Window x:Class="DataGrid_Themes.MainWindow"
                             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                             xmlns:local="clr-namespace:DataGrid_Themes"
                             xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
                             xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
                             Icon="App.ico"
                             Title="Getting Started"
                             WindowStartupLocation="CenterScreen"
                             syncfusionskin:SfSkinManager.Theme="{syncfusionskin:SkinManagerExtension ThemeName=Windows11Light}">

    <Grid DataContext="{StaticResource viewmodel}">
        <syncfusion:SfDataGrid Name="sfgrid" Margin="5"
                                       AutoGenerateColumns="False"
                                       AllowDraggingColumns="True"
                                       AllowEditing="True"
                                       LiveDataUpdateMode="AllowDataShaping"
                                       AllowFiltering="True"
                                       HeaderRowHeight="26"
                                       SelectionMode="Extended"
                                       ColumnSizer="Auto"
                                       ItemsSource="{Binding EmployeeDetails}">
        </syncfusion:SfDataGrid>
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetTheme(this, new Theme("Windows11Light"));

{% endhighlight %}

{% endtabs %}

![Applied skinmanager theme for WPF ChromelessWindow and SfDataGrid control](Skin-Manager_images/Applied-SkinManager-Theme-WPF-ChromelessWindow-DataGrid.jpg)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/wpf-themes-demo-using-skinmanager).

## Apply a theme globally in the application

By default, [SfSkinManager](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinManager.SfSkinManager.html) merges the required resource files from the theme assembly to the element to which the theme is applied. To apply a theme globally in an application, set the `ApplyStylesOnApplication` property to `True`. It merges all the theme resource files to `Application.Current.Resources`.

N> The `SfSkinManager.ApplyStylesOnApplication` static property should be set before `InitializeComponent` of the window or during application start up, when applying for multiple windows. 

{% tabs %}

{% highlight C# %}

SfSkinManager.ApplyStylesOnApplication = true;

{% endhighlight %}

{% endtabs %}


## Apply themes to the controls derived from Syncfusion<sup>&reg;</sup> controls

To apply themes to the derived control using `SfSkinManager`, call [SetResourceReference](https://learn.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.setresourcereference?view=windowsdesktop-8.0) method and, pass the `StyleProperty` and derived control type as parameters. 

{% tabs %}

{% highlight XAML %}

 <local:SfDataGridExt x:Name="grid"
                             AllowGrouping="True"
                             AutoGenerateColumns="False"
                             ItemsSource="{Binding EmployeeDetails}"
                             ShowGroupDropArea="True">
            <local:SfDataGridExt.Resources>
                <ResourceDictionary>
                    <ResourceDictionary.MergedDictionaries>
                        <ResourceDictionary Source="/Syncfusion.SfGrid.WPF;component/Styles/Styles.xaml" />
                    </ResourceDictionary.MergedDictionaries>
                </ResourceDictionary>
            </local:SfDataGridExt.Resources>
            <local:SfDataGridExt.Columns>
                <syncfusion:GridNumericColumn MappingName="EmployeeAge" />
                <syncfusion:GridTextColumn MappingName="EmployeeName" />
                <syncfusion:GridTextColumn MappingName="EmployeeGender" />
                <syncfusion:GridTextColumn AllowEditing="True" MappingName="Country" />
                <syncfusion:GridNumericColumn MappingName="EmployeeSalary" />
            </local:SfDataGridExt.Columns>
</local:SfDataGridExt>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 public class SfDataGridExt : SfDataGrid
    {
        public SfDataGridExt()
        {
            SetResourceReference(StyleProperty, typeof(SfDataGrid));
        }
    }

{% endhighlight %}

{% endtabs %}

## How to

### Customize theme in application level

To customize the Syncfusion<sup>&reg;</sup> theme at application level, merge the theme into ResourceDictionary and override the style using 'BasedOn' property. 

In 'ResourceDictionary', mention the style path which needs to be overridden, in 'BasedOn', mention the key stated in the table.

We can customize or override the theme styles by following the steps outlined below.


**Step 1**: Merge the resource dictionaries of the controls which need to be customized. In this example, we have merged the Framework Button‘s resource dictionary.
{% tabs %}

{% highlight XAML %}

<ResourceDictionary.MergedDictionaries> 
     <ResourceDictionary Source="/Syncfusion.Themes.Windows11Light.WPF;component/MSControl/Button.xaml" /> 
</ResourceDictionary.MergedDictionaries>

{% endhighlight %}

{% endtabs %}

**Step 2**: Declare style for the control with 'BasedOn' key. Here style of the button has been declared and its key is used in 'BasedOn'. Button's Background, Foreground, FontFamily, BorderBrush have been overridden.

{% tabs %}

{% highlight XAML %}

   <Style BasedOn="{StaticResource WPFButtonStyle}" 
          x:Key="customizeButtonStyle"    
          TargetType="{x:Type Button}">
         <Setter Property="Background" Value="#5dbea3" />
         <Setter Property="Foreground" Value="White" />
         <Setter Property="FontFamily" Value="Berlin Sans FB Demi" />
         <Setter Property="BorderBrush" Value="#5dbea3" />   
   </Style>

{% endhighlight %}

{% endtabs %}

**Step 3**: Now, utilize the customized styles in our application using the 'Style' property. This step adds custom styles of Buttons in WPF application. 

{% tabs %}

{% highlight XAML %}

<StackPanel Orientation="Horizontal" >
    <Button Content="OK" Height="30" Width="120" Margin="10" Style="{StaticResource customizeButtonStyle}"></Button>
    <Button Content="Cancel" Height="30" Width="120" Margin="10" Style="{StaticResource customizeButtonStyle}"></Button>          
</StackPanel>

{% endhighlight %}

{% endtabs %}

![Customizing theme styles basedOn for buttons](Skin-Manager_images/CustomizingStyle.png)

### Change visual style at runtime

Themes for application can be changed at runtime by changing `VisualStyle` property. Make sure that the new theme assembly is attached as reference in the application when applying theme.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="DataGrid_Themes.MainWindow"
                             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                             xmlns:local="clr-namespace:DataGrid_Themes"
                             xmlns:system="clr-namespace:System;assembly=mscorlib"
                             xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
                             xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
                             syncfusionskin:SfSkinManager.VisualStyle="{Binding ElementName=comboVisualStyle, Path=SelectedValue, Mode=OneWay, UpdateSourceTrigger=PropertyChanged}">

    <syncfusion:ChromelessWindow.Resources>
        <ObjectDataProvider
            x:Key="Themes"
            MethodName="GetValues"
            ObjectType="{x:Type system:Enum}">
            <ObjectDataProvider.MethodParameters>
                <x:Type TypeName="syncfusionskin:VisualStyles" />
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>
    </syncfusion:ChromelessWindow.Resources>

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="40"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <ComboBox
                x:Name="comboVisualStyle"
                Grid.Row="0"
                Width="250"
                Margin="5"
                ItemsSource="{Binding Source={StaticResource Themes}}"
                SelectedIndex="18" />
                
        <Grid Grid.Row="1" DataContext="{StaticResource viewmodel}">
            <syncfusion:SfDataGrid Name="sfgrid" Margin="5"
                                       AutoGenerateColumns="False"
                                       AllowDraggingColumns="True"
                                       AllowEditing="True"
                                       LiveDataUpdateMode="AllowDataShaping"
                                       AllowFiltering="True"
                                       HeaderRowHeight="26"
                                       SelectionMode="Extended"
                                       ColumnSizer="Auto"
                                       ItemsSource="{Binding EmployeeDetails}">
             
            </syncfusion:SfDataGrid>
        </Grid>
    </Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetVisualStyle(this, (VisualStyles)Enum.Parse(typeof(VisualStyles), comboVisualStyle.SelectedItem.ToString()));

{% endhighlight %}

{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/change-themes-at-runtime-using-skinmanager).

### Switch theme with custom styles

To change a theme dynamically with custom styles, utilize the resource dictionary and override the style using the 'BasedOn' property.

We have provided an example that demonstrates switching between the Window11Light and Windows11Dark themes using the SfGrid control. In this example, we customize the foreground color of the GridTableSummaryCell to green in **Window 11 Light** and red in **Windows 11 Dark**.
 
*  **Step 1**: In this example, we have an SfDataGrid and a RadioButton which is used to switching theme and we need to add resource dictionaries with paths in merged dictionaries in view model or code behind. The following code can be used to effortlessly switch themes.
 
{% tabs %}

{% highlight C# %}

        private void RadioButton_Click(object sender, RoutedEventArgs e)
        {
            var themeName = (sender as RadioButton).Content.ToString();
            string syncfusionTheme = string.Empty;
            if (themeName == "Dark")
            {
                syncfusionTheme = "Windows11Dark";
                SfSkinManager.SetTheme(Application.Current.MainWindow, new Theme("Windows11Dark"));
            }
            else if (themeName == "Light")
            {
                syncfusionTheme = "Windows11Light";
                SfSkinManager.SetTheme(Application.Current.MainWindow, new Theme("Windows11Light"));
            }
            
            MergeResourceDictionary(syncfusionTheme);
            MergeCustomResourceDictionary(themeName);
        }

        private void MergeResourceDictionary(string syncfusionTheme)
        {
            Application.Current.Resources.MergedDictionaries.Add(new ResourceDictionary()
            {
                Source = new Uri($"/Syncfusion.Themes.{syncfusionTheme}.WPF;component/MSControl/Window.xaml", UriKind.RelativeOrAbsolute)
            });
            Application.Current.Resources.MergedDictionaries.Add(new ResourceDictionary()
            {
                Source = new Uri($"/Syncfusion.Themes.{syncfusionTheme}.WPF;component/MSControl/ComboBox.xaml", UriKind.RelativeOrAbsolute)
            });       
            Application.Current.Resources.MergedDictionaries.Add(new ResourceDictionary()
            {
                Source = new Uri($"/Syncfusion.Themes.{syncfusionTheme}.WPF;component/SfDataGrid/SfDataGrid.xaml", UriKind.RelativeOrAbsolute)
            });
        }

        private void MergeCustomResourceDictionary(object selectedTheme)
        {
            Application.Current.Resources.MergedDictionaries.Add(new ResourceDictionary()
            {
                Source = new Uri($"/WpfApp1;component/Themes/{selectedTheme}.xaml", UriKind.RelativeOrAbsolute)
            });
        }

{% endhighlight %}

{% endtabs %}

*  **Step 2**: Customize the foreground color and font weight of the table summary row in both light and dark themes.

**Light Theme**

{% tabs %}

{% highlight XAML %}

<!--Light.xaml-->
<ResourceDictionary>
           <Style BasedOn="{StaticResource SyncfusionGridTableSummaryCellStyle}"
                  TargetType="syncfusion:GridTableSummaryCell">      
                <Setter Property="FontWeight"  Value="Bold" />
                <Setter Property="Foreground" Value="Green" />      
           </Style>
</ResourceDictionary>

{% endhighlight %}

{% endtabs %}

**Dark Theme**

{% tabs %}

{% highlight XAML %}

<!--Dark.xaml-->

<ResourceDictionary>
                <Style BasedOn="{StaticResource SyncfusionGridTableSummaryCellStyle}"
                           TargetType="syncfusion:GridTableSummaryCell">      
                               <Setter Property="FontWeight"    Value="Bold" />
                               <Setter Property="Foreground"   Value="Red" />       
            </Style>
</ResourceDictionary>

{% endhighlight %}

{% endtabs %}

**Output Screenshots**

Light Theme:

![Customizing theme while run time in Light](Skin-Manager_images/Switching-theme-at-runtime-light1.png)

Dark Theme:
![Customizing theme while run time in Dark](Skin-Manager_images/Switching-theme-at-runtime-Dark1.png)

