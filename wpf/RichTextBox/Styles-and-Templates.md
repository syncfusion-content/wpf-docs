---
title: Styles and Templates in WPF RichTextBox control | Syncfusion
description: Learn here all about Styles and Templates support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
 documentation: ug
keywords: styles-and-templates, custom-style
---
# Styles and Templates in WPF RichTextBox (SfRichTextBoxAdv)

This section describes the styles and templates for the SfRichTextBoxAdv control. The Template defines the structure of the SfRichTextBoxAdv control and the Style defines its visual appearance. You can modify the default Control template to define a unique appearance for the control.
The following XAML shows the default style and template for the SfRichTextBoxAdv control.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdvResourceWrapper x:Key="SfRichTextBoxAdvResourceWrapper"/>
<SolidColorBrush x:Key="RichTextBoxAdvBackgroundBrush" Color="#000000"/>
<SolidColorBrush x:Key="TextSelectionBrush" Color="#FF808080"/>

<SolidColorBrush x:Key="ContextMenuForegroundBrush" Color="#333333"/>
<SolidColorBrush x:Key="ContextMenuBorderBrush" Color="#D7D7D7"/>
<SolidColorBrush x:Key="ContextMenuBackgroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="ContextMenuMouseOverBackgroundBrush" Color="#D5DDEB"/>

<SolidColorBrush x:Key="MiniToolBarButtonMouseOverBrush" Color="#CAD5E5"/>
<SolidColorBrush x:Key="MiniToolBarButtonSelectedBrush" Color="#AABBD6"/>
<SolidColorBrush x:Key="MiniToolBarBorderBrush" Color="LightGray"/>
<SolidColorBrush x:Key="MiniToolBarBackgroundBrush" Color="#FFFFFF"/>

<SolidColorBrush x:Key="PaneBackgroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="SearchResultItemBackgroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="SearchResultItemForegroundBrush" Color="#333333"/>
<SolidColorBrush x:Key="SearchResultItemSelectedBorderBrush" Color="#959595"/>
<SolidColorBrush x:Key="SearchResultItemMouseOverBorderBrush" Color="#959595"/>
<SolidColorBrush x:Key="SearchResultItemSeparatorForegroundBrush" Color="#666666"/>

<SolidColorBrush x:Key="SuggestionItemSelectedBrush" Color="#FFCBCFE5"/>
<SolidColorBrush x:Key="SuggestionItemMouseOverBrush" Color="#FFD5E1F2"/>

<SolidColorBrush x:Key="DialogHeaderForegroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="DialogHeaderBackgroundBrush" Color="#0071BC"/>
<SolidColorBrush x:Key="DialogBorderBrush" Color="#8E8E8E"/>
<SolidColorBrush x:Key="DialogBackgroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="HeaderLabelForegroundBrush" Color="#0071BC"/>
<SolidColorBrush x:Key="TextBoxForegroundBrush" Color="#333333"/>
<SolidColorBrush x:Key="TextBoxLightForegroundBrush" Color="#666666"/>
<SolidColorBrush x:Key="TextBoxBackgroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="TextBoxBorderBrush" Color="#A5A5A5"/>
<SolidColorBrush x:Key="ButtonForegroundBrush" Color="#333333"/>
<SolidColorBrush x:Key="ButtonBackgroundBrush" Color="#F7F7F7"/>
<SolidColorBrush x:Key="ButtonBorderBrush" Color="#606060"/>
<SolidColorBrush x:Key="ButtonMouseOverBackgroundBrush" Color="#E5F0FC"/>
<SolidColorBrush x:Key="ButtonMouseOverForegroundBrush" Color="#6BA5C6" />
<SolidColorBrush x:Key="ButtonMouseOverBorderBrush" Color="#569DE5"/>
<SolidColorBrush x:Key="ButtonPressedForegroundBrush" Color="#FFFFFF"/>
<SolidColorBrush x:Key="ButtonPressedBackgroundBrush" Color="#0071BC"/>
<SolidColorBrush x:Key="ButtonPressedBorderBrush" Color="#0071BC"/>
<SolidColorBrush x:Key="ButtonDisabledForegroundBrush" Color="#A5A5A5"/>
<SolidColorBrush x:Key="ButtonDisabledBorderBrush" Color="#A5A5A5"/>
<SolidColorBrush x:Key="ButtonDisabledBackgroundBrush" Color="#FFFFFF"/>

