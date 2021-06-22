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

## Resize based on collapse order

The Ribbon control provides support to resize the RibbonBar's based on the order specified in the `SizeReductionOrder` property in the [`RibbonTab`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonTab.html). The `SizeReductionOrder` property accepts the names of the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) that determines the order in which [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) size is reduced. The Ribbon will begin to resize its elements with the following priority. 

1. **Compressing the RibbonBar specified in the SizeReductionOrder:**

    a)  The Ribbon will initially retrieve the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) corresponding to the first name specified in the `SizeReductionOrder` and resize its elements based on its SizeForm. This [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) will be converted to a dropdown if there are no three or more consecutive Large or Small size form items.

    b)	Once the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) corresponding to the first name specified in the `SizeReductionOrder` is collapsed, the Ribbon will retrieve the next name and its corresponding [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) and begin resizing in the same manner as in the previous step. This process continues until all of the `SizeReductionOrder` property's corresponding RibbonBar's are collapsed into a dropdown.

2. **Compressing the other RibbonBar’s:**

    The remaining RibbonBar's that are not specified in the `SizeReductionOrder` property will be resized according to the Ribbon's default resizing behaviour once the corresponding [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) of the names specified in the `SizeReductionOrder` property are resized and collapsed. To know more about the default resizing behavior, refer [here](https://help.syncfusion.com/wpf/ribbon/dealingwithribbon#resize-ribbon-window).

When the size of the window is increased, the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) will become visible if the spacing between the window border and the [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) is large enough to accommodate its items. These items will then be expanded in the order, starting with the most recently collapsed item and ending with the initially collapsed item.

