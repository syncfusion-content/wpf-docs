---
layout: post
title: Getting Started| ThemeStudio | WPF | Syncfusion
description: Getting Started ThemeStudio
platform: WPF
control: ThemeStudio
documentation: ug
---

# Overview

Theme Studio for WPF can be used to create and apply new theme for Syncfusion controls from an existing theme. The primary goal here is to deliver an appearance rich Syncfusion controls that suits bests for every user application, based on their needs. 

## Supportive Themes in Theme Studio

The following list of predefined themes are currently provided in theme studio,
* Material Light
* Material Dark
* Material Light Blue
* Material Dark Blue

## Customizing theme color from Theme Studio

In theme studio utility, each theme has a unique common variable list. When user change the common variable color code value, it will reflect in all the Syncfusion WPFcontrols. All Syncfusion WPF control styles are derived from these theme-based common variables. This common variable list is handled inside the theme studio application for customizing theme-based colors. 

Let us now see the step-by-step procedure to launch and work with the theme studio utility below.


**Step 1:**

On installing the "Syncfusion WPF" suite, launch and select "Theme Studio" from the start-up panel.

![Theme Studio for WPF](ThemeStudio_images/Built-In-ThemeStudio.png)


**Step 2:**

The theme studio application has been divided into two sections: the controls preview section on the right, and the theme customization section on the left.

![Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Built-in-Dark.png)

**Step 3:**

To apply predefined themes, we need to choose the needed themes from Themes List available in ComboBox in the TopLeft Corner. 



![Shows the List of Themes in ThemeStudio](ThemeStudio_images/ThemeStudio-Theme-Selection.png)

**Step 4:**

Click the color pickers in the theme customization section to select the desired color.

![Choose color in Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Color-Selection.png)


**Step 5:**

The Syncfusion WPF controls will be rendered with the newly selected colors in the preview section, after selecting the desired color. 

![Color reflected in controls loaded inside Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Color-Selection-Change.png)


## Export the customized theme
 
You can export the custom theme after changing the theme colors.


**Step 1:**

Click the Export button in the top right corner below the exit of the theme studio application. 

![Export option in Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Export-Dark.png)


**Step 2:**

Now the export dialog appears with an option to select either entire controls or just the desired control(s). This option is useful when you have integrated a selective list of Syncfusion WPF controls in your application. The theme studio will filter only the selected controls and customize the final output for those controls alone. 

![Export dialog in Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Export-1.png)
**Step 3:**

You can select the required folder to be selected for Theme Export. On exporting,the download theme will come as a Theme Project that contains color codes for the selected Syncfusion WPF controls. 

![Export Theme assembly from Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Export-Dialog-1.png)

![Add Theme as Project for Theme Export](ThemeStudio_images/ThemeStudio-Themes-Folder.png)


## Using customized theme in a WPF application

You can now add the exported theme project in your WPF application and set the custom theme to the appropriate controls. In this illustration, we are going to witness the custom theme set for DockingManager.

**Step 1:**

Attach the exported theme project in your WPF project by right clicking the solution, Add-> Existing Project.

![Add reference for the Theme Export](ThemeStudio_images/ThemeStudio-Add-Project.png)

 
 **

**Step 3:**

`SfSkinManager` control helps to apply the built-in themes to the Syncfusion UI controls for WPF.
 There are several ways to add `SfSkinManager` in to Visual Studio WPF project.
The following steps help to add through XAML Code

1) Create a WPF project in Visual Studio and refer to the SfSkinManager assembly (Syncfusion.SfSkinManager.Wpf)
2) Include an XML namespace for the assembly to the Main window.

{% tabs %}

{% highlight XAML %}

    <Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"/>

{% endhighlight %}

{% endtabs %}

**Step 4:**

Any built-in themes can applied to the required control by `VisualStyle` attached property of the SfSkinManager.  Now, apply the value as `MaterialDark` to the VisualStyle property of the SfSkinManager for the Docking Manager control.


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

{% tabs %}

**Step 5:**

Compile and run the WPF application and you can now witness the custom theme applied to DockingManager control at run-time. 

![Apply Visual Style to the controls](ThemeStudio_images/ThemeStudio-Output1.png)






