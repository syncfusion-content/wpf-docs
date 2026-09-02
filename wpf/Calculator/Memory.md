---
layout: post
title: Memory in WPF SfCalculator | Syncfusion®
description: Store and recall values with the built-in memory support of the Syncfusion WPF SfCalculator control for repeated calculations.
platform: wpf
control: SfCalculator
documentation: ug
---

# Memory in WPF SfCalculator

The [SfCalculator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html) control supports memory operations that let users store, recall, add to, subtract from, and clear a single value, much like a standard pocket calculator. The memory is held per `SfCalculator` instance and is reset to `0` when the control is first created.

The [Memory](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfCalculator.html#Syncfusion_Windows_Controls_Input_SfCalculator_Memory) property retrieves the value currently stored in memory.

N> The `Memory` property is a **Read-Only** property of type `decimal`. The default value is `0`. There is no `MemoryChanged` event; if you need to react to memory updates, read the `Memory` property after the user performs a memory operation (for example, in a button click handler).

The following buttons are available in the SfCalculator control to perform memory-related operations.

## MS

The `MS` button performs memory storage. Clicking the `MS` button will store the current calculator value in memory, where it can be retrieved and used later.

## MR

The `MR` button performs memory restore. Clicking the `MR` button will paste the value stored in memory into the current expression for use in further calculations.

## M+

Clicking the `M+` button will add the current calculator value to the value already stored in memory. The new total is then stored in memory.

## M-

Clicking the `M-` button will subtract the current calculator value from the value already stored in memory. The new total is then stored in memory.

## MC

Clicking the `MC` button clears the value stored in memory by resetting it to `0`.





