---
layout: post
title: Cancel the ActiveWindow Change | DockingManager | wpf | Syncfusion
description: Cancel the activewindow change in Syncfusion Essential Studio WPF DockingManager Control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# Cancel the ActiveWindow Change

ActiveWindowChanging event is used to cancel the ActiveWindow change. This event will be triggered before the new window is set as active window, the usage is shown below.


{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager UseDocumentContainer="True"     ActiveWindowChanging="DockingManager_ActiveWindowChanging">            
	 
	<Grid Name="grid1" syncfusion:DockingManager.Header="grid1" syncfusion:DockingManager.State="Document"/>

	<Grid Name="grid2" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.State="Document"/>

	<Grid Name="grid3" syncfusion:DockingManager.Header="grid3" syncfusion:DockingManager.State="Document"/>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

private void DockingManager_ActiveWindowChanging(FrameworkElement sender, Syncfusion.Windows.Tools.Controls.ActiveWindowChangingEventArgs e)
{     
   if (sender.Name == "grid1")     
   {         
     e.Cancel = true;     
   }
}

{% endhighlight  %}

{% endtabs %}
