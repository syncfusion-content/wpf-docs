---
layout: post
title: Dealing with Ribbon in WPF Ribbon control | Syncfusion
description: Learn about Dealing with Ribbon support in Syncfusion Essential Studio WPF Ribbon control, its elements and more.
platform: wpf
control: Ribbon
documentation: ug
---
# Dealing with Ribbon in WPF Ribbon

Ribbon can be changed into three different states such as `Normal`, `Hide` and `Adorner`

## Three types of RibbonState

**Normal** – Ribbon control displays the RibbonTab content and the window content is arranged below the Ribbon. This is the default state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Normal" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![RibbonStates](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img1.jpeg)

**Hide** - RibbonTab content gets hidden in this state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Hide" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![RibbonStates](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img2.jpeg)


**Adorner** – In this state, RibbonTab content adorned above the window content

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Adorner" VerticalAlignment="Top" x:Name="_ribbon" >
<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >
<syncfusion:RibbonBar  Header="Acions">
<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>
<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >
<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>
<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>
</syncfusion:SplitButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Header="Properties">
<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>
<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![Ribbon Adorner state](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img3.jpeg)

## How to change the RibbonState in run time

Ribbon State can also be changed at the Runtime.In the below code, Ribbon State has been changed dynamically in the button click event

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner

{% endhighlight %}

{% endtabs %}

## Resize Ribbon Window
The ribbon control dynamically resizes as width of the window decreases, when the windows border touches the last placed Ribbon bar, the Ribbon will begin to resize its elements with the following priority.

