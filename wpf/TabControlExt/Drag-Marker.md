---
layout: post
title: Drag-Marker
description: drag marker
platform: wpf
control: TabControlExt
documentation: ug
---

# Drag Marker

You can set the color for the Drag Marker by using the DragMarkerColor property. This dependency property sets the brush value for the DragMarkerColor property while you drag the TabItemExt.

Use the following code snippet to set the color for the Drag Marker.


{% highlight xml %}
[XAML]



<!-- Adding TabControlExt -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" DragMarkerColor="Red">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>

</syncfusion:TabControlExt>
{% endhighlight %}

{% highlight c# %}
[C#]



// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();



//Creating the instance of StackPanel

StackPanel stackPanel = new StackPanel();



//Creating instance of the TabItemExt 

TabItemExt tabItemExt1 = new TabItemExt();



// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";



//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt1);                  



//Setting Drag Marker Color 

tabControlExt.DragMarkerColor = Brushes.Red;  



//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 
{% endhighlight %}


