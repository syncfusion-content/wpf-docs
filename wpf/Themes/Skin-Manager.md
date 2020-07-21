---
layout: post
title: Steps to apply themes for Syncfusion Essential WPF controls
description: Learn here about how to apply the themes for Syncfusion Essential WPF controls using SfSkinManager control
platform: wpf
control: Themes
documentation: ug
---
# SkinManager overview

## Themes overview

`SfSkinManager` control helps to apply the built-in themes to the Syncfusion UI controls for WPF. There are 22 built-in themes that can be applied using `SfSkinManager` for rich user interface experience. Some of the built-in themes can be generated and referred in the [ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio). Refer to the following built in themes and its available assemblies below.

<table>
<tr>
<th>
Styles</th><th>
Assemblies</th></tr>
<tr>
<td>
MaterialLight</td><td>
Syncfusion.Themes.MaterialLight.Wpf.dll</td></tr>
<tr>
<td>
MaterialDark</td><td>
Syncfusion.Themes.MaterialDark.Wpf.dll</td></tr>
<tr>
<td>
MaterialLightBlue</td><td>
Syncfusion.Themes.MaterialLightBlue.Wpf.dll</td></tr>
<tr>
<td>
MaterialDarkBlue</td><td>
Syncfusion.Themes.MaterialDarkBlue.Wpf.dll</td></tr>
<tr>
<td>
Office2019Colorful</td><td>
Syncfusion.Themes.Office2019Colorful.Wpf.dll</td></tr>
<tr>
<td>
Office2019Black</td><td>
Syncfusion.Themes.Office2019Black.Wpf.dll</td></tr>
<tr>
<td>
Metro</td><td>
Syncfusion.Themes.Metro.Wpf.dll</td></tr>
<tr>
<td>
Lime</td><td>
Syncfusion.Themes.Lime.Wpf.dll</td></tr>
<tr>
<td>
Saffron</td><td>
Syncfusion.Themes.Saffron.Wpf.dll</td></tr>
<tr>
<td>
Blend</td><td>
Syncfusion.Themes.Blend.Wpf.dll</td></tr>
<tr>
<td>
Office2013White</td><td>
Syncfusion.Themes.Office2013White.Wpf.dll</td></tr>
<tr>
<td>
Office2013LightGray</td><td>
Syncfusion.Themes.Office2013LightGray.Wpf.dll</td></tr>
<tr>
<td>
Office2013DarkGray</td><td>
Syncfusion.Themes.Office2013DarkGray.Wpf.dll</td></tr>
<tr>
<td>
VisualStudio2013</td><td>
Syncfusion.Themes.VisualStudio2013.Wpf.dll</td></tr>
<tr>
<td>
Office2010Black</td><td>
Syncfusion.Themes.Office2010Black.Wpf.dll</td></tr>
<tr>
<td>
Office2010Blue</td><td>
Syncfusion.Themes.Office2010Blue.Wpf.dll</td></tr>
<tr>
<td>
Office2010Silver</td><td>
Syncfusion.Themes.Office2010Silver.Wpf.dll</td></tr>
<tr>
<td>
Office365</td><td>
Syncfusion.Themes.Office365.Wpf.dll</td></tr>
<tr>
<td>
Office2016Colorful</td><td>
Syncfusion.Themes.Office2016Colorful.Wpf.dll</td></tr>
<tr>
<td>
Office2016White</td><td>
Syncfusion.Themes.Office2016White.Wpf.dll</td></tr>
<tr>
<td>
Office2016DarkGray</td><td>
Syncfusion.Themes.Office2016DarkGray.Wpf.dll</td></tr>
<tr>
<td>
VisualStudio2015</td><td>
Syncfusion.Themes.VisualStudio2015.Wpf.dll</td></tr>
</table>

## Apply a theme to a control

This section covers how to apply themes for controls using `SfSkinManager`.

### Add SfSkinManager Reference

There are several ways to add the Syncfusion `SfSkinManager` in to Visual Studio WPF project. The following steps help to add through XAML Code

1) Create a WPF project in Visual Studio and refer to the `SfSkinManager` assembly from the build which is currently used. (Syncfusion.SfSkinManager.Wpf)
2) Include an XML namespace for the assembly to the Main window.

![Add SfSkinManager Reference](Skin-Manager_images/Skin-Manager_img1.png)

{% tabs %}