1. **Compress Gallery** - If there is a [`RibbonGallery`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonGallery.html) in a [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html), it will be resized until it is converted to a dropdown button. Once it is converted into dropdown button, then the Ribbon will begin to resize the [`Large`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items.

2. **Compress Large items** - When there are three or more continuous [`Large`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) items, then Ribbon will reduce each pair of three continuous [`Large`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items, starting from the right side, into [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items. Once each pair of three continuous [`Large`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items are converted into [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form, then Ribbon will begin to resize the [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items.

3. **Compress Small items** - When there are three or more continuous [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) items, then Ribbon will reduce each pair of three continuous [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items, starting from the right side, into [`ExtraSmall`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items. Once each pair of three continuous [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items are converted into [`ExtraSmall`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form, then Ribbon will begin convert the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) into dropdown button.

4. **Collapsing the RibbonBar** - When there are no three or more continuous [`Large`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) or [`Small`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.SizeForm.html) size form items and when there are other ribbon items such as CheckBox, RadioButton, ComboBox, TextBox, ListBox or any other custom items, then, starting with the last bar, each [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) will be converted into a dropdown button, with its items accessible by clicking on the dropdown arrow.

When the size of the window is increased, the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) will become visible if the spacing between the window border and the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) is large enough to accommodate its items. These items will then be expanded in the order, starting with the most recently collapsed item and ending with the initially collapsed item.

The [`IsAutoSizeFormEnabled`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html#Syncfusion_Windows_Tools_Controls_Ribbon_SetIsAutoSizeFormEnabled_System_Windows_DependencyObject_System_Boolean_) property must be set to True to get responsive ribbon window. The following snippet is used for resize the ribbon window.

{% tabs %}

{% highlight XAML %}

<Grid>
 <syncfusion:Ribbon syncfusion:Ribbon.IsAutoSizeFormEnabled="True" x:Name="_ribbon" VerticalAlignment="Top">            
 </syncfusion:Ribbon>
 </Grid>

{% endhighlight %}

{% endtabs %}

![Resize Ribbon Window](RibbonResizeWindow-images/ResizeRibbonWindow.gif)

## Right RibbonBar support

The [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) can be positioned at the right side of the [`Ribbon`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html) by using the `Position` property.
In order to position the RibbonBar at right side of the Ribbon, set `Position` property in RibbonBar as `Right`. 
The following code snippet illustrates this right RibbonBar support.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
    x:Class="RightRibbonBar.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:local="clr-namespace:RightRibbonBar"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:skinManager="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    Title="Right RibbonBar"
    Width="950"
    Height="475"
    syncfusion:SfSkinManager.Theme="{syncfusion:SkinManagerExtension ThemeName=FluentLight}"
    WindowStartupLocation="CenterScreen"
    mc:Ignorable="d">
    <Grid>
        <syncfusion:Ribbon>
            <syncfusion:RibbonTab Caption="Home" IsChecked="True">
                <syncfusion:RibbonBar Header="Clipboard">
                    <syncfusion:RibbonButton
                        syncfusion:RibbonCommandManager.SynchronizedItem="Paste"
                        IconType="VectorImage"
                        Label="Paste"
                        SizeForm="Large">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Margin="0,4,6,2"
                                Data="M17,0 L21,0 21,7 20,7 20,1.0000001 17,1.0000001 z M0,0 L4,0 4,1.0000001 1.0000001,1.0000001 1.0000001,23 12,23 12,24 0,24 z"
                                Fill="#FFED8733"
                                Stretch="Fill" />
                            <Path
                                Margin="13,12,0,0"
                                Data="M1.0000002,0.99999994 L1.0000002,17 13,17 13,0.99999994 z M0,0 L14,0 14,18 0,18 z"
                                Fill="#FF3C3B39"
                                Stretch="Fill" />
                            <Path
                                Margin="1,5,7,3"
                                Data="M16,0 L17,0 19,0 19,6 17,6 17,2 16,2 z M0,0 L2,0 3,0 3,2 2,2 2,20 11,20 11,22 0,22 z"
                                Fill="#FFF8DB8F"
                                Stretch="Fill" />
                            <Path
                                Margin="3,0.5,1,1"
                                Data="M10.999956,12.5 L22.999956,12.5 22.999956,28.5 10.999956,28.5 z M7.4999558,0 C9.1569382,0 10.499956,1.3439941 10.499956,3 L13.499956,3 13.499956,6.5 15,6.5 15,10.5 9.0000001,10.5 9.0000001,24.5 0,24.5 0,6.5 1.4999557,6.5 1.4999557,3 4.4999558,3 C4.4999558,1.3439941 5.8439499,0 7.4999558,0 z"
                                Fill="White"
                                Stretch="Fill" />
                            <Path
                                Height="8"
                                Margin="4,0,10,0"
                                VerticalAlignment="Top"
                                Data="M6.5,0.99999996 C5.1209717,0.99999996 4,2.1209716 4,3.5 L4,4 0.99999994,4 0.99999994,7 12,7 12,4 9,4 9,3.5 C9,2.1209716 7.8790283,0.99999996 6.5,0.99999996 z M6.5,0 C8.2600098,-4.4703484E-08 9.7209473,1.3060302 9.9649658,3 L13,3 13,8 0,8 0,3 3.0350342,3 C3.2790527,1.3060302 4.7399902,-4.4703484E-08 6.5,0 z"
                                Fill="#FF797774"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                        <syncfusion:RibbonButton.ToolTip>
                            <syncfusion:ScreenTip Content="Paste the contents of clipboard." Description="Paste (Ctrl+V)" />
                        </syncfusion:RibbonButton.ToolTip>
                    </syncfusion:RibbonButton>
                    <syncfusion:RibbonButton
                        HorizontalAlignment="Left"
                        IconType="VectorImage"
                        Label="Cut"
                        SizeForm="Small">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Width="10"
                                Height="8"
                                Margin="3.747,0,1.805,4.614"
                                Data="M0.4800034,0 L3.2370005,5.6329948 5.9950049,0 6.4480002,1.3919982 3.8000043,6.7859942 6.4040015,12.108999 5.4240053,12.385 3.2370005,7.9400011 1.0859987,12.314001 0,12.249991 2.675004,6.7859942 0.027000348,1.3919982 z"
                                Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                Stretch="Fill" />
                            <Path
                                Width="13"
                                Height="4"
                                Margin="2,0,0,1"
                                VerticalAlignment="Bottom"
                                Data="M2.0000019,1.0000033 C1.4480005,1.0000033 1.0000028,1.4489932 1.0000028,2.0000033 1.0000028,2.5509982 1.4480005,3.0000033 2.0000019,3.0000033 2.5519957,3.0000033 3.0000009,2.5509982 3.0000009,2.0000033 3.0000009,1.4489932 2.5519957,1.0000033 2.0000019,1.0000033 z M7.9999966,0.99999999 C7.4479966,0.99999993 6.9999966,1.449 6.9999966,2 6.9999966,2.5509999 7.4479966,3 7.9999966,3 8.5519962,3 8.9999962,2.5509999 8.9999962,2 8.9999962,1.449 8.5519962,0.99999993 7.9999966,0.99999999 z M2.0000019,3.2782542E-06 C3.1029978,3.3312692E-06 4,0.89700651 4,2.0000033 4,3.1030002 3.1029978,4.0000033 2.0000019,4.0000033 0.8969985,4.0000033 0,3.1030002 0,2.0000033 0,0.89700651 0.8969985,3.3312692E-06 2.0000019,3.2782542E-06 z M7.9999966,0 C9.1029968,-3.7871359E-08 9.9999962,0.89699995 9.9999962,2 9.9999962,3.1029999 9.1029968,4 7.9999966,4 6.8969965,4 5.9999966,3.1029999 5.9999966,2 5.9999966,0.89699995 6.8969965,-3.7871359E-08 7.9999966,0 z"
                                Fill="#FF1D8BCC"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                        <syncfusion:RibbonButton.ToolTip>
                            <syncfusion:ScreenTip Description="Cut (Ctrl+X)">
                                <TextBlock
                                    Width="130"
                                    HorizontalAlignment="Left"
                                    Text="Cut the selection and put it on the clipboard."
                                    TextWrapping="Wrap" />
                            </syncfusion:ScreenTip>
                        </syncfusion:RibbonButton.ToolTip>
                    </syncfusion:RibbonButton>
                    <syncfusion:RibbonButton
                        HorizontalAlignment="Left"
                        IconType="VectorImage"
                        Label="Copy"
                        SizeForm="Small">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Margin="3,1,0.5,0.5"
                                Data="M5.5000009,2.500005 L10.500001,2.500005 14.500001,6.500005 14.500001,14.500005 5.5000009,14.500005 z M0,0 L4.0000037,0 4.0000037,12 0,12 z"
                                Fill="White"
                                Stretch="Fill" />
                            <Path
                                Margin="2,0,0,0"
                                Data="M9.0000026,11.999999 L13.000003,11.999999 13.000003,12.999999 9.0000026,12.999999 z M9.0000026,9.9999986 L13.000003,9.9999986 13.000003,10.999999 9.0000026,10.999999 z M12,4.7070035 L12,7.0000033 14.293,7.0000033 z M6.9999967,4.0000001 L6.9999967,15 14.999997,15 14.999997,8.0000033 11,8.0000033 11,4.0000001 z M5.9999967,2.9999999 L11.706997,2.9999999 15.999997,7.293 15.999997,16 5.9999967,16 z M0,0 L6.9999967,0 6.9999967,2 5.9999971,2 5.9999971,1 1,1 1,13 4.9999976,13 4.9999976,14 0,14 z"
                                Fill="#FF3A3939"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                        <syncfusion:RibbonButton.ToolTip>
                            <syncfusion:ScreenTip Description="Copy (Ctrl+C)">
                                <TextBlock
                                    Width="130"
                                    HorizontalAlignment="Left"
                                    Foreground="#FF4C4C4C"
                                    Text="Copy the selection and put it on the clipboard."
                                    TextWrapping="Wrap" />
                            </syncfusion:ScreenTip>
                        </syncfusion:RibbonButton.ToolTip>
                    </syncfusion:RibbonButton>
                    <syncfusion:RibbonButton
                        IconType="VectorImage"
                        Label="Format Painter"
                        SizeForm="Small">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Margin="2.048,0.498,0.501,0.705"
                                Data="M13.434632,4.827646E-05 C13.680801,0.0024180976 13.926775,0.092046673 14.121765,0.27108389 14.544701,0.66010981 14.565695,1.3190858 14.167659,1.7340507 L11.531004,4.480899 13.369993,6.3119885 11.726018,7.9489524 6.8310282,12.794981 0,5.9919826 3.8440161,5.3719827 6.5970273,2.8419837 11.564087,7.7877166 6.5979662,2.8409979 8.2409729,1.2050026 10.105034,3.0610356 12.670845,0.32509833 C12.8764,0.10675568 13.155641,-0.0026375318 13.434632,4.827646E-05 z"
                                Fill="White"
                                Stretch="Fill" />
                            <Path
                                Margin="7.936,0,0,4.845"
                                Data="M2.3529817,2.4090486 L1.417989,3.3400479 5.8379548,7.7410448 6.7719474,6.8110455 z M7.5172076,0.99873667 C7.3818266,1.0037418 7.2480633,1.0597443 7.1480229,1.165737 L4.9139335,3.5478707 5.6360054,4.2659228 7.9211223,1.8858034 C8.0180495,1.782771 8.0700533,1.6487924 8.0661471,1.5067568 8.0611417,1.3647821 8.0010812,1.2347711 7.8960969,1.1377204 7.7895868,1.0397238 7.6525886,0.99373155 7.5172076,0.99873667 z M7.5527165,7.1653047E-05 C7.9184291,0.0035863224 8.2838595,0.13640766 8.5721467,0.40172305 8.8770893,0.68072825 9.0521443,1.0617281 9.0650842,1.4747729 9.0791228,1.8877565 8.9290931,2.2788277 8.6430719,2.5777922 L6.3439374,4.9723075 8.1899364,6.8110455 5.8379548,9.153044 0,3.3400479 2.3529817,0.99704962 4.205102,2.8418849 6.4200914,0.48174404 C6.7234051,0.15819254 7.1382422,-0.0039115331 7.5527165,7.1653047E-05 z"
                                Fill="#FF484644"
                                Stretch="Fill" />
                            <Path
                                Margin="2.049,6.365,4.368,0.705"
                                Data="M0.77698034,0 L10.585,3.2109802 6.8309581,6.9279997 0,0.12499928 z"
                                Fill="#FFF8DB8F"
                                Stretch="Fill" />
                            <Path
                                Margin="1,2.648,2.518,0"
                                Data="M2.3239305,4.4059882 L7.8809197,9.9390366 10.69988,7.1480067 z M7.630995,1.3829954 L5.1189968,3.6919881 3.9397421,3.8823536 11.49895,6.3573499 12.063992,5.7979813 z M7.657995,0 L13.483991,5.7999814 7.9662354,11.262604 7.8789665,11.349017 7.8779948,11.349963 0,3.5039886 4.6639969,2.7519911 z"
                                Fill="#FFEE9243"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                        <syncfusion:RibbonButton.ToolTip>
                            <syncfusion:ScreenTip Description="Format painter (Ctrl+Shift+C)" HelpText="Press F1 for more help.">
                                <TextBlock
                                    Width="175"
                                    HorizontalAlignment="Left"
                                    Foreground="#FF4C4C4C"
                                    TextWrapping="Wrap">
                                    <Run Text="Copy formatting from one place and apply it to another." />
                                    <LineBreak />
                                    <LineBreak />
                                    <Run Text="Double-click this button to apply the same formatting to multiple places in the document." />
                                </TextBlock>
                            </syncfusion:ScreenTip>
                        </syncfusion:RibbonButton.ToolTip>
                    </syncfusion:RibbonButton>
                </syncfusion:RibbonBar>
                <syncfusion:RibbonBar Header="Font" IsLargeButtonPanel="False">
                    <syncfusion:ButtonPanel SeparatorVisibility="Collapsed">
                        <syncfusion:RibbonComboBox Width="100" IsEditable="True">
                            <syncfusion:RibbonComboBox.ToolTip>
                                <syncfusion:ScreenTip Description="Font (Ctrl+Shift+F)">
                                    <TextBlock
                                        Width="165"
                                        HorizontalAlignment="Left"
                                        Foreground="#FF4C4C4C"
                                        Text="Change the font face."
                                        TextWrapping="Wrap" />
                                </syncfusion:ScreenTip>
                            </syncfusion:RibbonComboBox.ToolTip>
                        </syncfusion:RibbonComboBox>
                        <syncfusion:RibbonComboBox Width="40" IsEditable="True" />
                    </syncfusion:ButtonPanel>
                    <syncfusion:ButtonPanel SeparatorVisibility="Collapsed">
                        <syncfusion:RibbonButton
                            IconType="VectorImage"
                            Label="Increase Font Size"
                            SizeForm="ExtraSmall">
                            <syncfusion:RibbonButton.VectorImage>
                                <Path
                                    Width="5.005"
                                    Height="3.002"
                                    Margin="3,-1,1,2"
                                    HorizontalAlignment="Right"
                                    VerticalAlignment="Top"
                                    Data="M2.5189795,0 L5.0050001,2.2590036 4.3330035,3.0000011 2.5149817,1.3470006 0.66799865,3.002 0,2.2570047 z"
                                    Fill="#FF3094D0"
                                    Stretch="Fill" />
                                <Path
                                    Margin="2,1,4,0"
                                    Data="M4.4360077,0.8710022 C4.3949921,0.98799133 4.3580048,1.1040039 4.321994,1.2200012 4.2859833,1.3549957 4.2420075,1.4919891 4.1850006,1.6309967 L2.3469865,6.2549896 6.5470016,6.2549896 4.7169835,1.6179962 C4.6359894,1.427002 4.5530121,1.1779938 4.4660065,0.8710022 z M4.0639984,0 L4.7779882,0 8.8869998,10 8.0589959,10 6.8140003,6.8899994 2.0889907,6.8899994 0.84298758,10 0,10 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                    Stretch="Fill" />
                            </syncfusion:RibbonButton.VectorImage>
                        </syncfusion:RibbonButton>
                        <syncfusion:RibbonButton
                            IconType="VectorImage"
                            Label="Decrease Font Size"
                            SizeForm="ExtraSmall">
                            <syncfusion:RibbonButton.VectorImage>
                                <Path
                                    Width="5.006"
                                    Height="3.002"
                                    Margin="2,-1,2,2"
                                    HorizontalAlignment="Right"
                                    VerticalAlignment="Top"
                                    Data="M4.3379981,0 L5.0059998,0.74500296 2.4870088,3.002 0,0.74300412 0.67199955,0.0019988532 2.4910066,1.6549994 z"
                                    Fill="#FF3094D0"
                                    Stretch="Fill" />
                                <Path
                                    Margin="2,1,4,0"
                                    Data="M4.4360077,0.8710022 C4.3949921,0.98799133 4.3580048,1.1040039 4.321994,1.2200012 4.2859833,1.3549957 4.2420075,1.4919891 4.1850006,1.6309967 L2.3469865,6.2549896 6.5470016,6.2549896 4.7169835,1.6179962 C4.6359894,1.427002 4.5530121,1.1779938 4.4660065,0.8710022 z M4.0639984,0 L4.7779882,0 8.8869998,10 8.0589959,10 6.8140003,6.8899994 2.0889907,6.8899994 0.84298758,10 0,10 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                    Stretch="Fill" />
                            </syncfusion:RibbonButton.VectorImage>
                        </syncfusion:RibbonButton>
                    </syncfusion:ButtonPanel>
                    <syncfusion:ButtonPanel SeparatorVisibility="Collapsed">
                        <syncfusion:RibbonButton
                            IconType="VectorImage"
                            IsToggle="True"
                            Label="Bold"
                            SizeForm="ExtraSmall">
                            <syncfusion:RibbonButton.VectorImage>
                                <Path
                                    Width="10"
                                    Height="12"
                                    Margin="4,2,2,2"
                                    HorizontalAlignment="Center"
                                    VerticalAlignment="Center"
                                    Data="M1.3320006,5.8759918 L1.3320006,9.8339996 3.1399993,9.8339996 C3.9220123,9.8339996 4.5279998,9.6549988 4.9589996,9.2969971 5.3899993,8.9389954 5.6040038,8.447998 5.6040038,7.8239899 5.6040038,6.5249939 4.6900024,5.8759918 2.8619995,5.8759918 z M1.3320006,1.1660004 L1.3320006,4.7180023 2.6950073,4.7180023 C3.425003,4.7180023 3.998001,4.5469971 4.4160003,4.2079926 4.8330078,3.8669891 5.0420074,3.3880005 5.0420074,2.769989 5.0420074,1.701004 4.3150024,1.1660004 2.8619995,1.1660004 z M0,0 L3.2340087,0 C4.2180023,0 4.9970092,0.23300171 5.572998,0.69799811 6.149002,1.1629944 6.4370117,1.769989 6.4370117,2.5159912 6.4370117,3.1399994 6.2630004,3.6819916 5.9140014,4.1419983 5.5650024,4.6029968 5.0839996,4.9299927 4.4710082,5.125 L4.4710082,5.1549988 C5.2369995,5.2419891 5.8509979,5.5220032 6.3110046,5.9949951 6.7700042,6.4680023 6.9999999,7.0829926 6.9999999,7.8399963 6.9999999,8.7799988 6.6510009,9.5429993 5.95401,10.125992 5.2560119,10.709 4.376007,11 3.3130035,11 L0,11 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" />
                            </syncfusion:RibbonButton.VectorImage>
                        </syncfusion:RibbonButton>
                        <syncfusion:RibbonButton
                            IconType="VectorImage"
                            IsToggle="True"
                            Label="Italic"
                            SizeForm="ExtraSmall">
                            <syncfusion:RibbonButton.VectorImage>
                                <Path
                                    Width="10"
                                    Height="12"
                                    Margin="4,3,2,1"
                                    HorizontalAlignment="Center"
                                    VerticalAlignment="Center"
                                    Data="M2.000005,0 L6.000005,0 6.000005,1 4.4186966,1 2.4888427,8.9999952 4,8.9999952 4,9.9999952 0,9.9999952 0,8.9999952 1.4594386,8.9999952 3.3901918,1 2.000005,1 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" />
                            </syncfusion:RibbonButton.VectorImage>
                        </syncfusion:RibbonButton>
                        <syncfusion:RibbonButton
                            IconType="VectorImage"
                            Label="Underline"
                            SizeForm="ExtraSmall">
                            <syncfusion:RibbonButton.VectorImage>
                                <Path
                                    Width="10"
                                    Height="12"
                                    Margin="4,2,2,2"
                                    HorizontalAlignment="Center"
                                    VerticalAlignment="Center"
                                    Data="M0,10.999995 L9.0000002,10.999995 9.0000002,11.999995 0,11.999995 z M1.000005,0 L2.0000049,0 2.0000049,6.5 C2.000005,7.8779907 3.1210072,9 4.500005,9 5.8790028,9 7.000005,7.8779907 7.000005,6.5 L7.000005,0 8.000005,0 8.000005,6.5 C8.000005,8.4299927 6.4299977,10 4.500005,10 2.5699971,10 1.000005,8.4299927 1.000005,6.5 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" />
                            </syncfusion:RibbonButton.VectorImage>
                        </syncfusion:RibbonButton>
                    </syncfusion:ButtonPanel>
                    <syncfusion:ButtonPanel syncfusion:SimplifiedLayoutSettings.DisplayMode="Normal" SeparatorVisibility="Collapsed">
                        <syncfusion:SplitButton
                            IconType="VectorImage"
                            Label="Text Highlight Color"
                            SizeForm="ExtraSmall">
                            <syncfusion:SplitButton.VectorImage>
                                <Path
                                    Height="4"
                                    Margin="1"
                                    VerticalAlignment="Bottom"
                                    Data="M0,0 L16,0 16,4 0,4 z"
                                    Fill="Yellow"
                                    Stretch="Fill" />
                                <Path
                                    Margin="6.5,0.502,1.934,8.048"
                                    Data="M6.4365052,0.00010436084 C6.6881317,-0.0035195307 6.9411348,0.087229683 7.1381453,0.27322931 L8.254165,1.3292008 C8.6621631,1.7171909 8.6711658,2.3651685 8.2731775,2.763153 L2.5470487,8.4889981 0,6.0360758 5.7431277,0.29321776 C5.9346298,0.10172514 6.1848787,0.0037282004 6.4365052,0.00010436084 z"
                                    Fill="#FFF3F2F1"
                                    Stretch="Fill" />
                                <Path
                                    Margin="2.061,0,1.434,5"
                                    Data="M10.881433,1.0010477 C10.756186,1.0027986 10.631936,1.052303 10.535929,1.1488092 L5.1529995,6.5319232 6.9789655,8.2909641 12.358904,2.9118485 C12.454911,2.815838 12.506913,2.6878447 12.504899,2.55184 12.502915,2.4158355 12.446916,2.2888338 12.347918,2.1958293 L11.232911,1.1398066 C11.132922,1.0452991 11.00668,0.99929665 10.881433,1.0010477 z M10.868932,0.0001521778 C11.245179,-0.005222887 11.623424,0.13178115 11.920921,0.41278561 L13.035898,1.4688085 C13.332891,1.7498205 13.498905,2.1298184 13.504886,2.5378322 13.509891,2.9468378 13.354894,3.329857 13.065897,3.6188647 L6.9929731,9.6919965 6.6261415,9.3388461 5.5570025,10.219989 C4.9130021,10.748988 4.1050018,11.038988 3.2720014,11.038988 L0,11.038988 0.22000027,10.953988 C2.0155009,10.255738 3.3807202,8.7842073 3.9559099,6.9755153 L4.0042109,6.8147053 3.725008,6.5459155 9.8289366,0.44179319 C10.118438,0.15328126 10.492686,0.0055271609 10.868932,0.0001521778 z"
                                    Fill="#FF3A3937"
                                    Stretch="Fill" />
                            </syncfusion:SplitButton.VectorImage>
                        </syncfusion:SplitButton>
                        <syncfusion:SplitButton
                            IconType="VectorImage"
                            Label="Font Color"
                            SizeForm="ExtraSmall">
                            <syncfusion:SplitButton.VectorImage>
                                <Path
                                    Height="4"
                                    VerticalAlignment="Bottom"
                                    Data="M0,0 L16,0 16,4 0,4 z"
                                    Fill="#FFFE0000"
                                    Stretch="Fill" />
                                <Path
                                    Margin="3.344,0,3.352,5"
                                    Data="M4.6480023,0.95898432 C4.6079937,1.0870056 4.5689923,1.2149963 4.533012,1.34198 4.4980089,1.4909973 4.4510118,1.6419983 4.394005,1.7949829 L2.5330156,6.8809814 6.787006,6.8809814 4.9330055,1.7799988 C4.8510047,1.5699768 4.7659832,1.2969971 4.6790081,0.95898432 z M4.0779959,0 L5.209006,0 9.304,11 8.3170024,11 7.2039977,8.0019836 2.1150171,8.0029907 1.0100081,11 0,11 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                    Stretch="Fill" />
                            </syncfusion:SplitButton.VectorImage>
                        </syncfusion:SplitButton>
                        <syncfusion:SplitButton
                            IconType="VectorImage"
                            Label="Shading"
                            SizeForm="ExtraSmall">
                            <syncfusion:SplitButton.VectorImage>
                                <Path
                                    Margin="1"
                                    Data="M0,12 L15,12 15,15 0,15 z M7.9999695,0 C8.5529652,0 8.9999628,0.44699955 8.9999628,1 L8.9999628,6 10.999949,3.5 11.002948,6.414 6.7919779,10.625 2.5420079,6.375 6.9999766,1.9169998 6.9999766,1 C6.9999766,0.44699955 7.4469733,0 7.9999695,0 z"
                                    Fill="White"
                                    Stretch="Fill" />
                                <Path
                                    Height="4"
                                    Margin="1"
                                    VerticalAlignment="Bottom"
                                    Data="M1,1 L1,3 15,3 15,1 z M0,0 L16,0 16,4 0,4 z"
                                    Fill="#FFA1A0A0"
                                    Stretch="Fill" />
                                <Path
                                    Margin="2.335,0,3.997,4.168"
                                    Data="M6.1649812,0 C6.9919994,0 7.6649669,0.6729753 7.6649669,1.5000038 L7.6649669,6.5000162 6.6649764,6.5000162 6.6649764,1.5000038 C6.6649764,1.2249787 6.4400027,1.0000025 6.1649812,1.0000025 5.8899591,1.0000025 5.6649859,1.2249787 5.6649859,1.5000038 L5.6649859,2.6240301 1.4140491,6.8750172 4.9569843,10.418056 8.6680091,6.7069869 8.6649573,4.0009866 9.6649478,3.9990335 9.6679995,7.1209893 4.9569843,11.832 0,6.8750172 4.664995,2.2100275 4.664995,1.5000038 C4.664995,0.6729753 5.3379624,0 6.1649812,0 z"
                                    Fill="#FF505050"
                                    Stretch="Fill" />
                                <Path
                                    Width="2"
                                    Margin="0,4,2,6"
                                    HorizontalAlignment="Right"
                                    Data="M0,0 C1.1040039,0 2,0.89599609 2,2 L2,6 1,6 C1,6 1.1300049,2.6829834 0.68994144,2.1170044 0.53698733,1.9199829 2.9802322E-08,2 0,2 z"
                                    Fill="#FF135C9A"
                                    Stretch="Fill" />
                            </syncfusion:SplitButton.VectorImage>
                        </syncfusion:SplitButton>
                        <syncfusion:SplitButton
                            IconType="VectorImage"
                            Label="Borders"
                            SizeForm="ExtraSmall">
                            <syncfusion:SplitButton.VectorImage>
                                <Path
                                    Margin="1"
                                    Data="M0,0 L15,0 15,14 0,14 z"
                                    Fill="White"
                                    Stretch="Fill" />
                                <Path
                                    Margin="1"
                                    Data="M0,14 L15,14 15,15 0,15 z M14,12 L15,12 15,13 14,13 z M7,12 L8,12 8,13 7,13 z M0,12 L1,12 1,13 0,13 z M14,10 L15,10 15,11 14,11 z M7,10 L8,10 8,11 7,11 z M0,10 L1,10 1,11 0,11 z M14,8 L15,8 15,8.9999999 14,8.9999999 z M7,8 L8,8 8,8.9999999 7,8.9999999 z M0,8 L1,8 1,8.9999999 0,8.9999999 z M12,7 L13,7 13,8 12,8 z M10,7 L11,7 11,8 10,8 z M8,7 L8.9999999,7 8.9999999,8 8,8 z M6,7 L7,7 7,8 6,8 z M4,7 L5,7 5,8 4,8 z M2,7 L3,7 3,8 2,8 z M14,6.0000001 L15,6.0000001 15,7 14,7 z M7,6.0000001 L8,6.0000001 8,7 7,7 z M0,6.0000001 L1,6.0000001 1,7 0,7 z M14,4 L15,4 15,5 14,5 z M7,4 L8,4 8,5 7,5 z M0,4 L1,4 1,5 0,5 z M14,2 L15,2 15,3 14,3 z M7,2 L8,2 8,3 7,3 z M0,2 L1,2 1,3 0,3 z M14,0 L15,0 15,1 14,1 z M12,0 L13,0 13,1 12,1 z M10,0 L11,0 11,1 10,1 z M8,0 L8.9999999,0 8.9999999,1 8,1 z M6,0 L7,0 7,1 6,1 z M4,0 L5,0 5,1 4,1 z M2,0 L3,0 3,1 2,1 z M0,0 L1,0 1,1 0,1 z"
                                    Fill="#FF3A3A38"
                                    Stretch="Fill" />
                            </syncfusion:SplitButton.VectorImage>
                        </syncfusion:SplitButton>
                    </syncfusion:ButtonPanel>
                </syncfusion:RibbonBar>
                <syncfusion:RibbonBar Name="Delete" Header="Delete">
                    <syncfusion:RibbonButton Label="Ignore" />
                    <syncfusion:SplitButton Label="Clean Up">
                        <syncfusion:DropDownMenuItem Header="Clean Up Folder" />
                        <syncfusion:DropDownMenuItem Header="Clean Up Conversation" />
                        <syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder" />
                    </syncfusion:SplitButton>
                    <syncfusion:SplitButton HorizontalAlignment="Left" Label="Junk" />
                    <syncfusion:RibbonButton
                        IconType="VectorImage"
                        Label="Delete"
                        SizeForm="Large">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Margin="4"
                                Data="M1.4139423,0L7.0029922,5.5845888 12.592018,0 14.006015,1.4149939 8.4180527,6.9985202 14.006,12.582007 12.591996,13.997001 7.0030056,8.4124444 1.4140122,13.997001 1.5026823E-05,12.582007 5.5879484,6.9985092 0,1.4149939z "
                                Fill="Red"
                                SnapsToDevicePixels="True"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                    </syncfusion:RibbonButton>
                </syncfusion:RibbonBar>
                <syncfusion:RibbonBar
                    x:Name="help"
                    Header="Help"
                    Position="Right">
                    <syncfusion:RibbonButton
                        IconType="VectorImage"
                        Label="About"
                        SizeForm="Large">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Width="18"
                                Height="18"
                                Margin="0.5,0.5,8.354,8.353"
                                Data="M10,0 C15.52301,0 20,4.4769897 20,10 20,15.522003 15.52301,20 10,20 4.4780121,20 0,15.522003 0,10 0,4.4769897 4.4780121,0 10,0 z"
                                Fill="White"
                                Stretch="Fill" />
                            <Path
                                Margin="4"
                                Data="M10.5,1 C5.262001,1 1,5.2619991 1,10.499999 1,15.737999 5.262001,19.999999 10.5,19.999999 15.738001,19.999999 20.000001,15.737999 20.000001,10.499999 20.000001,5.2619991 15.738001,1 10.5,1 z M10.5,0 C16.290001,0 21.000001,4.7099991 21.000001,10.499999 21.000001,13.214061 19.965089,15.690819 18.269143,17.556394 L18.266851,17.558856 28.853999,28.146005 28.146998,28.853005 17.559885,18.265892 17.556396,18.269141 C15.690821,19.965087 13.214063,20.999999 10.5,20.999999 4.710001,20.999999 0,16.289999 0,10.499999 0,4.7099991 4.710001,0 10.5,0 z"
                                Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                    </syncfusion:RibbonButton>
                    <syncfusion:RibbonButton
                        IconType="VectorImage"
                        Label="Help"
                        SizeForm="Large">
                        <syncfusion:RibbonButton.VectorImage>
                            <Path
                                Margin="6"
                                Data="M3.9400001,13.238 L5.5349999,13.238 5.5349999,14.833 3.9400001,14.833 z M4.7539988,0 C6.2060028,8.8817842E-16 7.3750015,0.39599991 8.2300044,1.1770003 9.0749989,1.9500008 9.5039998,2.8959999 9.5039998,3.9900017 9.5039998,4.6220016 9.3539982,5.2110023 9.0599995,5.743 8.7549992,6.2900009 8.1419993,6.9750023 7.2350021,7.7770004 6.5800033,8.3570023 6.1620041,8.7770004 5.9580017,9.0590019 5.7429972,9.3530006 5.5830012,9.6930008 5.4789973,10.070999 5.3929988,10.394001 5.3399974,10.871002 5.3170024,11.521999 L4.0500041,11.521999 C4.0479975,11.409 4.0459986,11.316002 4.0459986,11.244999 4.0459986,10.528 4.1480036,9.9029999 4.3499995,9.387001 4.4899989,9.0110016 4.7289973,8.618 5.0599986,8.2180023 5.310998,7.9189987 5.7679992,7.4770012 6.4180008,6.9049988 7.1190048,6.2859993 7.5660034,5.7989998 7.7829991,5.4169998 8.0100032,5.0200005 8.1240016,4.5839996 8.1240016,4.1189995 8.1240016,3.288002 7.796999,2.5480003 7.1510025,1.9220008 6.5110031,1.2989998 5.7139979,0.98400116&#xd;&#xa;4.784997,0.9840011 3.8870018,0.98400116 3.1250005,1.2709999 2.5199972,1.8380011 1.9710011,2.3500004 1.5930027,3.1230011 1.3939974,4.1389999 L0,3.9729996 C0.19999708,2.7350006 0.6869967,1.7670002 1.4499972,1.0950012 2.2720037,0.36900139 3.3850029,8.8817842E-16 4.7539988,0 z"
                                Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                Stretch="Fill" />
                        </syncfusion:RibbonButton.VectorImage>
                    </syncfusion:RibbonButton>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
            <syncfusion:RibbonTab Caption="Insert" />
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

this.help.Position = Syncfusion.Windows.Tools.Controls.HorizontalPosition.Right;

{% endhighlight %}

{% endtabs %}

![Image set for RibbonBar with Position as Right](RibbonResizeWindow-images/RibbonBar_Position.png)

## Setting collapse image for RibbonBar

When the RibbonBar is converted into a dropdown button during resizing, the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) allows us to display a image using its [`IconTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_IconTemplate) or [`CollapseImage`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_CollapseImage) property.

 N> The [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) loads icon in the following priority order,
 * [`IconTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_IconTemplate)
 * [`CollapseImage`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_CollapseImage)

### Setting icon template

The [`IconTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_IconTemplate) property provides support to set any type of image such as glyph, font or any custom content to the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html). The [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) displays the [`IconTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_IconTemplate) in 16 * 16 size.

{% tabs %}

{% highlight XAML %}

 <syncfusion:RibbonWindow x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="MaterialLight"
        Title="MainWindow" Height="350" Width="600">
    <Grid>
        <syncfusion:Ribbon VerticalAlignment="Top">
            <syncfusion:RibbonTab Caption="Home">
                <syncfusion:RibbonBar Header="Clipboard" >
                    <syncfusion:RibbonBar.IconTemplate>
                        <DataTemplate>
                            <Grid Width="14" Height="16">
                                <Path Width="7" Margin="0,7,0,0" HorizontalAlignment="Right" Fill="#FF3A3A38" Stretch="Fill"
                                      Data="F1M122,367L127,367L127,360L122,360z M128,368L121,368L121,359L128,359z" />
                                <Path Margin="0,2,2,0" Fill="#FFDE6C00" Stretch="Fill"
                                      Data="M0,0 L12,0 12,4 11,4 11,0.99999994 1.0000002,0.99999994 1.0000002,13 6.0000001,13 6.0000001,14 0,14 z" />
                                <Path Margin="1,3,3,1" Fill="#FFF8DB8F" Stretch="Fill"
                                      Data="M0,0 L10,0 10,3 9.0000001,3 9.0000001,0.99999994 1.0000001,0.99999994 1.0000001,1.5829999 1.0000001,2.5 1.0000001,11 5.0000001,11 5.0000001,12 0,12 z" />
                                <Path Margin="2.011,0.5,0.983,0.983" Fill="#FFFAFAFA" Stretch="Fill"
                                      Data="M5.9873815,7.496151 L11.006,7.496151 11.006,14.516999 5.9873815,14.516999 z M0,5.4959998 L3.9880071,5.4964137 3.9880071,13.51695 0,13.51695 z M3.9889999,2.2337155E-15 C4.8170028,-4.4703477E-08 5.4889999,0.67098993 5.4889999,1.5 L5.4889999,2 7.4889999,2 7.4889999,5 0.4889999,5 0.4889999,2 2.4889999,2 2.4889999,1.5 C2.4889999,0.67098993 3.1609969,-4.4703477E-08 3.9889999,2.2337155E-15 z" />
                                <Path Height="6" Margin="2,0,4,0" VerticalAlignment="Top" Fill="#FF797774" Stretch="Fill"
                                      Data="M4,1 C3.447998,1 3,1.4490051 3,2 L3,3 1,3 1,5 7,5 7,3 5,3 5,2 C5,1.4490051 4.552002,1 4,1 z M4,0 C5.1029968,0 6,0.89700317 6,2 L8,2 8,6 0,6 0,2 2,2 C2,0.89700317 2.8970032,0 4,0 z" />
                            </Grid>
                        </DataTemplate>
                    </syncfusion:RibbonBar.IconTemplate>
                </syncfusion:RibbonBar>
                <syncfusion:RibbonBar Header="Font" >
                    <syncfusion:RibbonBar.IconTemplate>
                        <DataTemplate>
                            <Grid>
                                <Path
                                    Height="4" VerticalAlignment="Bottom" Data="M0,0 L16,0 16,4 0,4 z"
                                    Fill="#FFFE0000" Stretch="Fill" />
                                <Path
                                    Margin="3.344,0,3.352,5"
                                    Data="M4.6480023,0.95898432 C4.6079937,1.0870056 4.5689923,1.2149963 4.533012,1.34198 4.4980089,1.4909973 4.4510118,1.6419983 4.394005,1.7949829 L2.5330156,6.8809814 6.787006,6.8809814 4.9330055,1.7799988 C4.8510047,1.5699768 4.7659832,1.2969971 4.6790081,0.95898432 z M4.0779959,0 L5.209006,0 9.304,11 8.3170024,11 7.2039977,8.0019836 2.1150171,8.0029907 1.0100081,11 0,11 z"
                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" Stretch="Fill" />
                            </Grid>
                        </DataTemplate>
                    </syncfusion:RibbonBar.IconTemplate>
                </syncfusion:RibbonBar>
            </syncfusion:RibbonTab>
        </syncfusion:Ribbon>
    </Grid>
 </syncfusion:RibbonWindow>

 {% endhighlight %}

 {% highlight C# %}

 Ribbon ribbon = new Ribbon();
 ribbon.VerticalAlignment = VerticalAlignment.Top;
 // Creating new tabs
 RibbonTab homeTab = new RibbonTab();
 homeTab.Caption = "Home";
 homeTab.IsChecked = true;
 
 // Creating new bar
 RibbonBar clipboardBar = new RibbonBar();
 clipboardBar.Header = "Clipboard";
 
 DataTemplate iconDataTemplate = new DataTemplate();
 FrameworkElementFactory gridElement = new FrameworkElementFactory(typeof(Grid));
 FrameworkElementFactory pathElement1 = new FrameworkElementFactory(typeof(Path));
 FrameworkElementFactory pathElement2 = new FrameworkElementFactory(typeof(Path));
 FrameworkElementFactory pathElement3 = new FrameworkElementFactory(typeof(Path));
 FrameworkElementFactory pathElement4 = new FrameworkElementFactory(typeof(Path));
 FrameworkElementFactory pathElement5 = new FrameworkElementFactory(typeof(Path));
 
 gridElement.SetValue(Grid.WidthProperty, (double)14);
 gridElement.SetValue(Grid.HeightProperty, (double)16);
 pathElement1.SetValue(Path.DataProperty, Geometry.Parse("F1M122,367L127,367L127,360L122,360z M128,368L121,368L121,359L128,359z"));
 pathElement1.SetValue(Path.MarginProperty, new Thickness(0, 7, 0, 0));
 pathElement1.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(58, 58, 56)));
 pathElement1.SetValue(Path.StretchProperty, Stretch.Fill);
 pathElement1.SetValue(Path.WidthProperty, (double)7);
 pathElement1.SetValue(Path.HorizontalAlignmentProperty, HorizontalAlignment.Right);
 
 pathElement2.SetValue(Path.DataProperty, Geometry.Parse("M0,0 L12,0 12,4 11,4 11,0.99999994 1.0000002,0.99999994 1.0000002,13 6.0000001,13 6.0000001,14 0,14 z"));
 pathElement2.SetValue(Path.MarginProperty, new Thickness(0, 2, 2, 0));
 pathElement2.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(222, 108, 0)));
 pathElement2.SetValue(Path.StretchProperty, Stretch.Fill);
 
 pathElement3.SetValue(Path.DataProperty, Geometry.Parse("M0,0 L10,0 10,3 9.0000001,3 9.0000001,0.99999994 1.0000001,0.99999994 1.0000001,1.5829999 1.0000001,2.5 1.0000001,11 5.0000001,11 5.0000001,12 0,12 z"));
 pathElement3.SetValue(Path.MarginProperty, new Thickness(1, 3, 3, 1));
 pathElement3.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(248, 219, 143)));
 pathElement3.SetValue(Path.StretchProperty, Stretch.Fill);
 
 pathElement4.SetValue(Path.DataProperty, Geometry.Parse("M5.9873815,7.496151 L11.006,7.496151 11.006,14.516999 5.9873815,14.516999 z M0,5.4959998 L3.9880071,5.4964137 3.9880071,13.51695 0,13.51695 z M3.9889999,2.2337155E-15 C4.8170028,-4.4703477E-08 5.4889999,0.67098993 5.4889999,1.5 L5.4889999,2 7.4889999,2 7.4889999,5 0.4889999,5 0.4889999,2 2.4889999,2 2.4889999,1.5 C2.4889999,0.67098993 3.1609969,-4.4703477E-08 3.9889999,2.23
 pathElement4.SetValue(Path.MarginProperty, new Thickness(2.011, 0.5, 0.983, 0.983));
 pathElement4.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(250, 250, 250)));
 pathElement4.SetValue(Path.StretchProperty, Stretch.Fill);
 
 pathElement5.SetValue(Path.DataProperty, Geometry.Parse("M4,1 C3.447998,1 3,1.4490051 3,2 L3,3 1,3 1,5 7,5 7,3 5,3 5,2 C5,1.4490051 4.552002,1 4,1 z M4,0 C5.1029968,0 6,0.89700317 6,2 L8,2 8,6 0,6 0,2 2,2 C2,0.89700317 2.8970032,0 4,0 z"));
 pathElement5.SetValue(Path.MarginProperty, new Thickness(2, 0, 4, 0));
 pathElement5.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(121, 119, 116)));
 pathElement5.SetValue(Path.StretchProperty, Stretch.Fill);
 pathElement5.SetValue(Path.HeightProperty, (double)6);
 pathElement5.SetValue(Path.VerticalAlignmentProperty, VerticalAlignment.Top);
 gridElement.AppendChild(pathElement1);
 gridElement.AppendChild(pathElement2);
 gridElement.AppendChild(pathElement3);
 gridElement.AppendChild(pathElement4);
 gridElement.AppendChild(pathElement5);
 iconDataTemplate.VisualTree = gridElement;
 clipboardBar.IconTemplate = iconDataTemplate;
 
 RibbonBar fontBar = new RibbonBar();
 fontBar.Header = "Font";
 
 DataTemplate iconDataTemplate2 = new DataTemplate();
 FrameworkElementFactory gridElement2 = new FrameworkElementFactory(typeof(Grid));
 FrameworkElementFactory fontElement1 = new FrameworkElementFactory(typeof(Path));
 FrameworkElementFactory fontElement2 = new FrameworkElementFactory(typeof(Path));
 
 fontElement1.SetValue(Path.DataProperty, Geometry.Parse("M0,0 L16,0 16,4 0,4 z"));
 fontElement1.SetValue(Path.FillProperty, new SolidColorBrush(Color.FromRgb(254, 0, 0)));
 fontElement1.SetValue(Path.StretchProperty, Stretch.Fill);
 fontElement1.SetValue(Path.HeightProperty, (double)4);
 fontElement1.SetValue(Path.VerticalAlignmentProperty, VerticalAlignment.Bottom);
 fontElement2.SetValue(Path.DataProperty, Geometry.Parse("M4.6480023,0.95898432 C4.6079937,1.0870056 4.5689923,1.2149963 4.533012,1.34198 4.4980089,1.4909973 4.4510118,1.6419983 4.394005,1.7949829 L2.5330156,6.8809814 6.787006,6.8809814 4.9330055,1.7799988 C4.8510047,1.5699768 4.7659832,1.2969971 4.6790081,0.95898432 z M4.0779959,0 L5.209006,0 9.304,11 8.3170024,11 7.2039977,8.0019836 2.1150171,8.0029907 1.0100081,11 0,11 z"));
 fontElement2.SetValue(Path.MarginProperty, new Thickness(3.344, 0, 3.352, 5));
 fontElement2.SetValue(Path.FillProperty, new SolidColorBrush(Colors.Black));
 fontElement2.SetValue(Path.StretchProperty, Stretch.Fill);
 
 gridElement2.AppendChild(fontElement1);
 gridElement2.AppendChild(fontElement2);
 
 iconDataTemplate2.VisualTree = gridElement2;
 clipboardBar.IconTemplate = iconDataTemplate2;
 
 // Adding bars to the tabs
 homeTab.Items.Add(clipboardBar);
 homeTab.Items.Add(fontBar);
 
 // Adding tabs to ribbon
 ribbon.Items.Add(homeTab);
 grid.Children.Add(ribbon);
 SfSkinManager.SetVisualStyle(this, VisualStyles.MaterialLight);

 {% endhighlight %}

 {% endtabs %}

 ![Image set for RibbonBar using IconTemplate](RibbonResizeWindow-images/RibbonBar_IconTemplate.png)

 N> [View sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-ribbon-examples/tree/main/Samples/Setting-icons-using-IconTemplate)

