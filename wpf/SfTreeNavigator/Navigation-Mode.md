---
layout: post
title: Navigation-Mode
description: navigation mode  
platform: wpf
control: Tree Navigator 
documentation: ug
---

# Navigation Mode  

Two types of Navigation mode are supported by Tree Navigator to navigate between hierarchy levels. 

## Default 

In this navigation mode, the header of current hierarchy level item can be displayed in the top of the Tree Navigator with the back button. This back button is used to navigate towards the root from the current level. 


{% highlight xml %}

<navigation:SfTreeNavigator ItemsSource="{Binding Models}"  

                            Header="Enterprise Toolkit"

                            NavigationMode="Default"

                            Width="300" Height="400"

                            HorizontalAlignment="Center"

                            VerticalAlignment="Center" />

{% endhighlight %}



![](Navigation-Mode_images/Navigation-Mode_img1.png)





## Extended 

In this navigation mode, header of each level from the root to current level stacked one by one in the top of the Tree Navigator.  When click on any of that header will take us to the corresponding level. 


{% highlight xml %}

<navigation:SfTreeNavigator ItemsSource="{Binding Models}"  

                            Header="Enterprise Toolkit"

                            NavigationMode="Extended"

                            Width="300" Height="400"

                            HorizontalAlignment="Center"

                            VerticalAlignment="Center" />


{% endhighlight %}


![](Navigation-Mode_images/Navigation-Mode_img2.png)


> Note: Header of the Extended mode can be styled using TreeNavigatorHeaderItem available in the same namespace.


