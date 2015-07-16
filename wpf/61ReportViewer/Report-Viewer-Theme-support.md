---
layout: post
title: Report-Viewer-Theme-support
description: report viewer theme support
platform: wpf
control: Report Viewer
documentation: ug
---

# Report Viewer Theme support

Theme support for Report Viewer is provided by modifying the UserControl as a ControlTemplate. You can now modify the Report Viewer in your own style, by writing a customized control template for Report Viewer. 

To customize a Report Viewer, you have to modify the following control parts.

* PART_exportControl
* PART_comboBoxPageZoom
* PART_Zoom
* PART_ShowError
* PART_PageViewBody
* PART_PageFooterBorder
* PART_PageBodyBorder
* PART_PageHeaderBorder
* PART_scrollViewer
* PART_scorllDSCredentialBlock
* PART_groupBoxExpandedExceptionScroll
* PART_scrollViewerParamBlock
* PART_canvasContentPage
* PART_CanvasFooter
* PART_CanvasHeader
* PART_treeItemArea
* PART_renderArea
* PART_grid_ReportParameterBlock
* PART_gridRenderingRegion
* PART_ExceptionGrid
* PART_gridException
* PART_gridLoadingIndicator
* PART_MainGrid
* PART_viewerSpliter
* PART_PageView
* PART_sPanel_Head
* PART_PageViewContainer
* PART_toolBar
* PART_DocumentMap
* PART_btnViewReport1
* PART_buttonNext
* PART_buttonParameters
* PART_buttonPrint
* PART_buttonFirst
* PART_buttonLast
* PART_buttonPrevious
* PART_buttonShowOrHideDocumentMap
* PART_buttonPrintLayout
* PART_buttonPageSetup
* PART_buttonRefresh
* PART_btnViewReport
* PART_buttonFind
* PART_btnback
* PART_toggleShowDetails
* PART_textBoxTotalPages
* PART_labelOf
* PART_textBlockException
* PART_textBoxFind
* PART_textBoxCurrentPage
* PART_textBlockStackTrace
* PART_gridExceptionRow
* PART_loadingIndicatorRow
* PART_toolBarGridRow
* PART_dsCredentialRow
* PART_parameterGridRow
* PART_viewerContentRow



The following code example illustrates a Report Viewer control template.

[XAML]



