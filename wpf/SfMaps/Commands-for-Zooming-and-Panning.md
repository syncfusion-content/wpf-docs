---
layout: post
title: Commands for Zooming and Panning | SfMap | wpf | Syncfusion
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

## ZoomIn Command

ZoomIn command—zooms in the map.


{% highlight xaml %}




<syncfusion:SfMap x:Name="Map">

                < syncfusion:SfMap.Layers>

                     < syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp">

                        </ syncfusion:ShapeFileLayer>

                 </ syncfusion:SfMap.Layers>

            </ syncfusion:SfMap >

         <Button Content="ZoomIn" Name="zoomIn" Grid.Row="0" Command="{Binding ElementName=Map,Path=ZoomInCommand}" VerticalAlignment="Bottom"/>
{% endhighlight %}

## ZoomOut Command

ZoomOut Command--zooms out the map.


{% highlight xaml %}




       <syncfusion:SfMap x:Name="Map">

            <syncfusion:SfMap.Layers>

                <syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp">

                </syncfusion:ShapeFileLayer>

            </syncfusion:SfMap.Layers>

        </syncfusion:SfMap >

 <Button Content="ZoomOut" Name="zoomOut" Grid.Row="2"  Command="{Binding ElementName=Map,Path=ZoomOutCommand}"/>
{% endhighlight %}

## Pan Command

Pan Command is used to navigate on the Map control. The direction of the navigation is the Command parameter for the Pan Command.


{% highlight xaml %}



      <syncfusion:SfMap x:Name="Map">

            <syncfusion:SfMap.Layers>

                <syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp">

                </syncfusion:ShapeFileLayer>

            </syncfusion:SfMap.Layers>

        </syncfusion:SfMap >





        <Button Width="50" Height="20" Grid.Column="0" Content="Left" Name="LeftPanButton" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="left" Margin="43,257,667,227" />

        <Button Width="50" Height="20" Content="Right"  Name="RightPanButton"  Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="right" Margin="659,257,51,227"/>

        <Button Width="50" Height="20"  Grid.Row="0" Content="Top" Name="topPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="top" Margin="355,10,355,474"/>

        <Button Width="75" Height="20" Content="Bottom" Name="bottomPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="bottom" Margin="355,442,330,42"/>
{% endhighlight %}

## ZoomReset Command

The ZoomReset command resets the ZoomLevel value of the Map control.


{% highlight xaml %}




          <syncfusion:SfMap x:Name="Map" >

                <syncfusion:SfMap.Layers>

                <syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp">

                    </syncfusion:ShapeFileLayer>

                </syncfusion:SfMap.Layers>

            </syncfusion:SfMap >

            <Button Grid.Column="0" Grid.Row="0"  Content="ZoomRest" Command="{Binding ElementName=Map,Path=ZoomResetCommand}" Margin="0,435,10,10"/>

{% endhighlight %}

## PanReset Command

The PanReset command resets the map at its initial position; it resets the pan values.


{% highlight xaml %}




        <syncfusion:SfMap x:Name="Map" >

            <syncfusion:SfMap.Layers>

                <syncfusion:ShapeFileLayer  x:Name="shapeControl" Uri="MapApp.world1.shp">

                </syncfusion:ShapeFileLayer>

            </syncfusion:SfMap.Layers>

        </syncfusion:SfMap >





        <Button Grid.Row="0" Content="PanRest" Command="{Binding ElementName=Map,Path=PanResetCommand}" Margin="0,440,0,0"/>

{% endhighlight %}

