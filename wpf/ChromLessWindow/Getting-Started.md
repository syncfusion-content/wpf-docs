---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: ChromelessWindow
documentation: ug
---

# Getting Started

This section guides you on getting started with ChromelessWindow control. It describes the following:

## Create ChromelessWindow Control

You can create a ChromelessWindow by using the following XAML code example.
{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1" 

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300" >

</shared:ChromelessWindow>

{% endhighlight  %}

## Create a Custom ChromelessWindow Control

To create a custom ChromelessWindow, follow the below steps:

1. Use the following code to create a transparent window.


{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="300" Width="300"  >

</ shared:ChromelessWindow>

{% endhighlight  %}

2. Now you can write your own ChromelessWindowTemplate to customize your ChromelessWindow. For example, the following code can be used to create a ControlTemplate for the ChromelessWindow.

{% highlight html %}

[XAML]



<ControlTemplate x:Key="ChromelessWindowTemplate" TargetType="{x:Type shared:ChromelessWindow}">

    <AdornerDecorator>

        <Border Name="OuterBorder" Background="#F1401013" BorderThickness="{Binding ElementName=ResizeThicknessSlider,Path=Value}"CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}"  BorderBrush="#401013">

            <Border  Name="ContentAreaBorder" CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}" >

                <ContentPresenter Grid.Row="1"  Margin="0,0,0,0"  />

            </Border>

        </Border>

    </AdornerDecorator>

</ControlTemplate>

{% endhighlight %}

> Note: All the templates should be written in App.xaml file only.



3. Now to apply the custom template you have created, and then set the Template property, refer the following code example.


{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

    xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

    Title="ChromelessWindowTestSample"  Height="300" Width="300" 

Template="{StaticResource ChromelessWindowTemplate}” >

<Grid>

<TextBlock> Hello World! </TextBlock>

</Grid>

</ shared:ChromelessWindow>

{% endhighlight %}

This displays a ChromelessWindow with "Hello World" in it.



4. Now if you wish to include a TitleBar, you need to write another template for the TitleBar. The following code (for example) can be used to create a TitleBarTemplate.


{% highlight html %}
[XAML]



<ControlTemplate x:Key="Titlebartemplate" TargetType="{x:Type shared:TitleBar}">

    <Border Name="border" Background="#AA161616" Height="30"   >

        <ContentPresenter HorizontalAlignment="Stretch" VerticalAlignment="Bottom" Margin="0,0,0,0"/>

    </Border>

</ControlTemplate>
{% endhighlight %}


> Note: The drag and drop feature for the ChromelessWindow is available only with the TitleBar. You will have to include a TitleBar into your ChromelessWindow, to incorporate this feature. Also it is necessary to specify the name of the TitleBar as "PART_TitleBar", to enable the drag and drop feature.



5. The following code indicates the modified ControlTemplate for the ChromelessWindow, which includes the TitleBar.


{% highlight html %}
[XAML]



<ControlTemplate x:Key="ChromelessWindowTemplate" TargetType="{x:Type shared:ChromelessWindow}">

    <AdornerDecorator>

        <Border Name="OuterBorder" Background="#F1401013" BorderThickness="{Binding ElementName=ResizeThicknessSlider,Path=Value}" CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}"  BorderBrush="#401013">

            <Grid>

                <Grid.RowDefinitions>

                    <RowDefinition Height="30"/>

                    <RowDefinition Height="*"/>

                </Grid.RowDefinitions>

                <shared:TitleBar Name="PART_TitleBar" Grid.Row="0" Template="{StaticResource Titlebartemplate}" >

                    <Grid VerticalAlignment="Top" Height="30">

                        <StackPanel Orientation="Horizontal">

                            <Image x:Name="PART_Icon" Source="{Binding RelativeSource={RelativeSource FindAncestor,  AncestorType={x:Type shared:ChromelessWindow}}, Path=Icon}" VerticalAlignment="Center"  HorizontalAlignment="Left" Margin="4,4,2,4"  MaxWidth="16" MaxHeight="16" MinWidth="16" MinHeight="16" />

                            <ContentControl Foreground="{TemplateBinding Foreground}"  Content="{TemplateBinding Title}" VerticalAlignment="Center" HorizontalAlignment="Left" x:Name="TitlePresenter" Margin="5,5,5,5" />

                        </StackPanel>

                    </Grid>

                </shared:TitleBar>

                <Border Grid.Row="1" Name="ContentAreaBorder"  CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}" >

                    <ContentPresenter Grid.Row="1"  Margin="0,0,0,0"  />

                </Border>

            </Grid>

        </Border>

    </AdornerDecorator>

