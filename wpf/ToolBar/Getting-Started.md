---
layout: post
title: Getting Started with Syncfusion ToolBarAdv control for WPF
description: A quick tour to initial users on Syncfusion ToolBarAdv control for WPF and also its basic features like appearance and properties
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Getting Started with ToolBarAdv

>**Important**
Starting with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or from the NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your WPF application to use our components.

This section explains how to add the ToolBarAdv control to an application and its structure.

## Adding ToolBarAdv to a WPF Application

ToolBarAdv can be added to an application in a following way.

### Create the ToolBarAdv Control to an application by using XAML:

The following ways explains how to add ToolBarAdv control using XAML code:

* Create a WPF project in Visual Studio and refer “Syncfusion.Shared.Wpf” assembly to the project.    
* Include an XML namespace for the above assemblies to the Main window.

{% tabs %}

{% highlight XAML %}

<Window x:Class="Application_New.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

Title="MainWindow" Height="350" Width="525">



{% endhighlight %}

{% endtabs %}
* Now add the ToolBarAdv control with a required optimal name using the namespace 

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarAdv Height="100" HorizontalAlignment="Left" Margin="92,90,0,0" Name="toolBarAdv1" VerticalAlignment="Top" Width="200" />



{% endhighlight %}

{% endtabs %}

### Create the ToolBarAdv control to an application by C#:

{% tabs %}

