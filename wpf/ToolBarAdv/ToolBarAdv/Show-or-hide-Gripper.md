---
layout: post
title: Show or hide Gripper | ToolBarAdv | wpf | Syncfusion
description: show or hide gripper 
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Show or hide Gripper 

You can show or hide the gripper in ToolBarAdv using the _GripperVisibility_ property. 

Following code illustrates how to hide the gripper:


{%tabs%}
{% highlight xml %}



<shared:ToolBarAdv GripperVisibility="Collapsed" ></shared:ToolBarAdv>


{% endhighlight %}


{% highlight C# %}



ToolBarAdv toolBar = new ToolBarAdv();

            toolBar.GripperVisibility = Visibility.Collapsed;


{% endhighlight %}

{%endtabs%}


![](Show-or-hide-Gripper_images/Show-or-hide-Gripper_img1.png)




