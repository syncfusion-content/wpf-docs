---
layout: post
title: Commands-for-Zooming-and-Panning
description: commands for zooming and panning
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

ZoomIn Command

ZoomIn command—zooms in the map.

[XAML]

&lt;syncfusion:SfMap x:Name="Map"&gt;

                &lt; syncfusion:SfMap.Layers&gt;

                     &lt; syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp"&gt;

                        &lt;/ syncfusion:ShapeFileLayer&gt;

                 &lt;/ syncfusion:SfMap.Layers&gt;

            &lt;/ syncfusion:SfMap &gt;

         &lt;Button Content="ZoomIn" Name="zoomIn" Grid.Row="0" Command="{Binding ElementName=Map,Path=ZoomInCommand}" VerticalAlignment="Bottom"/&gt;

ZoomOut Command

ZoomOut Command--zooms out the map.

[XAML]

       &lt;syncfusion:SfMap x:Name="Map"&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp"&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;

 &lt;Button Content="ZoomOut" Name="zoomOut" Grid.Row="2"  Command="{Binding ElementName=Map,Path=ZoomOutCommand}"/&gt;

Pan Command

Pan Command is used to navigate on the Map control. The direction of the navigation is the Command parameter for the Pan Command.

[XAML]

      &lt;syncfusion:SfMap x:Name="Map"&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp"&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;





        &lt;Button Width="50" Height="20" Grid.Column="0" Content="Left" Name="LeftPanButton" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="left" Margin="43,257,667,227" /&gt;

        &lt;Button Width="50" Height="20" Content="Right"  Name="RightPanButton"  Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="right" Margin="659,257,51,227"/&gt;

        &lt;Button Width="50" Height="20"  Grid.Row="0" Content="Top" Name="topPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="top" Margin="355,10,355,474"/&gt;

        &lt;Button Width="75" Height="20" Content="Bottom" Name="bottomPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="bottom" Margin="355,442,330,42"/&gt;

ZoomReset Command

The ZoomReset command resets the ZoomLevel value of the Map control.

[XAML]

          &lt;syncfusion:SfMap x:Name="Map" &gt;

                &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp"&gt;

                    &lt;/syncfusion:ShapeFileLayer&gt;

                &lt;/syncfusion:SfMap.Layers&gt;

            &lt;/syncfusion:SfMap &gt;

            &lt;Button Grid.Column="0" Grid.Row="0"  Content="ZoomRest" Command="{Binding ElementName=Map,Path=ZoomResetCommand}" Margin="0,435,10,10"/&gt;



PanReset Command

The PanReset command resets the map at its initial position; it resets the pan values.

[XAML]

        &lt;syncfusion:SfMap x:Name="Map" &gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp"&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;





        &lt;Button Grid.Row="0" Content="PanRest" Command="{Binding ElementName=Map,Path=PanResetCommand}" Margin="0,440,0,0"/&gt;



