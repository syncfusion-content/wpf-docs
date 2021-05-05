---
layout: post
title: Custom Node Style in WPF Gantt control | Syncfusion
description: Learn about Custom Node Style support in Syncfusion WPF Gantt control and more.
platform: wpf
control: Gantt
documentation: ug
---

# Custom Node Style in WPF Gantt

Custom node style enables you to design your own style to the nodes that will be displayed in the Gantt. You can also customize the progress bar of the Task Node.Currently Gantt Control supports three types of node. They are:

* Header Node 
* Task Node
* Milestone

You can apply custom styles for all the three nodes. The basic functionalities of the Gantt nodes like resizing, drag and drop and tooltip are available only when the custom node style has the built-in node style’s such as drag and drop the thumb and resizing the thumbs. Otherwise the custom node will work properly, but you cannot access these features of Gantt. 

## Use Case Scenarios

You can customize the node to give a similar look and feel of your product. For example if you are from a steel company, then you can add a style that gives steel rod like look and feel to the node. 

You can also design the node based on your organization’s logo.

## Adding Custom Node Style to an Application 

The following are the steps to add custom node style to an application:

1. Define a style as needed with the target type for each node type as given in the following table:

### Custom Node Types

<table>
<tr>
<th>
Node Type</th><th>
Target Type</th></tr>
<tr>
<td>
Header Node</td><td>
HeaderNode</td></tr>
<tr>
<td>
Task Node</td><td>
GanttNode</td></tr>
<tr>
<td>
Milestone</td><td>
MileStone</td></tr>
</table>


The following code illustrates how to define style:


{% highlight xaml %}

<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                    xmlns:gantt="http://schemas.syncfusion.com/wpf"
                    xmlns:chart="clr-namespace:Syncfusion.Windows.Controls.Gantt.Chart;assembly=Syncfusion.Gantt.Wpf" >

    <!-- Header Node style-->
    <Style TargetType="chart:HeaderNode">
        <Setter Property="MaxHeight" Value="24"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="chart:HeaderNode">
                    <Border Background="{TemplateBinding Background}" Name="PART_HeaderBorder" 
                            BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="0">
                        <Grid Width="{TemplateBinding NodeWidth}" VerticalAlignment="Center">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="10" />
                                <ColumnDefinition Width="*" />
                                <ColumnDefinition Width="10" />
                            </Grid.ColumnDefinitions>
                            <Rectangle HorizontalAlignment="Left" Grid.Column="1" Height="6.4" 
                                       VerticalAlignment="Top" 
                                       Width="{TemplateBinding NodeWidth}" 
                                       Stroke="#FF111111">
                                <Rectangle.Fill>
                                    <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                                        <GradientStop Color="#FF414141" Offset="0" />
                                        <GradientStop Color="#FF6D6D6D" Offset="0.087" />
                                        <GradientStop Color="#FF767676" Offset="0.304" />
                                        <GradientStop Color="Black" Offset="0.957" />
                                        <GradientStop Color="#FF343434" Offset="1" />
                                    </LinearGradientBrush>
                                </Rectangle.Fill>
                            </Rectangle>
                            <Path Data="M0.3,0.3 L9.834909,0.30036073 9.8351226,5.9832297 5.0695471,10.734966 0.32096295,5.9863821 z"
                                  HorizontalAlignment="Left"
                                  Grid.Column="0"
                                  Height="11.435"
                                  Stretch="Fill"
                                  Stroke="#FF111111"
                                  VerticalAlignment="Top"
                                  Width="10.135">
                                <Path.Fill>
                                    <LinearGradientBrush EndPoint="1.009,0.985" StartPoint="0.339,0.286">
                                        <GradientStop Color="DimGray" Offset="0.008" />
                                        <GradientStop Color="#FF7F7F7F" Offset="0.511" />
                                        <GradientStop Color="#FF2A2A2A" Offset="1" />
                                    </LinearGradientBrush>
                                </Path.Fill>
                            </Path>
                            <Path Data="M0.3,0.3 L9.834909,0.30036073 9.8351226,5.9832297 5.0695471,10.734966 0.32096295,5.9863821 z"
                                  HorizontalAlignment="Left"
                                  Grid.Column="2"
                                  Height="11.435"
                                  Stretch="Fill"
                                  Stroke="#FF111111"
                                  VerticalAlignment="Top"
                                  Width="10.135">
                                <Path.Fill>
                                    <LinearGradientBrush EndPoint="1.009,0.985" StartPoint="0.339,0.286">
                                        <GradientStop Color="DimGray" Offset="0.008" />
                                        <GradientStop Color="#FF7F7F7F" Offset="0.511" />
                                        <GradientStop Color="#FF2A2A2A" Offset="1" />
                                    </LinearGradientBrush>
                                </Path.Fill>
                            </Path>
                        </Grid>
                    </Border>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>

    <!-- Task Node style-->
    <Style x:Key="TaskNode" TargetType="{x:Type chart:GanttNode}">
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type  chart:GanttNode}">
                    <Border Name="PART_Border" Height="18" VerticalAlignment="Center" BorderThickness="0.5" BorderBrush="#FF4D4D4D">
                        <Border.Background>
                            <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                                <GradientStop Color="#FFF6F6F6" Offset="0"/>
                                <GradientStop Color="#FFC5C5C5" Offset="1"/>
                            </LinearGradientBrush>
                        </Border.Background>
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="Auto" />
                                <ColumnDefinition Width="*" />
                                <ColumnDefinition Width="Auto" />
                            </Grid.ColumnDefinitions>
                            <!-- To access the drag and drop feature, have the thumb with specified name -->
                            <Thumb Cursor="SizeAll" x:Name="PART_DragDropThumb"  Grid.Column="0" Grid.ColumnSpan="3">
                                <Thumb.Template>
                                    <ControlTemplate>
                                        <Border Background="Transparent"/>
                                    </ControlTemplate>
                                </Thumb.Template>
                            </Thumb>

                            <Border HorizontalAlignment="Left" 
                                    VerticalAlignment="Center" 
                                    Width="{TemplateBinding ProgressWidth}" 
                                    Grid.Column="0" 
                                    Grid.ColumnSpan="3">
                                <Grid HorizontalAlignment="Stretch" Width="{TemplateBinding ProgressWidth}">
                                    <Rectangle HorizontalAlignment="Stretch" Height="12" 
                                               Stroke="#FFD26202" 
                                               VerticalAlignment="Center">
                                        <Rectangle.Fill>
                                            <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                                                <GradientStop Color="#FFFEB300" Offset="0"/>
                                                <GradientStop Color="#FFFE7600" Offset="1"/>
                                            </LinearGradientBrush>
                                        </Rectangle.Fill>
                                    </Rectangle>
                                    <!-- To access the progress resizing feature, have the thumb with specified name -->
                                    <Thumb Cursor="SizeWE" x:Name="PART_ProgressThumb" HorizontalAlignment="Right">
                                        <Thumb.Template>
                                            <ControlTemplate>
                                                <Border Background="Transparent" BorderBrush="Transparent">
                                                    <Rectangle Height="2" Width="5" Fill="Transparent" />
                                                </Border>
                                            </ControlTemplate>
                                        </Thumb.Template>
                                    </Thumb>
                                </Grid>
                            </Border>

                            <!-- To access the resizing feature, have the thumb with the specified name -->
                            <Thumb Cursor="ScrollE" Grid.Column="2" x:Name="PART_RightThumb" HorizontalAlignment="Right">
                                <Thumb.Template>
                                    <ControlTemplate>
                                        <Rectangle HorizontalAlignment="Right" 
                                                   Height="20" 
                                                   VerticalAlignment="Center" 
                                                   Width="6" 
                                                   Stroke="#FFD26202">
                                            <Rectangle.Fill>
                                                <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                                                    <GradientStop Color="#FFFEB300" Offset="0"/>
                                                    <GradientStop Color="#FFFE7600" Offset="1"/>
                                                </LinearGradientBrush>
                                            </Rectangle.Fill>
                                        </Rectangle>
                                    </ControlTemplate>
                                </Thumb.Template>
                            </Thumb>

                            <!-- To access the resizing feature, have the thumb with the specified name -->
                            <Thumb Cursor="SizeWE" Grid.Column="0" x:Name="PART_LeftThumb" HorizontalAlignment="Left">
                                <Thumb.Template>
                                    <ControlTemplate>
                                        <Border Background="Transparent"
                                                BorderBrush="Transparent" 
                                                BorderThickness="0" 
                                                Width="4" Height="20"/>
                                    </ControlTemplate>
                                </Thumb.Template>
                            </Thumb>
                        </Grid>
                    </Border>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>

 <!--Milestone style-->
    <Style x:Key="MileStone" TargetType="chart:MileStone">
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="chart:MileStone">
                    <Grid>
                        <Path Stretch="Fill" 
                              Data="F1 M 551.156,416.878L 552.734,419.766L 555.621,421.344L 552.734,422.922L 551.156,425.81L 549.577,422.922L 546.69,421.344L 549.577,419.766L 551.156,416.878 Z" 
                              HorizontalAlignment="Left" 
                              Height="19" Width="19"
                              VerticalAlignment="Center" 
                              Stroke="#FFD26202">
                            <Path.Fill>
                                <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                                    <GradientStop Color="#FFFEB300" Offset="0"/>
                                    <GradientStop Color="#FFFE7600" Offset="1"/>
                                </LinearGradientBrush>
                            </Path.Fill>
                        </Path>
                    </Grid>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
