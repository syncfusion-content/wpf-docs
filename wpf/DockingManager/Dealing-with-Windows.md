---
layout: post
title: Dealing with Windows of Syncfusion DockingManager control for WPF
description: Learn how to deal with windows of DockingManager progrmmatically and customize the windows
platform: wpf
control: DockingManager
documentation: ug
---
# Dealing with Windows

## Activating a window

A particular child window can be activated in DockingManager using its name or reference through the property `ActiveWindow` and `ActivateWindow` method that passes the element as argument to activate.

{% tabs %}

{% highlight C# %}

DockingManager1.ActiveWindow = Content1;

DockingManager1.ActivateWindow("Content1");

{% endhighlight %}

{% highlight VB %}

DockingManager1.ActiveWindow = Content1

DockingManager1.ActivateWindow("Content1") 

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img1.jpeg)


## Adding Window Programmatically

Any UI element can be added inside the DockingManager as its child windows. The windows is added as Dock windows, since the default value of the state is `Dock`.  The UI element is added in the DockingManager using the `Add` method of the Children property of the DockingManager.

For example, ContentControl is added as a window for DockingManager

{% tabs %}

{% highlight C# %}

DockingManager DockingManager1 = new DockingManager();

ContentControl content1 = new ContentControl();

DockingManager.SetHeader(content1,"Window1");

ContentControl content2 = new ContentControl();

DockingManager.SetHeader(content2,"Window2");

ContentControl content3 = new ContentControl();

DockingManager.SetHeader(content3, "Window3");

ContentControl content4 = new ContentControl();

DockingManager.SetHeader(content4,"Window4");

ContentControl content5 = new ContentControl();

DockingManager.SetHeader(content5,"window5");

DockingManager1.Children.Add(content1);

DockingManager1.Children.Add(content2);

DockingManager1.Children.Add(content3);

DockingManager1.Children.Add(content4);

DockingManager1.Children.Add(content5);




{% endhighlight %}

{% highlight VB %}

Dim DockingManager1 As New DockingManager()

Dim content1 As New ContentControl()

DockingManager.SetHeader(content1, "Window1")

Dim content2 As New ContentControl()

DockingManager.SetHeader(content2, "Window2")

Dim content3 As New ContentControl()

DockingManager.SetHeader(content3, "Window3")

Dim content4 As New ContentControl()

DockingManager.SetHeader(content4, "Window4")

Dim content5 As New ContentControl()

DockingManager.SetHeader(content5, "window5")

DockingManager1.Children.Add(content1)

DockingManager1.Children.Add(content2)

DockingManager1.Children.Add(content3)

DockingManager1.Children.Add(content4)

DockingManager1.Children.Add(content5) 

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img2.jpeg)


### Setting State for Window programmatically

The state for the particular child window can be set programmatically using the `SetState` method of DockingManager.

{% tabs %}

