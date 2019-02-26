---
layout: post
title: Pulsing Tile Control | SfPulsingTile | WPF | Syncfusion
description: This section explains how to configure the pulsing tile zooming functionalities and translation movement.
platform: WPF
control: SfPulsingTile
documentation: ug
---

# Pulsing Tile Control

[SfPulsingTile](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.SfPulsingTile.html) control allows to create a tile similar to Music and Video hub tile in Windows Phone. The content zooms in/out randomly with random translation in X and Y axis.

## Setting Title, Header and Image on Pulsing Tile

You can set the title, header and image on SfPulsingTile by setting [Title](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.HubTileBase~Title.html), [Header](https://help.syncfusion.com/cr/wpf/Syncfusion.SfShared.Wpf~Syncfusion.Windows.Primitives.HeaderedContentControl~Header.html) and [ImageSource](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.HubTileBase~ImageSource.html) properties.

{% tabs %}
{% highlight XAML %}
<!--Pulsing Tile-->
<syncfusion:SfPulsingTile x:Name="pulsingTile" Header="Pulsing Tile" Title="This is title area." Background="DeepSkyBlue">
	<Image Source="Assets\PulsingTile.jpg" HorizontalAlignment="Center" VerticalAlignment="Center" />
</syncfusion:SfPulsingTile>
{% endhighlight %}
{% endtabs %}

![wpf pulsing tile structure](Getting-Started_images/wpf-pulsing-tile.png)

## Customizing Animation

You can change pulsing tile animation by using pulsing scale, pulsing duration, RadiusX and RadiusY properties.

### PulseScale

The [PulseScale](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.SfPulsingTile~PulseScale.html) property specifies the range of translation in the x- and y-axis while pulsing the content.

{% tabs %}
{% highlight XAML %}
<!-- SfPulsingTile Control -->
<syncfusion:SfPulsingTile x:Name="pulsingTile" Width="200" Height="200" PulseScale="2" Header="PulsingTile" >
	<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" VerticalAlignment="Center" HorizontalAlignment="Center" Height="200" />
</syncfusion:SfPulsingTile>
{% endhighlight %}
{% endtabs %}

### PulseDuration

The [PulseDuration](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.SfPulsingTile~PulseDuration.html) property specifies the time taken for a single scaling animation to complete in pulsing tile. 

{% tabs %}
{% highlight XAML %}
<!-- SfPulsingTile Control -->
<syncfusion:SfPulsingTile x:Name="pulsingTile" Width="200" Height="200" PulseDuration="00:00:00.5" Header="PulsingTile" >
	<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" VerticalAlignment="Center" HorizontalAlignment="Center" Height="200" />
</syncfusion:SfPulsingTile>
{% endhighlight %}
{% endtabs %}

### RadiusX

The [RadiusX](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.SfPulsingTile~RadiusX.html) property specifies the range of the translation in the pulsing tile along the x-axis.

{% tabs %}
{% highlight XAML %}
<!-- SfPulsingTile Control -->
<syncfusion:SfPulsingTile x:Name="pulsingTile" Width="200" Height="200" RadiusX="100" Header="PulsingTile" >
	<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" VerticalAlignment="Center" HorizontalAlignment="Center" Height="200" />
</syncfusion:SfPulsingTile>
{% endhighlight %}
{% endtabs %}

### RadiusY

The [RadiusY](https://help.syncfusion.com/cr/wpf/Syncfusion.SfHubTile.Wpf~Syncfusion.Windows.Controls.Notification.SfPulsingTile~RadiusY.html) property specifies the range of the translation in the pulsing tile along y-axis.

{% tabs %}
{% highlight XAML %}
<!-- SfPulsingTile Control -->
<syncfusion:SfPulsingTile x:Name="pulsingTile" Width="200" Height="200"  RadiusY="100" Header="PulsingTile" >
	<Image Source="Assets/PulsingTile.jpg" Stretch="UniformToFill" VerticalAlignment="Center" HorizontalAlignment="Center" Height="200" />
</syncfusion:SfPulsingTile>
{% endhighlight %}
{% endtabs %}

