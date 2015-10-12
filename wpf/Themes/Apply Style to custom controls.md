---
layout: post
title: Themes
description: common supports
platform: wpf
control: Themes
documentation: ug
---
## Apply Style to custom controls

To apply the build in themes to your derived control using SfSkinManager, you have to set the **SetResourceReference** in the custom control. This is required to refer style property of the derived control.

{% highlight xml %}


<local:DockingAdv x:Name="SyncDockingManager" UseDocumentContainer="True" PersistState="True" >

<ContentControl x:Name="SolutionExplorer" local:DockingAdv.Header="Solution Explorer"  local:DockingAdv.SideInDockedMode="Right"/>

<ContentControl x:Name="ToolBox" local:DockingAdv.Header="Toolbox" local:DockingAdv.State="AutoHidden" />

<ContentControl x:Name="Properties" local:DockingAdv.Header="Properties" local:DockingAdv.State="Float" />

<ContentControl x:Name="Output" local:DockingAdv.Header="Output" local:DockingAdv.SideInDockedMode="Tabbed" local:DockingAdv.TargetNameInDockedMode="SolutionExplorer"/>

<ContentControl x:Name="StartPage" local:DockingAdv.Header="Start Page" local:DockingAdv.State="Document" />

</local:DockingAdv>

public class DockingAdv : DockingManager

{

public DockingAdv()

{

SetResourceReference(StyleProperty, typeof(DockingManager));

}

}



{% endhighlight %}