In the below code snippet, the `SizeReductionOrder` property in the **Home** [`RibbonTab`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonTab.html) contains the name of **Clipboard** and **Paragraph** [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html). So, when resizing the Ribbon, the Clipboard [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html) will be compressed and converted to a dropdown first, followed by the Paragraph [`RibbonBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonBar.html). The remaining RibbonBar's will be collapsed as per the default resizing behaviour once the **Clipboard** and **Paragraph** RibbonBar's are converted to dropdown.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
    x:Class="RibbonSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:interactivity="clr-namespace:System.Windows.Interactivity;assembly=System.Windows.Interactivity"
    xmlns:local="clr-namespace:RibbonSample"
    xmlns:skinManager="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    x:Name="ribbonWindow"
    Title="Untitled 1 - Ribbon Control"
    Width="980" Height="700"
    skinManager:SfSkinManager.VisualStyle="FluentLight"
    FlowDirection="{Binding WindowFlowDirectionProperty}"
    Icon="/Resources/App.ico" IsGlassActive="False"
    Office2010Icon="/Resources/syncfusion.png"
    SnapsToDevicePixels="True" WindowStartupLocation="CenterScreen"
    WindowState="Normal">
    <syncfusion:RibbonWindow.DataContext>
        <local:ViewModel />
    </syncfusion:RibbonWindow.DataContext>
    <syncfusion:RibbonWindow.Resources>
        <syncfusion:ColorToBrushConverter x:Key="ColorToBrushConverter" />
        <syncfusion:RibbonContextMenu
            x:Key="GalleryContextMenu"
            x:Name="contextMenu"
            ItemsSource="{Binding}">
            <syncfusion:RibbonMenuItem
                Command="{Binding ButtonCommand}"
                Header="Apply Style"
                IconBarEnabled="True" />
            <syncfusion:RibbonMenuItem
                Command="{Binding RemoveStyleCommand}"
                Header="Remove from Style Gallery"
                IconBarEnabled="True" />
            <Separator />
            <syncfusion:RibbonMenuItem
                Command="{Binding MinimizeRibbonCommand}"
                Header="Minimize Ribbon"
                IconBarEnabled="True" />
        </syncfusion:RibbonContextMenu>
    </syncfusion:RibbonWindow.Resources>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Grid.Resources>
            <ResourceDictionary>
                <ResourceDictionary.MergedDictionaries>
                    <ResourceDictionary Source="/Resources/PathIcon.xaml"/>
                </ResourceDictionary.MergedDictionaries>
            </ResourceDictionary>
        </Grid.Resources>
        <Grid x:Name="ribbonGrid">
            <syncfusion:Ribbon
                Name="mainRibbon"
                local:ViewModel.Ribbon="{Binding ElementName=mainRibbon}"
                syncfusion:Ribbon.IsAutoSizeFormEnabled="True"
                BackStageCornerImageVisibility="Collapsed"
                BackStageHeader="File"
                EnableMoreCommands="True"
                ShowCustomizeRibbon="True">
                <syncfusion:Ribbon.TabPanelItem>
                    <syncfusion:RibbonButton SizeForm="ExtraSmall" SmallIcon="Resources/Smile16.png" />
                </syncfusion:Ribbon.TabPanelItem>
                <syncfusion:RibbonTab
                    syncfusion:Ribbon.KeyTip="H" SizeReductionOrder="clipboardBar,paragraphBar"
                    Caption="Home"
                    IsChecked="True">
                    <syncfusion:RibbonBar
                        Name="clipboardBar"
                        syncfusion:Ribbon.KeyTip="FN"
                        syncfusion:Ribbon.ShowInMoreCommands="False"
                        Header="Clipboard"
                        IconTemplate="{StaticResource Paste}">
                        <interactivity:Interaction.Triggers>
                            <interactivity:EventTrigger EventName="LauncherClick">
                                <interactivity:InvokeCommandAction    />
                            </interactivity:EventTrigger>
                        </interactivity:Interaction.Triggers>
                        <syncfusion:RibbonButton
                            syncfusion:Ribbon.KeyTip="CP"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Paste"
                            Command="ApplicationCommands.Paste"
                            IconTemplate="{StaticResource Paste}"
                            Label="Paste"
                            SizeForm="Large">
                            <syncfusion:RibbonButton.ToolTip>
                                <syncfusion:ScreenTip Description="Paste (Ctrl+V)">
                                    <TextBlock
                                        Width="130"
                                        HorizontalAlignment="Left"
                                        Foreground="#FF4C4C4C"
                                        Text="Paste the contents of clipboard."
                                        TextWrapping="Wrap" />
                                </syncfusion:ScreenTip>
                            </syncfusion:RibbonButton.ToolTip>
                        </syncfusion:RibbonButton>
                        <syncfusion:RibbonButton
                            x:Name="cut"
                            HorizontalAlignment="Left"
                            syncfusion:Ribbon.KeyTip="CT"
                            Command="ApplicationCommands.Cut"
                            IconTemplate="{StaticResource Cut}"
                            Label="Cut"
                            SizeForm="Small">
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
                            x:Name="copy"
                            HorizontalAlignment="Left"
                            syncfusion:Ribbon.KeyTip="CY"
                            Command="ApplicationCommands.Copy"
                            IconTemplate="{StaticResource Copy}"
                            Label="Copy"
                            SizeForm="Small">
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
                            x:Name="formatPainter"
                            syncfusion:Ribbon.KeyTip="CR"
                              
                            IconTemplate="{StaticResource FormatPainter}"
                            Label="Format Painter"
                            SizeForm="Small">
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
                    <syncfusion:RibbonBar
                        Name="barFont"
                        syncfusion:Ribbon.KeyTip="HF"
                        Header="Font" IconTemplate="{StaticResource FormatBorder}"
                        IsLargeButtonPanel="False"
                        KeyTipOnCollapsed="ZF">
                        <interactivity:Interaction.Triggers>
                            <interactivity:EventTrigger EventName="LauncherClick">
                                <interactivity:InvokeCommandAction    />
                            </interactivity:EventTrigger>
                        </interactivity:Interaction.Triggers>
                        <syncfusion:ButtonPanel SeparatorVisibility="Collapsed">
                            <syncfusion:RibbonComboBox
                                Name="fontFamilyComboBox"
                                Width="110"
                                syncfusion:Ribbon.KeyTip="FF"
                                syncfusion:Ribbon.ShowInMoreCommands="False"
                                DisplayMemberPath="FontFamily"
                                IsEditable="True"
                                ItemsSource="{Binding FontFamilyList}"
                                SelectedIndex="0">
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
                                <interactivity:Interaction.Triggers>
                                    <interactivity:EventTrigger EventName="SelectionChanged">
                                        <interactivity:InvokeCommandAction CommandParameter="{Binding ElementName=fontFamilyComboBox, Path=SelectedIndex}" />
                                    </interactivity:EventTrigger>
                                </interactivity:Interaction.Triggers>
                            </syncfusion:RibbonComboBox>
                            <syncfusion:RibbonComboBox
                                Name="fontSizeComboBox"
                                Width="40"
                                syncfusion:Ribbon.KeyTip="FZ"
                                syncfusion:Ribbon.ShowInMoreCommands="False"
                                DisplayMemberPath="FontSize"
                                IsEditable="True"
                                ItemsSource="{Binding FontSizeList}"
                                SelectedIndex="4">
                                <interactivity:Interaction.Triggers>
                                    <interactivity:EventTrigger EventName="SelectionChanged">
                                        <interactivity:InvokeCommandAction  CommandParameter="{Binding ElementName=fontSizeComboBox, Path=SelectedIndex}" />
                                    </interactivity:EventTrigger>
                                </interactivity:Interaction.Triggers>
                            </syncfusion:RibbonComboBox>
                            <syncfusion:RibbonButton
                                Name="increaseFontSize"
                                syncfusion:Ribbon.KeyTip="IF"
                                Command="EditingCommands.IncreaseFontSize"
                                IconTemplate="{StaticResource IncreaseFontSize}"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="decreaseFontSize"
                                syncfusion:Ribbon.KeyTip="DF"
                                Command="EditingCommands.DecreaseFontSize"
                                IconTemplate="{StaticResource DecreaseFontSize}"
                                SizeForm="ExtraSmall" />
                        </syncfusion:ButtonPanel>
                        <syncfusion:ButtonPanel Height="24">
                            <syncfusion:RibbonButton
                                Name="formatBold"
                                syncfusion:Ribbon.KeyTip="B"
                                Command="EditingCommands.ToggleBold"
                                IconTemplate="{StaticResource Bold}"
                                IsSelected="{Binding IsFormatBoldSelected}"
                                IsToggle="True"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="formatItalic"
                                syncfusion:Ribbon.KeyTip="I"
                                Command="EditingCommands.ToggleItalic"
                                IconTemplate="{StaticResource Italics}"
                                IsSelected="{Binding IsFormatItalicSelected}"
                                IsToggle="True"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="formatUnderLine"
                                syncfusion:Ribbon.KeyTip="U"
                                Command="EditingCommands.ToggleUnderline"
                                IconTemplate="{StaticResource Underline}"
                                IsSelected="{Binding IsFormatUnderLineSelected}"
                                SizeForm="ExtraSmall" />
                        </syncfusion:ButtonPanel>
                        <syncfusion:ButtonPanel Height="24" SeparatorVisibility="Collapsed">
                            <syncfusion:SplitButton
                                x:Name="textHighlight"
                                syncfusion:Ribbon.KeyTip="TH"
                                IconTemplate="{StaticResource TextHighlight}"
                                SizeForm="ExtraSmall">
                                <syncfusion:ColorPickerPalette
                                    x:Name="highlightColorPicker"
                                    BorderThickness="0"
                                    IsExpanded="True"
                                    Color="White" />
                            </syncfusion:SplitButton>
                            <syncfusion:SplitButton
                                x:Name="fontColor"
                                syncfusion:Ribbon.KeyTip="FC"
                                IconTemplate="{StaticResource FontColor}"
                                SizeForm="ExtraSmall">
                                <syncfusion:ColorPickerPalette
                                    x:Name="fontColoPicker"
                                    BorderThickness="0"
                                    IsExpanded="True"
                                    Color="Black" />
                            </syncfusion:SplitButton>
                            <syncfusion:SplitButton
                                Name="formatShading"
                                syncfusion:Ribbon.KeyTip="FS"
                                IconTemplate="{StaticResource Shading}"
                                SizeForm="ExtraSmall">
                                <syncfusion:ColorPickerPalette
                                    x:Name="shadingColorPicker"
                                    Margin="3"
                                    BorderThickness="0"
                                    IsExpanded="True"
                                    Color="White" />
                            </syncfusion:SplitButton>
                            <syncfusion:SplitButton
                                Name="formatBorder"
                                syncfusion:Ribbon.KeyTip="BF"
                                IconTemplate="{StaticResource FormatBorder}"
                                SizeForm="ExtraSmall">
                                <ListBox BorderThickness="0">
                                    <interactivity:Interaction.Triggers>
                                        <interactivity:EventTrigger EventName="SelectionChanged">
                                            <interactivity:InvokeCommandAction    />
                                        </interactivity:EventTrigger>
                                    </interactivity:Interaction.Triggers>
                                    <ListBoxItem Margin="5">Full Border</ListBoxItem>
                                    <ListBoxItem Margin="5">Half Border</ListBoxItem>
                                    <ListBoxItem Margin="5">Inside Border</ListBoxItem>
                                    <ListBoxItem Margin="5">Outside Border</ListBoxItem>
                                </ListBox>
                            </syncfusion:SplitButton>
                        </syncfusion:ButtonPanel>
                    </syncfusion:RibbonBar>
                    <syncfusion:RibbonBar
                        Name="paragraphBar"
                        syncfusion:Ribbon.KeyTip="HP"
                        Header="Paragraph" IconTemplate="{StaticResource AlignJustifyLarge}"
                        IsLargeButtonPanel="False"
                        KeyTipOnCollapsed="ZP">
                        <interactivity:Interaction.Triggers>
                            <interactivity:EventTrigger EventName="LauncherClick">
                                <interactivity:InvokeCommandAction    />
                            </interactivity:EventTrigger>
                        </interactivity:Interaction.Triggers>
                        <syncfusion:ButtonPanel Height="24">
                            <syncfusion:SplitButton
                                Name="formatBullet"
                                syncfusion:Ribbon.KeyTip="FN"
                                Command="EditingCommands.ToggleBullets"
                                IconTemplate="{StaticResource Bullets}"
                                SizeForm="ExtraSmall">
                                <ListBox BorderThickness="0">
                                    <interactivity:Interaction.Triggers>
                                        <interactivity:EventTrigger EventName="SelectionChanged">
                                            <interactivity:InvokeCommandAction    />
                                        </interactivity:EventTrigger>
                                    </interactivity:Interaction.Triggers>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Bullets_Arrow"
                                                Width="40"
                                                Height="40"
                                                HorizontalAlignment="Left"
                                                VerticalAlignment="Top"
                                                Background="Transparent">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L39,0 39,39 0,39 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="9.181,7.2,9.502,8.146"
                                                    Data="M2.6369915,2.600007 L7.8879943,11.789005 7.8822666,11.799983 19.284758,11.799983 z M0,0 L21.316999,11.78101 0.049011266,24.654001 6.7489877,11.811009 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Arrow Bullet" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Bullets_Circle"
                                                Width="40"
                                                Height="40"
                                                HorizontalAlignment="Left"
                                                VerticalAlignment="Top"
                                                Background="Transparent">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L39,0 39,39 0,39 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="14,16,15,11"
                                                    Data="M7.5,0.99999991 C3.9160004,1 1,3.6910096 0.99999994,7 1,10.308991 3.9160004,13 7.5,13 11.084,13 14,10.308991 14,7 14,3.6910096 11.084,1 7.5,0.99999991 z M7.5,0 C11.636002,2.9802322E-08 15,3.1409912 15,7 15,10.859009 11.636002,14 7.5,14 3.3639984,14 0,10.859009 0,7 0,3.1409912 3.3639984,2.9802322E-08 7.5,0 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Circle Bullet" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Bullets_Dot"
                                                Width="40"
                                                Height="40"
                                                HorizontalAlignment="Left"
                                                VerticalAlignment="Top"
                                                Background="Transparent">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L39,0 39,39 0,39 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="14,16,15,11"
                                                    Data="M5.5,0 C8.5370026,0 11,2.4630127 11,5.5 11,8.5369873 8.5370026,11 5.5,11 2.4629974,11 0,8.5369873 0,5.5 0,2.4630127 2.4629974,0 5.5,0 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Dot Bullet" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Bullets_None"
                                                Width="40"
                                                Height="40"
                                                HorizontalAlignment="Left"
                                                VerticalAlignment="Top"
                                                Background="Transparent">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L39,0 39,39 0,39 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="7.449,16.465,7.849,15.607"
                                                    Data="M22.333007,2.7070129 C21.957,2.707013 21.640006,2.8580138 21.380004,3.160992 21.120002,3.4640006 20.954001,3.8559983 20.883002,4.3400065 L23.708008,4.3400065 23.708008,4.1999923 C23.708008,3.7670091 23.594002,3.410015 23.364006,3.1290095 23.135002,2.848004 22.791,2.707013 22.333007,2.7070129 z M9.9689951,2.7069989 C9.4389954,2.7069988 9.0409956,2.9089988 8.7759953,3.3139987 8.5119953,3.7179987 8.3789959,4.2319986 8.3789959,4.8549985 L8.3789959,4.9839984 C8.3789959,5.6179985 8.5119953,6.1329983 8.7759953,6.5309981 9.0409956,6.9279979 9.4419956,7.1269983 9.9799957,7.1269983 10.509995,7.1269983 10.908996,6.926998 11.176995,6.5279983 11.445995,6.1289982 11.579995,5.6139983 11.579995,4.9839984 L11.579995,4.8549985 C11.579995,4.2319986 11.444995,3.7179987 11.174995,3.3139987 10.903996,2.9089988 10.501995,2.7069988 9.9689951,2.7069989 z M16.590996,1.9020022 C17.225996,1.9020023 17.709996,2.0800021 18.046996,2.4390017 18.383996,2.7970013 18.551996,3.3670007 18.551996,4.1529998 L18.551996,7.8209957 17.552996,7.8209957 17.552996,4.1739999 C17.552996,3.6400003 17.451996,3.2660007 17.249996,3.0510012 17.046996,2.8360013 16.729996,2.7290013 16.295996,2.7290014 15.969996,2.7290013 15.688997,2.8060013 15.450997,2.9590012 15.211997,3.113001 15.019997,3.3280007 14.872997,3.6040006 L14.872997,7.8209957 13.874998,7.8209957 13.874998,2.0090022 14.770997,2.0090022 14.840997,2.8790012 14.856997,2.885001 C15.045997,2.5720015 15.287997,2.3310018 15.579997,2.1590019 15.871997,1.9880022 16.207996,1.9020023 16.590996,1.9020022 z M22.333007,1.9010142 C23.121002,1.9010143 23.713005,2.1330086 24.108002,2.5940064 24.504005,3.0570186 24.702004,3.6879992 24.702004,4.4899999 L24.702004,5.1410002 20.851005,5.1410002 C20.865004,5.734017 21.012999,6.2150038 21.294005,6.5799936 21.575004,6.9450139 21.975005,7.1269902 22.494003,7.1269902 22.855003,7.1269902 23.168007,7.0770024 23.432006,6.9769963 23.694008,6.8769907 23.932007,6.7349924 24.144005,6.5530161 L24.535004,7.2129887 C24.324005,7.4209961 24.053001,7.5919861 23.722008,7.7269953 23.391006,7.859991 22.981003,7.9280146 22.494003,7.9280146 21.678001,7.9280146 21.033004,7.6640071 20.561003,7.1359929 20.088004,6.6070017 19.852004,5.9060138 19.852003,5.0329987 L19.852003,4.7909948 C19.852004,3.9459945 20.094,3.2530023 20.579001,2.7129943 21.064002,2.1720101 21.649001,1.9010143 22.333007,1.9010142 z M9.9689951,1.9009991 C10.784995,1.900999 11.423995,2.1739989 11.883995,2.7199987 12.343995,3.2659987 12.572995,3.9779986 12.572995,4.8549985 L12.572995,4.9839984 C12.572995,5.8649982 12.344995,6.5759982 11.885995,7.1169981 11.427995,7.656998 10.791995,7.926998 9.9799957,7.926998 9.1629953,7.926998 8.5249958,7.656998 8.0669956,7.1169981 7.6089954,6.5759982 7.3799953,5.8649982 7.3799953,4.9839984 L7.3799953,4.8549985 C7.3799953,3.9779986 7.6089954,3.2659987 8.0669956,2.7199987 8.5249958,2.1739989 9.1589956,1.900999 9.9689951,1.9009991 z M0,0 L0.99299812,0 4.8769979,6.1550182 4.8939981,6.1550182 4.8939981,0 5.8869982,0 5.8869982,7.8200229 4.8939981,7.8200229 1.0099983,1.6600049 0.99299812,1.6600049 0.99299812,7.8200229 0,7.8200229 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Remove Bullet" />
                                        </StackPanel>
                                    </ListBoxItem>
                                </ListBox>
                            </syncfusion:SplitButton>
                            <syncfusion:SplitButton
                                Name="formatNumbering"
                                syncfusion:Ribbon.KeyTip="FB"
                                Command="EditingCommands.ToggleNumbering"
                                IconTemplate="{StaticResource Numbering}"
                                SizeForm="ExtraSmall">
                                <ListBox BorderThickness="0">
                                    <interactivity:Interaction.Triggers>
                                        <interactivity:EventTrigger EventName="SelectionChanged">
                                            <interactivity:InvokeCommandAction    />
                                        </interactivity:EventTrigger>
                                    </interactivity:Interaction.Triggers>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Numbering_LowLetterBrace"
                                                Width="60"
                                                Height="60"
                                                HorizontalAlignment="Right"
                                                VerticalAlignment="Top">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L75,0 75,75 0,75 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Width="9.369"
                                                    Margin="6.948,11.249,0,14.376"
                                                    HorizontalAlignment="Left"
                                                    Data="M2.8240006,41.163951 C3.5700009,41.163951 4.177001,41.378952 4.6430013,41.807953 5.1100011,42.237955 5.3450012,42.788957 5.3490009,43.46096 L4.318001,43.46096 C4.314001,43.053958 4.174001,42.716957 3.8960007,42.446956 3.6190009,42.177955 3.2610009,42.042954 2.8240006,42.042954 2.1950006,42.042954 1.7490005,42.260955 1.4850001,42.695956 1.2210002,43.131958 1.0900006,43.675961 1.0900006,44.327963 L1.0900006,44.573964 C1.0900006,45.241967 1.2200003,45.790969 1.4820008,46.219971 1.7440004,46.649972 2.1910007,46.864973 2.8240006,46.864973 3.2260008,46.864973 3.5750008,46.747972 3.8700006,46.512972 4.1650009,46.278971 4.314001,45.981969 4.318001,45.622968 L5.3490009,45.622968 C5.3450012,46.200971 5.0950012,46.697972 4.5960011,47.113974 4.098001,47.529976 3.5080009,47.737976 2.8240006,47.737976 1.8940005,47.737976 1.1910005,47.441975 0.71500015,46.849973 0.23800039,46.25897 0,45.499968 0,44.573964 L0,44.327963 C0,43.40596 0.23800039,42.647956 0.71500015,42.053954 1.1910005,41.460952 1.8940005,41.163951 2.8240006,41.163951 z M6.052991,37.999981 C6.7559884,38.399029 7.4089983,39.136028 8.0129974,40.212017 8.6159894,41.288006 8.9179888,42.603985 8.9179888,44.158001 L8.9179888,44.217021 C8.9179888,45.783001 8.6159894,47.102032 8.0129974,48.171978 7.4089983,49.241985 6.7559884,49.977032 6.052991,50.374981 L5.8239892,49.725018 C6.3669839,49.306988 6.8379884,48.632 7.2359951,47.699993 7.6349791,46.769024 7.8339827,45.61198 7.8339827,44.228985 L7.8339827,44.147014 C7.8339827,42.787029 7.6289977,41.639996 7.2189975,40.704021 6.808997,39.769024 6.3440043,39.084026 5.8239892,38.650982 z M2.9069784,23.066991 C2.5279789,23.066991 2.2139792,23.15499 1.9659796,23.330991 1.7179794,23.505991 1.5199795,23.748991 1.3719802,24.056991 L1.3719802,26.839993 C1.5239797,27.152992 1.7239795,27.396993 1.9719794,27.572992 2.219979,27.748993 2.5359788,27.835993 2.9189782,27.835993 3.4849782,27.835993 3.9009777,27.642993 4.1669779,27.255993 4.4319773,26.869992 4.5649772,26.345992 4.5649769,25.685991 L4.5649769,25.562992 C4.5649772,24.812991 4.4299773,24.208991 4.160978,23.75199 3.8909777,23.294991 3.4729781,23.066991 2.9069784,23.066991 z M0.28198004,19.480989 L1.3719802,19.480989 1.3719802,23.042991 1.3889799,23.04899 C1.5849795,22.759991 1.8289795,22.54099 2.1219795,22.38999 2.414979,22.23999 2.7659786,22.16499 3.1759784,22.16499 3.9689777,22.16499 4.5799772,22.47099 5.0069767,23.08399 5.4349765,23.69799 5.6489763,24.523992 5.6489762,25.562992 L5.6489762,25.685991 C5.6489763,26.623992 5.4349765,27.366993 5.0069767,27.915993 4.5799772,28.463993 3.9729776,28.738993 3.1879783,28.738993 2.7619786,28.738993 2.3969791,28.658993 2.0919793,28.498993 1.7879796,28.337993 1.5319796,28.097993 1.3249798,27.777992 L1.2189798,28.621993 0.28198004,28.621993 z M6.5039962,19.000002 C7.2069905,19.399002 7.8599851,20.136002 8.4639802,21.212002 9.0669756,22.288002 9.3689733,23.604002 9.3689728,25.158002 L9.3689728,25.217002 C9.3689733,26.783002 9.0669756,28.102001 8.4639802,29.172002 7.8599851,30.242002 7.2069905,30.977002 6.5039962,31.375001 L6.2749974,30.725002 C6.8179935,30.307002 7.2889898,29.632002 7.6869868,28.700002 8.0859835,27.769002 8.2849817,26.612001 8.284982,25.229002 L8.284982,25.147001 C8.2849817,23.787002 8.0799835,22.640001 7.669987,21.704002 7.25999,20.769001 6.7949937,20.084002 6.2749974,19.651001 z M2.8069894,6.6679878 C2.302989,6.6679878 1.9069889,6.7859879 1.6179886,7.0229893 1.3289886,7.2589912 1.1839881,7.5429935 1.1839886,7.8749962 1.1839881,8.1679993 1.2749882,8.3969994 1.4569883,8.5610008 1.6379886,8.7250023 1.9109888,8.807003 2.273989,8.807003 2.6799893,8.807003 3.0449896,8.7130032 3.3669899,8.526001 3.6889901,8.3379993 3.9219903,8.1079979 4.0669904,7.8339958 L4.0669904,6.6679878 z M2.7489893,3.1639595 C3.4789898,3.1639595 4.0619904,3.3439636 4.4979901,3.7029648 4.932991,4.0629692 5.1509911,4.5899734 5.150991,5.2859764 L5.150991,8.3439999 C5.1509911,8.5710011 5.1629911,8.7870026 5.1859914,8.9940052 5.2099912,9.2020054 5.2529912,9.4110069 5.3149914,9.6210098 L4.1959903,9.6210098 C4.1569904,9.4220085 4.1279904,9.258007 4.1079899,9.1290054 4.0879904,9.0000038 4.0749904,8.866003 4.0669904,8.7250023 3.8399901,9.0220051 3.55899,9.265007 3.2229898,9.4540081 2.8869896,9.6440086 2.5179892,9.7390099 2.1159892,9.7390099 1.4479885,9.7390099 0.94498825,9.5740089 0.60698795,9.2440071 0.26898766,8.9130039 0.099987507,8.4500008 0.099987507,7.8519955 0.099987507,7.2349911 0.34198761,6.757988 0.82698822,6.4219856 1.3109884,6.0859833 1.9829888,5.9179802&#xd;&#xa;2.8419898,5.9179802 L4.0669904,5.9179802 4.0669904,5.2739754 C4.0669904,4.8869743 3.9479903,4.5849724 3.70999,4.368969 3.4709899,4.1519699 3.1309898,4.0429688 2.6899893,4.0429688 2.279989,4.0429688 1.9489889,4.1399689 1.6969886,4.3329697 1.4449887,4.5269699 1.3189883,4.7619743 1.3189888,5.0389748 L0.23498821,5.0389748 C0.23498774,4.550972 0.46698761,4.1169701 0.93198824,3.7359657 1.3969884,3.3549614 2.0029888,3.1639595 2.7489893,3.1639595 z M6.2819852,0 C6.9849864,0.39900208 7.6379876,1.1360016 8.2419887,2.2120018 8.84499,3.288002 9.1469905,4.6040001 9.1469905,6.1580009 L9.1469905,6.217001 C9.1469905,7.7830009 8.84499,9.1020012 8.2419887,10.172001 7.6379876,11.242002 6.9849864,11.977001 6.2819852,12.375002 L6.052985,11.725002 C6.5959857,11.307001 7.0669866,10.632002 7.464987,9.7000008 7.8639882,8.769001 8.0629885,7.6120014 8.0629883,6.229002 L8.0629883,6.1470013 C8.0629885,4.7870026 7.8579881,3.6400032 7.4479872,2.7040024 7.0379865,1.769001 6.5729856,1.0840034 6.052985,0.65100098 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="18,16,7,20"
                                                    Data="M0,37.999999 L51,37.999999 51,39.999999 0,39.999999 z M0.99999994,18.999999 L51,18.999999 51,20.999999 0.99999994,20.999999 z M0.99999994,0 L51,0 51,1.9999992 0.99999994,1.9999992 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Lowercase Braces" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Numbering_Lowletter_Dot"
                                                Width="60"
                                                Height="60"
                                                HorizontalAlignment="Right"
                                                VerticalAlignment="Top">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L75,0 75,75 0,75 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Width="8.28"
                                                    Margin="6.948,14.413,0,17.013"
                                                    HorizontalAlignment="Left"
                                                    Data="M6.7260109,43.302991 L7.8280107,43.302991 7.8280107,44.456992 6.7260109,44.456992 z M2.8240008,37.99999 C3.5700009,37.99999 4.177001,38.214991 4.6430008,38.643993 5.1100011,39.073995 5.3450011,39.624997 5.3490012,40.296999 L4.318001,40.296999 C4.3140008,39.889998 4.174001,39.552996 3.8960011,39.282995 3.6190009,39.013994 3.2610006,38.878994 2.8240008,38.878994 2.1950006,38.878994 1.7490005,39.096994 1.4850001,39.531996 1.2210002,39.967998 1.0900002,40.512 1.0900006,41.164003 L1.0900006,41.410003 C1.0900002,42.078006 1.2200003,42.627008 1.4819999,43.05601 1.7440004,43.486012 2.1910005,43.701012 2.8240008,43.701012 3.2260008,43.701012 3.5750008,43.584012 3.8700008,43.349011 4.1650009,43.11501 4.3140008,42.818009 4.318001,42.459008 L5.3490012,42.459008 C5.3450011,43.03701 5.0950011,43.534012 4.5960011,43.950013 4.098001,44.366015 3.5080009,44.574016 2.8240008,44.574016 1.8940005,44.574016 1.1910005,44.278015 0.71499968,43.686012 0.23800039,43.09501 0,42.336007 0,41.410003 L0,41.164003 C0,40.241999 0.23800039,39.483996 0.71499968,38.889994 1.1910005,38.296991 1.8940005,37.99999 2.8240008,37.99999 z M7.1780095,24.303017 L8.2799587,24.303017 8.2799587,25.457026 7.1780095,25.457026 z M2.9070091,19.90303 C2.5280094,19.90303 2.2140098,19.99103 1.9660091,20.16703 1.7180099,20.34203 1.52001,20.58503 1.3720102,20.89303 L1.3720102,23.676031 C1.5240102,23.989033 1.72401,24.233032 1.9720106,24.409033 2.2200098,24.585032 2.5360093,24.672031 2.9190087,24.672031 3.4850085,24.672031 3.9010081,24.479033 4.1670079,24.092031 4.4320078,23.706032 4.5650077,23.182032 4.5650079,22.522032 L4.5650079,22.399031 C4.5650077,21.649031 4.4300077,21.045031 4.1610081,20.58803 3.8910081,20.131031 3.4730086,19.90303 2.9070091,19.90303 z M0.28201103,16.317028 L1.3720102,16.317028 1.3720102,19.87903 1.38901,19.885031 C1.5850101,19.596029 1.82901,19.377029 2.1220098,19.22603 2.4150095,19.076029 2.7660091,19.00103 3.1760087,19.00103 3.9690082,19.00103 4.5800076,19.30703 5.0070069,19.920031 5.435007,20.534031 5.6490068,21.360031 5.6490072,22.399031 L5.6490072,22.522032 C5.6490068,23.460032 5.435007,24.203032 5.0070069,24.752033 4.5800076,25.300032 3.9730082,25.575033 3.188009,25.575033 2.7620091,25.575033 2.3970094,25.495033 2.0920095,25.335033 1.7880101,25.174032 1.5320101,24.934032 1.3250098,24.614033 L1.2190108,25.458033 0.28201103,25.458033 z M6.9549709,5.3030167 L8.0569813,5.3030167 8.0569813,6.4570236 6.9549709,6.4570236 z M2.8069746,3.5040283 C2.3029714,3.5040283 1.9069686,3.6220284 1.6179676,3.8590279 1.3289652,4.0950317 1.1839643,4.3790321 1.1839643,4.7110367 1.1839643,5.0040398 1.2749648,5.2330399 1.4569664,5.3970413 1.6379671,5.5610428 1.9109688,5.6430435 2.2739706,5.6430435 2.6799741,5.6430435 3.0449762,5.5490417 3.3669782,5.3620415 3.6889806,5.1740379 3.921982,4.9440384 4.0669835,4.6700363 L4.0669835,3.5040283 z M2.7489743,0 C3.4789791,0 4.0619829,0.18000031 4.4979858,0.53900528 4.9329886,0.89900589 5.1509901,1.4260101 5.1509905,2.1220169 L5.1509905,5.1800385 C5.1509901,5.4070396 5.1629902,5.6230431 5.1859901,5.8300438 5.2099905,6.038044 5.2529907,6.2470474 5.3149912,6.4570503 L4.1959839,6.4570503 C4.1569836,6.258049 4.1279833,6.0940475 4.1079834,5.9650459 4.0879831,5.8360443 4.0749831,5.7020416 4.0669835,5.5610428 3.8399816,5.8580437 3.5589797,6.1010475 3.2229779,6.2900467 2.8869753,6.4800491 2.5179729,6.5750504 2.1159701,6.5750504 1.4479656,6.5750504 0.9449625,6.4100494 0.6069603,6.0800476 0.26895809,5.7490425 0.099956989,5.2860413 0.099956512,4.6880341 0.099956989,4.0710297 0.34195852,3.5940285 0.82696152,3.2580261 1.3109651,2.9220238 1.9829693,2.7540207&#xd;&#xa;2.841975,2.7540207 L4.0669835,2.7540207 4.0669835,2.1100159 C4.066983,1.7230148 3.9479823,1.4210129 3.7099807,1.2050095 3.470979,0.98800659 3.1309769,0.87900543 2.6899738,0.87900543 2.2799711,0.87900543 1.9489689,0.97600937 1.6969681,1.1690102 1.4449658,1.3630104 1.318965,1.598011 1.3189645,1.8750153 L0.23495817,1.8750153 C0.2349577,1.3870125 0.46695948,0.95300674 0.93196249,0.57200623 1.3969655,0.19100189 2.0029693,0 2.7489743,0 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="17,16,6,20"
                                                    Data="M0,38 L53,38 53,40 0,40 z M1,19 L53,19 53,21 1,21 z M1,0 L53,0 53,2 1,2 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Lowercase Dot" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Numbering_Dot"
                                                Width="60"
                                                Height="60"
                                                HorizontalAlignment="Left"
                                                VerticalAlignment="Top">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L75,0 75,75 0,75 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Width="8.244"
                                                    Margin="6.925,12.339,0,17.007"
                                                    HorizontalAlignment="Left"
                                                    Data="M7.1420118,45.376981 L8.2440114,45.376981 8.2440114,46.530981 7.1420118,46.530981 z M2.7070026,37.877029 C3.5110023,37.877029 4.1420021,38.083028 4.5990024,38.495026 5.0560019,38.907024 5.2850019,39.508022 5.285002,40.297019 5.2850019,40.660017 5.1780019,41.014015 4.963002,41.357013 4.7480021,41.701012 4.4220021,41.967011 3.9840024,42.15401 4.5110021,42.32201 4.883002,42.584008 5.0970023,42.939007 5.3120018,43.295005 5.4200019,43.701003 5.420002,44.158001 5.4200019,44.950998 5.1700019,45.564995 4.6700022,46.000993 4.1700022,46.436991 3.5170023,46.65399&#xd;&#xa;2.7130027,46.65399 1.9240026,46.65399 1.275003,46.445991 0.76700258,46.029993 0.26000309,45.613995 0.0060033798,45.028998 0.0060033798,44.275001 L1.0950031,44.275001 C1.0950031,44.739999 1.2380028,45.106997 1.5230026,45.376996 1.8080029,45.645995 2.2050028,45.780994 2.7130027,45.780994 3.2320025,45.780994 3.6330023,45.648995 3.9140022,45.385996 4.1950021,45.121997 4.3360021,44.720999 4.3360023,44.182001 4.3360021,43.639004 4.2070022,43.242005 3.949002,42.992007 3.6910024,42.742008 3.2810025,42.617008 2.7190032,42.617008 L1.7400026,42.617008 1.7400026,41.750012 2.7190032,41.750012 C3.2580025,41.750012 3.6390023,41.621012 3.8640022,41.363014 4.0890021,41.105015 4.2010021,40.742016 4.2010024,40.273019 4.2010021,39.77002 4.0780022,39.391022 3.8320022,39.137024 3.5860023,38.883025 3.2110023,38.756025 2.7070026,38.756025 2.2340026,38.756025 1.8590026,38.889025 1.5820031,39.154024 1.3040028,39.420022 1.1660032,39.779021 1.1660028,40.232018 L0.082003593,40.232018 C0.082003117,39.557022 0.32200336,38.995024 0.80300379,38.548026 1.2830029,38.101028 1.9180026,37.877029 2.7070026,37.877029 z M7.1420013,26.377007 L8.2439969,26.377007 8.2439969,27.531015 7.1420013,27.531015 z M2.8469973,18.876986 C3.6209977,18.876986 4.2309973,19.094986 4.6789968,19.532986 5.1259966,19.969986 5.3489965,20.542986 5.3489965,21.249987 5.3489965,21.721987 5.2129966,22.185987 4.9389961,22.640989 4.665997,23.095989 4.2729971,23.60499 3.761997,24.16799 L1.4709992,26.657991 5.6599964,26.657991 5.6599964,27.530993 0.16400003,27.530993 0.16400003,26.762993 2.9589972,23.651989 C3.4739978,23.081989 3.8199975,22.633989 3.9959974,22.306988 4.1719973,21.980988 4.2599974,21.641987 4.2599976,21.290987 4.2599974,20.844986 4.1339974,20.477987 3.8819973,20.188986 3.6299977,19.899986 3.2849979,19.755985 2.8469973,19.755985 2.2379985,19.755985 1.7919989,19.905987 1.5089989,20.206985 1.2249994,20.507986 1.0839992,20.940987 1.0839996,21.507988 L0,21.507988 C0,20.745987 0.24799967,20.116985 0.74399948,19.620985 1.2399993,19.124985 1.9409986,18.876986 2.8469973,18.876986 z M7.142002,7.3770065 L8.2439969,7.3770065 8.2439969,8.5310135 7.142002,8.5310135 z M3.539005,0 L3.539005,8.5309944 2.4550076,8.5309944 2.4550076,1.2419968 0.71501112,1.2889977 0.71501112,0.59199905 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="18,16,6,20"
                                                    Data="M0,38 L52,38 52,40 0,40 z M0,19 L52,19 52,21 0,21 z M0,0 L52,0 52,2 0,2 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Number Dot" />
                                        </StackPanel>
                                    </ListBoxItem>
                                    <ListBoxItem>
                                        <StackPanel Orientation="Horizontal">
                                            <Grid
                                                x:Name="Numbering_Upletter"
                                                Width="60"
                                                Height="60"
                                                HorizontalAlignment="Right"
                                                VerticalAlignment="Top">
                                                <Path
                                                    Margin="0.5"
                                                    Data="M0,0 L75,0 75,75 0,75 z"
                                                    Fill="Transparent"
                                                    Stretch="Fill" />
                                                <Path
                                                    Width="9.756"
                                                    Margin="5.608,12.339,0,17.007"
                                                    HorizontalAlignment="Left"
                                                    Data="M8.396025,45.377015 L9.4980357,45.377015 9.4980357,46.531025 8.396025,46.531025 z M3.798023,37.877038 C4.7550271,37.877038 5.4960306,38.124035 6.0210326,38.618035 6.547035,39.112034 6.856036,39.812031 6.9500363,40.719025 L5.8660315,40.719025 C5.7680314,40.070027 5.5600308,39.581032 5.2420295,39.25103 4.9240282,38.921032 4.442026,38.756035 3.798023,38.756035 3.1260205,38.756035 2.5960184,39.015034 2.2070163,39.532033 1.818015,40.05003 1.6240142,40.707024 1.6240142,41.504021 L1.6240142,43.021016 C1.6240142,43.826012 1.818015,44.487008 2.2070163,45.005005 2.5960184,45.522004 3.1260205,45.781003 3.798023,45.781003 4.4460261,45.781003 4.9290279,45.621003 5.2450293,45.301007 5.5610307,44.980008 5.7680314,44.49001 5.8660315,43.830014 L6.9500363,43.830014 C6.856036,44.689007 6.5430348,45.375004 6.0100325,45.887002 5.4760302,46.397999 4.7390273,46.654 3.798023,46.654 2.8130191,46.654 2.024016,46.318001 1.4300135,45.646004 0.83701092,44.975007 0.54000967,44.10001 0.54000955,43.021016 L0.54000955,41.516022 C0.54000967,40.441025 0.83701092,39.566029 1.4300135,38.891034 2.024016,38.215035 2.8130191,37.877038 3.798023,37.877038 z M8.3550103,26.377017 L9.4570211,26.377017 9.4570211,27.531024 8.3550103,27.531024 z M1.9220321,23.517018 L1.9220321,26.658001 3.9550276,26.658001 C4.506027,26.658001 4.9310263,26.528002 5.2300256,26.268004 5.5280254,26.008006 5.6780251,25.632006 5.6780251,25.140009 5.6780251,24.628012 5.5520251,24.230013 5.3000258,23.945015 5.0480259,23.660018 4.6540268,23.517018 4.1190279,23.517018 z M1.9220321,19.878037 L1.9220321,22.644022 3.8670285,22.644022 C4.3170274,22.632021 4.6730269,22.510024 4.9370263,22.278023 5.2000259,22.045025 5.3320258,21.712027 5.3320258,21.279028 5.3320258,20.802031 5.185026,20.450034 4.8900259,20.221034 4.5950268,19.993035 4.1560276,19.878037 3.5740295,19.878037 z M0.83803361,18.999041 L3.5740295,18.999041 C4.4810274,18.999041 5.1810258,19.18804 5.6750253,19.565037 6.1690238,19.942036 6.4160235,20.521033 6.4160235,21.302029 6.4160235,21.693026 6.298024,22.037026 6.0620239,22.333024 5.8250249,22.630023 5.514025,22.849021 5.1270254,22.990021 L5.1270254,23.00702 C5.639025,23.11302 6.0390242,23.360018 6.3280237,23.748017 6.6170233,24.137015 6.7620228,24.597012 6.7620228,25.12801 6.7620228,25.921006 6.5140231,26.520003 6.0180243,26.924 5.5220254,27.328999 4.8340266,27.530997 3.9550276,27.530997 L0.83803361,27.530997 z M8.6540301,7.3770161 L9.7560094,7.3770161 9.7560094,8.5310245 8.6540301,8.5310245 z M3.7560075,1.3419791 L2.2680033,5.3849449 5.2210024,5.3849449 z M3.292996,0 L4.2309831,0 7.471,8.5309997 6.3639763,8.5309997 5.537988,6.2579918 1.9459817,6.2579918 1.1080008,8.5309997 0,8.5309997 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                                <Path
                                                    Margin="18,16,7,20"
                                                    Data="M1.9999999,38 L51,38 51,40 1.9999999,40 z M1,19 L51,19 51,21 1,21 z M0,0 L51,0 51,2 0,2 z"
                                                    Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}"
                                                    Stretch="Fill" />
                                            </Grid>
                                            <TextBlock
                                                Margin="5"
                                                VerticalAlignment="Center"
                                                Text="Uppercase Dot" />
                                        </StackPanel>
                                    </ListBoxItem>
                                </ListBox>
                            </syncfusion:SplitButton>
                            <syncfusion:SplitButton
                                Name="formatLineSpacing"
                                syncfusion:Ribbon.KeyTip="FA"
                                IconTemplate="{StaticResource LineSpacing}"
                                SizeForm="ExtraSmall">
                                <ListBox BorderThickness="0">
                                    <interactivity:Interaction.Triggers>
                                        <interactivity:EventTrigger EventName="SelectionChanged">
                                            <interactivity:InvokeCommandAction    />
                                        </interactivity:EventTrigger>
                                    </interactivity:Interaction.Triggers>
                                    <ListBoxItem Margin="5">1</ListBoxItem>
                                    <ListBoxItem Margin="5">1.15</ListBoxItem>
                                    <ListBoxItem Margin="5">1.5</ListBoxItem>
                                    <ListBoxItem Margin="5">2</ListBoxItem>
                                    <ListBoxItem Margin="5">2.5</ListBoxItem>
                                    <ListBoxItem Margin="5">3</ListBoxItem>
                                </ListBox>
                            </syncfusion:SplitButton>
                        </syncfusion:ButtonPanel>
                        <syncfusion:ButtonPanel Height="24">
                            <syncfusion:RibbonButton
                                Name="formatLeftAlign"
                                syncfusion:Ribbon.KeyTip="LA"
                                Command="EditingCommands.AlignLeft"
                                IconTemplate="{StaticResource AlignLeft}"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="formatCenterAlign"
                                syncfusion:Ribbon.KeyTip="CA"
                                Command="EditingCommands.AlignCenter"
                                IconTemplate="{StaticResource AlignCenter}"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="formatRightAlign"
                                syncfusion:Ribbon.KeyTip="RA"
                                Command="EditingCommands.AlignRight"
                                IconTemplate="{StaticResource AlignRight}"
                                SizeForm="ExtraSmall" />
                            <syncfusion:RibbonButton
                                Name="formatJustify"
                                syncfusion:Ribbon.KeyTip="JA"
                                Command="EditingCommands.AlignJustify"
                                IconTemplate="{StaticResource AlignJustify}"
                                SizeForm="ExtraSmall" />
                        </syncfusion:ButtonPanel>
                    </syncfusion:RibbonBar>
                    <syncfusion:RibbonBar Header="Styles" IconTemplate="{StaticResource IncreaseFontSize}">
                        <interactivity:Interaction.Triggers>
                            <interactivity:EventTrigger EventName="LauncherClick">
                                <interactivity:InvokeCommandAction    />
                            </interactivity:EventTrigger>
                        </interactivity:Interaction.Triggers>
                        <syncfusion:RibbonGallery
                            x:Name="gallery"
                            Width="350"
                            Height="67"
                            ContextMenu="{DynamicResource GalleryContextMenu}"
                            IconTemplate="{StaticResource Styling}"
                            ItemHeight="60"
                            ItemWidth="65"
                            Label="Styles"
                            MenuIconBarEnabled="True"
                            SelectedItem="{Binding RibbonGallerySelectedItem}"
                            SizeForm="Large">
                            <interactivity:Interaction.Triggers>
                                <interactivity:EventTrigger EventName="SelectedItemChanged">
                                    <interactivity:InvokeCommandAction    />
                                </interactivity:EventTrigger>
                            </interactivity:Interaction.Triggers>
                            <syncfusion:RibbonGalleryItem
                                x:Name="firstItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemOneCommand}"
                                Tag="firstItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,11,0,0"
                                        Text="Normal"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="secondItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemTwoCommand}"
                                Tag="secondItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,11,0,0"
                                        Text="No Spa.."
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="thirdItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemThreeCommand}"
                                Tag="thirdItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,5,0,0"
                                        FontSize="18"
                                        Foreground="DarkBlue"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,6,0,0"
                                        Text="Heading 1"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="fourthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemFourCommand}"
                                Tag="fourthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,6,0,0"
                                        FontSize="16"
                                        Foreground="DarkBlue"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,8,0,0"
                                        Text="Heading 2"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="fifthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemFiveCommand}"
                                Tag="fifthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,7,0,0"
                                        FontSize="15"
                                        Foreground="DarkBlue"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Text="Heading 3"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="sixthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemSixCommand}"
                                Tag="sixthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,7,0,0"
                                        FontSize="14"
                                        Foreground="DarkBlue"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Text="Heading 4"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="seventhItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemSevenCommand}"
                                Tag="seventhItem">
                                <StackPanel>
                                    <TextBlock
                                        FontSize="24"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,5,0,0"
                                        Text="Title"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="eighthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemEightCommand}"
                                Tag="eighthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,7,0,0"
                                        FontStyle="Italic"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,13,0,0"
                                        Text="Emphasis"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="ninthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemNineCommand}"
                                Tag="ninthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        FontWeight="Bold"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,10,0,0"
                                        Text="Strong"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="tenthItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemTenCommand}"
                                Tag="tenthItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Text="AaBbCc"
                                        TextAlignment="Center"
                                        TextDecorations="Underline" />
                                    <TextBlock
                                        Margin="0,10,0,0"
                                        Text="Underline"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="eleventhItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemElevenCommand}"
                                Tag="eleventhItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        Foreground="Red"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,10,0,0"
                                        Text="Important"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="italicItem"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemTwelveCommand}"
                                Tag="italicItem">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        FontStyle="Italic"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,10,0,0"
                                        Text="Italic"
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGalleryItem
                                x:Name="superString"
                                Margin="2"
                                CheckOnClick="True"
                                Command="{Binding GalleryItemThirteenCommand}"
                                Tag="superString">
                                <StackPanel>
                                    <TextBlock
                                        Margin="0,9,0,0"
                                        FontWeight="ExtraBold"
                                        Text="AaBbCc"
                                        TextAlignment="Center" />
                                    <TextBlock
                                        Margin="0,10,0,0"
                                        Text="Super Str.."
                                        TextAlignment="Center" />
                                </StackPanel>
                            </syncfusion:RibbonGalleryItem>
                            <syncfusion:RibbonGallery.MenuItems>
                                <syncfusion:RibbonButton IconTemplate="{StaticResource IncreaseFontSize}" Label="Create a style" />
                                <syncfusion:RibbonButton
                                    IconTemplate="{StaticResource ClearFormatting}"
                                    Label="Clear Formatting" />
                            </syncfusion:RibbonGallery.MenuItems>
                        </syncfusion:RibbonGallery>
                    </syncfusion:RibbonBar>
                </syncfusion:RibbonTab>
                <syncfusion:RibbonTab
                            syncfusion:Ribbon.KeyTip="I"
                            Caption="Insert"
                            IsChecked="False">
                </syncfusion:RibbonTab>
                <syncfusion:RibbonTab
                            syncfusion:Ribbon.KeyTip="D"
                            Caption="Design"
                            IsChecked="False">
                </syncfusion:RibbonTab>
                <syncfusion:Ribbon.BackStage>
                    <syncfusion:Backstage Name="ribbonBackStage">
                        <syncfusion:BackStageCommandButton
                            syncfusion:Ribbon.ShowInMoreCommands="False"
                            Command="{Binding ButtonCommand}"
                            Header="Save" />
                        <syncfusion:BackStageCommandButton
                            syncfusion:Ribbon.ShowInMoreCommands="False"
                            Command="{Binding SaveAsCommand}"
                            Header="Save As" />
                        <syncfusion:BackStageCommandButton
                            syncfusion:Ribbon.ShowInMoreCommands="False"
                            Command="{Binding OpenCommand}"
                            Header="Open" />
                        <syncfusion:BackStageCommandButton
                            syncfusion:Ribbon.ShowInMoreCommands="False"
                            Command="{Binding CloseCommand}"
                            Header="Close" />
                        <syncfusion:BackStageCommandButton
                            syncfusion:Ribbon.ShowInMoreCommands="False"
                            Command="{Binding BackStageExitCommand}"
                            Header="Exit" />
                    </syncfusion:Backstage>
                </syncfusion:Ribbon.BackStage>
                <syncfusion:Ribbon.QuickAccessToolBar>
                    <syncfusion:QuickAccessToolBar>
                        <syncfusion:QuickAccessToolBar.QATMenuItems>
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Save" Label="Save" />
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Quick Print" Label="Quick Print" />
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Print Preview" Label="Print Preview" />
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Undo" Label="Undo" />
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Redo" Label="Redo" />
                            <syncfusion:RibbonButton syncfusion:RibbonCommandManager.SynchronizedItem="Paste" Label="Paste" />
                        </syncfusion:QuickAccessToolBar.QATMenuItems>
                        <syncfusion:RibbonButton
                            Width="24"
                            Height="24"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Undo"
                            Command="ApplicationCommands.Undo"
                            IconTemplate="{StaticResource Undo}"
                            Label="Undo"
                            SizeForm="ExtraSmall"
                            ToolTip="Undo"/>
                        <syncfusion:RibbonButton
                            Width="24"
                            Height="24"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Redo"
                            Command="ApplicationCommands.Redo"
                            IconTemplate="{StaticResource Redo}"
                            Label="Redo"
                            SizeForm="ExtraSmall"
                            ToolTip="Redo"/>
                        <syncfusion:RibbonButton
                            Width="24"
                            Height="24"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Save"
                            Command="{Binding ButtonCommand}"
                            IconTemplate="{StaticResource Save}"
                            Label="Save"
                            SizeForm="ExtraSmall"/>
                        <syncfusion:RibbonButton
                            Width="24"
                            Height="24"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Quick Print"
                            IconTemplate="{StaticResource QuickPrint}"
                            Label="QuickPrint"
                            SizeForm="ExtraSmall"/>
                        <syncfusion:RibbonButton
                            Width="24"
                            Height="24"
                            syncfusion:RibbonCommandManager.SynchronizedItem="Paste"
                            IconTemplate="{StaticResource Paste}"
                            Label="Paste"
                            SizeForm="ExtraSmall"
                            ToolTip="Paste"/>
                    </syncfusion:QuickAccessToolBar>
                </syncfusion:Ribbon.QuickAccessToolBar>
            </syncfusion:Ribbon>
        </Grid>
        <ScrollViewer
            x:Name="scrollViewer"
            Grid.Row="1"
            Grid.ColumnSpan="2"
            VerticalScrollBarVisibility="Auto">
            <Grid>
                <RichTextBox
                    Name="editor"
                    Margin="100,10"
                    Padding="50"
                    local:ViewModel.RichTextBox="richTextBoxText"
                    AcceptsTab="True"
                    Background="{Binding ElementName=shadingColorPicker, Path=Color, Mode=OneWay, Converter={StaticResource ColorToBrushConverter}}"
                    ContextMenu="{x:Null}"
                    FontSize="14"
                    Foreground="{Binding ElementName=fontColoPicker, Path=Color, Mode=OneWay, Converter={StaticResource ColorToBrushConverter}}"
                    SelectionBrush="{Binding ElementName=highlightColorPicker, Path=Color, Mode=OneWay, Converter={StaticResource ColorToBrushConverter}}">
                    <interactivity:Interaction.Triggers>
                        <interactivity:EventTrigger EventName="SelectionChanged">
                            <interactivity:InvokeCommandAction Command="{Binding Path=RichTextBoxSelectionChangedCommand}" />
                        </interactivity:EventTrigger>
                        <interactivity:EventTrigger EventName="PreviewMouseLeftButtonUp">
                            <interactivity:InvokeCommandAction Command="{Binding Path=RichTextBoxPreviewMouseLeftButtonUpCommand}" />
                        </interactivity:EventTrigger>
                    </interactivity:Interaction.Triggers>
                </RichTextBox>
            </Grid>
        </ScrollViewer>
    </Grid>
</syncfusion:RibbonWindow>


{% endhighlight %}

{% endtabs %}

![WPF Ribbon Resize based on collapse order](RibbonResizeWindow-images/wpf-ribbon-resize-based-on-collapse-order.gif)

N> View sample in GitHub.

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

