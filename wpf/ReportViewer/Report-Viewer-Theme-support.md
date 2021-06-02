---
layout: post
title: ReportViewer Theme support | ReportViewer | WPF | Syncfusion
description: ReportViewer theme support in Syncfusion Essential Studio WPF ReportViewer Control, its elements, and more.
platform: wpf
control: ReportViewer
documentation: ug
---

# ReportViewer Theme support

Theme support for ReportViewer is provided by modifying the UserControl as a ControlTemplate. You can now modify the ReportViewer in your own style, by writing a customized control template for ReportViewer. 

To customize a ReportViewer, you have to modify the following control parts.

* PART_exportControl
* PART_comboBoxPageZoom
* PART_Zoom
* PART_ShowError
* PART_PageViewBody
* PART_PageFooterBorder
* PART_PageBodyBorder
* PART_PageHeaderBorder
* PART_scrollViewer
* PART_scrollDSCredentialBlock
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
* PART_viewerSplitter
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
* PART_buttonViewReport
* PART_buttonFind
* PART_button back
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
* PART_CredentialRow
* PART_parameterGridRow
* PART_viewerContentRow

The following code example illustrates a ReportViewer control template.

{% highlight xaml %}

    <Style TargetType="local:ReportViewer">
        <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="local:ReportViewer">
                <Grid x:Name="PART_MainGrid" Height="Auto" Margin="0,0,0,0" Background="Transparent">
                    <Grid.RowDefinitions>
                        <RowDefinition Name="PART_toolBarGridRow" Height="28"/>
                        <RowDefinition Name="PART_dsCredentialRow" Height="Auto"/>
                        <RowDefinition Name="PART_parameterGridRow" Height="Auto"/>
                        <RowDefinition Name="PART_viewerContentRow" Height="*" />
                        <RowDefinition Name="PART_gridExceptionRow" Height="0"/>
                        <RowDefinition Name="PART_loadingIndicatorRow" Height="0"/>
                    </Grid.RowDefinitions>
                    <!--Toolbar-->
                <StackPanel Name="PART_toolBar" Height="28" Orientation="Horizontal" Grid.ColumnSpan="2" Margin="0">
                    <StackPanel.Background>
                        <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                            <GradientStop Color="#FFFEFBF4" Offset="0.027"/>
                            <GradientStop Color="#FFEAEEEF" Offset="0.029"/>
                            <GradientStop Color="#FFDCE4F1" Offset="0.498"/>
                            <GradientStop Color="#FFE6EAF3" Offset="0.966"/>
                            <GradientStop Color="FloralWhite" Offset="0.968"/>
                            <GradientStop Color="#FFD4DBEB" Offset="0.503"/>
                        </LinearGradientBrush>
                    </StackPanel.Background>
                    <!--Print-->
                    <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPrint" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrint}" IsEnabled="False" Margin="2,3,2,3" >
                        <Image Stretch="None">
                        <Image.Style>
                            <Style>
                            <Style.Triggers>
                                <Trigger Property="Button.IsEnabled" Value="False">
                                    <Setter Property="Image.Source" Value="{StaticResource PrintDisabled}"/>
                                </Trigger>
                                <Trigger Property="Button.IsEnabled" Value="True">
                                    <Setter Property="Image.Source" Value="{StaticResource Print}"/>
                                </Trigger>
                            </Style.Triggers>
                            </Style>
                        </Image.Style>
                        </Image>
                    <!--PrintDisabled-->
                    </Button>
                    <ComboBox Name="PART_exportControl" Height="22" Width="35" Style="{StaticResource ExportComboBox}" ItemContainerStyle="{StaticResource ItemTemplate}" IsEnabled="False" ToolTip="Export" />
                        <Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6">
                        <Rectangle.Fill>
                            <LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5">
                                <GradientStop Color="#FFBCBCBC" Offset="0.508"/>
                                <GradientStop Color="White" Offset="0.525"/>
                            </LinearGradientBrush>
                        </Rectangle.Fill>
                        </Rectangle>
                    <!--Navigates to First-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonFirst" ToolTip="{x:Static prop:Resources.menuItemFirst}" Width="22" Height="22" IsEnabled="False" Margin="0,3,0,3" >
                            <Image Stretch="None">
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource First_NavDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource First_Nav}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--First_NavDisabled-->
                        </Button>
                    <!--Navigates to Previous-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPrevious" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrevious}" IsEnabled="False" Margin="2,3,2,3" >
                            <Image>
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource Previous_NavDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Previous_Nav}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--Previous_NavDisabled-->
                        </Button>
                    <!--Current Page-->
                        <TextBox Name="PART_textBoxCurrentPage" Width="60" Height="22" IsReadOnly="False" IsEnabled="False" BorderBrush="Gray" Margin="2,3,2,3" >
                        </TextBox>
                        <TextBlock Name="PART_labelOf" Width="Auto" VerticalAlignment="Center" Foreground="Black" Margin="2,3,5,3">of</TextBlock>
                    <!--Total number of pages-->
                        <TextBlock Name="PART_textBoxTotalPages" Width="Auto" xml:space="preserve" IsEnabled="false" Margin="2,3,5,3" VerticalAlignment="Center" Foreground="Black" TextAlignment="Center" HorizontalAlignment="Center"/>
                    <!--Navigates to Next-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonNext" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemNext}" IsEnabled="False" Margin="2,3,2,3" >
                            <Image Stretch="None">
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource Next_NavDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Next_Nav}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--Next_NavDisabled-->
                        </Button>
                    <!--Navigates to Last-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonLast" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemLast}" IsEnabled="False" Margin="2,3,2,3" >
                            <Image Stretch="None">
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource Last_NavDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Last_Nav}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--Last_NavDisabled-->
                        </Button>
                    <!--Back Parent Report-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_btnback" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipBack}" IsEnabled="True" Margin="2,3,2,3" Visibility="Collapsed">
                            <Image Source="{StaticResource ReportBack}" Stretch="None"/>
                        </Button>
                        <Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6">
                        <Rectangle.Fill>
                            <LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5">
                                <GradientStop Color="#FFBCBCBC" Offset="0.508"/>
                                <GradientStop Color="White" Offset="0.525"/>
                            </LinearGradientBrush>
                        </Rectangle.Fill>
                        </Rectangle>
                    <!--Zooming-->
                        <Border Name="PART_comboBoxExternalBorder" BorderBrush="Gray" Width="70" Height="22" ToolTip="{x:Static prop:Resources.toolTipZoom}" BorderThickness="0" Margin="2,3,2,3">
                            <ComboBox Name="PART_comboBoxPageZoom" Width="70" Height="22"  SelectedIndex="2" IsEnabled="False">
                                <ComboBoxItem Content="25%"/>
                                <ComboBoxItem Content="50%"/>
                                <ComboBoxItem Content="100%"/>
                                <ComboBoxItem Content="200%"/>
                                <ComboBoxItem Content="300%"/>
                                <ComboBoxItem Content="400%"/>
                                <ComboBoxItem Content="500%"/>
                            </ComboBox>
                        </Border>
                    <!--Prints Layout-->
                        <ToggleButton Style="{StaticResource ViewerToggleButtonStyle}" Name="PART_buttonPrintLayout" Width="22" Height="22" ToolTip="{x:Static prop:Resources.menuItemPrintLayout}" IsEnabled="False" Margin="2,3,2,3">
                            <Image Stretch="None" >
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="ToggleButton.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource PrintLayoutXDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="ToggleButton.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource PrintLayoutX}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--PrintLayoutXDisabled-->
                        </ToggleButton>
                    <!--Prints Setup-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonPageSetup" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipPageSetUp}" IsEnabled="False" Margin="2,3,2,3" Visibility="Visible" >
                            <Image Source="{StaticResource PageSetup}" Stretch="None"/>
                        <!--PrintSetupDisabled-->
                        </Button>
                        <Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6">
                        <Rectangle.Fill>
                            <LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5">
                                <GradientStop Color="#FFBCBCBC" Offset="0.508"/>
                                <GradientStop Color="White" Offset="0.525"/>
                            </LinearGradientBrush>
                        </Rectangle.Fill>
                        </Rectangle>
                    <!--Refresh -->
                        <Button Style="{StaticResource ButtonStyle}" Height="22" Width="22" Name="PART_buttonRefresh" ToolTip="{x:Static prop:Resources.menuItemRefresh}" IsEnabled="False" Margin="2,3,2,3">
                            <Image HorizontalAlignment="Center" VerticalAlignment="Center" Height="16" Width="16" Stretch="Fill" >
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource RefreshDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Refresh}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--RefreshDisabled-->
                        </Button>
                    <!--Shows/Hides Document map-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonShowOrHideDocumentMap" Width="22" ToolTip="{x:Static prop:Resources.menuItemShowHide}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3">
                            <Image Source="{StaticResource ShowHideDisabled}" Stretch="None" HorizontalAlignment="Center" VerticalAlignment="Center" Height="16" Width="16"/>
                        <!--ShowHideDisabled-->
                        </Button>
                    <!--Parameterised query-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonParameters" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipParameters}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3" Background="Transparent" >
                            <Image Stretch="None" >
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource ParametersDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Parameters}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--ParametersDisabled-->
                        </Button>
                        <Rectangle HorizontalAlignment="Center"  Height="21.599" VerticalAlignment="Center" Width="1.6">
                        <Rectangle.Fill>
                            <LinearGradientBrush EndPoint="0.662,0.5" StartPoint="0.338,0.5">
                                <GradientStop Color="#FFBCBCBC" Offset="0.508"/>
                                <GradientStop Color="White" Offset="0.525"/>
                            </LinearGradientBrush>
                        </Rectangle.Fill>
                        </Rectangle>
                        <TextBox Name="PART_textBoxFind" Width="60" Height="22" xml:space="preserve" IsEnabled="False" BorderBrush="Gray" ToolTip="{x:Static prop:Resources.toolTipFindTextBox}" Margin="2,3,2,3" Visibility="Collapsed"/>
                    <!--Find-->
                        <Button Style="{StaticResource ButtonStyle}" Name="PART_buttonFind" Width="22" Height="22" ToolTip="{x:Static prop:Resources.toolTipFind}" IsEnabled="False" Visibility="Collapsed" Margin="2,3,2,3">
                            <Image Stretch="None">
                            <Image.Style>
                                <Style>
                                <Style.Triggers>
                                    <Trigger Property="Button.IsEnabled" Value="False">
                                        <Setter Property="Image.Source" Value="{StaticResource FindDisabled}"/>
                                    </Trigger>
                                    <Trigger Property="Button.IsEnabled" Value="True">
                                        <Setter Property="Image.Source" Value="{StaticResource Find}"/>
                                    </Trigger>
                                </Style.Triggers>
                                </Style>
                            </Image.Style>
                            </Image>
                        <!--FindDisabled-->
                        </Button>
                </StackPanel>
            <!-- DataSoruce Credential Prompt -->
                <Grid Grid.Row="1" FlowDirection="LeftToRight">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" x:Name="PART_rowDefinitionFordsCredentialBlock"/>
                    </Grid.RowDefinitions>
                    <ScrollViewer Name="PART_scorllDSCredentialBlock" HorizontalAlignment="Stretch" VerticalScrollBarVisibility="Auto"  HorizontalScrollBarVisibility="Disabled" Visibility="Collapsed">
                        <StackPanel Name="PART_stackPaneldsCredential" Grid.Row="0" Background="LightBlue" Width="Auto" Height="Auto">
                            <Grid>
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="300*"/>
                                    <ColumnDefinition Width="100*"/>
                                </Grid.ColumnDefinitions>
                                <Grid Background="#efefef" x:Name="PART_grid_DsCredentialblock" Grid.Column="0" Width="Auto">
                                    <StackPanel Width="Auto" Name="PART_sPanel_Head">
                                    </StackPanel>
                                </Grid>
                                <StackPanel Grid.Column="1" Background="#efefef">
                                    <Button Content="{x:Static prop:Resources.btnViewReport}" HorizontalAlignment="Right" x:Name="PART_btnViewReport1" Width="Auto" Margin="0,5,20,5"/>
                                </StackPanel>
                            </Grid>
                        </StackPanel>
                    </ScrollViewer>
                </Grid>
                <Grid Grid.Row="2" FlowDirection="LeftToRight">
                <!--Parameter prompt panel-->
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" x:Name="PART_rowDefinitionForParameterBlock"/>
                    </Grid.RowDefinitions>
                    <ScrollViewer x:Name="PART_scrollViewerParamBlock" HorizontalAlignment="Stretch" VerticalScrollBarVisibility="Auto"  HorizontalScrollBarVisibility="Disabled" Visibility="Collapsed">
                        <StackPanel Name="PART_stackPanelParameters" Grid.Row="0" Background="LightBlue" Width="Auto" Height="Auto">
                            <Grid>
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="Auto"/>
                                    <ColumnDefinition Width="100*"/>
                                </Grid.ColumnDefinitions>
                                <Grid Background="#efefef" x:Name="PART_grid_ReportParameterBlock" Grid.Column="0" >
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="Auto"/>
                                        <ColumnDefinition Width="Auto"/>
                                        <ColumnDefinition Width="Auto"/>
                                        <ColumnDefinition Width="Auto"/>
                                    </Grid.ColumnDefinitions>
                                    <Grid.RowDefinitions>
                                    </Grid.RowDefinitions>
                                </Grid>
                                <StackPanel Grid.Column="1" Background="#efefef">
                                    <Button Content="{x:Static prop:Resources.btnViewReport}" HorizontalAlignment="Right" x:Name="PART_btnViewReport" Width="Auto" Margin="0,5,20,5"/>
                                </StackPanel>
                            </Grid>
                        </StackPanel>
                    </ScrollViewer>
                </Grid>
                <Grid Name="PART_gridRenderingRegion" Grid.Row="3" Height="Auto" Margin="0,0,0,0" FlowDirection="LeftToRight">
                    <Grid>
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"></RowDefinition>
                            <RowDefinition Height="*"></RowDefinition>
                        </Grid.RowDefinitions>
                        <Grid Name="PART_ExceptionGrid" Grid.Row="0" Visibility="Collapsed" Background="LightBlue">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="24"></ColumnDefinition>
                                <ColumnDefinition Width="749"></ColumnDefinition>
                                <ColumnDefinition Width="0" />
                            </Grid.ColumnDefinitions>
                            <Image Source="{StaticResource error}" Height="24" Width="24" Margin="5,5,5,5" Grid.ColumnSpan="2" HorizontalAlignment="Left">
                            </Image>
                            <TextBlock Grid.Column="1" HorizontalAlignment="Stretch" VerticalAlignment="Center" Height="23" Margin="10,7,10,0" Width="730">
                                ReportViewer encountered some issues loading this report. Please click <Hyperlink x:Name="PART_hyperlink">here </Hyperlink>  to see details of the issues.
                            </TextBlock>
                        </Grid>
                        <Grid Grid.Row="1" x:Name="PART_renderArea">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="Auto"></ColumnDefinition>
                                <ColumnDefinition Width="Auto"></ColumnDefinition>
                                <ColumnDefinition Width="*"></ColumnDefinition>
                            </Grid.ColumnDefinitions>
                            <Grid Grid.Column="0" Height="Auto" Width="Auto" x:Name="PART_treeItemArea" Visibility="Collapsed">
                                <TreeView Name="PART_DocumentMap" Height="Auto" Width="Auto" BorderThickness="0"/>
                            </Grid>
                            <GridSplitter x:Name="PART_viewerSpliter" Visibility="Collapsed" Grid.Column="1" ShowsPreview="True" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" ResizeBehavior="PreviousAndNext" Width="5" Background="#FFD4DBEB"/>
                            <!--Viewer Page-->
                                <ScrollViewer x:Name="PART_scrollViewer" Grid.Column="2" Height="Auto" Width="Auto" HorizontalScrollBarVisibility="Auto" VerticalScrollBarVisibility="Auto" HorizontalContentAlignment="Center" VerticalContentAlignment="Center">
                                    <ScrollViewer.Resources>
                                        <DataTemplate x:Key="ReportViewerCellTeamplate">
                                            <ContentControl Content="{Binding Path=CellBoundValue}"></ContentControl>
                                        </DataTemplate>
                                    </ScrollViewer.Resources>
                                    <StackPanel Orientation="Vertical" Name="PART_PageView" Height="Auto" Width="Auto" Background="White">
                                        <StackPanel.LayoutTransform>
                                            <ScaleTransform x:Name="PART_Zoom"></ScaleTransform>
                                        </StackPanel.LayoutTransform>
                                        <Border x:Name="PART_PageViewBody" Background="Transparent" Height="Auto" Width="Auto">
                                            <StackPanel x:Name="PART_PageViewContainer" Background="Transparent" Height="Auto" Width="Auto">
                                                <Border Name="PART_PageHeaderBorder" Height="Auto" Width="Auto" Background="Transparent">
                                                    <Canvas x:Name="PART_CanvasHeader" Visibility="Collapsed" Background="Transparent"/>
                                                </Border>
                                                <Border Name="PART_PageBodyBorder" Height="Auto" Width="Auto" Background="Transparent">
                                                    <Canvas x:Name="PART_canvasContentPage" Grid.Row="2" Background="Transparent" Width="Auto" Height="Auto"/>
                                                </Border>
                                                <Border Name="PART_PageFooterBorder" Height="Auto" Width="Auto" Background="Transparent">
                                                    <Canvas x:Name="PART_CanvasFooter" Visibility="Collapsed" Background="Transparent"/>
                                                </Border>
                                            </StackPanel>
                                        </Border>
                                    </StackPanel>
                                </ScrollViewer>
                            </Grid>
                        </Grid>
                    </Grid>
                    <Grid x:Name="PART_gridException" Grid.Row="4" Background="White" Visibility="Collapsed" FlowDirection="LeftToRight">
                        <StackPanel  Orientation="Vertical" HorizontalAlignment="Center">
                            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" >
                                <Image Name="PART_imageException" Source="{StaticResource Exception}" Width="48" HorizontalAlignment="Center"/>
                                <TextBlock Name="PART_textBlockException">
                                </TextBlock>
                            </StackPanel>
                            <ScrollViewer Name="PART_groupBoxExpandedExceptionScroll" Grid.Row="3" VerticalScrollBarVisibility="Auto" HorizontalScrollBarVisibility="Auto" Height="400">
                                <GroupBox Name="PART_groupBoxExpandedException" Width="420" Margin="5,0,5,0" FlowDirection="RightToLeft" BorderThickness="0">
                                    <GroupBox.Header>
                                        <ToggleButton Name="PART_toggleShowDetails" HorizontalAlignment="Right" Margin="0,0,0,0" VerticalAlignment="Bottom">Show Details</ToggleButton>
                                    </GroupBox.Header>
                                    <WrapPanel Name="PART_ShowError" Visibility="Collapsed" Width="auto">
                                        <TextBox Name="PART_textBlockStackTrace" TextWrapping="Wrap" FlowDirection="LeftToRight" Width="390" IsReadOnly="True" ></TextBox>
                                        <TextBox Name="PART_textBlockStackTraceMessage" TextWrapping="Wrap" FlowDirection="LeftToRight" Width="390" IsReadOnly="True" ></TextBox>
                                    </WrapPanel>
                                </GroupBox>
                            </ScrollViewer>
                        </StackPanel>
                    </Grid>
                    <Grid x:Name="PART_gridLoadingIndicator" Grid.Row="5" Background="White" Visibility="Collapsed" FlowDirection="LeftToRight">
                        <loading:LoadingIndicator></loading:LoadingIndicator>
                    </Grid>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="local:ReportViewer.ViewMode" Value="Normal">
                        <Setter TargetName="PART_gridRenderingRegion" Property="Background" Value="White"/>
                    </Trigger>
                    <Trigger Property="local:ReportViewer.ViewMode" Value="Print">
                        <Setter TargetName="PART_gridRenderingRegion" Property="Background" Value="LightGray"/>
                    </Trigger>
                </ControlTemplate.Triggers>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
        </Setter>
    </Style>
	
{%endhighlight%}