</ControlTemplate>


{% endhighlight  %}
6. ChromelessWindow provides options to customize the TitleBar Buttons by writing custom templates for the Maximize, Minimize, Restore and Close Buttons and include these Buttons in the TitleBar.

For example, the following code can be used to create a ControlTemplate for the MinimizeButton.

{% highlight html %}

[XAML]



<ControlTemplate x:Key="MinimizeIcon" TargetType="{x:Type Button}">

    <Border Name="minborder4"   BorderThickness="1" CornerRadius="1" Background="Transparent"  Height="20" Width="22"  Margin="1,0,1,5">

        <Canvas Width="9" Height="9">

            <Line X1="0" X2="8"  Y1="6" Y2="6" Stroke="White" StrokeThickness="1"/>

            <Line X1="0" X2="8"  Y1="7" Y2="7" Stroke="White" StrokeThickness="1"/>

            <Line X1="0" X2="8"  Y1="8" Y2="8" Stroke="White" StrokeThickness="1"/>

        </Canvas>

    </Border>

    <ControlTemplate.Triggers>

        <Trigger Property="IsMouseOver" Value="true">

            <Setter TargetName="minborder4" Property="Background" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#66FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

            <Setter TargetName="minborder4" Property="BorderBrush" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#00FFFFFF" Offset="0"/>

                        <GradientStop Color="#7FFFFFFF" Offset="0.1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

        <Trigger Property="IsPressed" Value="true">

            <Setter TargetName="minborder4" Property="Background">

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#99FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

    </ControlTemplate.Triggers>

</ControlTemplate>

{% endhighlight %}

For example, the following code can be used to create a ControlTemplate for the RestoreButton.

{% highlight html %}

[XAML]



<ControlTemplate x:Key="RestoreIcon" TargetType="{x:Type Button}">

    <Border Name="resborder4"   BorderThickness="1" CornerRadius="1" Background="Transparent"  Height="20" Width="20"  Margin="1,0,1,5">

        <Canvas Width="9" Height="8">

            <Line X1="2" X2="9"  Y1="1.5" Y2="1.5" Stroke="White" StrokeThickness="1"/>

            <Rectangle Canvas.Left="6" Canvas.Top="2"  Stroke="White" Width="3" Height="5" StrokeThickness="1"/>

            <Line X1="3" X2="8"  Y1="3" Y2="3" Stroke="White" StrokeThickness="1"/>

            <Line X1="2" X2="8"  Y1="7" Y2="7" Stroke="White" StrokeThickness="1"/>

            <Line X1="0" X2="7"  Y1="2.5" Y2="2.5" Stroke="White" StrokeThickness="1"/>

            <Rectangle Canvas.Left="0" Canvas.Top="3" Stroke="White" Width="7" Height="5" StrokeThickness="1"/>

            <Line X1="1" X2="6"  Y1="4" Y2="4" Stroke="White" StrokeThickness="1"/>

            <Line X1="0" X2="6"  Y1="8" Y2="8" Stroke="White" StrokeThickness="1"/>

        </Canvas>

    </Border>

    <ControlTemplate.Triggers>

        <Trigger Property="IsMouseOver" Value="true">

            <Setter TargetName="resborder4" Property="Background" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#66FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

            <Setter TargetName="resborder4" Property="BorderBrush" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#00FFFFFF" Offset="0"/>

                        <GradientStop Color="#7FFFFFFF" Offset="0.1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

        <Trigger Property="IsPressed" Value="true">

            <Setter TargetName="resborder4" Property="Background">

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#99FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>



    </ControlTemplate.Triggers>

