---
layout: post
title: Extended Scrolling | IntegerTextBox | wpf | Syncfusion
description: extended scrolling
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Extended Scrolling

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property is used to change the values based on the click and drag direction of the mouse movements. The range will increase when the mouse moves to the right or top of the screen, and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state.

![Extended scrolling](Extended-Scrolling_images/Extended-Scrolling_img1.png)

## Adding extended scrolling to an application 

The [EnableExtendedScrolling](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnableExtendedScrolling.html) property must be set either in XAML or the code file.

{%tabs%}
{% highlight xaml %}  EnableExtendedScrolling ="True"{% endhighlight %}

{% highlight C# %}  control.EnableExtendedScrolling = true;{% endhighlight %}
{%endtabs%}
