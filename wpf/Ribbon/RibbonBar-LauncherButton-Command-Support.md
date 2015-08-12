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



## Setting RibbonBar LauncherButton Command

Command for RibbonBar LauncherButton can be set using LauncherCommand attached property. The following code example illustrates this.



{% highlight xml %}


[XAML] 
<TextBox Name="mainTextBox" Width="150"></TextBox>       

 <!-- LauncherButton Command and LauncherButton CommandTarget-->       
 <syncfusion:RibbonBar  IsLauncherButtonVisible="True" syncfusion:RibbonBar.LauncherCommand="ApplicationCommands.Paste" syncfusion:RibbonBar.LauncherCommandTarget="{Binding ElementName=mainTextBox}" >        
 </syncfusion:RibbonBar>
{% endhighlight %}

{% highlight C# %}

[C#]
//LauncherButton Command
RibbonBar.SetLauncherCommand(mainRibbonBar, ApplicationCommands.Paste);

//LauncherButton CommandTarget
RibbonBar.SetLauncherCommandTarget(mainRibbonBar, mainTextBox);

{% endhighlight %}