</ControlTemplate>

{% endhighlight %}

For example, the following code can be used to create a ControlTemplate for the MaximizeButton.


{% highlight html %}
[XAML]



<ControlTemplate x:Key="MaximizeIcon" TargetType="{x:Type Button}">

    <Border Name="maxborder4" BorderThickness="1" CornerRadius="1" Background="Transparent" Height="20" Width="22" HorizontalAlignment="Right" Margin="1,2,1,5">

        <Canvas Width="9" Height="9">

            <Rectangle Fill="Transparent" Stroke="White" Width="9" Height="7"/>

            <Rectangle Canvas.Top="1" Canvas.Left="1" Fill="{TemplateBinding Background}" Stroke="{TemplateBinding Background}" Width="7" Height="3" Margin="0,2,0,0"/>

            <Line X1="0" X2="8"  Y1="8" Y2="8" Stroke="Transparent" StrokeThickness="1"/>

        </Canvas>

    </Border>

    <ControlTemplate.Triggers>

        <Trigger Property="IsMouseOver" Value="true">

            <Setter TargetName="maxborder4" Property="Background" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#66FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

            <Setter TargetName="maxborder4" Property="BorderBrush" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#00FFFFFF" Offset="0"/>

                        <GradientStop Color="#7FFFFFFF" Offset="0.1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

        <Trigger Property="IsPressed" Value="true">

            <Setter TargetName="maxborder4" Property="Background">

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#99FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

    </ControlTemplate.Triggers>

</ControlTemplate>

{% endhighlight  %}

For example, the following code can be used to create a ControlTemplate for the CloseButton.

{% highlight html %}

[XAML]



<ControlTemplate x:Key="CloseIcon" TargetType="{x:Type Button}">

    <Border Name="closeborder4" BorderThickness="1" CornerRadius="1" Background="Transparent" Height="20" Width="22" HorizontalAlignment="Right" Margin="1,0,1,5">

        <Canvas Width="12" Height="9">

            <Path Fill="#FFFFFFFF" Stretch="Fill" Stroke="#FF000000" Width="11" Height="10" Canvas.Left="0.875" Data="M284.20002,237.66667 L287.59967,237.66667 288.733,239.46634 290.06676,237.53303 293.0665,237.53303 293.0665,238.99951 290.59978,241.26536 290.59978,242.26457 293.19982,244.59636 293.19982,245.66247 290.13311,245.72877 288.74141,243.79678 287.39973,245.59584 284.26634,245.59584 284.26634,244.663 286.66638,242.39751 286.66638,241.26476 284.19968,238.79938 z"/>

        </Canvas>

    </Border>

    <ControlTemplate.Triggers>

        <Trigger Property="IsMouseOver" Value="true">

            <Setter TargetName="closeborder4" Property="Background" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#66FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

            <Setter TargetName="closeborder4" Property="BorderBrush" >

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#00FFFFFF" Offset="0"/>

                        <GradientStop Color="#7FFFFFFF" Offset="0.1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

        <Trigger Property="IsPressed" Value="true">

            <Setter TargetName="closeborder4" Property="Background">

                <Setter.Value>

                    <LinearGradientBrush EndPoint="0,1" StartPoint="0,0">

                        <GradientStop Color="#99FFFFFF" Offset="0"/>

                        <GradientStop Color="#00FFFFFF" Offset="1"/>

                    </LinearGradientBrush>

                </Setter.Value>

            </Setter>

        </Trigger>

    </ControlTemplate.Triggers>

</ControlTemplate>

{% endhighlight %}

The Buttons can then be added to the TitleBar using the below code.

{% highlight html %}

[XAML]



