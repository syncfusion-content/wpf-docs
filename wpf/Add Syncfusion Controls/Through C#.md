## Through C# / VB

The following steps will helps to add a required Essential WPF Control (For example:DockingManager) through C# / VB Code

1. Create a WPF project in Visual Studio and refer the following assemblies.
* Syncfusion.Tools.Wpf
* Syncfusion.Shared.Wpf
2. Create instance of Docking Manager.

{% highlight c# %}

Syncfusion.Windows.Tools.Controls.DockingManager dockingManager = new Syncfusion.Windows.Tools.Controls.DockingManager();

{% endhighlight %}

3. Add the DockingManager instace as the content of the Window (or required element). 

{% highlight c# %}

Syncfusion.Windows.Tools.Controls.DockingManager dockingManager = new Syncfusion.Windows.Tools.Controls.DockingManager(); 

this.Content = dockingManager; 

{% endhighlight %}

