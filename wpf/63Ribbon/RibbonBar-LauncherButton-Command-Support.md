---
layout: post
title: RibbonBar-LauncherButton-Command-Support
description: ribbonbar launcherbutton command support
platform: wpf
control: Ribbon
documentation: ug
---

# RibbonBar LauncherButton Command Support

Ribbon instance now provides command support for RibbonBar LauncherButton. It provides the following option.

* Setting LauncherButton Command
* Setting LauncherButton CommandTarget
* Setting LauncherButton CommandParameter



Setting RibbonBar LauncherButton Command

Command for RibbonBar LauncherButton can be set using LauncherCommand attached property. The following code example illustrates this.



<table>
<tr>
<td>
[XAML] &lt;TextBox Name="mainTextBox" Width="150"&gt;&lt;/TextBox&gt;        &lt;!-- LauncherButton Command and LauncherButton CommandTarget--&gt;        &lt;syncfusion:RibbonBar  IsLauncherButtonVisible="True" syncfusion:RibbonBar.LauncherCommand="ApplicationCommands.Paste" syncfusion:RibbonBar.LauncherCommandTarget="{Binding ElementName=mainTextBox}" &gt;        &lt;/syncfusion:RibbonBar&gt;</td></tr>
<tr>
<td>
[C#]//LauncherButton CommandRibbonBar.SetLauncherCommand(mainRibbonBar, ApplicationCommands.Paste);//LauncherButton CommandTargetRibbonBar.SetLauncherCommandTarget(mainRibbonBar, mainTextBox);</td></tr>
</table>


