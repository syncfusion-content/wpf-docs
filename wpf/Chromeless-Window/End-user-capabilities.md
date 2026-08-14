---
layout: post
title: End-User Capabilities in WPF ChromelessWindow | Syncfusion®
description: End-user capabilities in the ChromelessWindow provide support for window operations such as moving, resizing, minimizing, and maximizing.
platform: wpf
control: ChromelessWindow
documentation: ug
---
# End-User Capabilities in WPF ChromelessWindow

The user can perform the operations listed below through the UI provided by the ChromelessWindow.

1. Maximize/Minimize

2. Restore

3. Close

4. Resize

## Maximize/Minimize

The end user can maximize or minimize the window by using the Maximize and Minimize buttons at the top-right corner of the ChromelessWindow.

![End-user-capabilities_images1](End-user-capabilities_images/End-user-capabilities_img1.jpeg)

## Restore

After the window is minimized or maximized, the respective button is replaced by a **Restore** button. By clicking this restore button, the user can bring the **ChromelessWindow** to its **Normal** state.

![End-user-capabilities_img2](End-user-capabilities_images/End-user-capabilities_img2.jpeg)

## Close

The user can close the window by using the Close button at the top-right corner of the ChromelessWindow.

![End-user-capabilities_images3](End-user-capabilities_images/End-user-capabilities_img3.jpeg)

## Resize

The window can be resized by clicking and dragging the resize border.

ChromelessWindow supports the following four resize modes. The default value is `CanResize`.

* `NoResize`
* `CanMinimize`
* `CanResize`
* `CanResizeWithGrip`

### NoResize

In `NoResize` mode, the window cannot be resized. The Minimize and Maximize buttons are not displayed in the title bar.

![End-user-capabilities_img4](End-user-capabilities_images/End-user-capabilities_img4.jpeg)

### CanMinimize

In `CanMinimize` mode, the window can only be minimized, since only the Minimize button is enabled.

![End-user-capabilities_img5](End-user-capabilities_images/End-user-capabilities_img5.jpeg)

### CanResize

In `CanResize` mode, a window can be resized. The Minimize and Maximize buttons are both shown and enabled.

![End-user-capabilities_img6](End-user-capabilities_images/End-user-capabilities_img6.jpeg)

### CanResizeWithGrip

In `CanResizeWithGrip` mode, a window can be resized. A resize grip appears in the bottom-right corner of the window. The Minimize and Maximize buttons are both shown and enabled.

![End-user-capabilities_img7](End-user-capabilities_images/End-user-capabilities_img7.jpeg)
