---
layout: post
title: Events
description: events
platform: wpf
control: ButtonAdv
documentation: ug
---

# Events

The ButtonAdv control comprises the following events:

* Click—The event occurs when the ButtonAdv Control is clicked.

The following code adds the Click event handler to the ButtonAdv control:

<table>
<tr>
<td>
[XAML]&lt;sync:ButtonAdv Click="button_Click"/&gt;</td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Click += new RoutedEventHandler(button_Click);</td></tr>
</table>


* Checked—The event occurs when the element is checked.

The following code adds the Checked event handler to the ButtonAdv control:

<table>
<tr>
<td>
[XAML]&lt;sync:ButtonAdv Checked="button_Checked"/&gt;</td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Checked += new RoutedEventHandler(button_Checked);</td></tr>
</table>


