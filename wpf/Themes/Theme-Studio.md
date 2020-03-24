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

## Customizing theme color from theme studio

In theme studio utility, each theme has a unique common variable list. When user change the common variable color code value, it will reflect in all the Syncfusion WPFcontrols. All Syncfusion WPF control styles are derived from these theme-based common variables. This common variable list is handled inside the theme studio application for customizing theme-based colors. 

Let us now see the step-by-step procedure to launch and work with the theme studio utility below.


**Step 1:**

On installing the "Syncfusion WPF" suite, lunch and select "Theme Studio" from the start-up panel.

![Theme Studio for WPF](ThemeStudio_images/Built-ThemeStudio.png)


**Step 2:**

The theme studio application form has been divided into two sections: the controls preview section on the right, and the theme customization section on the left.

![Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Built-in-Dark.png)

**Step 3:**

To apply predefined themes, we need to choose the needed themes from Themes List available in ComboBox in the TopLeft Corner. 

The following list of predefined themes are currently provided in theme studio,
* Material Light
* Material Dark
* Material Light Blue
* Material Dark Blue
* Default

![Shows the List of Themes in ThemeStudio](ThemeStudio_images/Themes-Selection-Dark.png)

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

Now the export dialog appears with an option to select either entire controls or just the desired control(s). This option is useful when you have integrated a selective list of Syncfusion WPF controls in your application. The theme studio will filter only the selected controls and customize the final output for those controls alone thereby reducing the final output assembly size. 

![Export dialog in Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Export-Dialog-Dark.png)
**Step 3:**

You can select the required folder to be selected for Theme Export. The download theme will come as an assembly (*.dll) file that contains color codes for the selected Syncfusion WPF controls. 

![Export Theme assembly from Theme Studio for WPF](ThemeStudio_images/ThemeStudio-Browse-Export.png)


 You can enter the assembly name of your own choice while exporting. But remember that the assembly (*.dll) name will be custom theme name, when you refer it in your WPF application. 


## Add customized theme in a WPF application
**Add Themes as a Project**

`SfSkinManager` control helps to apply the built-in themes to the Syncfusion UI controls for WPF. You can select it export theme folder that were atated above and add them as a project to the WPF Application.  To apply Visual Studio style, use “Syncfusion.Themes.MaterialDark.WPF_2013.csproj”. 



**Add SfSkinManager to the WPF Application**

 There are several ways to add `SfSkinManager` in to Visual Studio WPF project.
The following steps help to add through XAML Code

1) Create a WPF project in Visual Studio and refer to the SfSkinManager assembly (Syncfusion.SfSkinManager.Wpf)
2) Include an XML namespace for the assembly to the Main window.

{% tabs %}

{% highlight XAML %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusionskin ="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" />

{% endhighlight %}

{% endtabs %}

**Step2**


**Step 3:**

Compile and run the WPF application and you can now witness the custom theme applied to SfDataGrid control at run-time. 

![Theme applied in SfDataGrid](ThemeStudio_images/Theme-applied-SfDataGrid.png)
