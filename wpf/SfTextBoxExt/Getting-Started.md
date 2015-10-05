---
layout: post
title: Getting Started | SfTextBoxExt | wpf | Syncfusion
description: getting started
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Getting Started

Namespace:  Syncfusion.Windows.Controls.Input

Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

The following code sample shows how to create the TextBoxExt from code-behind and XAML:

{% tabs %}

{% highlight xaml %}

Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"

    <Grid> 

           <editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="200"

                            Text="Hello! World..."/>

    </Grid>

</Page>

{% endhighlight %}

{% highlight c# %}

SfTextBoxExt textBox = new SfTextBoxExt();

{% endhighlight %}

{% endtabs %}