{% highlight C# %}

DockingManager.SetState(content1, DockState.Float);


{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(content1, DockState.Float) 

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img3.jpeg)





* Setting state as Document – To create document window in the DockingManager, set UseDocumentContainer as True for DockingManager and set its state as Document.

{% tabs %}

{% highlight C# %}

DockingManager1.UseDocumentContainer = true;
DockingManager.SetState(content1, DockState.Document);

{% endhighlight %}

{% highlight VB %}

DockingManager1.UseDocumentContainer = True
DockingManager.SetState(content1, DockState.Document)

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img4.jpeg)


* Setting state as AutoHidden

{% tabs %}

{% highlight C# %}

DockingManager.SetState(content1, DockState.AutoHidden);

{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(content1, DockState.AutoHidden)

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img5.jpeg)

#### Making Window AutoHide programmatically

To auto hide the window programmatically call `ExecuteAutoHide` method of DockingManager.

{% tabs %}

{% highlight C# %}

DockingManager1.ExecuteAutoHide(Content1);

{% endhighlight %}

{% highlight VB %}

DockingManager1.ExecuteAutoHide(Content1)

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img6.jpeg)


#### Making Window Float and Document programmatically

The docking window can be made to float and document using the SetState method with its DockState value as `Float` and `Document` respectively

{% tabs %}

{% highlight C# %}

//to make the content1 float 

DockingManager.SetState(Content1, DockState.Float);

//to make the content1 as Document window

DockingManager.SetState(Content1, DockState.Document);

{% endhighlight %}

{% highlight VB %}

'to make the content1 float 

DockingManager.SetState(Content1, DockState.Float)

'to make the content1 as Document window

DockingManager.SetState(Content1, DockState.Document)

{% endhighlight %}

{% endtabs %}

## Hiding Window Programmatically

To hide the window, set `State` property of the DockingManager as `Hidden`.

{% tabs %}

{% highlight C# %}

DockingManager.SetState(Content1, DockState.Hidden);

{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(Content1, DockState.Hidden)

{% endhighlight %}

{% endtabs %}

To hide the window programmatically, call the `ExecuteClose` method with argument which refer the window need to be close.

{% tabs %}

{% highlight C# %}

//Hide the element that passed as argument
DockingManager1.ExecuteClose(Content1); 
  
{% endhighlight %}

{% highlight VB %}

'Hide the element that passed as argument
DockingManager1.ExecuteClose(Content1)

{% endhighlight %}

{% endtabs %}

## Restore Window Programmatically

To restore the closed window in the DockingManager, call `ExecuteRestore` method.

{% tabs %}

{% highlight C# %}

//Restore the passed element with the state value as its argument

DockingManager1.ExecuteRestore(Content1, DockState.Float); 


{% endhighlight %}


{% highlight VB %}

'Restore the passed element with the state value as its argument

DockingManager1.ExecuteRestore(Content1, DockState.Float) 

{% endhighlight %}

{% endtabs %}

## Detect the closing of a DockingManager child

`WindowClosing` and `CloseButtonClick` are the two events, which can be used to get notification when the child windows are being closed. 

### Dock Window Closing

`WindowClosing` event raised whenever a child in `Float`, `Dock` and `AutoHidden` windows are closing. 

### Document Window Closing
 
`CloseButtonClick` event raised only when close button of the `Document` child clicked. The following code describes how to handle the closing of all the children in `DockingManager`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="dockingManager" CloseButtonClick="dockingManager_CloseButtonClick"
                                                   WindowClosing="dockingManager_WindowClosing">

<ContentControl syncfusion:DockingManager.Header="Left"
                syncfusion:DockingManager.SideInDockedMode="Left"
                syncfusion:DockingManager.State="AutoHidden" />            

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

// For windows in Document state
dockingManager.CloseButtonClick += Docking_CloseButtonClick;

// For windows in Float, Dock and AutoHidden state
dockingManager.WindowClosing += Docking_WindowClosing;

private void dockingManager_CloseButtonClick(object sender, CloseButtonEventArgs e)

{

}

private void dockingManager_WindowClosing(object sender, WindowClosingEventArgs e)

{

}

{% endhighlight %}

{% endtabs %}

## Removing Window Programmatically

The windows for the DockingManager can be added using the Children collection. To remove the windows from the children collection, pass the window element that need to be remove using `Remove()` method of children property in DockingManager.

{% tabs %}

{% highlight C# %}

DockingManager dockingmanager  = new DockingManager();

ContentControl content1 = new ContentControl();

DockingManager.SetHeader(content1, "Dockwindow");

ContentControl content2 = new ContentControl();

DockingManager.SetHeader(content2,"Dockwindow2");

dockingmanager.Children.Add(content1);

dockingmanager.Children.Add(content2);

//The following code describes how to remove the child window programmatically using the remove method.

dockingmanager.Children.Remove(content2);

Grid1.Children.Add(dockingmanager);

{% endhighlight %}

{% highlight VB %}

Dim dockingmanager As New DockingManager()

Dim content1 As New ContentControl()

DockingManager.SetHeader(content1, "Dockwindow")

Dim content2 As New ContentControl()

DockingManager.SetHeader(content2,"Dockwindow2")

dockingmanager.Children.Add(content1)

dockingmanager.Children.Add(content2)

'The following code describes how to remove the child window programmatically using the remove method.

dockingmanager.Children.Remove(content2)

Grid1.Children.Add(dockingmanager) 

{% endhighlight %}

{% endtabs %}

## Restricting Docking in Float Window

The float window allows to dock another float window inside it by default. This behavior can be restricted by set `CanDockOnFloat` as False for that particular window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1">

<ContentControl syncfusion:DockingManager.Header="Item1"
                syncfusion:DockingManager.State="Float"
                syncfusion:DockingManager.CanDockonFloat="False"/>  

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}
            
DockingManager.SetCanDockonFloat(Item1, false);

{% endhighlight %}

{% endtabs %}

## Restricting Docking by Drag Providers

DockingManager allows to dock the children in different sides using the DragProviders. To restrict dock ability of the dock children to any particular side, set the property `DockAbility` with the required values.

* Setting DockAbility as Horizontal – Restrict the children to dock only on Horizontal side by providing the Horizontal Drag providers.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager>
	
<ContentControl syncfusion:DockingManager.Header="Document1" syncfusion:DockingManager.DockAbility="Horizontal">
	
</ContentControl>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDockAbility(window1, DockAbility.Horizontal);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img7.jpeg)

* Setting DockAbility as Vertical  – Restrict the children to dock only on Vertical side by providing the Vertical Drag providers

{% tabs %}

{%highlight XAML %}

<syncfusion:DockingManager >

<ContentControl syncfusion:DockingManager.Header="Document1" syncfusion:DockingManager.DockAbility="Vertical">

</ContentControl>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDockAbility(window1, DockAbility.Vertical);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img8.jpeg)


## Customizing a window

A Docking window can be customized using the property HeaderBackground, SelectedHeaderBackground, HeaderMouseHoverBackground with the desired brush values respectively.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager SelectedHeaderBackground="Red" HeaderBackground="Brown" HeaderMouseOverBackground="DarkOrchid"  >

<ContentControl syncfusion:DockingManager.Header="Dock"/>

<ContentControl syncfusion:DockingManager.Header="Dock1"/>                

<ContentControl syncfusion:DockingManager.Header="Dock2"/>            

</syncfusion:DockingManager> 

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.SelectedHeaderBackground = new SolidColorBrush(Colors.Red);

SyncDockingManager.HeaderBackground = new SolidColorBrush(Colors.Brown);

SyncDockingManager.HeaderMouseOverBackground = new SolidColorBrush(Colors.DarkOrchid);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img9.jpeg)


## Customizing FloatWindow

The float window can be customized by setting FloatWindowHeaderBackground, FloatWindowHeaderForeground, FloatWindowSelectedHeaderBackground, FloatWindowSelectedBorderBrush and FloatWindowMouseOverHeaderBackground properties with the required brush values respectively.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager FloatWindowHeaderBackground="Brown" FloatWindowHeaderForeground="Blue"
                           FloatWindowMouseOverBorderBrush="Orange" FloatWindowSelectedHeaderBackground="Pink"
                           FloatWindowBorderBrush="Red" FloatWindowSelectedBorderBrush="BlueViolet" >

<ContentControl syncfusion:DockingManager.Header="Float" syncfusion:DockingManager.State="Float"/>

<ContentControl syncfusion:DockingManager.Header="Float1" syncfusion:DockingManager.State="Float"/>

<ContentControl syncfusion:DockingManager.Header="Float2" syncfusion:DockingManager.State="Float"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.FloatWindowHeaderBackground = new SolidColorBrush(Colors.Brown);

SyncDockingManager.FloatWindowHeaderForeground = new SolidColorBrush(Colors.Blue);

SyncDockingManager.FloatWindowMouseOverBorderBrush = new SolidColorBrush(Colors.Orange);

SyncDockingManager.FloatWindowSelectedHeaderBackground = new SolidColorBrush(Colors.Pink);

SyncDockingManager.FloatWindowBorderBrush = new SolidColorBrush(Colors.Red);

SyncDockingManager.FloatWindowSelectedBorderBrush = new SolidColorBrush(Colors.BlueViolet);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img10.jpeg)


## Enable/Disable Dragging a Window

The attached property `CanDrag` that helps to enable or disable the dragging functionality of a window by setting its value as True or False respectively. By default its value is `True`, to disable this functionality turn its value to `False`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" >      

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.CanDrag="False"/>                     

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetCanDrag(Item1, false);

{% endhighlight %}

{% endtabs %}

## Drag Shadow of a Window

To drag child window in Shadow mode, set the DraggingType property of DockingManager as `ShadowDragging`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DraggingType="ShadowDragging"  >      

<ContentControl syncfusion:DockingManager.Header="Item1"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.DraggingType = DraggingType.ShadowDragging;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img11.jpeg)


## Drag Border of a Window

To drag child window in Border mode, set the DraggingType property of DockingManager as `BorderDragging`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DraggingType="BorderDragging">
	
<ContentControl syncfusion:DockingManager.Header="Item1"/>    

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.DraggingType = DraggingType.BorderDragging;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img12.jpeg)


## Customizing a resizing behaviors

DockingManager allows to resize the dock and float windows by default. To restrict resizing the dock and float windows respectively, set the `CanResizeInDockedState` and `CanResizeInFloatState` properties with it value as False.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1">

<ContentControl syncfusion:DockingManager.Header="Dockwindow" x:Name="Content1"
	            syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.CanResizeInDockedState="False"/>

<ContentControl syncfusion:DockingManager.Header="Floatwindow" x:Name="Content2"
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanResizeInFloatState="False"/>    

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetCanResizeInDockedState(Content1, false);

DockingManager.SetCanResizeInFloatState(Content2, false);

{% endhighlight %}

{% endtabs %}


###  Width resizing restriction 

To restrict resizing width for the Dock windows set the property `CanResizeWidthInDockedMode` and `CanResizeWidthInFloatState` as False.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Dockwindow" x:Name="Content1"
                syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.CanResizeWidthInDockedState="False"/>

<ContentControl syncfusion:DockingManager.Header="Floatwindow" x:Name="Content2"
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanResizeWidthInFloatState="False"/>

{% endhighlight %}

{% highlight C# %}
		
DockingManager.SetCanResizeWidthInDockedState(Content1, false);

DockingManager.SetCanResizeWidthInFloatState(Content2, false);

{% endhighlight %}

{% endtabs %}

### Height resizing restriction

To restrict resizing the height for the float and dock window respectively, set the property `CanResizeHeightInFloatState` and `CanResizeHeightInDockedState` as False.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Dockwindow" x:Name="Content1"
                syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.CanResizeHeightInDockedState="False"/>

<ContentControl syncfusion:DockingManager.Header="Floatwindow" x:Name="Content2"
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanResizeHeightInFloatState="False"/>

{% endhighlight %}

{% highlight C# %}
		
DockingManager.SetCanResizeHeightInDockedState(Content1, false);

DockingManager.SetCanResizeHeightInFloatState(Content2, false);

{% endhighlight %}

{% endtabs %}

### Setting MaxWidth and MaxHeight for Window

To set the desired maximum width for the float and dock windows respectively, set their properties `DesiredMaxWidthInDockedMode` and `DesiredMaxWidthInFloatingMode` with the desired values.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Dockwindow"
                syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.DesiredMaxWidthInDockedMode="1000"/>

<ContentControl syncfusion:DockingManager.Header="Floatwindow"
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.DesiredMaxWidthInFloatingMode="600"/>                     

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDesiredMaxWidthInDockedMode(dockWindow1,1000);

DockingManager.SetDesiredMaxWidthInFloatingMode(floatWindow1,600);

{% endhighlight %}

{% endtabs %}


![](Dealing-with-Windows_images/Dealing-with-Windows_img13.jpeg)


To set the maximum height for the float and dock windows respectively, set their properties `DesiredMaxHeightInDockedMode` and `DesiredMaxHeightInFloatingMode` with the desired values.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Dockwindow"
                syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.DesiredMaxHeightInDockedMode="300"/>

<ContentControl syncfusion:DockingManager.Header="Floatwindow"
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.DesiredMaxHeightInFloatingMode="200"/>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDesiredMaxHeightInDockedMode(dockWindow1,700);

DockingManager.SetDesiredMaxHeightInFloatingMode(floatWindow1,200);

{% endhighlight %}

{% endtabs %}


![](Dealing-with-Windows_images/Dealing-with-Windows_img14.jpeg)


## Configuring window sizing

DockingManager allows to set the desired width and height for the dock windows. The window `Width` and `Height` value set to "90" based on the container by default.

### Desire height and width

The desired height and width can be set for the Dock windows through the property `DesiredWidthInDockedMode` and `DesiredHeightInDockedMode`  with the desired values.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1">  

<ContentControl syncfusion:DockingManager.Header="Item1"
                syncfusion:DockingManager.DesiredHeightInDockedMode="400"
                syncfusion:DockingManager.DesiredWidthInDockedMode="300"/>             

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDesiredHeightInDockedMode(Content1,400);

DockingManager.SetDesiredWidthInDockedMode(Content1, 300);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img15.jpeg)

### Sizing Based on the Content

To size the float window based on the children window size, set the property `SizeToContentInFloat` property for the child window as True. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1"
                syncfusion:DockingManager.SizetoContentInFloat="True" Width="100" Height="24"/>             

{% endhighlight %}

{% highlight C# %}
		
DockingManager.SetSizetoContentInFloat(Content1,true);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img16.jpeg)

To size the Dock window based on the children window size, set the property `SizeToContentInDock` property for the child window as True. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" >

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1"
                syncfusion:DockingManager.SizetoContentInDock="True" Width="100" Height="24"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}
			
DockingManager.SetSizetoContentInDock(Content1,true);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img17.jpeg)