</ResourceDictionary>

{% endhighlight  %}

1. Add the style as a resource to the Gantt control in your application.

The following code illustrates how to add the styles to the application:


{% highlight xaml %}

<sync:GanttControl Grid.Row="1" x:Name="Gantt" 
                   ItemsSource="{Binding GanttItemSource}"
                   ToolTipTemplate="{StaticResource toolTipTemplate}"
                   VisualStyle="Office2010Silver">
    <sync:GanttControl.TaskAttributeMapping>
        <sync:TaskAttributeMapping TaskIdMapping="Id"
                                   TaskNameMapping="Name"
                                   StartDateMapping="StDate" 
                                   ChildMapping="ChildTask"
                                   FinishDateMapping="EndDate"
                                   DurationMapping="Duration"
                                   ProgressMapping="Complete"
                                   PredecessorMapping="Predecessor">
        </sync:TaskAttributeMapping>
    </sync:GanttControl.TaskAttributeMapping>
    
    <sync:GanttControl.Resources>
        <Style TargetType="chart:GanttNode" BasedOn="{StaticResource TaskNode}"/>
        <Style TargetType="chart:MileStone" BasedOn="{StaticResource MileStone}"/>
    </sync:GanttControl.Resources>
</sync:GanttControl>

{% endhighlight  %}

![Custom-Node-Style_img1](Custom-Node-Style_images/Custom-Node-Style_img1.png)



_Custom Node Style_



![Custom-Node-Style_img2](Custom-Node-Style_images/Custom-Node-Style_img2.png)



Custom Node Style
{:.caption}

## Samples Link

To view samples: 

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
3. Click Run Samples for WPF under User Interface Edition panel.
4. Select Gantt.
5. Expand the Styles item in the Sample Browser.
6. Choose the Custom Node Style sample to launch.



