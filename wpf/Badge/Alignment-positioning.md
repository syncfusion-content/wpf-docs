---
layout: post
title: Alignment and positioning in WPF Badge control | Syncfusion
description: Learn here all about Alignment and positioning support in Syncfusion WPF Badge (SfBadge) control and more.
platform: WPF
control: SfBadge
documentation: ug
---

# Alignment and positioning in WPF Badge (SfBadge)

This section explains the alignment and positioning functionalities available in the WPF [Badge](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html) control.

## Alignment of Badge

you can align the `Badge` either horizontally or vertically by using the `HorizontalAlignment` or `VerticalAlignment` properties. The default value of `HorizontalAlignment` property is `Right` and `VerticalAlignment` property is `Top`.

<style>
table, td, th { 
  text-align: center;
}
</style>
<table>

<tr>
<td class="invisible" ></td>
<th colspan = "4">HorizontalAlignment</th>
</tr>

<tr>
<th>VerticalAlignment</th>
<td>Left</td>
<td>Center</td>
<td>Right</td>
<td>Stretch</td>
</tr>

<tr>
<td>Top</td>
<td><img src="Getting-Started_images/Left-top.png" alt="Left-Top alignment of Badge"/></td>
<td><img src="Getting-Started_images/Center-Top.png" alt="Center-Top alignment of Badge"/></td>
<td><img src="Getting-Started_images/Right-Top.png" alt="Right-Top alignment of Badge"/></td>
<td><img src="Getting-Started_images/Stretch-Top.png" alt="Stretch-Top alignment of Badge"/></td>
</tr>

<tr>
<td>Center</td>
<td><img src="Getting-Started_images/Left-center.png" alt="Left-center alignment of Badge"/></td>
<td><img src="Getting-Started_images/Center-Center.png" alt="Center-Center alignment of Badge"/></td>
<td><img src="Getting-Started_images/Right-Center.png" alt="Right-Center alignment of Badge"/></td>
<td><img src="Getting-Started_images/Stretch-Center.png" alt="Stretch-Center alignment of Badge"/></td>
</tr>

<tr>
<td>Bottom</td>
<td><img src="Getting-Started_images/Left-Bottom.png" alt="Left-Bottom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Center-Bottom.png" alt="Center-Bottom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Right-Bottom.png" alt="Right-Bottom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Stretch-Bottom.png" alt="Stretch-Bottom alignment of Badge"/></td>
</tr>

<tr>
<td>Stretch</td>
<td><img src="Getting-Started_images/Left-Stretch.png" alt="Left-Stretch alignment of Badge"/></td>
<td><img src="Getting-Started_images/Center-Stretch.png" alt="Center-Stretch alignment of Badge"/></td>
<td><img src="Getting-Started_images/Right-Stretch.png" alt="Right-Stretch alignment of Badge"/></td>
<td><img src="Getting-Started_images/Stretch-Stretch.png" alt="Stretch-Stretch alignment of Badge"/></td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<Button Width="100"
        Height="50" 
        Content="Inbox">
    <notification:SfBadge.Badge>
        <notification:SfBadge HorizontalAlignment="Left"
                              VerticalAlignment="Center"
                              Content="99+"
                              x:Name="badge"/>
    </notification:SfBadge.Badge>
</Button>