### Absolute Sizing on Dock to fill

To load the child window initially with an absolute size, set the property DockFillMode as `Absolute`. By default, the child window loaded with the default size and it can be set through DockFillMode as `Default` also.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Item1"  
                syncfusion:DockingManager.DockFillMode="Absolute"/>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDockFillMode(content1, DockFillModes.Absolute);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img18.jpeg)


### Customizing the Splitter appearance

The Splitter of the dock window can be customized using the SplitterSize and SplitterBackground properties depends upon its values respectively. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager UseDocumentContainer=" True" SplitterBackground="Brown" SplitterSize="10" > 

<ContentControl syncfusion:DockingManager.Header="Item1"></ContentControl>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.SplitterBackground = new SolidColorBrush(Colors.Brown);

SyncDockingManager.SplitterSize = 10;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img19.jpeg)


## Occupy whole window

To arrange the dock windows to a whole available space in the DockingManager, set `DockFill` property of DockingManager as True. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager DockFill="True">        

<ContentControl syncfusion:DockingManager.Header="Item1"/>             

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.DockFill = true;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img20.jpeg)


And when DockFill functionality is enabled, DockingManager changes the DockWindow to AutoHidden state, if any Document state window is present .

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager UseDocumentContainer="True" DockFill="True">        

