---
layout: post
title: QTP-Support-for-DateTimeEdit-control
description: qtp support for datetimeedit control
platform: wpf
control: DateTimeEdit
documentation: ug
---

# QTP Support for DateTimeEdit control

The QTP tool can recognize the DateTimeEdit control. Hence with the DateTimeEdit control,  it is possible to record interactions such as opening the calendar popup, closing the calendar popup, choosing the date from  the calendar , setting the DateTime value and and so on, for testing using QTP.

## Mapping the Control to the Custom Server

QTP Tool interacts with the control through CustomServerBase extension through the RunInterface. The custom server must be mapped to the control type for the tool to identify the control. A conventional configuration file (*.cfg) will resemble the one shown in the following code snippet. When the configuration file and the dll containing the server type are loaded, QTP will recognize the control and record it.



[C#]

&lt;?xml version="1.0" encoding="UTF-8"?&gt;

&lt;Controls&gt;

  &lt;Control Type="Syncfusion.Windows.Shared.DateTimeEdit" MappedTo="SfDateTimeEdit"&gt;

    &lt;CustomServer&gt;

      &lt;Component&gt;

        <DllName>Syncfusion.QtpDateTimeEdit.Wpf.dll</DllName>

        <TypeName>Syncfusion.Windows.Controls.QTP.DateTimeEditServer</TypeName>

      &lt;/Component&gt;

    &lt;/CustomServer&gt;

  &lt;/Control&gt;

&lt;/Controls&gt;





This XML configuration file should contain the fully qualified type name of the control, fully qualified name of the custom server and the name of the dll containing the custom server.

MappedTo attribute, points to the name of the ClassInfo (an XML file containing the API information about the RunInterface).

