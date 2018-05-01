---
layout: post
title: QTP Support for DateTimeEdit control | DateTimeEdit | wpf | Syncfusion
description: qtp support for datetimeedit control
platform: wpf
control: DateTimeEdit
documentation: ug
---

# QTP Support for DateTimeEdit Control

The QTP tool can recognize the DateTimeEdit control. Hence with the DateTimeEdit control,  it is possible to record interactions such as opening the calendar popup, closing the calendar popup, choosing the date from  the calendar , setting the DateTime value and and so on, for testing using QTP.

## Mapping the control to the custom server

QTP Tool interacts with the control through CustomServerBase extension through the RunInterface. The custom server must be mapped to the control type for the tool to identify the control. A conventional configuration file (*.cfg) will resemble the one shown in the following code snippet. When the configuration file and the assembly containing the server type are loaded, QTP will recognize the control and record it.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<Controls>
<Control Type="Syncfusion.Windows.Shared.DateTimeEdit" MappedTo="SfDateTimeEdit">
<CustomServer>
<Component>
<DllName>Syncfusion.QtpDateTimeEdit.Wpf.dll</DllName>
<TypeName>Syncfusion.Windows.Controls.QTP.DateTimeEditServer</TypeName>
</Component>
</CustomServer>
</Control>
</Controls>

{% endhighlight  %}
{% endtabs %}

This XML configuration file should contain the fully qualified type name of the control, fully qualified name of the custom server and the name of the assembly containing the custom server.

MappedTo attribute, points to the name of the ClassInfo (an XML file containing the API information about the RunInterface).