<ContentControl syncfusion:DockingManager.Header="Item1"/>   

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.UseDocumentContainer = true;

SyncDockingManager.DockFill = true;

DockingManager.SetState(dockWindow1, DockState.Document);

DockingManager.SetState(document1, DockState.Document);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img21.jpeg)


### Restrict DockWindow to AutoHide while DockFill

To restrict the behavior of changing the DockWindow to AutoHide when DockFill is True, set the property `DockFillDocumentMode` as Normal.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="SyncDockingManager" UseDocumentContainer="True" DockFill="True" DockFillDocumentMode="Normal">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>   

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"
                                  syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.DockFillDocumentMode = DockFillDocumentMode.Normal;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img22.jpeg)


## Applying Context Menu

DockingManager allows to add  CustomContextMenuItems for Dock and Float windows through an attached property `CustomMenuItems`. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1">  
	
<syncfusion:DockingManager.CustomMenuItems>
	
<syncfusion:CustomMenuItemCollection>
	
<syncfusion:CustomMenuItem Header="CustomItem1"/>
	
<syncfusion:CustomMenuItem Header="CustomItem2"/>
	
</syncfusion:CustomMenuItemCollection>

</syncfusion:DockingManager.CustomMenuItems>    

<ContentControl syncfusion:DockingManager.Header="Item1"/> 
	               
