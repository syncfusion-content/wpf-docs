---
layout: post
title: Disable TabGroup Resize Preview | DockingManager | wpf | Syncfusion
description: disable tabgroup resize preview
platform: wpf
control: DockingManager
 documentation: ug
---

# Disable TabGroup Resize Preview

TabGroup preview can be enabled or disabled by using the IsTabPreviewEnabled property. The default value of the TabGroup preview is true. The usage of this property is shown below.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="dockingmanager" IsTabPreviewEnabled="False" UseDocumentContainer="True"> 

    <Grid syncfusion:DockingManager.Header="tab1" syncfusion:DockingManager.State="Document"/>            
	
	<Grid syncfusion:DockingManager.Header="tab2" syncfusion:DockingManager.State="Document"/>        
	
</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

dockingmanager.IsTabPreviewEnabled = false;

{% endhighlight  %}

{% endtabs %}



The above code disables the TabGroup preview, which is created by dragging and dropping the tab items.