### Setting image path

 The [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) allows to set the image for the dropdown button using its [`CollapseImage`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html#Syncfusion_Windows_Tools_Controls_RibbonBar_CollapseImage) property. The [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) displays the image in 16 * 16 size.


 {% tabs %}

 {% highlight XAML %}

 <syncfusion:RibbonWindow x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.VisualStyle="MaterialLight"
        Title="MainWindow" Height="350" Width="600">
    <Grid>
        <syncfusion:Ribbon VerticalAlignment="Top">
            <syncfusion:RibbonTab Caption="Home">
                <syncfusion:RibbonBar Header="Clipboard" CollapseImage="Resources/Paste16.png"/>
                <syncfusion:RibbonBar Header="Font" CollapseImage="Resources/FontColor.png"/>
            </syncfusion:RibbonTab>
        </syncfusion:Ribbon>
    </Grid>
 </syncfusion:RibbonWindow>

 {% endhighlight %}

 {% highlight C# %}

 Ribbon ribbon = new Ribbon();
 ribbon.VerticalAlignment = VerticalAlignment.Top;
 // Creating new tabs
 RibbonTab homeTab = new RibbonTab();
 homeTab.Caption = "Home";
 homeTab.IsChecked = true;
 
 // Creating new bar
 RibbonBar clipboardBar = new RibbonBar();
 clipboardBar.Header = "Clipboard";
 clipboardBar.CollapseImage = new BitmapImage(new Uri(@"/Resources/Paste16.png", UriKind.RelativeOrAbsolute));
 
 RibbonBar fontBar = new RibbonBar();
 fontBar.Header = "Font";
 fontBar.CollapseImage = new BitmapImage(new Uri(@"/Resources/FontColor.png", UriKind.RelativeOrAbsolute));
 
 // Adding bars to the tabs
 homeTab.Items.Add(clipboardBar);
 homeTab.Items.Add(fontBar);
 
 // Adding tabs to ribbon
 ribbon.Items.Add(homeTab);
 grid.Children.Add(ribbon);
 SfSkinManager.SetVisualStyle(this, VisualStyles.MaterialLight);

 {% endhighlight %}

 {% endtabs %}

 ![Resize Ribbon Window](RibbonResizeWindow-images/RibbonBar_CollapseImage.png)

## Grouping RibbonTabs using ContextTabGroups

ContextualTabGroups are used to group the RibbonTabs for easy Navigation. This ContextTabGroups appear when a user enable their context. 

## Creating ContextTabGroup 


This ContextTabGroup can also be kept hidden and shown while required cases like in Word Document’s TABLETOOLS ContextTabGroups which gets displayed automatically, while selecting the table.  The following code snippet used to create a ContextTabGroup

{% tabs %}
 
{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table tools" IsGroupVisible="True" BackColor="Green">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![ContextTabGroup](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img1.jpeg)

## Add ContextTabGroup to the simplified layout

When the simplified layout is enabled, the ContextTabGroup can be added and its items will be displayed in a single line as shown below. To know more about the simplified layout, refer [here](https://help.syncfusion.com/wpf/ribbon/simplifiedlayout).

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow x:Class="RibbonButton_IconTemp.Window1"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:RibbonButton_IconTemp" xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        skin:SfSkinManager.VisualStyle="MaterialLight"
        Title="Untitled 1 - Ribbon Control" Height="450" Width="800">
    <Grid x:Name="grid">
        <syncfusion:Ribbon VerticalAlignment="Top" EnableSimplifiedLayoutMode="True" LayoutMode="Simplified">
            <syncfusion:Ribbon.ContextTabGroups>
                <syncfusion:ContextTabGroup
                        BackColor="Orange" IsGroupVisible="True" Label="Tools">
                    <syncfusion:RibbonTab
                            Caption="Insert"
                            IsChecked="True">
                        <syncfusion:RibbonBar
                                Header="Illustrations"
                                IsLauncherButtonVisible="True">
                            <syncfusion:RibbonButton
                                    Label="Picture"
                                    MediumIcon="Resources/Picture20.png"
                                    SizeForm="Large">
                            </syncfusion:RibbonButton>
                            <syncfusion:RibbonButton
                                    Label="Comment"
                                    MediumIcon="Resources/New Comment20.png"
                                    SizeForm="Large">
                            </syncfusion:RibbonButton>
                            <syncfusion:DropDownButton
                                    Label="Shapes"
                                    MediumIcon="Resources/Insert Shapes20.png"
                                    SizeForm="Small">
                            </syncfusion:DropDownButton>
                            <syncfusion:DropDownButton
                                    Label="Chart"
                                    MediumIcon="Resources/Base chart20.png"
                                    SizeForm="Small">
                            </syncfusion:DropDownButton>
                        </syncfusion:RibbonBar>
                    </syncfusion:RibbonTab>
                </syncfusion:ContextTabGroup>
            </syncfusion:Ribbon.ContextTabGroups>
        </syncfusion:Ribbon>
    </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

Ribbon ribbon = new Ribbon();
ribbon.VerticalAlignment = VerticalAlignment.Top;
ribbon.EnableSimplifiedLayoutMode = true;
ribbon.LayoutMode = LayoutMode.Simplified;

//Creating context tab group
ContextTabGroup contextTab = new ContextTabGroup();
contextTab.Label = "Tools";
contextTab.BackColor = Colors.Orange;
contextTab.IsGroupVisible = true;

// Creating new tabs
RibbonTab insertTab = new RibbonTab();
insertTab.Caption = "Insert";
insertTab.IsChecked = true;

// Creating new bar
RibbonBar illustrationsBar = new RibbonBar();
illustrationsBar.Header = "Illustrations";

// Creating items
// Creating items
RibbonButton pictureButton = new RibbonButton();
pictureButton.Label = "Picture";
pictureButton.SizeForm = SizeForm.Large;
pictureButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Picture20.png", UriKind.RelativeOrAbsolute));

RibbonButton commentButton = new RibbonButton();
commentButton.Label = "Comment";
commentButton.SizeForm = SizeForm.Large;
commentButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/New Comment20.png", UriKind.RelativeOrAbsolute));

DropDownButton shapesButton = new DropDownButton();
shapesButton.Label = "Shapes";
shapesButton.SizeForm = SizeForm.Small;
shapesButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Insert Shapes20.png", UriKind.RelativeOrAbsolute));

DropDownButton chartButton = new DropDownButton();
chartButton.Label = "Chart";
chartButton.SizeForm = SizeForm.Small;
chartButton.MediumIcon = new BitmapImage(new Uri(@"/Resources/Base chart20.png", UriKind.RelativeOrAbsolute));

// Adding items to bar
illustrationsBar.Items.Add(pictureButton);
illustrationsBar.Items.Add(commentButton);
illustrationsBar.Items.Add(shapesButton);
illustrationsBar.Items.Add(chartButton);

// Adding bars to the tabs
insertTab.Items.Add(illustrationsBar);
//Adding ribbon tab to the context tab
contextTab.RibbonTabs.Add(insertTab);

// Adding context tab
ribbon.ContextTabGroups.Add(contextTab);
grid.Children.Add(ribbon);

SfSkinManager.SetVisualStyle(this, VisualStyles.MaterialLight);

{% endhighlight %}

{% endtabs %}

![ContextTabGroup during simplified layout](GroupingRibbonTabsusingContextTabGroups_images/ContextTabGroup_Simplified.png)


## Multiple ContextTabs

To differentiate one ContextTabGroup with one another, change its `BackColor` property of the ContextTabGroup , Since a ContextTabGroup Support to have multiple context Tab.
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table Tools" BackColor="Green" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
<syncfusion:ContextTabGroup Label="Table Grid" BackColor="Red" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![Multiple ContextTabs](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img2.jpeg)


## ContextTabGroup heading

The `Label` property of the ContextTabGroup is used to define the Heading for the ContextTabGroup. 
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup Label="Table tools" BackColor="Green" IsGroupVisible="True">
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />
<syncfusion:RibbonTab Caption="Design" IsChecked="False" />
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}
 
{% endtabs %}

![ContextTabGroup heading](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img3.jpeg)




## Changing the visibility at run time

ContextTabGroup visibility can also be changed at the runtime. To change the visibility, enable `IsGroupVisible` property of the ContextTabGroup
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  VerticalAlignment="Top" >
<syncfusion:Ribbon.ContextTabGroups>
<syncfusion:ContextTabGroup x:Name="_contextTabGroup" Label="Table tools" BackColor="Red"  >
<syncfusion:RibbonTab Caption="Tables" IsChecked="True" >
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="Design" IsChecked="False" >
</syncfusion:RibbonTab>
</syncfusion:ContextTabGroup>
</syncfusion:Ribbon.ContextTabGroups>
</syncfusion:Ribbon>

{% endhighlight %}
 
{% endtabs %}
 
{% tabs %}

{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)
{
    _contextTabGroup.IsGroupVisible = true;
}

{% endhighlight %}

{% highlight VB %}
 
Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
_contextTabGroup.IsGroupVisible = True
End Sub

{% endhighlight %}
 
{% endtabs %}

![Changing the visibility at run time](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img4.jpeg)


After the Button is clicked, the ContextTabGroup visibility changes as follows

![Changing the visibility at run time](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img5.jpeg)


## Creating ContextTabGroup in MVVM

To create context tab group in Ribbon, use  `ContextGroupSource` and `ContextGroupContainerStyle` properties. Similarly we can populate ContextTabGroup to corresponding RibbonTab using `ItemsSource` and `ItemContainerStyle` properties of ContextTabGroup.

To create a ContextTabGroup in MVVM, follow below steps. 

1. Create a class for ContextTabGroup, RibbonBar and RibbonItems in Model CS file.

{% tabs %}

{% highlight C# %}

  public class CustomContextTab : INotifyPropertyChanged
    {
        private string tabheader;

        public string TabHeader
        {
            get { return tabheader; }
            set
            {
                tabheader = value;
                RaisePropertyChanged("TabHeader");
            }
        }

        private Color _backcolor;

        public Color BackColor
        {
            get { return _backcolor; }
            set
            {
                _backcolor = value;
                RaisePropertyChanged("BackColor");
            }
        }

        private bool _isgroupvisible;

        public bool IsGroupVisible
        {
            get { return _isgroupvisible; }
            set
            {
                _isgroupvisible = value;
                RaisePropertyChanged("IsGroupVisible");
            }
        }

        public ObservableCollection<CustomRibbonTab> CustomContextRibbonTabs { get; set; }

        public CustomContextTab()
        {
            CustomContextRibbonTabs = new ObservableCollection<CustomRibbonTab>();
        }

        public void RaisePropertyChanged(string name)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(name));
            }
        }
        public event PropertyChangedEventHandler PropertyChanged;
    }
    public class CustomRibbonBar
    {
        public string BarHeader { get; set; }

        public ObservableCollection<CustomRibbonItem> CustomRibbonItems { get; set; }

        public CustomRibbonBar()
        {
            CustomRibbonItems = new ObservableCollection<CustomRibbonItem>();
        }

    }

    public class CustomRibbonItem
    {
        public CustomRibbonItem()
        {
            IsSplitButton = false;
            IsBoolean = true;
        }
        public string ItemHeader
        {
            get;
            set;
        }
        public string Image { get; set; }
        public bool IsBoolean { get; set; }

        public bool IsLarge { get; set; }

        public bool IsSplitButton { get; set; }
    }
{% endhighlight %}

{% highlight VB %}
 
Public Class CustomContextTab
    Inherits INotifyPropertyChanged

    Private tabheader As String

    Public Property TabHeader As String
        Get
            Return tabheader
        End Get
        Set(ByVal value As String)
            tabheader = value
            RaisePropertyChanged("TabHeader")
        End Set
    End Property

    Private _backcolor As Color

    Public Property BackColor As Color
        Get
            Return _backcolor
        End Get
        Set(ByVal value As Color)
            _backcolor = value
            RaisePropertyChanged("BackColor")
        End Set
    End Property

    Private _isgroupvisible As Boolean

    Public Property IsGroupVisible As Boolean
        Get
            Return _isgroupvisible
        End Get
        Set(ByVal value As Boolean)
            _isgroupvisible = value
            RaisePropertyChanged("IsGroupVisible")
        End Set
    End Property

    Public Property CustomContextRibbonTabs As ObservableCollection(Of CustomRibbonTab)

    Public Sub New()
        CustomContextRibbonTabs = New ObservableCollection(Of CustomRibbonTab)()
    End Sub

    Public Sub RaisePropertyChanged(ByVal name As String)
        RaiseEvent PropertyChanged(Me, New PropertyChangedEventArgs(name))
    End Sub

    Public Event PropertyChanged As PropertyChangedEventHandler
End Class

Public Class CustomRibbonBar
    Public Property BarHeader As String
    Public Property CustomRibbonItems As ObservableCollection(Of CustomRibbonItem)

    Public Sub New()
        CustomRibbonItems = New ObservableCollection(Of CustomRibbonItem)()
    End Sub
End Class

Public Class CustomRibbonItem
    Public Sub New()
        IsSplitButton = False
        IsBoolean = True
    End Sub

    Public Property ItemHeader As String
    Public Property Image As String
    Public Property IsBoolean As Boolean
    Public Property IsLarge As Boolean
    Public Property IsSplitButton As Boolean
End Class


{% endhighlight %}

{% endtabs %}

2. Create a View model class and then add ContextTabGroup , RibbonBars and RibbonItems with some properties.

{% tabs %}

{% highlight C# %}

  public class ViewModel
    {
        public ObservableCollection<CustomContextTab> CustomContextTabs { get; set; }

        public ViewModel()
        {
            CustomContextTabs = new ObservableCollection<CustomContextTab>();
            PopulateContextTabs();        
        }

        private void PopulateContextTabs()
        {
            CustomContextTab contexttab1 = new CustomContextTab() { TabHeader = "ContextTabGroup1",BackColor=Colors.Red,IsGroupVisible=true };
            CustomRibbonTab Tab1 = new CustomRibbonTab() { TabHeader = "TabGroup1" };
            PopulateRibbonHomeBars(Tab1);
            CustomRibbonTab Tab2 = new CustomRibbonTab() { TabHeader = "TabGroup2" };
            PopulateRibbonInsertBars(Tab2);

            contexttab1.CustomContextRibbonTabs.Add(Tab1);
            contexttab1.CustomContextRibbonTabs.Add(Tab2);

            CustomContextTabs.Add(contexttab1);

            CustomContextTab contexttab2 = new CustomContextTab() { TabHeader = "ContextTabGroup2",BackColor=Colors.Green,IsGroupVisible=true };
            CustomRibbonTab Tab11 = new CustomRibbonTab() { TabHeader = "TabGroup11" };
            PopulateRibbonHomeBars(Tab11);
            CustomRibbonTab Tab21 = new CustomRibbonTab() { TabHeader = "TabGroup21" };
            PopulateRibbonInsertBars(Tab21);

            contexttab2.CustomContextRibbonTabs.Add(Tab11);
            contexttab2.CustomContextRibbonTabs.Add(Tab21);

            CustomContextTabs.Add(contexttab2);
        }

        void PopulateRibbonHomeBars(CustomRibbonTab Tab)
        {
            CustomRibbonBar Bar1 = new CustomRibbonBar() { BarHeader = "Clipboard" };
            PopuplateRibbonNewItems(Bar1);
            CustomRibbonBar Bar2 = new CustomRibbonBar() { BarHeader = "Editing" };
            PopuplateRibbonEditingItems(Bar2);
            Tab.CustomRibbonBars.Add(Bar1);
            Tab.CustomRibbonBars.Add(Bar2);
        }

        void PopuplateRibbonNewItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Paste", IsLarge = true, Image = "Paste32.png" };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Cut", Image = "Cut16.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Copy", Image = "Copy16.png" };
            CustomRibbonItem Item4 = new CustomRibbonItem() { ItemHeader = "Format Painter", Image = "FormatPainter16.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
            Bar.CustomRibbonItems.Add(Item4);
        }

        private void PopuplateRibbonEditingItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Hyperlink", IsLarge = true, Image = "hyperlink32.png" };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Replace", IsLarge = true, Image = "replace_32.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Zoom", IsLarge = true, Image = "Zoom_32x32.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
        }

        private void PopulateRibbonInsertBars(CustomRibbonTab Tab)
        {
            CustomRibbonBar Bar2 = new CustomRibbonBar() { BarHeader = "Mail" };
            PopuplateRibbonMailItems(Bar2);
            CustomRibbonBar Bar1 = new CustomRibbonBar() { BarHeader = "Tables" };
            PopuplateRibbonTablesItems(Bar1);
            Tab.CustomRibbonBars.Add(Bar2);
            Tab.CustomRibbonBars.Add(Bar1);
        }

        private void PopuplateRibbonMailItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Attach File", IsLarge = true, Image = "base_paperclip_32.png",IsSplitButton=true };
            CustomRibbonItem Item2 = new CustomRibbonItem() { ItemHeader = "Business card", IsLarge = true, Image = "base_business_contacts.png" };
            CustomRibbonItem Item3 = new CustomRibbonItem() { ItemHeader = "Audio", IsLarge = true, Image = "base_speaker_32.png" };
            Bar.CustomRibbonItems.Add(Item1);
            Bar.CustomRibbonItems.Add(Item2);
            Bar.CustomRibbonItems.Add(Item3);
        }

        private void PopuplateRibbonTablesItems(CustomRibbonBar Bar)
        {
            CustomRibbonItem Item1 = new CustomRibbonItem() { ItemHeader = "Tables", IsLarge = true, IsSplitButton = true, Image = "Table_32.png" };
            Bar.CustomRibbonItems.Add(Item1);
        }
    }