<ContextMenu x:Key="ContextMenuStyle">
    <ContextMenu.Resources>
        <Style TargetType="MenuItem">
            <Setter Property="Height" Value="26" />
            <Setter Property="FontFamily" Value="Segoe UI"/>
            <Setter Property="FontSize" Value="12"/>
            <Setter Property="SnapsToDevicePixels" Value="True"/>
            <Setter Property="Foreground" Value="{StaticResource ContextMenuForegroundBrush}"/>
            <Style.Resources>
                <Style TargetType="Image">
                    <Setter Property="Height" Value="16" />
                    <Setter Property="Width" Value="16" />
                </Style>
            </Style.Resources>
        </Style>
        <Style TargetType="{x:Type ContextMenu}">
            <Setter Property="OverridesDefaultStyle" Value="True"/>
            <Setter Property="SnapsToDevicePixels" Value="True"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="{x:Type ContextMenu}">
                        <Border Margin="10,10,10,10" Background="{StaticResource ContextMenuBackgroundBrush}" BorderThickness="1" BorderBrush="{StaticResource ContextMenuBorderBrush}">
                            <StackPanel Orientation="Vertical" IsItemsHost="True" Margin="1,1,1,1"/>
                            <Border.Effect>
                                <DropShadowEffect Color="Black" BlurRadius="7" Direction="315"  Opacity="0.5" ShadowDepth="2"/>
                            </Border.Effect>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
        <ControlTemplate x:Key="{x:Static MenuItem.SubmenuHeaderTemplateKey}" TargetType="MenuItem">
            <Border x:Name="Border" Background="{StaticResource ContextMenuBackgroundBrush}">
                <Grid>
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="30"/>
                        <ColumnDefinition Width="*" />
                        <ColumnDefinition Width="30"/>
                    </Grid.ColumnDefinitions>
                    <ContentPresenter x:Name="Icon" Margin="0" VerticalAlignment="Center" HorizontalAlignment="Center" ContentSource="Icon" SnapsToDevicePixels="True"/>
                    <ContentPresenter x:Name="HeaderHost" Grid.Column="1" ContentSource="Header" VerticalAlignment="Center" HorizontalAlignment="Stretch" Margin="4,0,0,0" SnapsToDevicePixels="True"/>
                    <Path Grid.Column="3" HorizontalAlignment="Right" VerticalAlignment="Center" Data="M 0 0 L 0 7 L 4 3.5 Z" Width="12" Height="12" Margin="0 6 0 0" Fill="{StaticResource ContextMenuForegroundBrush}" SnapsToDevicePixels="True"/>
                    <Popup Name="Popup" Placement="Left" HorizontalOffset="-2" IsOpen="{TemplateBinding IsSubmenuOpen}" PopupAnimation="Fade">
                        <Border Name="SubmenuBorder" Background="{StaticResource ContextMenuBackgroundBrush}" BorderBrush="{StaticResource ContextMenuBorderBrush}" BorderThickness="1">
                            <StackPanel Orientation="Vertical" IsItemsHost="True" Margin="1,1,1,1"/>
                            <Border.Effect>
                                <DropShadowEffect Color="Black" BlurRadius="30" Direction="315"  Opacity="0.5" ShadowDepth="2"/>
                            </Border.Effect>
                        </Border>
                    </Popup>
                </Grid>
            </Border>
            <ControlTemplate.Triggers>
                <Trigger Property="IsHighlighted" Value="true">
                    <Setter TargetName="Border" Property="Background" Value="{StaticResource ContextMenuMouseOverBackgroundBrush}"/>
                </Trigger>
            </ControlTemplate.Triggers>
        </ControlTemplate>
        <ControlTemplate x:Key="{x:Static MenuItem.SubmenuItemTemplateKey}" TargetType="{x:Type MenuItem}">
            <Border x:Name="Border" Background="{StaticResource ContextMenuBackgroundBrush}">
                <Grid>
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="30"/>
                        <ColumnDefinition Width="*" />
                        <ColumnDefinition Width="30" />
                    </Grid.ColumnDefinitions>
                    <ContentPresenter x:Name="Icon" Grid.Column="0" Margin="0" HorizontalAlignment="Center" VerticalAlignment="Center" ContentSource="Icon" SnapsToDevicePixels="True"/>
                    <ContentPresenter x:Name="HeaderHost" Grid.Column="1" ContentSource="Header" HorizontalAlignment="Stretch" VerticalAlignment="Center" Margin="4,0,0,0" SnapsToDevicePixels="True"/>
                </Grid>
            </Border>
            <ControlTemplate.Triggers>
                <Trigger Property="IsHighlighted" Value="true">
                    <Setter TargetName="Border" Property="Background" Value="{StaticResource ContextMenuMouseOverBackgroundBrush}" />
                </Trigger>
                <Trigger Property="IsEnabled" Value="False">
                    <Setter TargetName="Icon" Property="Opacity" Value="0.5" />
                    <Setter TargetName="HeaderHost" Property="Opacity" Value="0.5" />
                </Trigger>
            </ControlTemplate.Triggers>
        </ControlTemplate>
    </ContextMenu.Resources>
    <Separator/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper},Path=ContextMenuIgnoreAll}" Visibility="Collapsed" Command="RichTextBoxAdv:SfRichTextBoxAdv.IgnoreAllSpellingErrorsCommand"/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper},Path=ContextMenuAddToDictionary}" Visibility="Collapsed" Command="RichTextBoxAdv:SfRichTextBoxAdv.AddToDictionaryCommand"/>
    <Separator/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuCut}" Command="RichTextBoxAdv:SfRichTextBoxAdv.CutCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Cut_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuCopy}" Command="RichTextBoxAdv:SfRichTextBoxAdv.CopyCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Copy_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuPaste}" Command="RichTextBoxAdv:SfRichTextBoxAdv.PasteCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Paste_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <Separator/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuEditHyperlink}" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowHyperlinkDialogCommand" CommandParameter="EditHyperlink">
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Hyperlink_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuOpenHyperlink}" Command="RichTextBoxAdv:SfRichTextBoxAdv.NavigateHyperlinkCommand" />
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuCopyHyperlink}" Command="RichTextBoxAdv:SfRichTextBoxAdv.CopyHyperlinkCommand" />
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuRemoveHyperlink}" Command="RichTextBoxAdv:SfRichTextBoxAdv.RemoveHyperlinkCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/RemoveHyperlink_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <Separator/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuFontDialog}" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowFontDialogCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Font_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuParagraphDialog}" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowParagraphDialogCommand"  >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Paragraph_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <Separator/>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuInsertTable}" Visibility="Collapsed">
        <MenuItem.Items>
            <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuInsertLeftColumn}" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertColumnCommand" CommandParameter="Left">
                <MenuItem.Icon>
                    <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/InsertColumnBefore_Icon.png"/>
                </MenuItem.Icon>
            </MenuItem>
            <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuInsertRightColumn}" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertColumnCommand" CommandParameter="Right">
                <MenuItem.Icon>
                    <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/InsertColumnAfter_Icon.png"/>
                </MenuItem.Icon>
            </MenuItem>
            <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuInsertRowAbove}" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertRowCommand" CommandParameter="Above">
                <MenuItem.Icon>
                    <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/InsertRowBefore_Icon.png"/>
                </MenuItem.Icon>
            </MenuItem>
            <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuInsertRowBelow}" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertRowCommand" CommandParameter="Below">
                <MenuItem.Icon>
                    <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/InsertRowAfter_Icon.png"/>
                </MenuItem.Icon>
            </MenuItem>
        </MenuItem.Items>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuMergeCell}" Command="RichTextBoxAdv:SfRichTextBoxAdv.MergeSelectedCellsCommand">
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/MergeCells_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuHyperlink}" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowHyperlinkDialogCommand" CommandParameter="Hyperlink">
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Hyperlink_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuComment}" Command="RichTextBoxAdv:SfRichTextBoxAdv.NewCommentCommand">
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Comment_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuDeleteComment}" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteCommentCommand">
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Comment_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
</ContextMenu>

