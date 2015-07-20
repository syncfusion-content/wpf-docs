---
layout: post
title: Enabling-and-Disabling-Schedule-Editor
description: enabling and disabling schedule editor
platform: wpf
control: SfSchedule
documentation: ug
---

# Enabling and Disabling Schedule Editor

The Editor can be disabled or enabled using the property AllowEditing and its default value is True.

[XAML]



     &lt;Schedule:SfSchedule AllowEditing="False" /&gt;





[C#]



              SfSchedule schedule = new SfSchedule();

               schedule.EnableTouch = true;

              schedule.AllowEditing = false;

              this.grid.Children.Add(schedule);

{ ![](Enabling-and-Disabling-Schedule-Editor_images/Enabling-and-Disabling-Schedule-Editor_img1.png) | markdownify }
{:.image }




{ ![](Enabling-and-Disabling-Schedule-Editor_images/Enabling-and-Disabling-Schedule-Editor_img2.png) | markdownify }
{:.image }


