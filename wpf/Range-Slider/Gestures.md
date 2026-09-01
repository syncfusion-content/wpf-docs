---
layout: post
title: Gestures in WPF Range Slider | Syncfusion®
description: Interact with the WPF Range Slider using keyboard navigation and mouse gestures for precise value and range selection.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Gestures in WPF Range Slider (SfRangeSlider)

The WPF Range Slider control supports keyboard navigation and mouse interactions, allowing users to select and modify values efficiently. You can move the slider thumbs using navigation keys, drag the thumbs with the mouse, or click the track to update the selected value or range.

## Keyboard 

The focused Thumb moves a certain distance on every navigation key press.  

### Left Key    

Thumb moves left and updates the corresponding value.  

### Right Key 

Thumbs moves right and updates the corresponding value.  

### Down Key 

Thumb moves down and updates the corresponding value.  

### Up Key 

Thumb moves up and updates the corresponding value.   

N> When the SnapsTo property is set to Ticks then the Thumb snaps to next tick based on the navigation key pressed.  

## Mouse  

The WPF Range Slider allows the mouse gesture to update the value of the WPF Range Slider either by dragging the thumb to a certain distance or by pressing the specified region in the track.  

N> When the thumb is released between two steps or when the pointer is pressed between two steps, then the value and thumb automatically snaps to nearest value.