{% highlight XAML %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" />

{% endhighlight %}

{% endtabs %}

### Add theme assembly reference

`SfSkinManager` supports various built-in themes mentioned above. The corresponding style resources are included with the specific theme assemblies. To add theme assemblies, add the assembly from the build which is currently used. For Example,To apply Material Dark theme, use “Syncfusion.Themes.MaterialDark.Wpf”. Also, refer to the required theme assemblies with the project when needed.

![Add theme assembly reference](Skin-Manager_images/Skin-Manager_img2.png)


### Set visual style

Any built-in themes can applied to the both MS Controls and Syncfusion Controls by `VisualStyle` attached property of the SfSkinManager. All built-in assemblies have style resources for controls, so whenever an application get its style through SfSkinManager, the Theme’s corresponding control style merges with the applied controls resource dictionary. Now, apply the value as `MaterialDark` to the VisualStyle property of the SfSkinManager for the Docking Manager control.

{% tabs %}
{% highlight XAML %}

    <syncfusion:DockingManager x:Name="SyncDockingManager" UseDocumentContainer="True"
    PersistState="True" syncfusionskin:SfSkinManager.VisualStyle="MaterialDark">
                           
    <ContentControl x:Name="SolutionExplorer" syncfusion:DockingManager.Header="Solution Explorer"
    syncfusion:DockingManager.SideInDockedMode="Right"/>

    <ContentControl x:Name="ToolBox" syncfusion:DockingManager.Header="Toolbox"
    syncfusion:DockingManager.State="AutoHidden" />
    
    <ContentControl x:Name="Output" syncfusion:DockingManager.Header="Output"
    syncfusion:DockingManager.SideInDockedMode="Tabbed"
	syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer"/>

    <ContentControl x:Name="StartPage" syncfusion:DockingManager.Header="Start Page"
     syncfusion:DockingManager.State="Document" >
       <TextBlock Text="Any built-in themes can applied to the required control by VisualStyle attached property of the SfSkinManager." />                           
    </ContentControl>
    </syncfusion:DockingManager>

{% endhighlight %}
{% endtabs %}

![Applied skinmanager for WPF DockingManager control](Skin-Manager_images/Skin-Manager_img3.png)


## Apply a theme globally in the application

By Default, SfSkinManager merges the required resource files from the Theme assembly to the applied control. To apply the theme globally in the application, set the `ApplyStylesOnApplication` property to `True`. It merges all the resource files to the Application’s Resource Dictionary.


{% tabs %}

{% highlight C# %}

SfSkinManager.ApplyStylesOnApplication = true;

{% endhighlight %}

{% highlight VB %}

SfSkinManager.ApplyStylesOnApplication = True

{% endhighlight %}

{% endtabs %}

## Apply Style to custom controls

To apply the built-in themes to derived control using SfSkinManager, set the `SetResourceReference` in the custom control. This is required to refer style property of the derived control.

{% tabs %}

{% highlight XAML %}


<local:DockingAdv x:Name="SyncDockingManager" UseDocumentContainer="True" PersistState="True" >
    <ContentControl x:Name="SolutionExplorer"
                local:DockingAdv.Header="Solution Explorer" local:DockingAdv.SideInDockedMode="Right"/>
    <ContentControl x:Name="ToolBox" local:DockingAdv.Header="Toolbox" local:DockingAdv.State="AutoHidden"/>
    <ContentControl x:Name="Properties" local:DockingAdv.Header="Properties" local:DockingAdv.State="Float"/>
    <ContentControl x:Name="Output" local:DockingAdv.Header="Output"
                local:DockingAdv.SideInDockedMode="Tabbed" local:DockingAdv.TargetNameInDockedMode="SolutionExplorer"/>
    <ContentControl x:Name="StartPage" local:DockingAdv.Header="Start Page" local:DockingAdv.State="Document"/>
</local:DockingAdv>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}


public class DockingAdv : DockingManager
{
    public DockingAdv()
	{
		SetResourceReference(StyleProperty, typeof(DockingManager));
	}
}


{% endhighlight %}

{% highlight VB %}

Public Class DockingAdv
	Inherits DockingManager
	Public Sub New()
		SetResourceReference(StyleProperty, GetType(DockingManager))
	End Sub
End Class 

{% endhighlight %}

{% endtabs %}

## Clearing SkinManager instance in an application

SfSkinManager will hold some instance to use it further while applying theme. But this can be cleared using the function named “Dispose(object)” that needs to be hooked to the position where you need to clear the theme applied from SfSkinManager as like below code. Here “object” refers to the element which instance needs to be cleared.


{% tabs %}

{% highlight C# %}


private void Window_Closed(object sender, EventArgs e) 
{ 
   SfSkinManager.Dispose(this); 
} 

{% endhighlight %}

{% highlight VB %}


Private Sub Window_Closed(sender As Object, e As EventArgs)
    SfSkinManager.Dispose(Me)
End Sub

{% endhighlight %}

{% endtabs %}