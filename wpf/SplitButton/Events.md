---
layout: post
title: Events
description: events
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Events

The SplitButtonAdv control comprises the following events:

Click 

This event occurs when the SplitButtonAdv control is clicked.

The following code adds the Click event handler to the SplitButtonAdv control:



[XAML]

<shared:SplitButtonAdv Click="SplitButtonAdv_Click"/>



[C#]

SplitButtonAdv button = new SplitButtonAdv();

button.Click +=new RoutedEventHandler(button_Click);



DropDownOpening 

This event occurs before opening the DropDown.

The following code adds the DropDownOpening event handler to the SplitButtonAdv control:



[XAML]

<shared:SplitButtonAdv DropDownOpening="SplitButtonAdv_DropDownOpening"/>



[C#]

SplitButtonAdv button = new SplitButtonAdv();

button.DropDownOpening +=new CancelEventHandler(button_DropDownOpening);



DropDownOpened 

This event occurs after opened the DropDown. 

The following code adds the DropDownOpened event handler to the SplitButtonAdv control:



[XAML]

<shared:SplitButtonAdv DropDownOpened="SplitButtonAdv_DropDownOpened"/>



[C#]

SplitButtonAdv button = new SplitButtonAdv();

button.DropDownOpened +=new RoutedEventHandler(button_DropDownOpened);



DropDownClosing 

This event occurs before closing the DropDown.

The following code adds the DropDownClosing event handler to the SplitButtonAdv control:



[XAML]

<shared:SplitButtonAdv DropDownClosing="SplitButtonAdv_DropDownClosing"/>



[XAML]

SplitButtonAdv button = new SplitButtonAdv();

button.DropDownClosing +=new CancelEventHandler(button_DropDownClosing);



DropDownClosed 

This event occurs after closed the DropDown.

The following code adds the DropDownClosed event handler to the SplitButtonAdv control:



[XAML]

<shared:SplitButtonAdv DropDownClosed="SplitButtonAdv_DropDownClosed"/>



[C#]

SplitButtonAdv button = new SplitButtonAdv();

button.DropDownClosed +=new RoutedEventHandler(button_DropDownClosed);