</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

CustomMenuItemCollection collection = new CustomMenuItemCollection();

CustomMenuItem item1 = new CustomMenuItem();

CustomMenuItem item2 = new CustomMenuItem();

item1.Header = "CustomItem1";

item2.Header = "CustomItem2";

collection.Add(item1);

collection.Add(item2);

DockingManager.SetCustomMenuItems(DockingManager1, collection);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img23.jpeg)


### Adding CustomContextMenuItems to Document window

The custom context menu items can be added in addition to default ContextMenu items for the document window through an attached property `DocumentTabItemContextMenuItems` 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager UseDocumentContainer="True" x:Name="DockingManager1">  

<syncfusion:DockingManager.DocumentTabItemContextMenuItems>

<syncfusion:DocumentTabItemMenuItemCollection>

<syncfusion:CustomMenuItem Header="CustomItem1"/>

<syncfusion:CustomMenuItem Header="CustomItem2"/>

</syncfusion:DocumentTabItemMenuItemCollection>

</syncfusion:DockingManager.DocumentTabItemContextMenuItems>    

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Document"/>                

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DocumentTabItemMenuItemCollection collection = new DocumentTabItemMenuItemCollection();

CustomMenuItem item1 = new CustomMenuItem();

CustomMenuItem item2 = new CustomMenuItem();

item1.Header = "CustomItem1";

item2.Header = "CustomItem2";

collection.Add(item1);

collection.Add(item2);
						 
DockingManager.SetDocumentTabItemContextMenuItems(DockingManager1, collection);

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img24.jpeg)

### CustomMenuItem as Separator

`IsSeparator` property of CustomMenuItem is used to display the Separator between CustomMenuItems. If the property `IsSeparator` is true, the CustomMenuItem will act as Separator.The default value of the property is false.

