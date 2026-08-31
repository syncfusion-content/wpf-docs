---
layout: post
title: Badges in WPF SfAvatarView | Syncfusion®
description: Badges in WPF SfAvatarView highlight user status, activity, or notifications, providing additional context alongside avatar content.
platform: wpf
control: AvatarView
documentation: ug
---

# Badges in WPF AvatarView 

The [AvatarView ](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SfAvatarView.html) control supports various [SfBadge](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html) states to notify users of new or unread messages, notifications, or status updates.

The following code explains how to set [SfBadge](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Notification.SfBadge.html) for [AvatarView ](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.SfAvatarView.html).

{% tabs %}
{% highlight xaml %}

<Grid HorizontalAlignment="Center" VerticalAlignment="Center">
    <syncfusion:SfAvatarView 
         x:Name="avatarView"
         ContentType="AvatarCharacter"
         AvatarCharacter="Avatar1"       
         AvatarShape="Circle"
         AvatarSize="Large" >
        <syncfusion:SfBadge.Badge>
            <syncfusion:SfBadge x:Name="badge" Shape="None" HorizontalPosition="0.83" VerticalPosition="0.85">
                <syncfusion:SfBadge.Content>
                    <Viewbox x:Name="badgeViewBox">
                        <Grid Height="13" Width="13">
                            <Ellipse x:Name="ellipse" Fill="LimeGreen" Stroke="White" StrokeThickness="1"/>   
                            <TextBlock x:Name="badgeTextBlock"
                                FontFamily="Segoe MDL2 Assets"
                                Text="&#xE930;"
                                Foreground="White"
                                HorizontalAlignment="Center"
                                VerticalAlignment="Center"/>
                        </Grid>
                    </Viewbox>
                </syncfusion:SfBadge.Content>
            </syncfusion:SfBadge>
        </syncfusion:SfBadge.Badge>
    </syncfusion:SfAvatarView>
</Grid>

{% endhighlight %}
{% endtabs %}

![WPF AvatarView control with Badge](avatarview_images/wpf_avatarview_with_badge.png)