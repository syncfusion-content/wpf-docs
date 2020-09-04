---
layout: post
title: WPF DateTimeEdit UI Automation | Syncfusion
description: This section explains about the Quick Test Professional (QTP) and Coded UI support of DateTimeEdit control.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# UI Automation in WPF DateTimePicker (DateTimeEdit)

Microsoft UI Automation is the new accessibility Framework for Microsoft Windows, available on all operating systems that support Windows Presentation Foundation (WPF). UI Automation provides accessibility to most UI elements and it provides the information about UI element to the end user. You can interact with the UI by using automated test scripts. To know more about UI Automation, refer the MSDN page [here](https://msdn.microsoft.com/en-us/library/ms747327(v=vs.110).aspx).

[DateTimeEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeEdit.html) supports the following types of UI Automation,

1. Quick Test Professional
2. Coded UI

## Quick Test Professional (QTP)

The QTP tool can recognize the `DateTimeEdit` control. Hence with the `DateTimeEdit` control, it is possible to record interactions such as opening the calendar popup, closing the calendar popup, choosing the date from  the calendar , setting the DateTime value and and so on, for testing using QTP.

### Mapping the control to the custom server

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

This XML configuration file should contain the fully qualified type name of the control, fully qualified name of the custom server and the name of the assembly containing the custom server. MappedTo attribute, points to the name of the ClassInfo (an XML file containing the API information about the RunInterface).

## Coded UI

You can refer the Coded UI document from [here](https://help.syncfusion.com/wpf/testing/coded-ui)
