---
layout: post
title: Layout Related Features of WPF NotifyIcon | Syncfusion
description: This section gives a detailed description of how to set the styles and events in the Syncfusion WPF NotifyIcon control.
platform: wpf
control: NotifyIcon
documentation: ug
---

# Layout Related Features in WPF NotifyIcon

This section illustrates the following Layout-related feature of NotifyIcon control.

## Theme

NotifyIcon supports various built-in themes. Refer to the below links to apply themes for the NotifyIcon,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  
  ![Set theme to WPF NotifyIcon](Getting-Started_images/wpf-notifyicon-theme.png)


## Customizing the Header of the NotifyIcon

You can customize the background and foreground for the BalloonTipHeader by using the [HeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_HeaderBackground) and [HeaderForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_HeaderForeground) properties.

{% tabs %}
{% highlight xaml %}

<Button x:Name="button" Height="30" Width="100" Click="Button_Click" Content="Notify show">
</Button>

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" BalloonTipTitle="Default NotifyIcon"
                       BalloonTipText="Custom NotifyIcon" BalloonTipIcon="Info"
                       ShowBalloonTipTime="1000" HideBalloonTipTime="1000"
                       HeaderBackground="Blue" HeaderForeground="White">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight c# %}

private void Button_Click(object sender, RoutedEventArgs e)
{
    notifyIcon.HeaderBackground = Brushes.Blue;
    notifyIcon.HeaderForeground = Brushes.White;
}

{% endhighlight %}
{% endtabs %}


![Customize the header style in WPF NotifyIcon](Layout-Related-Features_images/wpf-notifyicon-customization.png)

## Events

The [NotifyIcon](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html) includes several pre-defined events to perform any required action as follows:

* BalloonTipOpening
* BalloonTipOpened
* BalloonTipHiding
* BalloonTipHidden
* CloseButtonClick
* Click

### BalloonTipOpening event

The [BalloonTipOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_BalloonTipOpening) event occurs before opening the balloon tip and action can be handled in the respective event handler.

The `CancelEventArgs` object contains the following property.

* Cancel : Canceling the action of the balloon tip show.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" BalloonTipOpening="NotifyIcon_BalloonTipOpening">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.BalloonTipOpening += NotifyIcon_BalloonTipOpening;

private void NotifyIcon_BalloonTipOpening(object sender, System.ComponentModel.CancelEventArgs e)
{
    //Cancel the balloontip action.
    e.Cancel = true;
}

{% endhighlight %}

{% endtabs %}

### BalloonTipOpened event

The [BalloonTipOpened](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_BalloonTipOpened) event occurs after the balloon tip is opened and action can be handled in the respective event handler.

The [DependencyPropertyChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_OnBalloonTipHeaderVisibilityChanged_System_Windows_DependencyPropertyChangedEventArgs_) object contains the following properties:

* NewValue : gets an new value.
* OldValue : gets an old value.
* Property : Identify the value.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" BalloonTipOpened="NotifyIcon_BalloonTipOpened">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.BalloonTipOpened += NotifyIcon_BalloonTipOpened;

private void NotifyIcon_BalloonTipOpened(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    if(e.Property.Name == "IsOpen")
    {
        //Change the balloontip text.
        notifyIcon.BalloonTipText = "Welcome";
    }
}

{% endhighlight %}

{% endtabs %}

### BalloonTipHiding event

The [BalloonTipHiding](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_BalloonTipHiding) event occurs before hiding the balloon tip and action can be handled in the respective event handler.

The `CancelEventArgs` object contains the following property:

* Cancel : Canceling the hiding action of the balloon tip.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" BalloonTipHiding="NotifyIcon_BalloonTipHiding">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.BalloonTipHiding += NotifyIcon_BalloonTipHiding;

private void NotifyIcon_BalloonTipHiding(object sender, System.ComponentModel.CancelEventArgs e)
{
    //Cancel the hiding action.
    e.Cancel = true;            
}

{% endhighlight %}

{% endtabs %}


### BalloonTipHidden event

The [BalloonTipHidden](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_BalloonTipHidden) event occurs after hiding the balloon tip and action can be handled in the respective event handler.

The [DependencyPropertyChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_OnBalloonTipHeaderVisibilityChanged_System_Windows_DependencyPropertyChangedEventArgs_) object contains the following properties:

* NewValue : gets an new value.
* OldValue : gets an old value.
* Property : Identify the value.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" BalloonTipHidden="NotifyIcon_BalloonTipHidden">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.BalloonTipHidden += NotifyIcon_BalloonTipHidden;

private void NotifyIcon_BalloonTipHidden(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    
}

{% endhighlight %}

{% endtabs %}

### CloseButtonClick event

The [CloseButtonClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_CloseButtonClick) event occurs while clicking the close button in the balloon tip.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" CloseButtonClick="NotifyIcon_CloseButtonClick">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.CloseButtonClick += NotifyIcon_CloseButtonClick;

private void NotifyIcon_CloseButtonClick(object sender, EventArgs e)
{
            
}

{% endhighlight %}

{% endtabs %}

### Click event

The [Click](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.NotifyIcon.html#Syncfusion_Windows_Tools_Controls_NotifyIcon_Click) event occurs while clicking the icon inside the balloon tip.

{% tabs %}

{% highlight XAML %}

<syncfusion:NotifyIcon Name="notifyIcon" Header="NotifyIcon" Click="NotifyIcon_Click">
</syncfusion:NotifyIcon>

{% endhighlight %}

{% highlight C# %}

notifyIcon.Click += NotifyIcon_Click;

private void NotifyIcon_Click(object sender, EventArgs e)
{

}

{% endhighlight %}

{% endtabs %}
