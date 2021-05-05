---
layout: post
title: States in WPF circular progressbar control | Syncfusion
description: Learn here all about States support in Syncfusion WPF circular progressbar (SfCircularProgressBar) control and more.
platform: WPF
control: SfCircularProgressBar
documentation: ug
---

# States in WPF circular progressbar (SfCircularProgressBar)
States help to visualize the progress of a task in different modes. You can configure states of the circular progressbar control depending on its usage in following ways.

## Determinate
Determinate is the default state. You can use it when the progress estimation is known. [ShowProgressValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfCircularProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfCircularProgressBar_ShowProgressValueProperty) property allows to indicate the progress of the operation taken place  in numerical value.
![Determinate image](States_images/Determinate.png)

## Indeterminate
By enabling the [IsIndeterminate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.ProgressBarBase.html#Syncfusion_UI_Xaml_ProgressBar_ProgressBarBase_IsIndeterminateProperty) property, the state of the progressbar can be changed to indeterminate when the progress cannot be estimated or when not being calculated.

{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfCircularProgressBar Progress="70" IsIndeterminate="True"/>            
{% endhighlight %}
{% highlight C# %}
SfCircularProgressBar Circular = new SfCircularProgressBar { Progress = 70, IsIndeterminate=true};
grid.Children.Add(Circular);        
{% endhighlight %}
{% endtabs %}
![InDeterminate image](States_images/InDeterminate.png)

## Buffer
Buffer is used as a secondary progress indicator when the primary task depends on the secondary task. This will allow users to visualize both the primary and secondary tasks' progress simultaneously. The `SecondaryProgress` property can be set to visualize the secondary progress, and a separate color for the secondary progress can be set by the `SecondaryProgressColor` property.
{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfCircularProgressBar Progress="65" SecondaryProgress="75"/>      
{% endhighlight %}
{% highlight C# %}
SfCircularProgressBar Circular = new SfCircularProgressBar { Progress = 65, SecondaryProgress = 75 };
grid.Children.Add(Circular);      
{% endhighlight %}
{% endtabs %}
![Buffer image](States_images/BufferState.png)
