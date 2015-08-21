---
layout: post
title: Restrict-change-of-values-in-the-UpDown-control
description: restrict change of values in the updown control
platform: wpf
control: UpDown Control
documentation: ug
---

# Restrict change of values in the UpDown control

You can restrict the change of the values in the UpDown control by cancelling the ValueChanging event as shown in the following code example.

{%highlight c#%}

void upDown_ValueChanging(object sender, ValueChangingEventArgs e)

{

    e.Cancel = true;

}


{%endhighlight%}
