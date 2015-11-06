---
layout: post
title: Overview | Complete guide to WPF Theme Studio 
description: Desktop-based, intuitive UI customization tool for easy customization of skins and themes for the Syncfusion control suite
platform: wpf
control: Themes
documentation: ug
---

# Overview

The Theme Studio is a desktop-based, intuitive UI customization tool for easy customization of skins and themes for the Syncfusion control suite.

It comprises of many features such as predefined themes, Import and Export option to facilitate your process of getting custom skins for matching your visual representation of app.

![](ThemeStudio_images/ThemeStudio_img1.png)


## Applying predefined themes in Theme Studio

To apply predefined themes, we need to choose the needed themes from Themes List available in drop down near `Personalize` Heading. 

The following list of predefined themes are currently provided in theme studio,

*   Metro

*   Blend

*	Office2010Blue

*	Office2010Black

*	Office2010Silver

*	Office2013White

*	Office2013LightGray

*	Office2013DarkGray

*	VisualStudio2013

*	Lime

*	Saffron

![](ThemeStudio_images/ThemeStudio_img2.png)


## Applying customized skin in Theme Studio

We are currently providing 7 set of categories to customize the control colors. Each category containing different collection of color properties.

![](ThemeStudio_images/ThemeStudio_img3.png)


![](ThemeStudio_images/ThemeStudio_img4.png)


![](ThemeStudio_images/ThemeStudio_img5.png)


![](ThemeStudio_images/ThemeStudio_img6.png)


![](ThemeStudio_images/ThemeStudio_img7.png)


![](ThemeStudio_images/ThemeStudio_img8.png)


![](ThemeStudio_images/ThemeStudio_img9.png)


The hexadecimal color code can be given as input in Text area and press enter to apply the custom skin color.

![](ThemeStudio_images/ThemeStudio_img10.png)

To select desired color, click the colored button to display a popup with solid color palettes, gradient check box and Advance option.

![](ThemeStudio_images/ThemeStudio_img11.png)

Color Palette 
{:.caption}


*	`Solid Color Palettes`: Provides set of color palettes with 8 variants.

*	`Advance Option`: To choose wide range of colors, click Advance button option.

![](ThemeStudio_images/ThemeStudio_img12.png)

Advance Color Picker 
{:.caption}

*   `Gradient Check Box`: To choose gradient colors, select the “Gradient” check box to display a popup with 24 gradient palettes.

![](ThemeStudio_images/ThemeStudio_img13.png)

Gradient Palette 
{:.caption}

N> Gradient Support has been provided only for Background color properties residing in Default, Header, Hover and Active categories.

## Applying generated resource xaml in application

To [export](#exporting-custom-theme-from-theme-studio) the customized skin, click the `Export` button. The exported custom skin contains resource dictionary xaml files of Syncfusion controls and Framework Controls.

### Adding the xaml files to WPF Application

*	Open Visual Studio 20xx and create a WPF project.

*	Add the necessary dlls for the controls used.

For example, add SfRadialMenu Control to the application. The `SfRadialMenu` control requires `Syncfusion.SfRadialMenu.WPF` dll and dependency dll `Syncfusion.SfShared.WPF`.

*	The exported xaml file of controls can be obtained from the Output folder as described in the [export](#exporting-custom-theme-from-theme-studio) topic.

*	From the Output folder, browse the `Syncfusion Controls` folder and add the required xaml file to the project.

![](ThemeStudio_images/ThemeStudio_img14.png)


*	Now, initialize the SfRadialMenu control in the `MainWindow.xaml` as below:

{% highlight xml %}

        <syncfusion:SfRadialMenu x:Name="RadialMenu">
            <syncfusion:SfRadialMenuItem Header="Cut">
                <syncfusion:SfRadialMenuItem Header="Cut"/>
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Copy">
                <syncfusion:SfRadialMenuItem Header="Copy"/>
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Paste">
                <syncfusion:SfRadialMenuItem Header="Paste"/>
            </syncfusion:SfRadialMenuItem>
        </syncfusion:SfRadialMenu>

{% endhighlight %}

*	Merge the `SfRadialMenu.xaml` in the application resources using `MergedDictionaries`.

{% highlight xml %}

        <Application.Resources> 
    		<ResourceDictionary>
        		<ResourceDictionary.MergedDictionaries>
            		<ResourceDictionary Source="SfRadialMenu.xaml"/>
        		</ResourceDictionary.MergedDictionaries>
    		</ResourceDictionary>
		</Application.Resources>

{% endhighlight %}

*	Run the sample and the below output will be obtained:

![](ThemeStudio_images/ThemeStudio_img15.png)


## Exporting Custom theme from Theme Studio

To export custom theme, click `Export` button to display a popup containing option to select the controls to be exported. 

Select the control by checking the desired control’s check box or check `Select All` option in the popup to select all the controls. 

Click the `Export` button once selected the desired controls and provide a name for the customized theme. 

![](ThemeStudio_images/ThemeStudio_img16.png)


N> To obtain the customized themes for multiple controls in a single xaml file, check the `Merge and Export` option before clicking `Export` button.

The color values for customized theme will be saved in `*.wpft` format file. Along with `*.wpft` file, two folders `Framework Controls` and `Syncfusion Controls` are also generated.

*   `Framework Controls`: This folder contains the resource dictionary xaml files of framework controls.

*	`Syncfusion Controls`: This folder contains the resource dictionary xaml files of selected syncfusion controls.

![](ThemeStudio_images/ThemeStudio_img17.png)

Output Folder 
{:.caption}

## Importing Custom theme to Theme Studio

To import custom theme, click `Import` button for choosing `*.wpft` file containing customized skin color values. After importing, we can visualize the loaded custom skin color applied to controls.

![](ThemeStudio_images/ThemeStudio_img18.png)
