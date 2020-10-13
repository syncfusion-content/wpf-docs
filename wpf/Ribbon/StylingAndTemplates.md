---
layout: post
title: Styling and Template | Syncfusion | WPF Ribbon
description: Learn here about how to apply the Styles and ResourceDictinary Template for Syncfusion WPF Ribbon control. 
platform: wpf
control: Ribbon
documentation: ug
---
# Styling and Templates

The Ribbon control ships with a number of built-in themes such as Office2003, Office2007, Office2010 Silver, Blue, Black, Blend, VS, Transparent, Metro and Office2013. 

## Visual styles

The appearance of Ribbon control can be customized by `VisualStyles` attached property of the SfSkinManager. You can find the list of available built-in themes and the assemblies needs to be referred in the below documentation [link](https://help.syncfusion.com/wpf/themes/skin-manager).

### Add SfSkinManager reference

There are several ways to add the Syncfusion SfSkinManager reference in Visual Studio WPF project. The following steps will help to add through `XAML` code.

1) Add reference to `Syncfusion.SfSkinManager.WPF` assembly or Syncfusion.SfSkinManager.WPF [nuget package](https://www.nuget.org/packages/Syncfusion.SfSkinManager.WPF) to the project.

2) Import Syncfusion WPF schema `http://schemas.syncfusion.com/wpf` or the assembly namespace `Syncfusion.SfSkinManager` in XAML page.

### Apply styles using SfSkinManager

The SfSkinManger provides rich and professional look and feel UI for Ribbon window. The list of visual styles are given below,

* Office2010Black, Office2010Blue and Office2010Silver
* Office2013DarkGray, Office2013LightGray and Office2013White
* Office2016 Colorful, Office2016DarkGray, Office2016White
* Office2019Black, Office2019Colorful, Office2019DarkGray, Office2019White and Office2019HighContast
* VisualStudio2013 and VisualStudio2015
* Office365, SystemTheme, Saffron, Blend, Default and Lime
* MaterialDark, MaterialDarkBlue, MaterialLight, MaterialLightBlue

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp82"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApp82.MainWindow"
        mc:Ignorable="d" 
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="Office2019Colorful"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
            <syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
                <syncfusion:RibbonBar Name="New" Width="90"  Header="New">
                    <syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
                    <syncfusion:DropDownButton SizeForm="Large" Label="New Items">
                        <syncfusion:DropDownMenuItem Header="Task"/>
                    </syncfusion:DropDownButton>
                </syncfusion:RibbonBar>
                <syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
                    <syncfusion:RibbonButton Label="Ignore"/>
                    <syncfusion:SplitButton Label="Clean Up">
                        <syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
                    </syncfusion:SplitButton>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
            <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
            <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
            <syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

SfSkinManager.SetVisualStyle(this, VisualStyles.Office2019Colorful);

{% endhighlight %}

{% endtabs %}

* Office2019Colorful

![Apply Office2019Colorful theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2019colorful.png)

* Office2019HighContrast

![Apply Office2019HighContrast theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-Office2019HighContrast.png)

* VisualStudio2013

![Apply VisualStudio2013 theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-VisualStudio2013.png)

* Office2016Colorful

![Apply Office2016Colorful theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-Office2016Colorful.png)

* Office2016White

![Apply Office2016White theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2016white.png)

* Office2010Black

![Apply Office2010Black theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2010Black.png)

* Office2010Silver

![Apply Office2010Silver theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2010silver.png)

* Office2013DarkGray

![Apply Office2013DarkGray theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2013darkgray.png)

* Office2013White

![Apply Office2013White theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office2013white.png)

* Lime

![Apply Lime theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-lime.png)

* Office365

![Apply Office365 theme to WPF Ribbon](StylingandTemplates_images/wpf-ribbon-office365.png)

### Apply style using ResourceDictionary

To override the themes to the Ribbon control’s style, add ResourceDictionary in the sample and define new style with the BasedOn property. When the Resource Dictionary is added, all the properties of the base style can be acquired, then override them as desired. The same procedure can be used for overriding the other styles. Here an example is illustrated to set the BackStageColor for the Ribbon by customizing the RibbonStyle using the BasedOn property.

#### Syntax for ResourceDictionary

{% tabs %}

{% highlight XAML %}

<ResourceDictionary Source="/Syncfusion.Tools.WPF;Component/FrameWork/Ribbon/themes/Office2013Style.xaml">
</ResourceDictionary>

{% endhighlight %}

{% endtabs %}


#### Syntax for BasedOn

{% tabs %}

{% highlight XAML %}

BasedOn="{StaticResource <StyleName><ControlName>Style}"

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
        x:Class="RibbonVisualStyleSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="350" Width="525"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        syncfusion:SkinStorage.VisualStyle="Office2013">
    <syncfusion:RibbonWindow.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="/Syncfusion.Tools.WPF;Component/FrameWork/Ribbon/themes/Office2013Style.xaml"/>
            </ResourceDictionary.MergedDictionaries>
            <Style x:Key="RibbonStyle" TargetType="{x:Type syncfusion:Ribbon}" BasedOn="{StaticResource Office2013RibbonStyle}">
                <Setter Property="BackStageColor" Value="Red"/>
            </Style>
        </ResourceDictionary>
    </syncfusion:RibbonWindow.Resources>
    <Grid>
        <syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top"  Style="{StaticResource RibbonStyle}">
            <syncfusion:RibbonTab  Caption="Home" IsChecked="False">
                <syncfusion:RibbonBar Header="Respond" >
                    <syncfusion:RibbonButton  SizeForm="Large" Label="Large"/>
                    <syncfusion:RibbonButton SizeForm="Small" Label="Small"/>
                    <syncfusion:RibbonButton SizeForm="Small" Label="Forward"/>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
            <syncfusion:RibbonTab Caption="Send/Receive" IsChecked="True">
                <syncfusion:RibbonBar Header="Download">
                    <syncfusion:RibbonButton SizeForm="Small" Label="Show Progress"/>
                    <syncfusion:RibbonButton SizeForm="Small" Label="CancelAll"/>
                    <syncfusion:RibbonButton SizeForm="Large" Label="Download Headers"/>
                    <syncfusion:DropDownButton SizeForm="Large" Label="Mark to Download">
                    <syncfusion:DropDownButton>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![Apply Office2013 style to WPF Ribbon](StylingandTemplates_images/StylingandTemplates_img1.jpeg)