<Style TargetType="RichTextBoxAdv:SfRichTextBoxAdv">
    <Setter Property="Background" Value="{StaticResource RichTextBoxAdvBackgroundBrush}"/>
    <Setter Property="SelectionBrush" Value="{StaticResource TextSelectionBrush}"/>
    <Setter Property="ContextMenu" Value="{StaticResource ContextMenuStyle}"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="RichTextBoxAdv:SfRichTextBoxAdv">
                <Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}">
                    <Grid>
                        <Grid.Resources>
                            <Style x:Key="PaneCloseButtonStyle" TargetType="{x:Type Button}">
                                <Setter Property="Background" Value="Transparent" />
                                <Setter Property="Template">
                                    <Setter.Value>
                                        <ControlTemplate TargetType="{x:Type Button}">
                                            <Grid>
                                                <Grid.RowDefinitions>
                                                    <RowDefinition Height="5"/>
                                                    <RowDefinition Height="2*"/>
                                                    <RowDefinition Height="5"/>
                                                </Grid.RowDefinitions>
                                                <Grid.ColumnDefinitions>
                                                    <ColumnDefinition Width="4"/>
                                                    <ColumnDefinition Width="*"/>
                                                    <ColumnDefinition Width="4"/>
                                                </Grid.ColumnDefinitions>
                                                <Path x:Name="pathFill" Grid.Row="1" Grid.Column="1" Fill="{StaticResource ButtonForegroundBrush}" Height="16" Width="16" Stretch="Fill" Data="F1M306,369.225L15.3,74.7L0,90L0,120.401L279.225,396L0,671.599L0,702L15.3,717.3L306,422.775L596.7,717.3L612,702L612,671.599L332.775,396L612,120.401L612,90L596.7,74.7z"/>
                                                <Rectangle Grid.Row="0" Grid.RowSpan="3" Grid.Column="0" Grid.ColumnSpan="3" x:Name="border" Fill="{StaticResource ButtonForegroundBrush}"/>
                                            </Grid>
                                            <ControlTemplate.Triggers>
                                                <Trigger Property="IsEnabled" Value="true">
                                                    <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                </Trigger>
                                                <Trigger Property="IsMouseOver" Value="true">
                                                    <Setter Property="Fill" TargetName="pathFill" Value="{StaticResource ButtonMouseOverForegroundBrush}"/>
                                                    <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                </Trigger>
                                                <Trigger Property="IsPressed" Value="true">
                                                    <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                </Trigger>
                                            </ControlTemplate.Triggers>
                                        </ControlTemplate>
                                    </Setter.Value>
                                </Setter>
                            </Style>
                        </Grid.Resources>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="Auto"/>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="Auto"/>
                        </Grid.ColumnDefinitions>
                        <Grid x:Name="OptionsPane" Background="{StaticResource PaneBackgroundBrush}" Width="280" Visibility="Collapsed">
                            <Grid.Resources>
                                <Style x:Key="SearchTextBoxStyle" TargetType="{x:Type TextBox}">
                                    <Setter Property="Foreground" Value="{StaticResource TextBoxForegroundBrush}"/>
                                    <Setter Property="Background" Value="{StaticResource TextBoxBackgroundBrush}"/>
                                    <Setter Property="BorderBrush" Value="{StaticResource TextBoxBorderBrush}"/>
                                    <Setter Property="BorderThickness" Value="1"/>
                                    <Setter Property="FontFamily" Value="Segoe UI"/>
                                    <Setter Property="FontSize" Value="12"/>
                                    <Setter Property="HorizontalAlignment" Value="Stretch"/>
                                    <Setter Property="VerticalAlignment" Value="Center"/>
                                    <Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Hidden"/>
                                    <Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Hidden"/>
                                    <Setter Property="ScrollViewer.IsDeferredScrollingEnabled" Value="False"/>
                                    <Setter Property="Padding" Value="3 6 3 6"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="TextBox">
                                                <Grid>
                                                    <Grid.ColumnDefinitions>
                                                        <ColumnDefinition Width="*"/>
                                                        <ColumnDefinition Width="30"/>
                                                    </Grid.ColumnDefinitions>
                                                    <Border x:Name="BackgroundElement" Background="{TemplateBinding Background}" Grid.ColumnSpan="2" Margin="{TemplateBinding BorderThickness}"/>
                                                    <Border x:Name="BorderElement" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Grid.ColumnSpan="2"/>
                                                    <ScrollViewer x:Name="PART_ContentHost" HorizontalScrollBarVisibility="{TemplateBinding ScrollViewer.HorizontalScrollBarVisibility}" IsTabStop="False" IsDeferredScrollingEnabled="{TemplateBinding ScrollViewer.IsDeferredScrollingEnabled}" Margin="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}" VerticalScrollBarVisibility="{TemplateBinding ScrollViewer.VerticalScrollBarVisibility}"/>
                                                </Grid>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SearchResultTextBoxStyle" TargetType="{x:Type TextBox}">
                                    <Setter Property="Background" Value="Transparent"/>
                                    <Setter Property="Foreground" Value="{StaticResource TextBoxLightForegroundBrush}"/>
                                    <Setter Property="BorderThickness" Value="0"/>
                                    <Setter Property="KeyboardNavigation.TabNavigation" Value="None"/>
                                    <Setter Property="HorizontalContentAlignment" Value="Left"/>
                                    <Setter Property="FocusVisualStyle" Value="{x:Null}"/>
                                    <Setter Property="AllowDrop" Value="true"/>
                                    <Setter Property="Stylus.IsFlicksEnabled" Value="False"/>
                                    <Setter Property="FontFamily" Value="Segoe UI"/>
                                    <Setter Property="FontSize" Value="12"/>
                                    <Setter Property="HorizontalAlignment" Value="Left"/>
                                    <Setter Property="VerticalAlignment" Value="Center"/>
                                    <Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Hidden"/>
                                    <Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Hidden"/>
                                    <Setter Property="ScrollViewer.IsDeferredScrollingEnabled" Value="False"/>
                                    <Setter Property="Padding" Value="0,6,0,6"/>
                                    <Setter Property="MinHeight" Value="30"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type TextBox}">
                                                <Grid>
                                                    <Grid.ColumnDefinitions>
                                                        <ColumnDefinition Width="*"/>
                                                        <ColumnDefinition Width="30"/>
                                                    </Grid.ColumnDefinitions>
                                                    <Border x:Name="BackgroundElement" Background="{TemplateBinding Background}" Grid.ColumnSpan="2" Margin="{TemplateBinding BorderThickness}"/>
                                                    <Border x:Name="BorderElement" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Grid.ColumnSpan="2"/>
                                                    <ScrollViewer x:Name="PART_ContentHost" Focusable="false" HorizontalScrollBarVisibility="Hidden" VerticalScrollBarVisibility="Hidden"/>
                                                </Grid>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SearchButtonStyle" TargetType="{x:Type Button}">
                                    <Setter Property="Background" Value="{StaticResource TextBoxBackgroundBrush}" />
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type Button}">
                                                <Grid>
                                                    <Grid.RowDefinitions>
                                                        <RowDefinition Height="6"/>
                                                        <RowDefinition Height="*"/>
                                                        <RowDefinition Height="6"/>
                                                    </Grid.RowDefinitions>
                                                    <Grid.ColumnDefinitions>
                                                        <ColumnDefinition Width="7.25"/>
                                                        <ColumnDefinition Width="*"/>
                                                        <ColumnDefinition Width="7.25"/>
                                                    </Grid.ColumnDefinitions>
                                                    <Path x:Name="white" Grid.Row="1" Grid.Column="1" Data="F1M401.625,472.5C306,472.5,229.5,396,229.5,300.375C229.5,204.75,306,128.25,401.625,128.25C497.25,128.25,573.75,204.75,573.75,300.375C573.75,396,497.25,472.5,401.625,472.5 M401.625,90C286.875,90,191.25,185.625,191.25,300.375C191.25,346.275,206.55,384.525,229.5,418.95L19.125,629.325C7.64999999999998,640.8,7.64999999999998,656.1,19.125,663.75L38.25,682.875C49.725,694.35,65.025,694.35,72.675,682.875L283.05,472.5C317.475,495.45,359.55,510.75,401.625,510.75C516.375,510.75,612,415.125,612,300.375C612,185.625,516.375,90,401.625,90" Fill="{StaticResource ButtonForegroundBrush}" Stretch="Fill" Width="16" Height="16"/>
                                                    <Rectangle Grid.Row="0" Grid.RowSpan="3" Grid.Column="0" Grid.ColumnSpan="3" Canvas.ZIndex="-1" x:Name="border" Fill="{StaticResource ButtonForegroundBrush}" />
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <Trigger Property="IsEnabled" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                    </Trigger>
                                                    <Trigger Property="IsMouseOver" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0.1"/>
                                                    </Trigger>
                                                    <Trigger Property="IsPressed" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0.16"/>
                                                    </Trigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="NavigatePreviousButtonStyle" TargetType="{x:Type Button}">
                                    <Setter Property="Background" Value="Transparent" />
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type Button}">
                                                <Grid>
                                                    <Grid.RowDefinitions>
                                                        <RowDefinition Height="2"/>
                                                        <RowDefinition Height="2*"/>
                                                        <RowDefinition Height="2"/>
                                                    </Grid.RowDefinitions>
                                                    <Grid.ColumnDefinitions>
                                                        <ColumnDefinition Width="1"/>
                                                        <ColumnDefinition Width="*"/>
                                                        <ColumnDefinition Width="1"/>
                                                    </Grid.ColumnDefinitions>
                                                    <Path x:Name="pathFill" Grid.Row="1" Grid.Column="1" Width="12" Stretch="Uniform" Fill="{StaticResource ButtonForegroundBrush}"  Data="F1M512.55,327.15L340.425,151.2C332.775,143.55,321.3,143.55,313.65,151.2L137.7,327.15L164.475,353.925L306,212.4L306,663.75L344.25,663.75L344.25,212.4L485.775,353.925z" />
                                                    <Rectangle Grid.Row="0" Grid.RowSpan="3" Grid.Column="0" Grid.ColumnSpan="3" x:Name="border" Fill="{StaticResource ButtonForegroundBrush}"/>
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <Trigger Property="IsEnabled" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                    </Trigger>
                                                    <Trigger Property="IsMouseOver" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                        <Setter Property="Fill" TargetName="pathFill" Value="{StaticResource ButtonMouseOverForegroundBrush}"/>
                                                    </Trigger>
                                                    <Trigger Property="IsPressed" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                        <Setter Property="Fill" TargetName="pathFill" Value="{StaticResource ButtonPressedBackgroundBrush}"/>
                                                    </Trigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="NavigateNextButtonStyle" TargetType="{x:Type Button}">
                                    <Setter Property="Background" Value="Transparent" />
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type Button}">
                                                <Grid>
                                                    <Grid.RowDefinitions>
                                                        <RowDefinition Height="2"/>
                                                        <RowDefinition Height="2*"/>
                                                        <RowDefinition Height="2"/>
                                                    </Grid.RowDefinitions>
                                                    <Grid.ColumnDefinitions>
                                                        <ColumnDefinition Width="1"/>
                                                        <ColumnDefinition Width="*"/>
                                                        <ColumnDefinition Width="1"/>
                                                    </Grid.ColumnDefinitions>
                                                    <Path x:Name="pathFill" Grid.Row="1" Grid.Column="1" Width="12" Stretch="Uniform" Fill="{StaticResource ButtonForegroundBrush}"  Data="F1M512.55,327.15L340.425,151.2C332.775,143.55,321.3,143.55,313.65,151.2L137.7,327.15L164.475,353.925L306,212.4L306,663.75L344.25,663.75L344.25,212.4L485.775,353.925z" RenderTransformOrigin="0.5,0.5">
                                                        <Path.RenderTransform>
                                                            <RotateTransform Angle="180"/>
                                                        </Path.RenderTransform>
                                                    </Path>
                                                    <Rectangle Grid.Row="0" Grid.RowSpan="3" Grid.Column="0" Grid.ColumnSpan="3" x:Name="border" Fill="{StaticResource ButtonForegroundBrush}" />
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <Trigger Property="IsEnabled" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                    </Trigger>
                                                    <Trigger Property="IsMouseOver" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                        <Setter Property="Fill" TargetName="pathFill" Value="{StaticResource ButtonMouseOverForegroundBrush}"/>
                                                    </Trigger>
                                                    <Trigger Property="IsPressed" Value="true">
                                                        <Setter Property="Opacity" TargetName="border" Value="0"/>
                                                        <Setter Property="Fill" TargetName="pathFill" Value="{StaticResource ButtonPressedBackgroundBrush}"/>
                                                    </Trigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SearchResultItemStyle" TargetType="{x:Type ListBoxItem}" >
                                    <Setter Property="Padding" Value="6 3" />
                                    <Setter Property="FontFamily" Value="Segoe UI"/>
                                    <Setter Property="FontSize" Value="12"/>
                                    <Setter Property="HorizontalContentAlignment" Value="Left" />
                                    <Setter Property="VerticalContentAlignment" Value="Top" />
                                    <Setter Property="Background" Value="{StaticResource SearchResultItemBackgroundBrush}"/>
                                    <Setter Property="Foreground" Value="{StaticResource SearchResultItemForegroundBrush}"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="ListBoxItem">
                                                <Grid Background="{TemplateBinding Background}">
                                                    <Grid>
                                                        <Grid.RowDefinitions>
                                                            <RowDefinition Height ="Auto"/>
                                                            <RowDefinition Height="Auto" />
                                                        </Grid.RowDefinitions>
                                                        <Border x:Name="SelectedBorder" BorderBrush="{StaticResource SearchResultItemSelectedBorderBrush}" BorderThickness="2" Opacity="0" />
                                                        <Border x:Name="ItemBorder" BorderBrush="{StaticResource SearchResultItemMouseOverBorderBrush}" BorderThickness="1" Opacity="0" />
                                                        <ContentPresenter x:Name="contentPresenter" Content="{TemplateBinding Content}" ContentTemplate="{TemplateBinding ContentTemplate}" VerticalAlignment="Center" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}"/>
                                                        <Rectangle Margin="0,4,0,4" Height="1" Opacity="0.2" Grid.Row="1" Fill="{StaticResource SearchResultItemSeparatorForegroundBrush}"/>
                                                    </Grid>
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="IsMouseOver" Value="True"/>
                                                            <Condition Property="IsSelected" Value="False"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Opacity" TargetName="ItemBorder" Value="1"/>
                                                    </MultiTrigger>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="IsMouseOver" Value="True"/>
                                                            <Condition Property="IsSelected" Value="True"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Opacity" TargetName="SelectedBorder" Value="1"/>
                                                    </MultiTrigger>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="Selector.IsSelectionActive" Value="False"/>
                                                            <Condition Property="IsSelected" Value="True"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Opacity" TargetName="SelectedBorder" Value="1"/>
                                                    </MultiTrigger>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="Selector.IsSelectionActive" Value="True"/>
                                                            <Condition Property="IsSelected" Value="True"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Opacity" TargetName="SelectedBorder" Value="1"/>
                                                    </MultiTrigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SearchResultsListBoxStyle" TargetType="{x:Type ListBox}">
                                    <Setter Property="Padding" Value="1"/>
                                    <Setter Property="Background" Value="Transparent"/>
                                    <Setter Property="BorderThickness" Value="0"/>
                                    <Setter Property="Foreground" Value="{StaticResource TextBoxForegroundBrush}"/>
                                    <Setter Property="HorizontalContentAlignment" Value="Left" />
                                    <Setter Property="VerticalContentAlignment" Value="Top" />
                                    <Setter Property="IsTabStop" Value="False" />
                                    <Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Disabled"/>
                                    <Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Auto"/>
                                    <Setter Property="ItemContainerStyle" Value="{StaticResource SearchResultItemStyle}"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type ListBox}">
                                                <Grid>
                                                    <Border CornerRadius="2" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}">
                                                        <ScrollViewer x:Name="ScrollViewer" Padding="{TemplateBinding Padding}" Background="{TemplateBinding Background}" BorderBrush="Transparent" BorderThickness="0">
                                                            <Grid>
                                                                <Grid.ColumnDefinitions>
                                                                    <ColumnDefinition Width="*"/>
                                                                    <ColumnDefinition Width="20"/>
                                                                </Grid.ColumnDefinitions>
                                                                <ItemsPresenter />
                                                            </Grid>
                                                        </ScrollViewer>
                                                    </Border>
                                                </Grid>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                            </Grid.Resources>
                            <Grid.RowDefinitions>
                                <RowDefinition Height="20"/>
                                <RowDefinition Height="30"/>
                                <RowDefinition Height="12"/>
                                <RowDefinition Height="34"/>
                                <RowDefinition Height="12"/>
                                <RowDefinition Height="18"/>
                                <RowDefinition Height="Auto"/>
                                <RowDefinition Height="8"/>
                                <RowDefinition Height="*"/>
                                <RowDefinition Height="20"/>
                            </Grid.RowDefinitions>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="26"/>
                                <ColumnDefinition Width="*"/>
                                <ColumnDefinition Width="26"/>
                            </Grid.ColumnDefinitions>
                            <Rectangle Grid.Column="2" Grid.RowSpan="10" Width="2" HorizontalAlignment="Right" Opacity="0.5" Fill="{StaticResource ButtonBorderBrush}"/>
                            <TextBlock x:Name="PaneHeaderBlock" Grid.Row="1" Grid.Column="1" Text="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=OptionsPaneSearch}" FontFamily="Segoe UI"  FontSize="18" Foreground="{StaticResource HeaderLabelForegroundBrush}" VerticalAlignment="Center" HorizontalAlignment="Stretch"/>
                            <Button x:Name="ClosePaneButton" Grid.Row="1" Grid.Column="1" Grid.ColumnSpan="2" Style="{StaticResource PaneCloseButtonStyle}" HorizontalAlignment="Right" Margin="0 0 20 0"/>
                            <Grid Grid.Row="3" Grid.Column="1">
                                <Grid.ColumnDefinitions >
                                    <ColumnDefinition Width="5*"/>
                                    <ColumnDefinition Width="*"/>
                                    <ColumnDefinition Width="*"/>
                                </Grid.ColumnDefinitions>
                                <TextBox x:Name="SearchTextBox" MinHeight="32" Grid.ColumnSpan="3" Style="{StaticResource SearchTextBoxStyle}"/>
                                <Button x:Name="SearchButton" Grid.Column="2" Style="{StaticResource SearchButtonStyle}" ToolTip="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SearchButtonToolTip}"/>
                            </Grid>
                            <Grid Grid.Row="5" Grid.Column="1">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="*"/>
                                    <ColumnDefinition Width="Auto"/>
                                    <ColumnDefinition Width="12"/>
                                    <ColumnDefinition Width="Auto"/>
                                </Grid.ColumnDefinitions>
                                <TextBlock Grid.Column="0" Text="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=OptionsPaneResultsHeader}" FontFamily="Segoe UI"  FontSize="14" Foreground="{StaticResource TextBoxForegroundBrush}" HorizontalAlignment="Stretch" VerticalAlignment="Center"/>
                                <Button x:Name="NavigatePreviousResultButton" Grid.Column="1" Style="{StaticResource NavigatePreviousButtonStyle}" Visibility="Collapsed"/>
                                <Button x:Name="NavigateNextResultButton" Grid.Column="3" Style="{StaticResource NavigateNextButtonStyle}" Visibility="Collapsed"/>
                            </Grid>
                            <TextBox x:Name="SearchResultsCountTextBox" Grid.Row="6" Grid.Column="1" Style="{StaticResource SearchResultTextBoxStyle}" Visibility="Collapsed" IsReadOnly="True" Margin="-2 0 0 0" IsEnabled="False" HorizontalAlignment="Left" VerticalAlignment="Top" VerticalContentAlignment="Top"/>
                            <TextBox x:Name="SearchResultsTextBox" Grid.Row="8" Grid.Column="1" Text="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=OptionsPaneDescription, Mode=OneWay}" Style="{StaticResource SearchResultTextBoxStyle}" Margin="-2 0 0 0" Padding="0" HorizontalAlignment="Stretch" VerticalAlignment="Top" TextWrapping="Wrap" IsEnabled="False"/>
                            <ListBox x:Name="SearchResultsListBox" Grid.Row="8" Grid.Column="1" Style="{StaticResource SearchResultsListBoxStyle}" Margin="-4 0 0 0" SelectionMode="Single" Visibility="Collapsed"/>
                        </Grid>
                        <Grid Grid.Column="1">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="*"/>
                                <ColumnDefinition Width="Auto"/>
                            </Grid.ColumnDefinitions>
                            <Grid.RowDefinitions>
                                <RowDefinition Height="*"/>
                                <RowDefinition Height="Auto"/>
                            </Grid.RowDefinitions>
                            <ContentControl x:Name="content" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Grid.Row="0" Grid.Column="0" />
                            <ScrollBar x:Name="HorizontalScrollBar" Grid.Column="0" Height="16" Visibility="Collapsed" IsTabStop="False" Minimum="0" Orientation="Horizontal" Grid.Row="1"/>
                            <ScrollBar x:Name="VerticalScrollBar" Grid.Column="1" IsTabStop="False" Visibility="Collapsed" Minimum="0" Orientation="Vertical" Grid.Row="0" Width="16"/>
                        </Grid>
                        <Grid x:Name="SpellingPane" Grid.Column="2" Background="{StaticResource PaneBackgroundBrush}" Width="300" Visibility="Collapsed" SnapsToDevicePixels="False">
                            <Grid.Resources>
                                <Style x:Key="SpellingPaneButtonStyle" TargetType="{x:Type Button}">
                                    <Setter Property="Background" Value="{StaticResource ButtonBackgroundBrush}"/>
                                    <Setter Property="Foreground" Value="{StaticResource ButtonForegroundBrush}"/>
                                    <Setter Property="FontWeight" Value="Normal"/>
                                    <Setter Property="BorderBrush" Value="{StaticResource ButtonBorderBrush}"/>
                                    <Setter Property="BorderThickness" Value="1"/>
                                    <Setter Property="Padding" Value="10 1 10 1"/>
                                    <Setter Property="HorizontalAlignment" Value="Left"/>
                                    <Setter Property="VerticalAlignment" Value="Center"/>
                                    <Setter Property="FontFamily" Value="Segoe UI"/>
                                    <Setter Property="FontSize" Value="14"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type Button}">
                                                <Grid>
                                                    <Border x:Name="Border" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}"  SnapsToDevicePixels="True">
                                                        <ContentPresenter x:Name="ContentPresenter" ContentTemplate="{TemplateBinding ContentTemplate}" Content="{TemplateBinding Content}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                                                    </Border>
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <Trigger Property="IsMouseOver" Value="true">
                                                        <Setter Property="BorderBrush" TargetName="Border" Value="{StaticResource ButtonMouseOverBorderBrush}"/>
                                                        <Setter Property="Background" Value="{StaticResource ButtonMouseOverBackgroundBrush}"/>
                                                    </Trigger>
                                                    <Trigger Property="IsPressed" Value="true">
                                                        <Setter Property="Background" Value="{StaticResource ButtonPressedBackgroundBrush}"/>
                                                        <Setter Property="Foreground" Value="{StaticResource ButtonPressedForegroundBrush}"/>
                                                    </Trigger>
                                                    <Trigger Property="IsEnabled" Value="false">
                                                        <Setter Property="Foreground" Value="{StaticResource ButtonDisabledForegroundBrush}"/>
                                                        <Setter Property="Background" Value="{StaticResource ButtonDisabledBackgroundBrush}"/>
                                                        <Setter Property="BorderBrush" TargetName="Border" Value="{StaticResource ButtonDisabledBorderBrush}"/>
                                                    </Trigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SpellingSuggestionItemStyle" TargetType="{x:Type ListBoxItem}" >
                                    <Setter Property="Padding" Value="6 3" />
                                    <Setter Property="FontFamily" Value="Segoe UI"/>
                                    <Setter Property="FontSize" Value="14"/>
                                    <Setter Property="HorizontalContentAlignment" Value="Left" />
                                    <Setter Property="VerticalContentAlignment" Value="Top" />
                                    <Setter Property="Height" Value="30"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="ListBoxItem">
                                                <Grid Background="{TemplateBinding Background}" SnapsToDevicePixels="False">
                                                    <ContentPresenter x:Name="contentPresenter" Content="{TemplateBinding Content}" ContentTemplate="{TemplateBinding ContentTemplate}" VerticalAlignment="Center" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}"/>
                                                </Grid>
                                                <ControlTemplate.Triggers>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="IsMouseOver" Value="True"/>
                                                            <Condition Property="IsSelected" Value="False"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Background" Value="{StaticResource SuggestionItemMouseOverBrush}"/>
                                                    </MultiTrigger>
                                                    <MultiTrigger>
                                                        <MultiTrigger.Conditions>
                                                            <Condition Property="IsMouseOver" Value="True"/>
                                                            <Condition Property="IsSelected" Value="True"/>
                                                        </MultiTrigger.Conditions>
                                                        <Setter Property="Background" Value="{StaticResource SuggestionItemSelectedBrush}"/>
                                                    </MultiTrigger>
                                                    <Trigger Property="IsSelected" Value="True">
                                                        <Setter Property="Background" Value="{StaticResource SuggestionItemSelectedBrush}"/>
                                                    </Trigger>
                                                </ControlTemplate.Triggers>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                                <Style x:Key="SpellingSuggestionListBoxStyle" TargetType="{x:Type ListBox}">
                                    <Setter Property="Foreground" Value="{StaticResource TextBoxForegroundBrush}"/>
                                    <Setter Property="HorizontalContentAlignment" Value="Left" />
                                    <Setter Property="VerticalContentAlignment" Value="Top" />
                                    <Setter Property="IsTabStop" Value="True" />
                                    <Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Disabled"/>
                                    <Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Auto"/>
                                    <Setter Property="ItemContainerStyle" Value="{StaticResource SpellingSuggestionItemStyle}"/>
                                    <Setter Property="Template">
                                        <Setter.Value>
                                            <ControlTemplate TargetType="{x:Type ListBox}">
                                                <Grid SnapsToDevicePixels="False">
                                                    <Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}">
                                                        <ScrollViewer x:Name="ScrollViewer" Padding="{TemplateBinding Padding}" Background="{TemplateBinding Background}" BorderBrush="Transparent" >
                                                            <Grid>
                                                                <ItemsPresenter />
                                                            </Grid>
                                                        </ScrollViewer>
                                                    </Border>
                                                </Grid>
                                            </ControlTemplate>
                                        </Setter.Value>
                                    </Setter>
                                </Style>
                            </Grid.Resources>
                            <Grid.RowDefinitions>
                                <RowDefinition Height="41"/>
                                <RowDefinition Height="Auto"/>
                                <RowDefinition Height="27"/>
                                <RowDefinition Height="25"/>
                                <RowDefinition Height="17"/>
                                <RowDefinition Height="25"/>
                                <RowDefinition Height="15"/>
                                <RowDefinition Height="Auto"/>
                                <RowDefinition Height="15"/>
                                <RowDefinition Height="25"/>
                                <RowDefinition Height="*"/>
                            </Grid.RowDefinitions>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="13"/>
                                <ColumnDefinition Width="*"/>
                                <ColumnDefinition Width="13"/>
                            </Grid.ColumnDefinitions>
                            <TextBlock x:Name="SpellingPaneHeaderBlock" Grid.Row="0" Grid.Column="1" Text="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneSpelling}" FontFamily="Segoe UI"  FontSize="20" Foreground="{StaticResource HeaderLabelForegroundBrush}" VerticalAlignment="Center" HorizontalAlignment="Stretch"/>
                            <Button x:Name="SpellingPaneCloseButton" Grid.Row="0" Grid.Column="1" Style="{StaticResource PaneCloseButtonStyle}" HorizontalAlignment="Right" VerticalAlignment="Center"/>
                            <Separator Grid.Row="1" Grid.Column="1" Opacity="0.5" IsEnabled="False" VerticalAlignment="Bottom" ></Separator>
                            <TextBlock x:Name="SpellingPaneMisspelledWordBlock" Grid.Row="3" Grid.Column="1" FontFamily="Segoe UI" FontSize="14" Foreground="{StaticResource HeaderLabelForegroundBrush}" FontWeight="SemiBold" HorizontalAlignment="Stretch" VerticalAlignment="Center" Margin="0"/>
                            <Grid Grid.Row="5" Grid.Column="1">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="Auto"></ColumnDefinition>
                                    <ColumnDefinition Width="Auto"></ColumnDefinition>
                                    <ColumnDefinition Width="Auto"></ColumnDefinition>
                                </Grid.ColumnDefinitions>
                                <Button x:Name="SpellingPaneResumeButton" Content="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneResume}" Style="{StaticResource SpellingPaneButtonStyle}" Visibility="Collapsed"/>
                                <Button x:Name="SpellingPaneIgnoreAllButton" Grid.Column="1" Command="RichTextBoxAdv:SfRichTextBoxAdv.IgnoreAllSpellingErrorsCommand" CommandParameter="{Binding Text,ElementName=SpellingPaneMisspelledWordBlock}" Content="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneIgnoreAll}" Style="{StaticResource SpellingPaneButtonStyle}" Margin="0 0 0 0"/>
                                <Button x:Name="SpellingPaneAddToDictionaryButton" Grid.Column="2" Command="RichTextBoxAdv:SfRichTextBoxAdv.AddToDictionaryCommand" CommandParameter="{Binding Text,ElementName=SpellingPaneMisspelledWordBlock}" Content="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneAddToDictionary}" Style="{StaticResource SpellingPaneButtonStyle}" Margin="15 0 0 0"/>
                            </Grid>
                            <ListBox x:Name="SpellingPaneSuggestionListBox" Grid.Row="7" Grid.Column="1" Height="152" SelectionMode="Single" Style="{StaticResource SpellingSuggestionListBoxStyle}"/>
                            <Grid Grid.Row="9" Grid.Column="1">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="Auto"></ColumnDefinition>
                                    <ColumnDefinition Width="Auto"></ColumnDefinition>
                                </Grid.ColumnDefinitions>
                                <Button x:Name="SpellingPaneChangeButton" Command="RichTextBoxAdv:SfRichTextBoxAdv.ChangeSpellingCommand" CommandParameter="{Binding ElementName=SpellingPaneSuggestionListBox, Path=SelectedValue}" Content="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneChange}" Style="{StaticResource SpellingPaneButtonStyle}"/>
                                <Button x:Name="SpellingPaneChangeAllButton" Grid.Column="1" Command="RichTextBoxAdv:SfRichTextBoxAdv.ChangeAllSpellingCommand" CommandParameter="{Binding ElementName=SpellingPaneSuggestionListBox, Path=SelectedValue}" Content="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=SpellingPaneChangeAll}" Style="{StaticResource SpellingPaneButtonStyle}" Margin="15 0 0 0"/>
                            </Grid>
                        </Grid>
                    </Grid>
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>



