---
layout: post
title: Localization | DockingManager | WPF | Syncfusion®
description: Learn here about Localization in Syncfusion® Essential Studio® WPF DockingManager control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# Localization in WPF DockingManager control

Localization customizes the application towards a specific language and region. Syncfusion® Tools allow you to set custom resources through a `.resx` file. The table below shows how each DockingManager property is localized in English and French.

## Steps to localize

1. Add a `.resx` file (for example, `Syncfusion.Tools.Wpf.resx`) to your project, or use the default Syncfusion resources.
2. Set the `CultureInfo` of the current thread (e.g. `Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");`) at application startup.
3. Provide translated strings for the resource keys listed in the table below.
4. The DockingManager (and the rest of Syncfusion Tools) will pick up the localized values automatically.

The following table summarizes the resource keys used by the DockingManager.

<table>
<tr>
<th>
 Property</th><th>
Description</th></tr>
<tr>
<td>
FloatButtonTooltipText </td><td>
Sets the string for the ToolTip of Float button in the DockingManager.</td></tr>
<tr>
<td colspan = "2">
Float(en-US)                                           Flotteur(fr-FR)</td></tr>
<tr>
<td>
AwlButtonTooltipText</td><td>
Sets the string for the ToolTip of Auto Hide button in the DockingManager.</td></tr>
<tr>
<td colspan = "1">
![Localization_images1](Localization_images/Localization_img1.png)
</td>
<td>
![Localization_images2](Localization_images/Localization_img2.png)

</td></tr>
<tr>
<td>
CloseButtonTooltipText</td><td>
Sets the string for ToolTip of Close button in DockingManager.</td></tr>
<tr>
<td colspan = "1">
![Localization_images3](Localization_images/Localization_img3.png)

_CloseButtonTooltipText(en-US)_
</td>
<td>
![Localization_images4](Localization_images/Localization_img4.png)

_CloseButtonTooltipText(fr-FR)_</td></tr>
<tr>
<td>
ContextMenuButtonTooltipText</td><td>
Sets the string for the ToolTip of Context Menu button in DockingManager.</td></tr>
<tr>
<td colspan = "1">
![Localization_images5](Localization_images/Localization_img5.png)
</td>
<td>
![Localization_images6](Localization_images/Localization_img6.png)

</td></tr>
<tr>
<td>
TabbedAutoHideHide</td><td>
Sets the string for the context menu item in DockingManager.</td></tr>
<tr>
<td colspan = "1">
![Localization_images7](Localization_images/Localization_img7.png)

_ContextMenu(en-US)_
</td>
<td>
![Localization_images8](Localization_images/Localization_img8.png)

_ContextMenu(fr-FR)_</td></tr>
<tr>
<td>
MoveToNextTabGroup </td><td>
Sets the string for MoveToNextTabGroup context menu item in the DockingManager and Document Container.</td></tr>
<tr>
<td colspan = "1">
![Localization_images9](Localization_images/Localization_img9.png)

_MoveToNextTabGroup(en-US)_
</td>
<td>
![Localization_images10](Localization_images/Localization_img10.png)

_MoveToNextTabGroup(fr-FR)_</td></tr>
<tr>
<td>
MoveToPreviousTabGroup</td><td>
Sets the string for MoveToPreviousTabGroup context menu item in the DockingManager and Document Container.</td></tr>
<tr>
<td colspan = "1">
![Localization_images11](Localization_images/Localization_img11.png)

_MoveToPreviousTabGroup(en-US)_
</td>
<td>
![Localization_images12](Localization_images/Localization_img12.png)

_MoveToPreviousTabGroup(fr-FR)_</td></tr>
<tr>
<td>
NewTabgroupMenuItemCancel</td><td>
Sets the string for the Tab context menu item in the DockingManager and Document Container.</td></tr>
<tr>
<td colspan = "1">
![Localization_images13](Localization_images/Localization_img13.png)

_NewTabGroup(en-US)_
</td>
<td>
![Localization_images14](Localization_images/Localization_img14.png)

_NewTabGroup(fr-FR)_</td></tr>
<tr>
<td>
TabCloseCloseAllButThisTabCloseAllFloatingDocumentDockableNewHorizontalTabGroupNewVerticalTabGroup</td><td>
Sets the string for the menu item in the Document Container and DockingManager.</td></tr>
<tr>
<td colspan = "1">
![Localization_images15](Localization_images/Localization_img15.png)

_MenuItem(en-US)_
</td>
<td>
![Localization_images16](Localization_images/Localization_img16.png)

_MenuItem(fr-FR)_</td></tr>
</table>


