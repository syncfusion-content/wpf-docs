---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: HubTile
documentation: ug
---

# Getting Started

Namespace: Syncfusion.Windows.Controls.Notification
Assembly:  Syncfusion.SfHubTile.WPF (in Syncfusion.SfHubTile.WPF.dll) 

The following code sample shows how to create the hub tile from code-behind and XAML, which allows the user to set a title, image and header.

[XAML]



&lt;Page xmlns:control="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfHubTile.Wpf""&gt;

 &lt;Grid&gt;



        <control:SfHubTile x:Name="hubTile"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center">



        &lt;/control:SfHubTile&gt;



    &lt;/Grid&gt;

&lt;/Page&gt;





[C#]

SfHubTile hubTile = new SfHubTile();

Tile Types

HubTile

This control provides notification through various transition effects. 

Key Properties

Title

The title will be displayed at the top of the hub tile.

Header

The header will be displayed at the bottom of the hub tile.

ImageSource

An image will be displayed at the center of the hub tile.

The following code sample shows the usage of the Title, Header and ImageSource properties.

[XAML]



&lt;Page xmlns:control="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfHubTile.Wpf""&gt;

 &lt;Grid&gt;



        <control:SfHubTile x:Name="hubTile"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

ImageSource="NewMail.png" 

                         Title="This is title area. Display your message 

                                                                       here."

                         Header="HubTile">



        &lt;/control:SfHubTile &gt;



    &lt;/Grid&gt;

&lt;/Page&gt;



{ ![C:/Users/ApoorvahR/Desktop/2.png](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


Secondary Content

Secondary content will be animated in the hub tile based on a specified interval.

Hub Tile Transitions

Hub tile transitions provide the transition effect in hub tile animation. They include the following transitions:

1. Slide
2. Fade

Slide Transition

Secondary content will be animated by sliding the tile.

{ ![C:/Users/ApoorvahR/Desktop/3.png](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


Fade__Transition

Secondary content will be animated by fading the tile.



{ ![C:/Users/ApoorvahR/Desktop/4.png](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


PulsingTile

This control resembles the Music and Video hub tiles in Windows Phone. The content will zoom in and out randomly and show a translation movement in the x- and y- axis randomly. 

The following code sample shows how to create a PulsingTile in code-behind and XAML:

 [XAML]



&lt;Page xmlns:control="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfHubTile.Wpf""&gt;

    &lt;Grid&gt;



        <control:SfPulsingTile x:Name="pulsingTile"  

                            Width="200"

                            Height="200"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"                             

                         Header="PulsingTile" >

            <Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" 

                   VerticalAlignment="Center" 

                   HorizontalAlignment="Center" 

                   Height="200" />

        &lt;/control:SfPulsingTile&gt;

    &lt;/Grid&gt;

&lt;/Page&gt;



{ ![C:/Users/ApoorvahR/Desktop/4.png](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }


PulseScale

The PulseScale property specifies the range of translation in the x- and y-axis while pulsing the content.

[XAML]



<control:SfPulsingTile x:Name="pulsingTile"  

                            Width="200"

                            Height="200"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

                         PulseScale="2"

                         Header="PulsingTile" >

            <Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"              

                       VerticalAlignment="Center"

                       HorizontalAlignment="Center" Height="200" />

&lt;/control:SfPulsingTile &gt;





PulseDuration

The PulseDuration property specifies the interval for the translation done in the pulsing tile.

[XAML]



<control:SfPulsingTile x:Name="pulsingTile"  

                            Width="200"

                            Height="200"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

                         PulseDuration="00:00:00.200"

                         Header="PulsingTile" >

            <Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"              

                       VerticalAlignment="Center"

                       HorizontalAlignment="Center" Height="200" />

&lt;/control:SfPulsingTile &gt;



RadiusX

The RadiusX property specifies the range of the translation in the pulsing tile along the x-axis.

[XAML]



<control:SfPulsingTile x:Name="pulsingTile"  

                            Width="200"

                            Height="200"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

                         RadiusX="2"

                         Header="PulsingTile" >

            <Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"              

                       VerticalAlignment="Center"

                       HorizontalAlignment="Center" Height="200" />

&lt;/control: SfPulsingTile&gt;





RadiusY

The RadiusY property specifies the range of the translation in the pulsing tile along y-axis.

[XAML]



<control:SfPulsingTile x:Name="pulsingTile"  

                            Width="200"

                            Height="200"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

                         RadiusY="2"

                         Header="PulsingTile" >

            <Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill"              

                       VerticalAlignment="Center"

                       HorizontalAlignment="Center" Height="200" />

&lt;/control:SfPulsingTile&gt;



Freezing

The animation of a hub tile can be frozen.

GroupName

Hub tiles can be given specific group name. The group name will be used when we need to freeze the entire group of hub tiles.

[XAML]



<control:SfHubTile HorizontalAlignment="Center"

                              VerticalAlignment="Center"

                              Width="170"

                              Height="170"

                              GroupName="Applications"

                       Background="Red"/>



Hub Tile Service

The HubTileService class provides the helper methods to freeze and unfreeze the animation by passing a HubTile instance or GroupName as an argument.

The following code sample can be used to freeze a particular hub tile.

[C#]

HubTileService.Freeze(hubTile);



The following code sample can be used to unfreeze a particular hub tile.

[C#]

HubTileService.UnFreeze(hubTile);



The following code sample can be used to freeze a particular group of hub tiles.

[C#]

HubTileService.Freeze("Group1");



The following code sample can be used to unfreeze a particular group of hub tiles.

[C#]

HubTileService.UnFreeze("Group1");



Using IsFrozen property

Setting the IsFrozen property in a hub tile to true will freeze the animation.

[XAML]



<Page xmlns:control="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfHubTile.Wpf""

      xmlns:shared="clr-namespace:Syncfusion.Windows.Controls;assembly=Syncfusion.SfShared.Wpf"">

    &lt;Grid&gt;



        <control:SfHubTile x:Name="hubTile"

                         HorizontalAlignment="Center"

                         VerticalAlignment="Center"

                         Header="HubTile" 

IsFrozen="True">

            &lt;control:HubTileTransitionCollection&gt;

                &lt;shared:FadeTransition/&gt;

            &lt;/control:HubTileTransitionCollection&gt;

            &lt;control:SfHubTile.SecondaryContent&gt;

                &lt;Image Source="Assets/HubTile.png" Stretch="UniformToFill" /&gt;

            &lt;/control:SfHubTile.SecondaryContent&gt;

        &lt;/control:SfHubTile &gt;



    &lt;/Grid&gt;

&lt;/Page&gt;