{% endhighlight %}

{% endtabs %}

N> In the control template, you are allowed to reorder the template parts and to add your own elements. However, when changing the control template you should be careful to include all required parts. Usually required parts are marked with Name attribute. Omission of required parts may impact some of the functionality. 

## Styling the SfRichTextBoxAdv

You can define custom style for the SfRichTextBoxAdv control either by creating empty style and set it up on your own or by copying the default style and modifying it. 
The following example demonstrates how to customize the style for SfRichTextBoxAdv control.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdvResourceWrapper x:Key="SfRichTextBoxAdvResourceWrapper"/>
<SolidColorBrush x:Key="RichTextBoxAdvBackgroundBrush" Color="#000000"/>
<SolidColorBrush x:Key="TextSelectionBrush" Color="#FF808080"/>

<ContextMenu x:Key="ContextMenuStyle">
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuCut}" Command="RichTextBoxAdv:SfRichTextBoxAdv.CutCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Cut_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuCopy}" Command="RichTextBoxAdv:SfRichTextBoxAdv.CopyCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Copy_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
    <MenuItem Header="{Binding Source={StaticResource SfRichTextBoxAdvResourceWrapper}, Path=ContextMenuPaste}" Command="RichTextBoxAdv:SfRichTextBoxAdv.PasteCommand" >
        <MenuItem.Icon>
            <Image Source="/Syncfusion.SfRichTextBoxAdv.WPF;component/Images/Paste_Icon.png"/>
        </MenuItem.Icon>
    </MenuItem>