{% endhighlight %}

{% highlight VB %}

Public Class ViewModel
    Public Property CustomContextTabs As ObservableCollection(Of CustomContextTab)

    Public Sub New()
        CustomContextTabs = New ObservableCollection(Of CustomContextTab)()
        PopulateContextTabs()
    End Sub

    Private Sub PopulateContextTabs()
        Dim contexttab1 As CustomContextTab = New CustomContextTab() With {
            .TabHeader = "ContextTabGroup1",
            .BackColor = Colors.Red,
            .IsGroupVisible = True
        }
        Dim Tab1 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup1"
        }
        PopulateRibbonHomeBars(Tab1)
        Dim Tab2 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup2"
        }
        PopulateRibbonInsertBars(Tab2)
        contexttab1.CustomContextRibbonTabs.Add(Tab1)
        contexttab1.CustomContextRibbonTabs.Add(Tab2)
        CustomContextTabs.Add(contexttab1)
        Dim contexttab2 As CustomContextTab = New CustomContextTab() With {
            .TabHeader = "ContextTabGroup2",
            .BackColor = Colors.Green,
            .IsGroupVisible = True
        }
        Dim Tab11 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup11"
        }
        PopulateRibbonHomeBars(Tab11)
        Dim Tab21 As CustomRibbonTab = New CustomRibbonTab() With {
            .TabHeader = "TabGroup21"
        }
        PopulateRibbonInsertBars(Tab21)
        contexttab2.CustomContextRibbonTabs.Add(Tab11)
        contexttab2.CustomContextRibbonTabs.Add(Tab21)
        CustomContextTabs.Add(contexttab2)
    End Sub

    Private Sub PopulateRibbonHomeBars(ByVal Tab As CustomRibbonTab)
        Dim Bar1 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Clipboard"
        }
        PopuplateRibbonNewItems(Bar1)
        Dim Bar2 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Editing"
        }
        PopuplateRibbonEditingItems(Bar2)
        Tab.CustomRibbonBars.Add(Bar1)
        Tab.CustomRibbonBars.Add(Bar2)
    End Sub

    Private Sub PopuplateRibbonNewItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Paste",
            .IsLarge = True,
            .Image = "Paste32.png"
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Cut",
            .Image = "Cut16.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Copy",
            .Image = "Copy16.png"
        }
        Dim Item4 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Format Painter",
            .Image = "FormatPainter16.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
        Bar.CustomRibbonItems.Add(Item4)
    End Sub

    Private Sub PopuplateRibbonEditingItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Hyperlink",
            .IsLarge = True,
            .Image = "hyperlink32.png"
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Replace",
            .IsLarge = True,
            .Image = "replace_32.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Zoom",
            .IsLarge = True,
            .Image = "Zoom_32x32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
    End Sub

    Private Sub PopulateRibbonInsertBars(ByVal Tab As CustomRibbonTab)
        Dim Bar2 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Mail"
        }
        PopuplateRibbonMailItems(Bar2)
        Dim Bar1 As CustomRibbonBar = New CustomRibbonBar() With {
            .BarHeader = "Tables"
        }
        PopuplateRibbonTablesItems(Bar1)
        Tab.CustomRibbonBars.Add(Bar2)
        Tab.CustomRibbonBars.Add(Bar1)
    End Sub

    Private Sub PopuplateRibbonMailItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Attach File",
            .IsLarge = True,
            .Image = "base_paperclip_32.png",
            .IsSplitButton = True
        }
        Dim Item2 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Business card",
            .IsLarge = True,
            .Image = "base_business_contacts.png"
        }
        Dim Item3 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Audio",
            .IsLarge = True,
            .Image = "base_speaker_32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
        Bar.CustomRibbonItems.Add(Item2)
        Bar.CustomRibbonItems.Add(Item3)
    End Sub

    Private Sub PopuplateRibbonTablesItems(ByVal Bar As CustomRibbonBar)
        Dim Item1 As CustomRibbonItem = New CustomRibbonItem() With {
            .ItemHeader = "Tables",
            .IsLarge = True,
            .IsSplitButton = True,
            .Image = "Table_32.png"
        }
        Bar.CustomRibbonItems.Add(Item1)
    End Sub