{% tabs %}
{% highlight C# %}
<syncfusion:DockingManager Grid.Row="1" DockFill="True"  Name="Docking">
            <syncfusion:DockingManager.CustomMenuItems>
                <syncfusion:CustomMenuItemCollection>
                    <syncfusion:CustomMenuItem Header="Custom1"/>
                    <syncfusion:CustomMenuItem Header="Custom2"/>
                    <syncfusion:CustomMenuItem BorderBrush="Red" IsSeparator="True"/>
                    <syncfusion:CustomMenuItem Header="Custom4"/>
                </syncfusion:CustomMenuItemCollection>
            </syncfusion:DockingManager.CustomMenuItems>
            <ContentControl x:Name="Dock1" syncfusion:DockingManager.Header="Dock1"/>
            <ContentControl syncfusion:DockingManager.Header="Dock2" syncfusion:DockingManager.SideInDockedMode="Tabbed" syncfusion:DockingManager.TargetNameInDockedMode="Dock1"/>
            <ContentControl syncfusion:DockingManager.Header="Dock3" syncfusion:DockingManager.State="Dock"/>
            <ContentControl syncfusion:DockingManager.Header="Dock4" syncfusion:DockingManager.State="Dock"/>
        </syncfusion:DockingManager>
{% endhighlight %}
{% endtabs %}

![Displaying Separator between CustomMenuItems](Dealing-with-Windows_images/Dealing-with-Windows_img29.png)

### Customizing ContextMenuItems Visibility

The default context menu is visible on right-clicking the different state child windows and its visibility can be customized.  

The default context menu items as shown in the following screenshot:

![](Dealing-with-Windows_images/Dealing-with-Windows_img25.jpeg)


To collapse the default context menu, set the property `CollapseDefaultContextMenu` as True.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" CollapseDefaultContextMenuItems="True"/>

{% endhighlight %}

{% highlight C# %}

DockingManager1.CollapseDefaultContextMenuItems = true;

{% endhighlight %}

{% endtabs %}

To collapse the default context menu in Dock state window, set the property `CollapseDefaultContextMenuInDock` as True. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" >

<ContentControl syncfusion:DockingManager.Header="DockWindow" x:Name="Content1"
                syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.CollapseDefaultContextMenuItemsInDock="True"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetCollapseDefaultContextMenuItemsInDock(Content1, true);

{% endhighlight %}

{% endtabs %}

To collapse the default context menu in Document state window, set the property `CollapseDefaultContextMenuInDocument` asTrue. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True">
	
<ContentControl syncfusion:DockingManager.Header="DockWindow" x:Name="Content1"
	           syncfusion:DockingManager.State="Document"
               syncfusion:DockingManager.CollapseDefaultContextMenuItemsInDocumentTab="True" /> 

</syncfusion:DockingManager>

{% endhighlight%}

{% highlight C# %}

DockingManager.SetCollapseDefaultContextMenuItemsInDocumentTab(Content1, true);

{% endhighlight%}

{% endtabs %}

To collapse the default context menu in Float state window, set the property `CollapseDefaultContextMenuInFloat` as True. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="DockWindow"
                syncfusion:DockingManager.State="Float"
                syncfusion:DockingManager.CollapseDefaultContextMenuItemsInFloat="True"/>


{% endhighlight %}

{% highlight C# %}

DockingManager.SetCollapseDefaultContextMenuItemsInFloat(Content1, true);

{% endhighlight %}

{% endtabs %}

## Hosting a client control between windows

To add a client control in the DockingManager, set an attached property `ClientControl`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="False">

// A client control TextBox has been added.

<syncfusion:DockingManager.ClientControl>

<TextBox x:Name="Text1" Width="100" Height="23" Text=" ClientControl" Background="Black" Foreground="White"/>

</syncfusion:DockingManager.ClientControl>

<ContentControl syncfusion:DockingManager.Header="Top" syncfusion:DockingManager.SideInDockedMode="Top"/>

<ContentControl syncfusion:DockingManager.Header="Left" syncfusion:DockingManager.SideInDockedMode="Left"/>

<ContentControl syncfusion:DockingManager.Header="Bottom" syncfusion:DockingManager.SideInDockedMode="Bottom"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager1.ClientControl = new TextBlock() { Text = "ClientControl", Width = 100, Height = 23, Background = Brushes.Black, Foreground = Brushes.White };

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img26.jpeg)




