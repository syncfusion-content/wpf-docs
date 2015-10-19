---
layout: post
title: Themes
description: common supports
platform: wpf
control: Themes
documentation: ug
---
#Themes

## Getting Started

### Add SfSkinManager to the Application

There are [several ways](C:\Users\Selvaganapathy\Desktop\Need to redirect to Common section# "") to add Syncfusion SfSkinManager to Visual Studio WPF project. The following steps help you add it through XAML Code.

1. Create a WPF project in Visual Studio and refer the SfSkinManager assembly (Syncfusion.SfSkinManager.Wpf)
2. Include an xml namespace for the assembly to the main window.

{% highlight xml %}

<Window

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"

xmlns:syncfusion=[http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "") />



{% endhighlight %}

### Add Themes to the Application

Syncfusion UI controls for WPF supports various visual styles stated above. Corresponding style resources are included with the specific theme assemblies.  To apply Visual Studio style, “Syncfusion.Themes.VisualStudio2013.Wpf” helps. Refer the required theme assemblies with the project if needed. Added here is “Syncfusion.Themes.VisualStudio2013.Wpf”

### Apply Visual Style to Controls

Using the **VisualStyle** attached property of the SfSkinManager, you can apply any built-in themes to the required control.  Now, apply the value as **VisualStudio2013** to Visual Style property of SfSkinManager for the Docking Manager control.

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

You can switch various built-in themes at runtime using the **VisualStyle** property. Here a ComboBox Control is used to switch various build in themes that are referred in assembly references.

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