{% highlight C# %}

ToolBarAdv tool = new ToolBarAdv();

tool.Name = "toolBarAdv1";

tool.Width = 100;

tool.Height = 50;





{% endhighlight %}

{% endtabs %}

## Appearance and Structure of the Control

![Appearance and Structure](Getting-Started-images/Getting-Started-img1.jpeg)


* The Overflow button is a toggle button that displays on clicking the Overflow panel.
* The Gripper is used to drag the ToolBarAdv to change its Band. The state of the ToolBarAdv can be changed to float and dock by clicking the gripper and dragging the ToolBarAdv, when the ToolBarAdv is hosted in ToolBarManager.

## Setting icon template

The IconTemplate property provides support to set any type of image such as glyphs or any custom control to the ToolBarAdv icon. The icon will automatically resize the template content according to its size provided in the data template.

{% tabs %}

{% highlight XAML %}

<skin:ChromelessWindow x:Class="ToolBarDemo.MainWindow" UseNativeChrome="True"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:str="clr-namespace:System;assembly=mscorlib"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:menu="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.Wpf"  
        xmlns:shared="clr-namespace:Syncfusion.Windows.Tools.Controls;assembly=Syncfusion.Shared.Wpf" xmlns:skin="http://schemas.syncfusion.com/wpf"
        Title="Getting Started" Height="600" Width="700" WindowStartupLocation="CenterScreen" Icon="App.ico" >
    <skin:ChromelessWindow.Resources>
        <Style TargetType="Image">
            <Setter Property="Height" Value="16"/>
            <Setter Property="Width" Value="16"/>
        </Style>
        
    </skin:ChromelessWindow.Resources>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="Auto"/>
        </Grid.RowDefinitions>
        <shared:ToolBarManager x:Name="toolBarManager" Grid.Row="1" CanDockAtLeft="{Binding IsChecked, ElementName=canDockAtLeft}"
                               CanDockAtTop="{Binding IsChecked, ElementName=canDockAtTop}" CanDockAtRight="{Binding IsChecked, ElementName=canDockAtRight}"
                               CanDockAtBottom="{Binding IsChecked, ElementName=canDockAtBottom}">

            <shared:ToolBarManager.Resources>
                <Style TargetType="Button">
                    <Setter Property="Height" Value="20" />
                    <Setter Property="Width" Value="20"/>
                </Style>
                <Style TargetType="ToggleButton">
                    <Setter Property="Height" Value="20"/>
                    <Setter Property="Width" Value="20"/>
                </Style>
                <DataTemplate x:Key="OpenDataTemplate">
                    <Path x:Name="Open_Folder" Data="M5.1229254,6 C4.9319264,6 4.7599241,6.1059875 4.6749264,6.2759857 L1.3099782,13 12.185817,13 14.935776,6.7459869 C15.058775,6.4989929 14.967774,6.3089905 14.923776,6.2369995 14.879777,6.1660004 14.750781,6 14.497787,6 z M1.5009773,1.0000001 C1.2249804,0.99999999 0.99998522,1.223999 0.99998528,1.5 L0.99998528,11.383987 3.7799429,5.8289947 C4.035936,5.3179932 4.5499283,5 5.1229254,5 L12.011824,5 12.011824,3.5 C12.011824,3.223999 11.786821,3 11.510823,3 L7.2768928,3 C6.938893,3 6.606897,2.8839874 6.3429009,2.673996 L4.3739358,1.1089935 C4.2859322,1.0389862 4.1749336,0.99999999 4.0619365,1.0000001 z M1.4999778,4.4408921E-16 L4.0619365,4.4408921E-16 C4.4009358,-6.475124E-09 4.7299258,0.11499023 4.9959208,0.3259887 L6.9648935,1.8909911 C7.0538965,1.9609985 7.1638881,2 7.2768928,1.9999999 L11.510823,1.9999999 C12.338815,2 13.011809,2.6719971 13.011809,3.5009918 L13.011809,5 14.497787,5 C15.021773,5 15.499771,5.2659912 15.77476,5.7119903 16.049759,6.1569977 16.074759,6.7029877 15.839762,7.17099 L13.100804,13.401993 C12.940803,13.764999 12.581815,14 12.184817,14 L0.99998528,14 C0.44799143,14 0,13.551987 0,13 L0,1.5 C0,0.67098998 0.67098773,-6.475124E-09 1.4999778,4.4408921E-16 z" 
                          Fill="{Binding Foreground, ElementName=button1}" HorizontalAlignment="Center" Stretch="Fill" Width="14" Height="14" VerticalAlignment="Center" />
                </DataTemplate>
                <DataTemplate x:Key="SaveDataTemplate">
                    <Path x:Name="Save" Data="M3.9989982,9.9999962 L3.9989982,14.999996 4.9989982,14.999996 4.9989982,10.999996 5.9989984,10.999996 5.9989984,14.999996 9.9989984,14.999996 9.9989984,9.9999962 z M2.9989938,1.0009929 L2.9989938,6 10.998994,6 10.998994,1.0009929 z M1.5,1.0009929 C1.2239999,1.0009929 0.99999988,1.2249929 0.99999988,1.500993 L0.99999988,12.843993 2.51,15.000993 2.9989983,15.000993 2.9989983,8.9999962 10.998998,8.9999962 10.998998,15.000993 12.5,15.000993 C12.776,15.000993 13,14.775993 13,14.500993 L13,1.500993 C13,1.2249929 12.776,1.0009929 12.5,1.0009929 L11.998994,1.0009929 11.998994,7 1.9989936,7 1.9989936,1.0009929 z M1.9989936,0 L11.998994,0 11.998994,0.00099283666 13,0.00099283666 C13.552,0.0009929199 14,0.44899291 14,1.0009929 L14,14.500993 C14,15.328993 13.328,16.000994 12.5,16.000994 L1.9889999,16.000994 0,13.157993 0,1.0009929 C-1.1920929E-07,0.44899291 0.44699991,0.0009929199 0.99999988,0.00099283666 L1.9989936,0.00099283666 z" 
                          Fill="{Binding Foreground, ElementName=button1}" HorizontalAlignment="Center" Stretch="Fill" Width="14" Height="14" VerticalAlignment="Center"/>
                </DataTemplate>
                <DataTemplate x:Key="PrintDataTemplate">
                    <Path x:Name="Print" Data="M3.9999731,11 L3.9999731,15 9.9999733,15 9.9999733,11 z M2.5000291,7.9999914 C2.7760291,7.9999913 3.0000291,8.2239914 3.0000291,8.4999914 3.0000291,8.7759914 2.7760291,8.9999914 2.5000291,8.9999914 2.2240291,8.9999914 2.0000291,8.7759914 2.0000291,8.4999914 2.0000291,8.2239914 2.2240291,7.9999913 2.5000291,7.9999914 z M1,6.9999933 L1,11.999993 2.9999731,11.999993 2.9999731,10 10.999973,10 10.999973,11.999993 13,11.999993 13,6.9999933 10.999973,6.9999933 2.9999731,6.9999998 z M3.9999731,1 L3.9999731,5.9999933 9.9999733,5.9999933 9.9999733,1 z M2.9999731,0 L10.999973,0 10.999973,5.9999933 14,5.9999933 14,12.999993 10.999973,12.999993 10.999973,16 2.9999731,16 2.9999731,12.999993 0,12.999993 0,5.9999933 2.9999731,5.9999933 z" 
                          Fill="{Binding Foreground, ElementName=button1}" HorizontalAlignment="Center" Stretch="Fill" Width="16" Height="14" VerticalAlignment="Center"/>
                </DataTemplate>
                <DataTemplate x:Key="FirstDataTemplate">
                    <Path Data="M0,0.01300294 L1.0000002,0.01300294 1.0000002,16.013003 0,16.013003 z M11.278009,0 L11.972009,0.72000102 4.4380183,7.9909952 11.99801,15.286999 11.30401,16.007 2.9970098,7.9909952 z" 
                          Fill="{Binding Foreground, ElementName=button1}" HorizontalAlignment="Center" Stretch="Fill" Width="10" Height="10" VerticalAlignment="Center"/>
                </DataTemplate>
            </shared:ToolBarManager.Resources>
            <shared:ToolBarManager.TopToolBarTray>
                <shared:ToolBarTrayAdv VerticalAlignment="Top"  IsLocked="{Binding IsChecked, ElementName=lockTop}">
                    <shared:ToolBarAdv x:Name="toolBar" ToolBarName="Standard" EnableAddRemoveButton="True">
                        <Button x:Name="button" shared:ToolBarAdv.Label="New Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/NewDocumentHS.png" ToolTip="New"   shared:ToolBarAdv.IconTemplate="{StaticResource FirstDataTemplate}">
                            <Image Source="Images/NewDocumentHS.png" Width="16" Height="16" />
                        </Button>
                        <Button x:Name="button1" shared:ToolBarAdv.Label="Open Document" Height="22" Width="22" ToolTip="Open" shared:ToolBarAdv.IconTemplate="{StaticResource OpenDataTemplate}">
                            <Image Source="Images/openHS.png"  Width="16" Height="16"/>
                        </Button>
                        <Button x:Name="button2" shared:ToolBarAdv.Label="Save Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/saveHS.png" ToolTip="Save"  shared:ToolBarAdv.IconTemplate="{StaticResource SaveDataTemplate}">
                            <Image Source="Images/saveHS.png"  Width="16" Height="16"/>
                        </Button>
                        <Button x:Name="button3" shared:ToolBarAdv.Label="Save Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/saveAllHS.png" ToolTip="SaveAll" shared:ToolBarAdv.IconTemplate="{StaticResource SaveDataTemplate}">
                            <Image Source="Images/saveAllHS.png"  Width="16" Height="16"/>
                        </Button>
                        <shared:ToolBarItemSeparator  />
                        <Button x:Name="button4" shared:ToolBarAdv.Label="Print Document"  Height="22" Width="22" shared:ToolBarAdv.Icon="Images/PrintHS.png" ToolTip="Print" shared:ToolBarAdv.IconTemplate="{StaticResource PrintDataTemplate}">
                            <Image Source="Images/PrintHS.png"  Width="16" Height="16"/>
                        </Button>
                    </shared:ToolBarAdv>
                </shared:ToolBarTrayAdv>
                
            </shared:ToolBarManager.TopToolBarTray>
           
            <shared:ToolBarManager.RightToolBarTray>
                <shared:ToolBarTrayAdv IsLocked="{Binding IsChecked, ElementName=lockRight}">
                   
                </shared:ToolBarTrayAdv>
            </shared:ToolBarManager.RightToolBarTray>
            <shared:ToolBarManager.BottomToolBarTray>
                <shared:ToolBarTrayAdv IsLocked="{Binding IsChecked, ElementName=lockBottom}"/>
            </shared:ToolBarManager.BottomToolBarTray>

            <Grid>
                <Grid.RowDefinitions>
                    <RowDefinition Height="*"/>
                    <RowDefinition Height="Auto"/>
                </Grid.RowDefinitions>
                <ScrollViewer >
                    <Grid Margin="20">
                        <Border CornerRadius="2" Background="Black" Opacity="0.3"   Width="600" Height="700">
                            <Border.Effect>
                                <BlurEffect Radius="15"/>
                            </Border.Effect>
                        </Border>
                        <RichTextBox  Width="600" Height="700" Padding="20">
                            <FlowDocument>
                                <FlowDocument.Blocks>
                                    <Paragraph>
                                        ToolBarAdv controls are containers for a group of commands or controls which are typically related in their function. A ToolBarAdv usually contains buttons which invoke commands. The ToolBarAdv control takes its name from the bar-like arrangement of buttons or other controls into a single row or column.
                                    </Paragraph>
                                </FlowDocument.Blocks>
                            </FlowDocument>
                        </RichTextBox>
                        </Grid>
                </ScrollViewer>
            </Grid>
        </shared:ToolBarManager>
       
    </Grid>
</skin:ChromelessWindow>


 {% endhighlight %}

 {% endtabs %}
 

 ![Setting Icon Template](Getting-Started-images/Getting-Started-img2.jpg)

## Properties

### Properties of ToolBarAdv

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
Band<br/><br/></td><td>
Gets or sets a value indicating where the ToolBarAdv should be placed in the ToolBarTrayAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td></tr>
<tr>
<td>
BandIndex<br/><br/></td><td>
Gets or sets the band index number indicating the position of the ToolBarAdv on the band.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td></tr>
<tr>
<td>
ToolBarName<br/><br/></td><td>
Gets or sets the name of the ToolBarAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
GripperVisibility<br/><br/></td><td>
Gets or sets a value indicating whether gripper can be visible.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
FloatingBarLocation<br/><br/></td><td>
Gets or sets the location for the floating ToolBarAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Point<br/><br/></td></tr>
<tr>
<td>
ControlsResourceDictionary<br/><br/></td><td>
Gets or sets resource dictionary in which ToolBarAdv will look up for Framework element’s styles.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Resource Dictionary<br/><br/></td></tr>
<tr>
<td>
IsOverflowOpen<br/><br/></td><td>
Gets or sets a value indicating whether overflow popup is open.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
ToolBarItemInfoCollection<br/><br/></td><td>
Gets or sets the items to be displayed in the Add or Remove Buttons popup.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ObservableCollection<br/><br/></td></tr>
<tr>
<td>
IsOverflowItem<br/><br/></td><td>
Gets or sets a value indicating whether an item can be displayed in overflow panel.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
OverflowMode<br/><br/></td><td>
Gets or sets an overflow mode for a specified item.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
OverflowMode<br/><br/></td></tr>
<tr>
<td>
Icon<br/><br/></td><td>
Gets or sets an icon for specified item to be displayed in the Add or Remove Buttons menu.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
ImageSource<br/><br/></td></tr>
<tr>
<td>
Label<br/><br/></td><td>
Gets or sets a label for specified item to be displayed in the Add or Remove Buttons menu.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
IsAvailable<br/><br/></td><td>
Gets or sets a value indicating whether a specified item should be hidden.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
Boolean<br/><br/></td></tr>
</table>
### Properties of ToolBarManager

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
IsLocked<br/><br/></td><td>
Gets or Sets a value indicating whether ToolBarTrayAdv is locked.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
bool<br/><br/></td></tr>
<tr>
<td>
Orientation<br/><br/></td><td>
Gets or Sets the orientation of the ToolBarAdv.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Orientation<br/><br/></td></tr>
<tr>
<td>
ToolBars<br/><br/></td><td>
Gets or sets toolbars.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
ObservableCollection<br/><br/></td></tr>
<tr>
<td>
TopToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the Top of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
BottomToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the bottom of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
LeftToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the left of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
RightToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the right of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
CanDockAtTop<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the top.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td></tr>
<tr>
<td>
CanDockAtBottom<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the bottom.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
CanDockAtLeft<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the left.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
CanDockAtRight<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the right.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
Content<br/><br/></td><td>
Gets or sets the content of the ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
UIElement<br/><br/></td><td>
<tr>
<td>
FloatingToolBarStyle<br/><br/></td><td>
Gets or sets a style of floating tool bar<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Style<br/><br/></td><td>
<tr>
<td>
ToolBarState<br/><br/></td><td>
Gets or sets the state of the toolbar.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
ToolBarState<br/><br/></td><td>



