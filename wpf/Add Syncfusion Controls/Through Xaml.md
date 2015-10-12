## Through XAML

The following steps will helps to add a required Essential WPF Control (For example__:__ DockingManager) through XAML Code

1. Create a WPF project in Visual Studio and refer the following assemblies.
* Syncfusion.Tools.Wpf
* Syncfusion.Shared.Wpf
2. Include an xml namespace for the above assemblies to the Main window.
{% highlight xml %}

<Window

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion=[http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "") />



{% endhighlight %}

3. Now, Add the Docking Manager control with a required optimal name, using the included namespace.

{% highlight xml %}

<syncfusion:DockingManager x:Name="SyncDockingManager" />



{% endhighlight %}