{% endhighlight %}
{% highlight C# %}

badge.HorizontalAlignment = HorizontalAlignment.Left;
badge.VerticalAlignment = VerticalAlignment.Center;
badge.Content = "99+";

{% endhighlight %}
{% endtabs %}

![Alignment of the Badge control is changed](Getting-Started_images/Alignment.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-badge-control-examples/blob/main/Samples/Badge_Features)

## Positioning of Badge

You can change the horizontal or vertical position of the `Badge` either inside, outside or in the middle by using the [HorizontalAnchor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_HorizontalAnchor) and [VerticalAnchor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_VerticalAnchor) properties. It will be placed based on the value of `HorizontalAlignment` and `VerticalAlignment` properties. The default value of `HorizontalAnchor` and `VerticalAnchor` properties is `Center`.

For example, you will change the `HorizontalAnchor` and `VerticalAnchor` property values on when the value of `HorizontalAlignment` properties is `Right` and `VerticalAlignment` property is `Top`. `Badge` will be positioned as follows,

<style>
table, td, th { 
  text-align: center;
}
</style>
<table>

<tr>
<td class="invisible" ></td>
<th colspan = "4">HorizontalAnchor</th>
</tr>

<tr>
<th>VerticalAnchor</th>
<td>Inside</td>
<td>Center</td>
<td>OutSide</td>
</tr>

<tr>
<td>Inside</td>
<td><img src="Getting-Started_images/Positioning_Inside_Inside.png" alt="Inside-Inside positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Center_Inside.png" alt="Center-Inside positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Outside_Inside.png" alt="Outside-Inside positioning of Badge"/></td>
</tr>

<tr>
<td>Center</td>
<td><img src="Getting-Started_images/Positioning_Inside_Center.png" alt="Inside-Center positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Center_Center.png" alt="Center-Center positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Outside_Center.png" alt="Outside-Center positioning of Badge"/></td>
</tr>

<tr>
<td>Outside</td>
<td><img src="Getting-Started_images/Positioning_Inside_Outside.png" alt="Inside-Outside positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Center_Outside.png" alt="Center-Outside positioning of Badge"/></td>
<td><img src="Getting-Started_images/Positioning_Outside_Outside.png" alt="Outside-Outside positioning of Badge"/></td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<Button Width="100"
        Height="50" 
        Content="Inbox">
    <notification:SfBadge.Badge>
        <notification:SfBadge HorizontalAnchor="Outside"
                              VerticalAnchor="Center"
                            Content="10"
                            x:Name="badge"/>
    </notification:SfBadge.Badge>
</Button>

{% endhighlight %}
{% highlight C# %}

badge.HorizontalAnchor = BadgeAnchor.Outside;
badge.VerticalAnchor = BadgeAnchor.Center;
badge.Content = "10";

{% endhighlight %}
{% endtabs %}

![Position of the Badge control is changed](Getting-Started_images/Anchor.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-badge-control-examples/blob/main/Samples/Badge_Features)

## Place the Badge any where on the container

If you want to place the `Badge` anywhere on any shaped container, use the [HorizontalPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_HorizontalPosition) or [VerticalPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_VerticalPosition) properties. The value range for `HorizontalPosition` and `VerticalPosition` properties is `0` to`1`. The default value of `HorizontalPosition` property is `1` and `VerticalPosition` property is `0`.

For example, if you use any circular containers, you can easily place the `Badge` anywhere by using the `HorizontalPosition` and `VerticalPosition` properties.

{% tabs %}
{% highlight XAML %}

<Image Source="/Images/avatar.png"
       Width="100"
       Height="100" >
    <notification:SfBadge.Badge>
        <notification:SfBadge Shape="None"
                              HorizontalPosition="0.9"
                              VerticalPosition="0.8"
                              x:Name="badge">
            <notification:SfBadge.Content>
                <Ellipse Width="20"
                         Height="20"
                         Fill="LimeGreen"/>
            </notification:SfBadge.Content>
        </notification:SfBadge>
    </notification:SfBadge.Badge>
</Image>


{% endhighlight %}
{% highlight C# %}

badge.HorizontalPosition = 0.9;
badge.VerticalPosition = 0.8;

{% endhighlight %}
{% endtabs %}

![Displaying the customized alignment of the Badge control](Getting-Started_images/Custom_Alignment.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-badge-control-examples/blob/main/Samples/Custom_Alignment)

## Custom alignment and positioning of Badge

You can customize the horizontal or vertical position of the `Badge` either inside, outside or in the middle with any point by using the `HorizontalPosition` & `VerticalPosition` properties and [HorizontalAnchorPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_HorizontalAnchorPosition) & [VerticalAnchorPosition](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html#Syncfusion_Windows_Controls_Notification_SfBadge_VerticalAnchorPosition) properties. This will effective only on by setting the `HorizontalAnchor` and `VerticalAnchor` properties value as `Custom`.  The value range for `HorizontalAnchorPosition` and `VerticalAnchorPosition` properties is `0` to`1`. The default value of `HorizontalAnchorPosition`and `VerticalAnchorPosition` properties is `0`.

<style>
table, td, th { 
  text-align: center;
}
</style>

<table>

<tr>
<td class="invisible" ></td>
<th colspan = "3">HorizontalPosition & 
HorizontalAnchorPosition</th>
</tr>

<tr>
<th>VerticalPosition & 

VerticalAnchorPosition</th>
<td>0</td>
<td >0.5</td>
<td>1</td>
</tr>


<tr>
<td>0</td>
<td><img src="Getting-Started_images/Custom_Left_top.png" alt="Left-Top custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Center_Top.png" alt="Center-Top custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Right_Top.png" alt="Right-Top custom alignment of Badge"/></td>
</tr>

<tr>
<td>0.5</td>
<td><img src="Getting-Started_images/Custom_Left_center.png" alt="Left-center custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Center_Center.png" alt="Center-Center custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Right_Center.png" alt="Right-Center custom alignment of Badge"/></td>
</tr>

<tr>
<td>1</td>
<td><img src="Getting-Started_images/Custom_Left_Bottom.png" alt="Left-Bottom custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Center_Bottom.png" alt="Center-Bottom custom alignment of Badge"/></td>
<td><img src="Getting-Started_images/Custom_Right_Bottom.png" alt="Right-Bottom custom alignment of Badge"/></td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<Button Width="100"
        Height="50" 
        Content="Inbox">
    <notification:SfBadge.Badge>
        <notification:SfBadge HorizontalAnchor="Custom"
                              VerticalAnchor="Custom"
                              HorizontalAnchorPosition="0.2"
                              VerticalAnchorPosition="0.4"
                              Content="99+"
                              x:Name="badge2"/>
    </notification:SfBadge.Badge>
</Button>

{% endhighlight %}
{% highlight C# %}

badge.HorizontalAnchor = BadgeAnchor.Custom;
badge.VerticalAnchor = BadgeAnchor.Custom;
badge.HorizontalAnchorPosition = 0.2;
badge.VerticalAnchorPosition = 0.4;
badge.Content = "99+";

{% endhighlight %}
{% endtabs %}

![Custom position of the Badge control is changed](Getting-Started_images/Custom_Anchor.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-badge-control-examples/blob/main/Samples/Custom_Alignment)

## Badge content alignment

you can place the `Badge` content either horizontally or vertically by using the `HorizontalContentAlignment` or `VerticalContentAlignment` properties. The default value of `HorizontalContentAlignment` and `VerticalContentAlignment` properties is `Center`.

{% tabs %}
{% highlight XAML %}

<Button Width="100"
        Height="50" 
        Content="Inbox">
    <notification:SfBadge.Badge>
        <notification:SfBadge HorizontalContentAlignment="Right"
                              VerticalContentAlignment="Center"
                              Content="10"
                              x:Name="badge"/>
    </notification:SfBadge.Badge>
</Button>

{% endhighlight %}
{% highlight C# %}

badge.HorizontalContentAlignment = HorizontalAlignment.Right;
badge.VerticalContentAlignment = VerticalAlignment.Center;
badge.Content = "99+";

{% endhighlight %}
{% endtabs %}

![Alignment of the Badge content is changed](Getting-Started_images/Content_Alignment.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-badge-control-examples/blob/main/Samples/Badge_Features)