</ContextMenu>

<Style TargetType="RichTextBoxAdv:SfRichTextBoxAdv" x:Key="RichTextBoxAdvCustomStyle" >
    <Setter Property="Background" Value="{StaticResource RichTextBoxAdvBackgroundBrush}"/>
    <Setter Property="SelectionBrush" Value="{StaticResource TextSelectionBrush}"/>
    <Setter Property="ContextMenu" Value="{StaticResource ContextMenuStyle}"/>
    <Setter Property="EnableMiniToolBar" Value="False"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="RichTextBoxAdv:SfRichTextBoxAdv">
                <Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="Auto"/>
                        </Grid.ColumnDefinitions>
                        <Grid.RowDefinitions>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="Auto"/>
                        </Grid.RowDefinitions>
                        <ContentControl x:Name="content" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Grid.Row="0" Grid.Column="0" />
                        <ScrollBar x:Name="HorizontalScrollBar" Grid.Column="0" Height="16" Visibility="Collapsed" IsTabStop="False" Minimum="0" Orientation="Horizontal" Grid.Row="1"/>
                        <ScrollBar x:Name="VerticalScrollBar" Grid.Column="1" IsTabStop="False" Visibility="Collapsed" Minimum="0" Orientation="Vertical" Grid.Row="0" Width="16"/>
                    </Grid>
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>



{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to apply the custom style for SfRichTextBoxAdv control. Applying this style will result in a SfRichTextBoxAdv control with no options pane and no spelling pane.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" Style="{StaticResource RichTextBoxAdvCustomStyle}" />


{% endhighlight %}

{% endtabs %}
