---
layout: post
title: Themes | WPF | Syncfusion
description: common supports
platform: wpf
control: Themes
documentation: ug
---
# Themes

SfSkinManager control helps to apply the built in themes to the Syncfusion UI controls for WPF. Refer to the following built in themes and its available assemblies.

<table>
<tr>
<td>
**Styles**<br/><br/></td><td>
**Assemblies**<br/><br/></td></tr>
<tr>
<td>
Metro<br/><br/></td><td>
Syncfusion.Themes.Metro.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Blend<br/><br/></td><td>
Syncfusion.Themes.Blend.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Office2013White<br/><br/></td><td>
Syncfusion.Themes.Office2013White.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Office2013LightGray<br/><br/></td><td>
Syncfusion.Themes.Office2013LightGray.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Office2013DarkGray<br/><br/></td><td>
Syncfusion.Themes.Office2013DarkGray.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
VisualStudio2013<br/><br/></td><td>
Syncfusion.Themes.VisualStudio2013.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Office2010Black<br/><br/></td><td>
Syncfusion.Themes.Office2010Black.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Offie2010Blue<br/><br/></td><td>
Syncfusion.Themes.Offie2010Blue.Wpf.dll<br/><br/></td></tr>
<tr>
<td>
Office2010Silver<br/><br/></td><td>
Syncfusion.Themes.Office2010Silver.Wpf.dll<br/><br/></td></tr>
</table>

## Getting Started

### Add SfSkinManager to the Application

There are several ways to add the Syncfusion SfSkinManager in to Visual Studio WPF project. The following steps help to add the SfSkinManager through XAML Code

1. Create a WPF project in Visual Studio and refer to the SfSkinManager assembly (Syncfusion.SfSkinManager.Wpf)
2. Include an xml namespace for the assembly to the Main window.

{% highlight xml %}

<Window

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"

xmlns:syncfusion=[http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "") />



{% endhighlight %}

### Add Themes to the Application

Syncfusion UI controls for WPF supports various visual styles stated above. The corresponding style resources are included with the specific theme assemblies.  To apply Visual Studio style, use “Syncfusion.Themes.VisualStudio2013.Wpf”. Also, refer to the required theme assemblies with the project when needed. Here, the “Syncfusion.Themes.VisualStudio2013.Wpf” is added.

### Apply Visual Style to Controls

By using the **VisualStyle** attached property of the **SfSkinManager**, you can apply any build in themes to the required control.  Now, apply the value as **VisualStudio2013** to the **Visual Style** property of the **SfSkinManager** for the Docking Manager control.

{% highlight xml %}
<syncfusion:DockingManager x:Name="SyncDockingManager" UseDocumentContainer="True" PersistState="True" syncfusionskin:SfSkinManager.VisualStyle="VisualStudio2013">

<ContentControl x:Name="SolutionExplorer" syncfusion:DockingManager.Header="Solution Explorer"  syncfusion:DockingManager.SideInDockedMode="Right"/>

<ContentControl x:Name="ToolBox" syncfusion:DockingManager.Header="Toolbox" syncfusion:DockingManager.State="AutoHidden" />

<ContentControl x:Name="Properties" syncfusion:DockingManager.Header="Properties" syncfusion:DockingManager.State="Float" />

<ContentControl x:Name="Output" syncfusion:DockingManager.Header="Output" syncfusion:DockingManager.SideInDockedMode="Tabbed" syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer"/>

<ContentControl x:Name="StartPage" syncfusion:DockingManager.Header="Start Page" syncfusion:DockingManager.State="Document" />

</syncfusion:DockingManager>





{% endhighlight %}

![](GettingStarted_images/GettingStarted_img1.jpeg)


### Apply themes at run time

You can switch various build in themes at the runtime by using the **VisualStyle** property. Here, a ComboBox Control is used to switch various build in themes that are referred in the assembly references.

![](GettingStarted_images/GettingStarted_img2.jpeg)


{% highlight xml %}
<Grid>

