---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: TextBoxExt
documentation: ug
---

# Getting Started

Namespace:  Syncfusion.Windows.Controls.Input
Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

The following code sample shows how to create the TextBoxExt from code-behind and XAML:


{% highlight xml %}
[XAML]



Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"

    <Grid> 

           <editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="200"

                            Text="Hello! World..."/>

    </Grid>

</Page>
{% endhighlight %}

{% highlight  %}
[C#]

SfTextBoxExt textBox = new SfTextBoxExt();
{% endhighlight %}