End Class

{% endhighlight %}

{% endtabs %}

3. Now bind the properties of View model in XAML.

{% tabs %}

{% highlight XAML %}

  <DataTemplate x:Key="Ribbonbutton">
     <syncfusion:RibbonButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}" Visibility="{Binding IsBoolean, Converter={StaticResource visibility}}" LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>
  </DataTemplate>

  <DataTemplate x:Key="Splitbutton">
     <syncfusion:SplitButton Label="{Binding ItemHeader}" SizeForm="{Binding IsLarge, Converter={StaticResource sizeform}}" Visibility="{Binding IsBoolean, Converter={StaticResource visibility}}" LargeIcon="{Binding Image,Converter={StaticResource image}}" SmallIcon="{Binding Image,Converter={StaticResource image}}"/>
   </DataTemplate>
    <syncfusion:Ribbon VerticalAlignment="Top"
                   Name="Ribbon1"     RibbonBarCollapseImage="App.ico"
			       ItemsSource="{Binding CustomRibbonTabs}" ContextGroupSource="{Binding CustomContextTabs}" >
            
            <syncfusion:Ribbon.ItemContainerStyle>
                            <Style TargetType="{x:Type syncfusion:RibbonTab}">
                                <Setter Property="Caption" Value="{Binding TabHeader}"></Setter>
                                <Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}"/>
                                <Setter Property="ItemContainerStyle">
                                    <Setter.Value>
                                        <Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">
                                <Setter Property="Header" Value="{Binding BarHeader}"/>
                                            <Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/>
                                <Setter Property="ItemTemplateSelector" Value="{StaticResource selector}"/>
                              
                            </Style>
                                    </Setter.Value>
                                </Setter>
                            </Style>
            </syncfusion:Ribbon.ItemContainerStyle>

            <syncfusion:Ribbon.ContextGroupContainerStyle>
                <Style TargetType="syncfusion:ContextTabGroup">
                    <Setter Property="Label" Value="{Binding TabHeader}" />
                    <Setter Property="BackColor" Value="{Binding BackColor, Mode=TwoWay}" />
                    <Setter Property="IsGroupVisible" Value="{Binding IsGroupVisible, Mode=TwoWay}" />
                    <Setter Property="ItemsSource" Value="{Binding CustomContextRibbonTabs}" />
                    <Setter Property="ItemContainerStyle">
                        <Setter.Value>
                            <Style TargetType="syncfusion:RibbonTab">
                                <Setter Property="Caption" Value="{Binding TabHeader}" />
                                <Setter Property="ItemsSource" Value="{Binding CustomRibbonBars}" />
                                <Setter Property="ItemContainerStyle">
                                    <Setter.Value>
                                        <Style BasedOn="{StaticResource Office2013RibbonBarStyle}" TargetType="{x:Type syncfusion:RibbonBar}">
                                            <Setter Property="Header" Value="{Binding BarHeader}"/>
                                            <Setter Property="ItemsSource" Value="{Binding CustomRibbonItems}"/>
                                            <Setter Property="ItemTemplateSelector" Value="{StaticResource selector}"/>

                                            <Setter Property="CollapseImage" Value="/Images/FormatPainter16.png" />
                                
                                        </Style>
                                    </Setter.Value>
                                </Setter>
                            </Style>
                        </Setter.Value>
                    </Setter>

                </Style>
            </syncfusion:Ribbon.ContextGroupContainerStyle>
         
        </syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}