<StackPanel   Orientation="Horizontal" HorizontalAlignment="Right" VerticalAlignment="Center">

    <shared:TitleButton x:Name="MinimizeButton" Command="shared:ChromelessWindow.ToggleMinimizedState" Template="{StaticResource MinimizeIcon}"  ToolTip="Minimize"/>

    <shared:TitleButton x:Name="PART_MaximizeButton"  Command="shared:ChromelessWindow.ToggleMaximizedState"   Template="{StaticResource MaximizeIcon}" ToolTip="Maximize"/>

    <shared:TitleButton x:Name="PART_RestoreButton"  Command="shared:ChromelessWindow.ToggleMaximizedState"  Template="{StaticResource RestoreIcon}" ToolTip="Maximize"/>

    <shared:TitleButton x:Name="CloseButton"  Command="shared:ChromelessWindow.CloseWindow"  Template="{StaticResource CloseIcon}" ToolTip="Close"/>

</StackPanel>

{% endhighlight %}

As the last step, some content can be added to the ChromelessWindow as follows.


{% highlight html %}
[XAML]



<shared:ChromelessWindow x:Class="TestChromeless.Window1"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:shared="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"

Title="ChromelessWindowTestSample"  Height="Auto" Width="Auto" 

        ResizeBorderThickness="{Binding ElementName=ResizeThicknessSlider,Path=Value}"

    CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}" Template="{StaticResource ChromelessWindowTemplate}">

    <Border  CornerRadius="{Binding ElementName=CornerRadiusSlider,Path=Value}">

        <Grid  x:Name="RootGrid">

            <Grid  x:Name="ControlsGrid" HorizontalAlignment="Center" VerticalAlignment="Center">

                <Grid.RowDefinitions>

                    <RowDefinition Height="50"/>

                    <RowDefinition Height="50"/>

                </Grid.RowDefinitions>

                <Grid.ColumnDefinitions>

                    <ColumnDefinition Width="160"/>

                    <ColumnDefinition Width="164"/>

                    <ColumnDefinition Width="*"/>

                </Grid.ColumnDefinitions>

                <Slider x:Name="CornerRadiusSlider" Height="Auto" Maximum="100" VerticalAlignment="Center" Grid.Row="0" Grid.Column="1" Grid.ColumnSpan="1" Value="5" HorizontalAlignment="Stretch"/>

                <TextBlock Text="Corner Radius"  Margin="10,0,4,0" FontSize="14" x:Name="CornerRadiusTextBlock" Grid.Row="0" VerticalAlignment="Center" Foreground="Brown"/>

<Slider x:Name="ResizeThicknessSlider" Height="Auto" Maximum="100" Grid.Row="1" VerticalAlignment="Center" Grid.Column="1" Grid.ColumnSpan="1" Value="2" HorizontalAlignment="Stretch"/>

<TextBlock Text="Resize Thickness"  HorizontalAlignment="Left" FontSize="14" Margin="10,0,0,0" x:Name="ResizeThicknessTextBlock" Grid.Row="2" VerticalAlignment="Center" Grid.ColumnSpan="2" Foreground="Brown"/>

<TextBlock Text="{Binding Path=Value, ElementName=CornerRadiusSlider, Mode=Default}" TextWrapping="NoWrap" x:Name="CornerRadiusValueTextBlock" HorizontalAlignment="Right" Margin="5,0,5,0" VerticalAlignment="Center" Width="60" Grid.Column="2" Grid.Row="0" FontSize="16" FontWeight="Bold" TextTrimming="CharacterEllipsis" Foreground="Brown"/>

<TextBlock Text="{Binding Path=Value, ElementName=ResizeThicknessSlider, Mode=Default}" TextWrapping="NoWrap" x:Name="ResizeThicknessValueTextBlock" FontSize="16" FontWeight="Bold" HorizontalAlignment="Right" Margin="5,0,5,0" VerticalAlignment="Center" Width="60" Grid.Column="2" Grid.Row="1" TextTrimming="CharacterEllipsis" Foreground="Brown"/>

</Grid>

        </Grid>

    </Border>



</shared:ChromelessWindow>

{% endhighlight  %}

The following screenshot shows the Custom ChromelessWindow control created using the preceding code.



![](Getting-Started_images/Getting-Started_img1.jpeg)



