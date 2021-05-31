---
layout: post
title: States of the WPF Linear ProgressBar control | Syncfusion
description: Learn here about states like determinate, indeterminate and Buffer in the Syncfusion WPF Linear ProgressBar control and more details.
platform: WPF
control: SfLinearProgressBar
 documentation: ug
---

# Different states in Linear ProgressBar
States help to visualize the progress of a task in different modes. You can configure states of the linear progressbar control depending on its usage in following ways.


## Determinate
Determinate is the default state. You can use it when the progress estimation is known.
![Determinate image](States_images/Determinate.png)

## Indeterminate
By enabling the [IsIndeterminate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.ProgressBarBase.html#Syncfusion_UI_Xaml_ProgressBar_ProgressBarBase_IsIndeterminateProperty) property, the state of the progressbar can be changed to indeterminate when the progress cannot be estimated or is not being calculated.
{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfLinearProgressBar Progress="70" IsIndeterminate="True" />      {% endhighlight %}
{% highlight C# %}
SfLinearProgressBar linear = new SfLinearProgressBar { Progress = 70, IsIndeterminate=true};
linear.Width = 500;
linear.Height = 20;
grid.Children.Add(linear);        
{% endhighlight %}
{% endtabs %}
![InDeterminate image](States_images/InDeterminate.png)

## Buffer
Buffer is used as a secondary progress indicator when the primary task depends on the secondary task. This will allow users to visualize both primary and secondary tasks progress simultaneously. The [SecondaryProgress](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfLinearProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfLinearProgressBar_SecondaryProgressProperty) property can be set to visualize secondary progress and  separate color for the secondary progress can bet set by [SecondaryProgressColor](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.SfLinearProgressBar.html#Syncfusion_UI_Xaml_ProgressBar_SfLinearProgressBar_SecondaryProgressColorProperty) property.
{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfLinearProgressBar Progress="70" SecondaryProgress="90" />      {% endhighlight %}
{% highlight C# %}
SfLinearProgressBar linear = new SfLinearProgressBar { Progress = 70, SecondaryProgress=90};
linear.Width = 500;
linear.Height = 20;
grid.Children.Add(linear);       
{% endhighlight %}
{% endtabs %}
![Buffer image](States_images/Buffer.png)