4. Add a converter class for binding conversions

{% tabs %}

{% highlight C# %}

 public class BooltoSizeformConverter:IValueConverter
    {
        #region IValueConverter Members

        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
           
            if (value.Equals(true))
            {
                return "Large";
            }
            else
            {
                return "Small";
            }
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new NotImplementedException();
        }

        #endregion
    }

    public class BooltoVisibilityConverter : IValueConverter
    {
        #region IValueConverter Members

        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            
            if (value.Equals(true))
            {
                return Visibility.Visible;
            }
            else
            {
                return Visibility.Collapsed;
            }
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new NotImplementedException();
        }

        #endregion
    }

    public class ItemDataTemplateSelector : DataTemplateSelector
    {
        public override DataTemplate SelectTemplate(object item, DependencyObject container)
        {
            FrameworkElement element = container as FrameworkElement;

            if (element != null && item != null )
            {
                if (item is CustomRibbonItem && (item as CustomRibbonItem).IsSplitButton)
                {
                    return
                        element.FindResource("Splitbutton") as DataTemplate;
                }
                else
                {
                    return element.FindResource("Ribbonbutton") as DataTemplate;
                }
                
            }

            return null;
        }
    }

    public class ImageConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            if (value != null)
            {
                string str = value.ToString();

                return "../Images/" + str;
            }
            else
                return value;
        }

        public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
        {
            throw new System.NotImplementedException();
        }
    }

