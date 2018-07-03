---
layout: post
title: Float Window of Syncfusion DockingManager control for WPF
description: This topic deals with float window features and how to position the float window
platform: wpf
control: DockingManager
documentation: ug
---
# Floating Window

Floating window is one of the state in the DockingManager. To make children of the DockingManager as Float, set its `State` values as `Float`.

Floating window is like a Popup and it has some limitation in resizing. To avoid this limitation, set the `UseNativeFloatWindow` property of the DockingManager as `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Float"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

dock.UseNativeFloatWindow = true;
			
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();
			
//Set Header

DockingManager.SetHeader(content1, "Item1");

//Set State

DockingManager.SetState(content1, DockState.Float);

//Add content controls to child of DockingManager

dock.Children.Add(content1);
			
//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

![](FloatingWindow_images/FloatingWindow_img1.jpeg)


## Rolling Up support

The float window is rolled up to top using the property `IsRollUpTopProperty`. To enable this functionality set its value as `True`, by default its value is `False`.        

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager IsRollupFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Float"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

dock.IsRollupFloatWindow = true;

//Create the instance of ContentControl

ContentControl content1 = new ContentControl();
			
//Set Header

DockingManager.SetHeader(content1, "Item1");

//Set State

DockingManager.SetState(content1, DockState.Float);

//Add content controls to child of DockingManager

dock.Children.Add(content1);
			
//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

![](FloatingWindow_images/FloatingWindow_img2.jpeg)

## Displaying Float Windows in Taskbar

Taskbar displays the icon of running applications for the purpose of switching between applications. Similarly `DockingManager` allows to display `NativeFloatWindow` in taskbar. It can be set using `ShowFloatWindowInTaskbar` property for all the `NativeFloatWindow` in `DockingManager` and default is false. Only `NativeFloatWindow` icon can be displayed in taskbar so it is necessary to set `UseNativeFloatWindow` to true. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager ShowFloatWindowInTaskbar="True" UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Toolbox"
                syncfusion:DockingManager.State="Float"
                Content="No items to display in toolbox"/>
                
<ContentControl syncfusion:DockingManager.Header="Solution Explorer"
                syncfusion:DockingManager.State="Float"
                Content="Loading failed"/>
                
</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//Show Floating Windows icons in TaskBar

dock.ShowFloatWindowInTaskbar = true;
			
dock.UseNativeFloatWindow = true;

//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Content = "No items to display in toolbox";

content2.Content = "Loading failed";

//Set Header

DockingManager.SetHeader(content1, "ToolBox");

DockingManager.SetHeader(content2, "Solution Explorer");

//Set State

DockingManager.SetState(content1, DockState.Float);

DockingManager.SetState(content2, DockState.Float);

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content1);
			
//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

### Show or Hide the Taskbar support for Selective Windows

To enable or disable the taskbar support for particular window, use the attached property `ShowInTaskbar` of `DockingManager` and the default is true. It is necessary to set `ShowFloatWindowInTaskbar` property of `DockingManager` to true for displaying even a single `NativeFloatWindow` in taskbar.

{% tabs %}

{% highlight XAML %}


<syncfusion:DockingManager ShowFloatWindowInTaskbar="True" UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Toolbox" syncfusion:DockingManager.State="Float"
                syncfusion:DockingManager.ShowInTaskbar="False"
                Content="No items to display in toolbox"/>

<ContentControl syncfusion:DockingManager.Header="Solution Explorer"
                syncfusion:DockingManager.State="Float"
                Content="Loading failed"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//Show Floating Windows icons in TaskBar

dock.ShowFloatWindowInTaskbar = true;
			
dock.UseNativeFloatWindow = true;

//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Content = "No items to display in toolbox";

content2.Content = "Loading failed";

//Set Header

DockingManager.SetHeader(content1, "ToolBox");

DockingManager.SetHeader(content2, "Solution Explorer");

//Set State

DockingManager.SetState(content1, DockState.Float);

DockingManager.SetState(content2, DockState.Float);

//To enable or disable the taskbar support for particular window

DockingManager.SetShowInTaskbar(content1, false);

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);
			
//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

## Multiple Monitor functionalities

The default behavior of the float window remains as Popup in the DockingManager. 

On using MultiMonitor scenario, the FloatWindow behavior as follows:

* FloatWindow can be resized both in primary and secondary monitor.
* On showing half of the float window between primary and secondary monitor, the float window remains in half between the monitor while plugged in and plugged out of the secondary monitor.
* When float window is moved to secondary monitor from primary monitor, the float window remains at the secondary monitor itself while plugged in.

To make float window behave like a WPF window in multiple monitor, set the property `UseNativeFloatWindow` as `True`. 

## Enabling or Disabling the float functionality

The `CanFloat` property helps to enable or disable the floating functionality by setting its value as `True` or `False` respectively. By default its value is `True`, to disable this functionality turn its value to `False`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" >

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.CanFloat="True"/>

<ContentControl syncfusion:DockingManager.Header="Item2" syncfusion:DockingManager.CanFloat="False"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Content = "No items to display in toolbox";

content2.Content = "Loading failed";

//Set Header

DockingManager.SetHeader(content1, "ToolBox");

DockingManager.SetHeader(content2, "Solution Explorer");

//To Enable the Float Functionality 

DockingManager.SetCanFloat(content1, true);

//To disable the Float Functionality

DockingManager.SetCanFloat(content2, false);
			
//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

![](FloatingWindow_images/FloatingWindow_img3.jpeg)


## Enabling and Disabling the float functionality Operation on Double Click

The float window changes its state to `Dock` when double click its header by default. To disable this functionality for the specific child, set `NoDock` property as `True`.       

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" 
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.NoDock="True"/>                      

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

//Set Header

DockingManager.SetHeader(content1, "Item1");

//To disable float functionality for the specific child

DockingManager.SetNoDock(content1, true);

DockingManager.SetState(content1, DockState.Float);

//Add content controls to child of DockingManager

dock.Children.Add(content1);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

## Maximize/Minimize Support

The float window provides Maximization support for better usability and it is only applicable for NativeFloatWindow. To enable the maximizing feature for the Float window, set `CanFloatMaximize` for the specific child as `True`. By default, its value is `False`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" 
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanFloatMaximize="True"/>    

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

dock.UseNativeFloatWindow = true;
			
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();
			
//Set Header

DockingManager.SetHeader(content1, "Item1");

//Set State

DockingManager.SetState(content1, DockState.Float);

//Set Float Window Maximization support

DockingManager.SetCanFloatMaximize(content1, true);

//Add content controls to child of DockingManager

dock.Children.Add(content1);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

![](FloatingWindow_images/FloatingWindow_img4.jpeg)


## Positioning on desire location

The FloatWindow can be placed at any desired location. To position the FloatWindow at the desired location with the required Rect Bounds, call `SetFloatingWindowRect` method of the DockingManager.


{% tabs %}

{% highlight C# %}

DockingManager.SetFloatingWindowRect(Content1,new Rect(200,200,200,200));

{% endhighlight %}

{% highlight VB %}

DockingManager.SetFloatingWindowRect(Content1, New Rect(200, 200, 200, 200)) 

{% endhighlight %}

{% endtabs %}
![](FloatingWindow_images/FloatingWindow_img5.jpeg)

## Snapping Float window

Float window can be snapped with the edge of another float window and moving all together in `DockingManager`. To enable snapping window feature for the Float window, set `AllowSnap` for the specific child as `True` and set `EnableSnappingFloatWindow` as `True` in `DockingManager`. By default, its value is `False`

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager  EnableSnappingFloatWindow="True">
  <ContentControl x:Name="Dock1" syncfusion:DockingManager.Header="Dock1"
                                 syncfusion:DockingManager.AllowSnap="True"/>
  <ContentControl x:Name="Dock2" syncfusion:DockingManager.Header="Dock2"
                                 syncfusion:DockingManager.AllowSnap="True"/>
  <ContentControl x:Name="Dock3" syncfusion:DockingManager.Header="Dock3"
                                 syncfusion:DockingManager.AllowSnap="True"/>
  <ContentControl x:Name="Dock4" syncfusion:DockingManager.Header="Dock4"
                                 syncfusion:DockingManager.AllowSnap="True"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

dock.EnableSnappingFloatWindow = true;
			
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

ContentControl content3 = new ContentControl();

ContentControl content4 = new ContentControl();

//Set Header

DockingManager.SetHeader(content1, "Dock1");

DockingManager.SetHeader(content2, "Dock2");

DockingManager.SetHeader(content3, "Dock3");

DockingManager.SetHeader(content4, "Dock4");

//Set State

DockingManager.SetState(content3, DockState.Float);

DockingManager.SetState(content4, DockState.Float);

//Set AllowSnap

DockingManager.SetAllowSnap(content1, true);

DockingManager.SetAllowSnap(content2, true);

DockingManager.SetAllowSnap(content3, true);

DockingManager.SetAllowSnap(content4, true);

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

dock.Children.Add(content3);

dock.Children.Add(content4);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}


![](FloatingWindow_images/FloatingWindow_img6.jpeg)

We can get the snapped windows collection for specific float child using `GetSnappedWindows` method.

{% tabs %}

{% highlight C# %}

DockingManager.GetSnappedWindows(Dock1); 

{% endhighlight %}

{% endtabs %}