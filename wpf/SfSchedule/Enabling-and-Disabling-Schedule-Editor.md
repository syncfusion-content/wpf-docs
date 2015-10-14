---
layout: post
title: Enabling and Disabling Schedule Editor| SfSchedule | Wpf | Syncfusion
description: enabling and disabling schedule editor
platform: wpf
control: SfSchedule
documentation: ug
---

# Enabling and Disabling Schedule Editor

The Editor can be disabled or enabled using the property AllowEditing and its default value is True.
{% tabs %}
{% highlight html %}



     <Schedule:SfSchedule AllowEditing="False" />



{% endhighlight  %}
{% highlight c# %}




              SfSchedule schedule = new SfSchedule();

               schedule.EnableTouch = true;

              schedule.AllowEditing = false;

              this.grid.Children.Add(schedule);
{% endhighlight  %}
{% endtabs %}

![](Enabling-and-Disabling-Schedule-Editor_images/Enabling-and-Disabling-Schedule-Editor_img1.png)





![](Enabling-and-Disabling-Schedule-Editor_images/Enabling-and-Disabling-Schedule-Editor_img2.png)