{% endhighlight %}

{% highlight VB %}

Public Class BooltoSizeformConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value.Equals(True) Then
            Return "Large"
        Else
            Return "Small"
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New NotImplementedException()
    End Function
End Class

Public Class BooltoVisibilityConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value.Equals(True) Then
            Return Visibility.Visible
        Else
            Return Visibility.Collapsed
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New NotImplementedException()
    End Function
End Class

Public Class ItemDataTemplateSelector
    Inherits DataTemplateSelector

    Public Overrides Function SelectTemplate(ByVal item As Object, ByVal container As DependencyObject) As DataTemplate
        Dim element As FrameworkElement = TryCast(container, FrameworkElement)

        If element IsNot Nothing AndAlso item IsNot Nothing Then

            If TypeOf item Is CustomRibbonItem AndAlso (TryCast(item, CustomRibbonItem)).IsSplitButton Then
                Return TryCast(element.FindResource("Splitbutton"), DataTemplate)
            Else
                Return TryCast(element.FindResource("Ribbonbutton"), DataTemplate)
            End If
        End If

        Return Nothing
    End Function
End Class

Public Class ImageConverter
    Inherits IValueConverter

    Public Function Convert(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        If value IsNot Nothing Then
            Dim str As String = value.ToString()
            Return "../Images/" & str
        Else
            Return value
        End If
    End Function

    Public Function ConvertBack(ByVal value As Object, ByVal targetType As Type, ByVal parameter As Object, ByVal culture As System.Globalization.CultureInfo) As Object
        Throw New System.NotImplementedException()
    End Function
End Class


{% endhighlight %}

{% endtabs %}

![RibbonContextTabGroupMVVM](GroupingRibbonTabsusingContextTabGroups_images/RibbonContextTabGroupMVVM.png)

## Detecting selection changes in RibbonTab

The [`SelectionChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html) event notifies when the user attempts to switch tab in the Ribbon control. The [`SelectionChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html) event  receives an argument of the type **CancelEventArgs** that allows us to cancel the switching operation. 

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top" SelectionChanging="Ribbon_SelectionChanging">
    <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
    <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
    <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
    <syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>


{% endhighlight %}
 
{% endtabs %}
 
{% tabs %}

{% highlight C# %}

private void Ribbon_SelectionChanging(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}

{% endhighlight %}

{% highlight VB %}
 
Private Sub Ribbon_SelectionChanging(ByVal sender As Object, ByVal e As System.ComponentModel.CancelEventArgs)
    e.Cancel = True
End Sub

{% endhighlight %}
 
{% endtabs %}