<Grid.RowDefinitions>

<RowDefinition Height="20"></RowDefinition>

<RowDefinition Height="*"></RowDefinition>

</Grid.RowDefinitions>

<ComboBox SelectionChanged="ComboBox_SelectionChanged">

<ComboBoxItem>Metro</ComboBoxItem>

<ComboBoxItem>Blend</ComboBoxItem>

<ComboBoxItem>VisualStudio2013</ComboBoxItem>

<ComboBoxItem>Office2013White</ComboBoxItem>

<ComboBoxItem>Office2013DarkGray</ComboBoxItem>

<ComboBoxItem>Office2013LightGray</ComboBoxItem>

<ComboBoxItem>Office2010Black</ComboBoxItem>

<ComboBoxItem>Office2010Blue</ComboBoxItem>

<ComboBoxItem>Office2010Silver</ComboBoxItem>

</ComboBox>

<syncfusion:DockingManager Grid.Row="1" x:Name="SyncDockingManager" UseDocumentContainer="True" PersistState="True" >

<ContentControl x:Name="SolutionExplorer" syncfusion:DockingManager.Header="Solution Explorer"  syncfusion:DockingManager.SideInDockedMode="Right"/>

<ContentControl x:Name="ToolBox" syncfusion:DockingManager.Header="Toolbox" syncfusion:DockingManager.State="AutoHidden" />

<ContentControl x:Name="Properties" syncfusion:DockingManager.Header="Properties" syncfusion:DockingManager.State="Float" />

<ContentControl x:Name="Output" syncfusion:DockingManager.Header="Output" syncfusion:DockingManager.SideInDockedMode="Tabbed" syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer"/>

<ContentControl x:Name="StartPage" syncfusion:DockingManager.Header="Start Page" syncfusion:DockingManager.State="Document" />

</syncfusion:DockingManager>

</Grid>

private void ComboBox_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

SfSkinManager.SetVisualStyle(this,(VisualStyles)Enum.Parse(typeof(VisualStyles),((sender as ComboBox).SelectedItem as ComboBoxItem).Content.ToString()));

}



{% endhighlight %}

## MS Controls Themes

All built-in assemblies have Style resources for MS controls, so whenever an application get its style through SfSkinManager, the Theme’s corresponding MS Control style merges with the applied controls resource dictionary. 

## Applying theme globally in the application

By Default SfSkinManager merges the required resource files from the Theme assembly to the applied control. To apply the theme globally in the application, set the **ApplyStylesOnApplication** property to **True.** It merges all the resource files to the Application’s Resource Dictionary.

{% highlight c# %}

SfSkinManager.ApplyStylesOnApplication = true;


{% endhighlight %}

## Apply Style to custom controls

To apply the built-in themes to your derived control using SfSkinManager, you have to set the **SetResourceReference** in the custom control. This is required to refer style property of the derived control.

{% highlight xml %}


<local:DockingAdv x:Name="SyncDockingManager" UseDocumentContainer="True" PersistState="True" >

<ContentControl x:Name="SolutionExplorer" local:DockingAdv.Header="Solution Explorer"  local:DockingAdv.SideInDockedMode="Right"/>

<ContentControl x:Name="ToolBox" local:DockingAdv.Header="Toolbox" local:DockingAdv.State="AutoHidden" />

<ContentControl x:Name="Properties" local:DockingAdv.Header="Properties" local:DockingAdv.State="Float" />

<ContentControl x:Name="Output" local:DockingAdv.Header="Output" local:DockingAdv.SideInDockedMode="Tabbed" local:DockingAdv.TargetNameInDockedMode="SolutionExplorer"/>

<ContentControl x:Name="StartPage" local:DockingAdv.Header="Start Page" local:DockingAdv.State="Document" />

</local:DockingAdv>

public class DockingAdv : DockingManager

{

public DockingAdv()

{

SetResourceReference(StyleProperty, typeof(DockingManager));

}

}



{% endhighlight %}


