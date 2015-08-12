---
layout: post
title: Getting-Started
description: getting started 
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Getting Started 

Namespace:  Syncfusion.Windows.Controls.Input

Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

Dependent assembly: Syncfusion.SfShared.WPF.dll

The following code sample illustrates how to create the SfRangeSlider from code-behind and XAML.

{% highlight xml %}

<Window xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"> 

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">     

<editors:SfRangeSlider Width="500" HorizontalAlignment="Center" VerticalAlignment="Center" Minimum="0" Maximum="100"/>

</Grid>

</Window> 

{%endhighlight%}


{% highlight c# %}

SfRangeSlider rangeSlider = new SfRangeSlider();

{%endhighlight%}