&lt;Style TargetType="local:ReportViewer"&gt;

        &lt;Setter Property="Template"&gt;

            &lt;Setter.Value&gt;

                &lt;ControlTemplate TargetType="local:ReportViewer"&gt;



                    &lt;Grid x:Name="PART_MainGrid" Height="Auto" Margin="0,0,0,0" Background="Transparent"&gt;

                        &lt;Grid.RowDefinitions&gt;

                            &lt;RowDefinition Name="PART_toolBarGridRow" Height="28"/&gt;

                            &lt;RowDefinition Name="PART_dsCredentialRow" Height="Auto"/&gt;

                            &lt;RowDefinition Name="PART_parameterGridRow" Height="Auto"/&gt;

                            &lt;RowDefinition Name="PART_viewerContentRow" Height="*" /&gt;

                            &lt;RowDefinition Name="PART_gridExceptionRow" Height="0"/&gt;

                            &lt;RowDefinition Name="PART_loadingIndicatorRow" Height="0"/&gt;

                        &lt;/Grid.RowDefinitions&gt;



                        &lt;!--Toolbar--&gt;

                        &lt;StackPanel Name="PART_toolBar" Height="28" Orientation="Horizontal" Grid.ColumnSpan="2" Margin="0"&gt;

                            &lt;StackPanel.Background&gt;

                                &lt;LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"&gt;

                                    &lt;GradientStop Color="#FFFEFBF4" Offset="0.027"/&gt;

                                    &lt;GradientStop Color="#FFEAEEEF" Offset="0.029"/&gt;

                                    &lt;GradientStop Color="#FFDCE4F1" Offset="0.498"/&gt;

                                    &lt;GradientStop Color="#FFE6EAF3" Offset="0.966"/&gt;

                                    &lt;GradientStop Color="FloralWhite" Offset="0.968"/&gt;

                                    &lt;GradientStop Color="#FFD4DBEB" Offset="0.503"/&gt;

                                &lt;/LinearGradientBrush&gt;



                            &lt;/StackPanel.Background&gt;



                            &lt;!--Print--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPrint" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrint}" IsEnabled="False" Margin="2,3,2,3" &gt;

                                &lt;Image Stretch="None"&gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource PrintDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Print}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--PrintDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;ComboBox Name="PART_exportControl" Height="22" Width="35" Style="{StaticResource ExportComboBox}" ItemContainerStyle="{StaticResource ItemTemplate}" IsEnabled="False" ToolTip="Export" /&gt;



                            &lt;Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6"&gt;

                                &lt;Rectangle.Fill&gt;

                                    &lt;LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5"&gt;

                                        &lt;GradientStop Color="#FFBCBCBC" Offset="0.508"/&gt;

                                        &lt;GradientStop Color="White" Offset="0.525"/&gt;

                                    &lt;/LinearGradientBrush&gt;

                                &lt;/Rectangle.Fill&gt;

                            &lt;/Rectangle&gt;



                            &lt;!--Navigates to First--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonFirst" ToolTip="{x:Static prop:Resources.menuItemFirst}" Width="22" Height="22" IsEnabled="False" Margin="0,3,0,3" &gt;

                                &lt;Image Stretch="None"&gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource First_NavDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource First_Nav}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--First_NavDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Navigates to Previous--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPrevious" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrevious}" IsEnabled="False" Margin="2,3,2,3" &gt;

                                &lt;Image&gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Previous_NavDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Previous_Nav}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--Previous_NavDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Current Page--&gt;

                            &lt;TextBox Name="PART_textBoxCurrentPage" Width="60" Height="22" IsReadOnly="False" IsEnabled="False" BorderBrush="Gray" Margin="2,3,2,3" &gt;

                            &lt;/TextBox&gt;

                            <TextBlock Name="PART_labelOf" Width="Auto" VerticalAlignment="Center" Foreground="Black" Margin="2,3,5,3">of</TextBlock>



                            &lt;!--Total number of pages--&gt;

                            &lt;TextBlock Name="PART_textBoxTotalPages" Width="Auto" xml:space="preserve" IsEnabled="false" Margin="2,3,5,3" VerticalAlignment="Center" Foreground="Black" TextAlignment="Center" HorizontalAlignment="Center"/&gt;



                            &lt;!--Navigates to Next--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonNext" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemNext}" IsEnabled="False" Margin="2,3,2,3" &gt;

                                &lt;Image Stretch="None"&gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Next_NavDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Next_Nav}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--Next_NavDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Navigates to Last--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonLast" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemLast}" IsEnabled="False" Margin="2,3,2,3" &gt;

                                &lt;Image Stretch="None"&gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Last_NavDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Last_Nav}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--Last_NavDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Back Parent Report--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_btnback" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipBack}" IsEnabled="True" Margin="2,3,2,3" Visibility="Collapsed"&gt;

                                &lt;Image Source="{StaticResource ReportBack}" Stretch="None"/&gt;

                            &lt;/Button&gt;



                            &lt;Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6"&gt;

                                &lt;Rectangle.Fill&gt;

                                    &lt;LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5"&gt;

                                        &lt;GradientStop Color="#FFBCBCBC" Offset="0.508"/&gt;

                                        &lt;GradientStop Color="White" Offset="0.525"/&gt;

                                    &lt;/LinearGradientBrush&gt;

                                &lt;/Rectangle.Fill&gt;

                            &lt;/Rectangle&gt;



                            &lt;!--Zooming--&gt;

                            &lt;Border Name="PART_comboBoxExternalBorder" BorderBrush="Gray" Width="70" Height="22" ToolTip="{x:Static prop:Resources.toolTipZoom}" BorderThickness="0" Margin="2,3,2,3"&gt;

                                &lt;ComboBox Name="PART_comboBoxPageZoom" Width="70" Height="22"  SelectedIndex="2" IsEnabled="False"&gt;

                                    &lt;ComboBoxItem Content="25%"/&gt;

                                    &lt;ComboBoxItem Content="50%"/&gt;

                                    &lt;ComboBoxItem Content="100%"/&gt;

                                    &lt;ComboBoxItem Content="200%"/&gt;

                                    &lt;ComboBoxItem Content="300%"/&gt;

                                    &lt;ComboBoxItem Content="400%"/&gt;

                                    &lt;ComboBoxItem Content="500%"/&gt;

                                &lt;/ComboBox&gt;

                            &lt;/Border&gt;



                            &lt;!--Prints Layout--&gt;

                            &lt;ToggleButton Style="{StaticResource ViewerToggleButtonStyle}" Name="PART_buttonPrintLayout" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrintLayout}" IsEnabled="False" Margin="2,3,2,3"&gt;

                                &lt;Image Stretch="None" &gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="ToggleButton.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource PrintLayoutXDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="ToggleButton.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource PrintLayoutX}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--PrintLayoutXDisabled--&gt;

                            &lt;/ToggleButton&gt;



                            &lt;!--Prints Setup--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPageSetup" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipPageSetUp}" IsEnabled="False" Margin="2,3,2,3" Visibility="Visible" &gt;

                                &lt;Image Source="{StaticResource PageSetup}" Stretch="None"/&gt;

                                &lt;!--PrintSetupDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6"&gt;

                                &lt;Rectangle.Fill&gt;

                                    &lt;LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5"&gt;

                                        &lt;GradientStop Color="#FFBCBCBC" Offset="0.508"/&gt;

                                        &lt;GradientStop Color="White" Offset="0.525"/&gt;

                                    &lt;/LinearGradientBrush&gt;

                                &lt;/Rectangle.Fill&gt;

                            &lt;/Rectangle&gt;



                            &lt;!--Refresh --&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Height="22" Width="22" Name="PART_buttonRefresh" ToolTip="{x:Static prop:Resources.menuItemRefresh}" IsEnabled="False" Margin="2,3,2,3"&gt;

                                &lt;Image HorizontalAlignment="Center" VerticalAlignment="Center" Height="16" Width="16" Stretch="Fill" &gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource RefreshDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Refresh}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--RefreshDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Shows/Hides Document map--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonShowOrHideDocumentMap" Width="22" ToolTip="{x:Static prop:Resources.menuItemShowHide}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3"&gt;

                                &lt;Image Source="{StaticResource ShowHideDisabled}" Stretch="None" HorizontalAlignment="Center" VerticalAlignment="Center" Height="16" Width="16"/&gt;

                                &lt;!--ShowHideDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;!--Parameterised query--&gt;

                            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonParameters" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipParameters}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3" Background="Transparent" &gt;

                                &lt;Image Stretch="None" &gt;

                                    &lt;Image.Style&gt;

                                        &lt;Style&gt;

                                            &lt;Style.Triggers&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource ParametersDisabled}"/&gt;

                                                &lt;/Trigger&gt;

                                                &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                                    &lt;Setter Property="Image.Source" Value="{StaticResource Parameters}"/&gt;

                                                &lt;/Trigger&gt;

                                            &lt;/Style.Triggers&gt;

                                        &lt;/Style&gt;

                                    &lt;/Image.Style&gt;

                                &lt;/Image&gt;

                                &lt;!--ParametersDisabled--&gt;

                            &lt;/Button&gt;



                            &lt;Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6"&gt;

                                &lt;Rectangle.Fill&gt;

                                    &lt;LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5"&gt;

                                        &lt;GradientStop Color="#FFBCBCBC" Offset="0.508"/&gt;

                                        &lt;GradientStop Color="White" Offset="0.525"/&gt;

                                    &lt;/LinearGradientBrush&gt;

                                &lt;/Rectangle.Fill&gt;

                            &lt;/Rectangle&gt;



                            &lt;TextBox Name="PART_textBoxFind" Width="60" Height="22" xml:space="preserve" IsEnabled="False" BorderBrush="Gray" ToolTip="{x:Static prop:Resources.toolTipFindTextBox}" Margin="2,3,2,3" Visibility="Collapsed"/&gt;



            &lt;!--Find--&gt;

            &lt;Button Style="{StaticResource ButtonStyle}" Name="PART_buttonFind" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipFind}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3"&gt;

                &lt;Image Stretch="None"&gt;

                    &lt;Image.Style&gt;

                        &lt;Style&gt;

                            &lt;Style.Triggers&gt;

                              &lt;Trigger Property="Button.IsEnabled" Value="False"&gt;

                                   &lt;Setter Property="Image.Source" Value="{StaticResource FindDisabled}"/&gt;

                              &lt;/Trigger&gt;

                              &lt;Trigger Property="Button.IsEnabled" Value="True"&gt;

                                   &lt;Setter Property="Image.Source" Value="{StaticResource Find}"/&gt;

                              &lt;/Trigger&gt;

                            &lt;/Style.Triggers&gt;

                        &lt;/Style&gt;

                    &lt;/Image.Style&gt;

                 &lt;/Image&gt;

                &lt;!--FindDisabled--&gt;

            &lt;/Button&gt;

        &lt;/StackPanel&gt;



                        &lt;!-- DataSoruce Credential Prompt --&gt;

                        &lt;Grid Grid.Row="1" FlowDirection="LeftToRight"&gt;

                            &lt;Grid.RowDefinitions&gt;

                                &lt;RowDefinition Height="Auto" x:Name="PART_rowDefinitionFordsCredentialBlock"/&gt;

                            &lt;/Grid.RowDefinitions&gt;

                            &lt;ScrollViewer Name="PART_scorllDSCredentialBlock" HorizontalAlignment="Stretch" VerticalScrollBarVisibility="Auto"  HorizontalScrollBarVisibility="Disabled" Visibility="Collapsed"&gt;

                                &lt;StackPanel Name="PART_stackPaneldsCredential" Grid.Row="0" Background="LightBlue" Width="Auto" Height="Auto"&gt;

                                    &lt;Grid&gt;

                                        &lt;Grid.ColumnDefinitions&gt;

                                            &lt;ColumnDefinition Width="300*"/&gt;

                                            &lt;ColumnDefinition Width="100*"/&gt;

                                        &lt;/Grid.ColumnDefinitions&gt;

                                        &lt;Grid Background="#efefef" x:Name="PART_grid_DsCredentialblock" Grid.Column="0" Width="Auto"&gt;

                                            &lt;StackPanel Width="Auto" Name="PART_sPanel_Head"&gt;

                                            &lt;/StackPanel&gt;

                                        &lt;/Grid&gt;

                                        &lt;StackPanel Grid.Column="1" Background="#efefef"&gt;

                                            &lt;Button Content="{x:Static prop:Resources.btnViewReport}" HorizontalAlignment="Right" x:Name="PART_btnViewReport1" Width="Auto" Margin="0,5,20,5"/&gt;

                                        &lt;/StackPanel&gt;

                                    &lt;/Grid&gt;

                                &lt;/StackPanel&gt;

                            &lt;/ScrollViewer&gt;

                        &lt;/Grid&gt;





                        &lt;Grid Grid.Row="2" FlowDirection="LeftToRight"&gt;

                            &lt;!--Parameter prompt panel--&gt;

                            &lt;Grid.RowDefinitions&gt;

                                &lt;RowDefinition Height="Auto" x:Name="PART_rowDefinitionForParameterBlock"/&gt;

                            &lt;/Grid.RowDefinitions&gt;

                            &lt;ScrollViewer x:Name="PART_scrollViewerParamBlock" HorizontalAlignment="Stretch" VerticalScrollBarVisibility="Auto"  HorizontalScrollBarVisibility="Disabled" Visibility="Collapsed"&gt;

                                &lt;StackPanel Name="PART_stackPanelParameters" Grid.Row="0" Background="LightBlue" Width="Auto" Height="Auto"&gt;

                                    &lt;Grid&gt;

                                        &lt;Grid.ColumnDefinitions&gt;

                                            &lt;ColumnDefinition Width="Auto"/&gt;

                                            &lt;ColumnDefinition Width="100*"/&gt;

                                        &lt;/Grid.ColumnDefinitions&gt;



                                        &lt;Grid Background="#efefef" x:Name="PART_grid_ReportParameterBlock" Grid.Column="0" &gt;

                                            &lt;Grid.ColumnDefinitions&gt;

                                                &lt;ColumnDefinition Width="Auto"/&gt;

                                                &lt;ColumnDefinition Width="Auto"/&gt;

                                                &lt;ColumnDefinition Width="Auto"/&gt;

                                                &lt;ColumnDefinition Width="Auto"/&gt;

                                            &lt;/Grid.ColumnDefinitions&gt;

                                            &lt;Grid.RowDefinitions&gt;

                                            &lt;/Grid.RowDefinitions&gt;

                                        &lt;/Grid&gt;



                                        &lt;StackPanel Grid.Column="1" Background="#efefef"&gt;

                                            &lt;Button Content="{x:Static prop:Resources.btnViewReport}" HorizontalAlignment="Right" x:Name="PART_btnViewReport" Width="Auto" Margin="0,5,20,5"/&gt;

                                        &lt;/StackPanel&gt;

                                    &lt;/Grid&gt;

                                &lt;/StackPanel&gt;

                            &lt;/ScrollViewer&gt;

                        &lt;/Grid&gt;



                        &lt;Grid Name="PART_gridRenderingRegion" Grid.Row="3" Height="Auto" Margin="0,0,0,0" FlowDirection="LeftToRight"&gt;

                            &lt;Grid&gt;

                                &lt;Grid.RowDefinitions&gt;

                                    &lt;RowDefinition Height="Auto"&gt;&lt;/RowDefinition&gt;

                                    &lt;RowDefinition Height="*"&gt;&lt;/RowDefinition&gt;

                                &lt;/Grid.RowDefinitions&gt;

                                &lt;Grid Name="PART_ExceptionGrid" Grid.Row="0" Visibility="Collapsed" Background="LightBlue"&gt;

                                    &lt;Grid.ColumnDefinitions&gt;

                                        &lt;ColumnDefinition Width="24"&gt;&lt;/ColumnDefinition&gt;

                                        &lt;ColumnDefinition Width="749"&gt;&lt;/ColumnDefinition&gt;

                                        &lt;ColumnDefinition Width="0" /&gt;

                                    &lt;/Grid.ColumnDefinitions&gt;

                                    &lt;Image Source="{StaticResource error}" Height="24" Width="24" Margin="5,5,5,5" Grid.ColumnSpan="2" HorizontalAlignment="Left"&gt;&lt;/Image&gt;

                                    &lt;TextBlock Grid.Column="1" HorizontalAlignment="Stretch" VerticalAlignment="Center" Height="23" Margin="10,7,10,0" Width="730"&gt;

                        Report Viewer encountered some issues loading this report. Please click <Hyperlink x:Name="PART_hyperlink">here &lt;/Hyperlink&gt;  to see details of the issues.

                                    &lt;/TextBlock&gt;

                                &lt;/Grid&gt;

                                &lt;Grid Grid.Row="1" x:Name="PART_renderArea"&gt;

                                    &lt;Grid.ColumnDefinitions&gt;

                                        &lt;ColumnDefinition Width="Auto"&gt;&lt;/ColumnDefinition&gt;

                                        &lt;ColumnDefinition Width="Auto"&gt;&lt;/ColumnDefinition&gt;

                                        &lt;ColumnDefinition Width="*"&gt;&lt;/ColumnDefinition&gt;

                                    &lt;/Grid.ColumnDefinitions&gt;

                                    &lt;Grid Grid.Column="0" Height="Auto" Width="Auto" x:Name="PART_treeItemArea" Visibility="Collapsed"&gt;

                                        &lt;TreeView Name="PART_DocumentMap" Height="Auto" Width="Auto" BorderThickness="0"/&gt;

                                    &lt;/Grid&gt;

                                    &lt;GridSplitter x:Name="PART_viewerSpliter" Visibility="Collapsed" Grid.Column="1" ShowsPreview="True" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" ResizeBehavior="PreviousAndNext" Width="5" Background="#FFD4DBEB"/&gt;

                                    &lt;!--Viewer Page--&gt;

                                    &lt;ScrollViewer x:Name="PART_scrollViewer" Grid.Column="2" Height="Auto" Width="Auto" HorizontalScrollBarVisibility="Auto" VerticalScrollBarVisibility="Auto" HorizontalContentAlignment="Center" VerticalContentAlignment="Center"&gt;

                                        &lt;ScrollViewer.Resources&gt;

                                            &lt;DataTemplate x:Key="ReportViewerCellTeamplate"&gt;

                                                &lt;ContentControl Content="{Binding Path=CellBoundValue}"&gt;&lt;/ContentControl&gt;

                                            &lt;/DataTemplate&gt;

                                        &lt;/ScrollViewer.Resources&gt;

                                        &lt;StackPanel Orientation="Vertical" Name="PART_PageView" Height="Auto" Width="Auto" Background="White"&gt;

                                            &lt;StackPanel.LayoutTransform&gt;

                                                &lt;ScaleTransform x:Name="PART_Zoom"&gt;&lt;/ScaleTransform&gt;

                                            &lt;/StackPanel.LayoutTransform&gt;

                                            &lt;Border x:Name="PART_PageViewBody" Background="Transparent" Height="Auto" Width="Auto"&gt;

                                                &lt;StackPanel x:Name="PART_PageViewContainer" Background="Transparent" Height="Auto" Width="Auto"&gt;

                                                    &lt;Border Name="PART_PageHeaderBorder" Height="Auto" Width="Auto" Background="Transparent"&gt;

                                                        &lt;Canvas x:Name="PART_CanvasHeader" Visibility="Collapsed" Background="Transparent"/&gt;

                                                    &lt;/Border&gt;

                                                    &lt;Border Name="PART_PageBodyBorder" Height="Auto" Width="Auto" Background="Transparent"&gt;

                                                        &lt;Canvas x:Name="PART_canvasContentPage" Grid.Row="2" Background="Transparent" Width="Auto" Height="Auto"/&gt;

                                                    &lt;/Border&gt;

                                                    &lt;Border Name="PART_PageFooterBorder" Height="Auto" Width="Auto" Background="Transparent"&gt;

                                                        &lt;Canvas x:Name="PART_CanvasFooter" Visibility="Collapsed" Background="Transparent"/&gt;

                                                    &lt;/Border&gt;

                                                &lt;/StackPanel&gt;

                                            &lt;/Border&gt;

                                        &lt;/StackPanel&gt;

                                    &lt;/ScrollViewer&gt;

                                &lt;/Grid&gt;

                            &lt;/Grid&gt;



                        &lt;/Grid&gt;



                        &lt;Grid x:Name="PART_gridException" Grid.Row="4" Background="White" Visibility="Collapsed" FlowDirection="LeftToRight"&gt;

                            &lt;StackPanel  Orientation="Vertical" HorizontalAlignment="Center"&gt;

                                &lt;StackPanel Orientation="Horizontal" HorizontalAlignment="Center" &gt;

                                    &lt;Image Name="PART_imageException" Source="{StaticResource Exception}" Width="48" HorizontalAlignment="Center"/&gt;

                                    &lt;TextBlock Name="PART_textBlockException"&gt;&lt;/TextBlock&gt;

                                &lt;/StackPanel&gt;

                                &lt;ScrollViewer Name="PART_groupBoxExpandedExceptionScroll" Grid.Row="3" VerticalScrollBarVisibility="Auto" HorizontalScrollBarVisibility="Auto" Height="400"&gt;

                                    &lt;GroupBox Name="PART_groupBoxExpandedException" Width="420" Margin="5,0,5,0" FlowDirection="RightToLeft" BorderThickness="0"&gt;

                                        &lt;GroupBox.Header&gt;

                                            <ToggleButton Name="PART_toggleShowDetails" HorizontalAlignment="Right" Margin="0,0,0,0" VerticalAlignment="Bottom">Show Details</ToggleButton>

                                        &lt;/GroupBox.Header&gt;

                                        &lt;WrapPanel Name="PART_ShowError" Visibility="Collapsed" Width="auto"&gt;

                                            &lt;TextBox Name="PART_textBlockStackTrace" TextWrapping="Wrap" FlowDirection="LeftToRight" Width="390" IsReadOnly="True" &gt;&lt;/TextBox&gt;

                                            &lt;TextBox Name="PART_textBlockStackTraceMessage" TextWrapping="Wrap" FlowDirection="LeftToRight" Width="390" IsReadOnly="True" &gt;&lt;/TextBox&gt;

                                        &lt;/WrapPanel&gt;

                                    &lt;/GroupBox&gt;

                                &lt;/ScrollViewer&gt;

                            &lt;/StackPanel&gt;

                        &lt;/Grid&gt;



                        &lt;Grid x:Name="PART_gridLoadingIndicator" Grid.Row="5" Background="White" Visibility="Collapsed" FlowDirection="LeftToRight"&gt;

                            &lt;loading:LoadingIndicator&gt;&lt;/loading:LoadingIndicator&gt;

                        &lt;/Grid&gt;

                    &lt;/Grid&gt;

                    &lt;ControlTemplate.Triggers&gt;

                        &lt;Trigger Property="local:ReportViewer.ViewMode" Value="Normal"&gt;

                            &lt;Setter TargetName="PART_gridRenderingRegion" Property="Background" Value="White"/&gt;

                        &lt;/Trigger&gt;

                        &lt;Trigger Property="local:ReportViewer.ViewMode" Value="Print"&gt;

                            &lt;Setter TargetName="PART_gridRenderingRegion" Property="Background" Value="LightGray"/&gt;

                        &lt;/Trigger&gt;

                    &lt;/ControlTemplate.Triggers&gt;

                &lt;/ControlTemplate&gt;

            &lt;/Setter.Value&gt;

        &lt;/Setter&gt;

&lt;/Style&gt;



