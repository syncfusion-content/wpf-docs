---
layout: post
title: Gestures in WPF Range Slider Control | Syncfusion®
description: Learn about Gesture support in the Syncfusion® WPF Range Slider (SfRangeSlider) control and more.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Gestures in WPF Range Slider (SfRangeSlider)

## Keyboard Gestures
The focused thumb shifts a specified distance with each navigation key press.

### Left Key    

The thumb shifts left, updating its value accordingly.
### Right Key 

The thumb shifts right, updating its value accordingly.
### Down Key 

The thumb shifts down, updating its value accordingly.
### Up Key 

The thumb shifts up, updating its value accordingly.
> **Note**: When the `SnapsTo` property is set to `Ticks`, the thumb snaps to the next tick based on the navigation key pressed.

## Mouse Gestures

The RangeSlider supports mouse gestures, allowing the SfRangeSlider's value to be updated either by dragging the thumb or by clicking a specific region of the track.
> **Note**: When the thumb is released between two steps, or when the pointer is clicked between two steps, the value and thumb position automatically snap to the nearest value.
