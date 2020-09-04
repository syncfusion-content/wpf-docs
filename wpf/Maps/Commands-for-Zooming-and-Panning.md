---
layout: post
title: Commands for Zooming and Panning | SfMap | wpf | Syncfusion
description: This section describes Zooming and Panning Commands in WPF SfMaps control with simple exercise sample.
platform: wpf
control: SfMap
documentation: ug
---

# Commands for Zooming and Panning

The Map control contains the following commands:

* ZoomIn Command
* ZoomOut Command
* Pan Command
* ZoomReset Command
* PanReset Command

## ZoomIn Command

[`ZoomIn`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_ZoomInCommand) command zooms in the map.

## ZoomOut Command

[`ZoomOut`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_ZoomOutCommand) command zooms out the map.

## Pan Command

[`PanCommand`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_PanCommand) is used to navigate on the Map control. The direction of the navigation is the Command parameter for the Pan Command.

## ZoomReset Command

The [`ZoomResetCommand`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_ZoomResetCommand) resets the ZoomLevel value of the Map control.

## PanReset Command

The [`PanResetCommand`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_PanResetCommand) resets the map at its initial position; it resets the pan values.

{% highlight xaml %}

    <Grid Margin="10">
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition Height="Auto"/>
        </Grid.RowDefinitions>
        <syncfusion:SfMap x:Name="Map">
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="DataMarkers.ShapeFiles.world1.shp">
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >
        
        <StackPanel Grid.Row="1" Orientation="Horizontal" Margin="10">
            <StackPanel.Resources>
                <Style TargetType="Button">
                    <Setter Property="Margin" Value="5"/>
                    <Setter Property="Padding" Value="5"/>
                </Style>
            </StackPanel.Resources>
            
            <Button Content="ZoomIn" Command="{Binding ElementName=Map,Path=ZoomInCommand}"/>
            <Button Content="ZoomOut" Command="{Binding ElementName=Map,Path=ZoomOutCommand}"/>
            
            <!--Panning commands-->
            <Button Content="LeftPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="left"/>
            <Button Content="RightPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="right"/>
            <Button Content="TopPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="top"/>
            <Button Content="BottomPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="bottom"/>

            <Button Content="ZoomReset" Command="{Binding ElementName=Map,Path=ZoomResetCommand}"/>
            <Button Content="PanReset" Command="{Binding ElementName=Map,Path=PanResetCommand}"/>
            
        </StackPanel>

    </Grid>

{% endhighlight %}

