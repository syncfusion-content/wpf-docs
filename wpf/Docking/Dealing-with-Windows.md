---
layout: post
title: Dealing with Windows in WPF Docking control | Syncfusion®
description: Learn here all about Dealing with Windows support in Syncfusion® WPF Docking (DockingManager) control and more.
platform: wpf
control: DockingManager
documentation: ug
---
# Dealing with Windows in WPF Docking (DockingManager)

## Activating a window

A particular child window can be activated in DockingManager using its name or reference through the property [ActiveWindow](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ActiveWindow) and [ActivateWindow](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ActivateWindow_System_String_) method that passes the element as argument to activate.

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

![WPF Dock Window Activation](Dealing-with-Windows_images/wpf-dock-window-activation.jpeg)


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

![WPF Docking Window Adding Programmatically](Dealing-with-Windows_images/wpf-docking-window-adding-programmatically.jpeg)


### Setting State for Window programmatically

The state for the particular child window can be set programmatically using the [SetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SetState_System_Windows_DependencyObject_Syncfusion_Windows_Tools_Controls_DockState_) method of DockingManager.

{% tabs %}

{% highlight C# %}

DockingManager.SetState(content1, DockState.Float);


{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(content1, DockState.Float) 

{% endhighlight %}

{% endtabs %}

![WPF Docking Window States](Dealing-with-Windows_images/wpf-docking-window-states.jpeg)





* Setting state as Document – To create document window in the DockingManager, set [UseDocumentContainer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_UseDocumentContainer) as True for DockingManager and set its state as Document.

{% capture codesnippet1 %}
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
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

![WPF Docking Window Document State](Dealing-with-Windows_images/wpf-docking-window-document-state.jpeg)


* Setting state as AutoHidden

{% capture codesnippet2 %}
{% tabs %}

{% highlight C# %}

DockingManager.SetState(content1, DockState.AutoHidden);

{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(content1, DockState.AutoHidden)

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | UnOrderList_Indent_Level_1 }}

![WPF Docking Window AutoHidden State](Dealing-with-Windows_images/wpf-docking-window-autohidden-state.jpeg)

#### Making Window AutoHide programmatically

To auto hide the window programmatically call [ExecuteAutoHide](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ExecuteAutoHide_System_Windows_FrameworkElement_) method of DockingManager.

{% tabs %}

{% highlight C# %}

DockingManager1.ExecuteAutoHide(Content1);

{% endhighlight %}

{% highlight VB %}

DockingManager1.ExecuteAutoHide(Content1)

{% endhighlight %}

{% endtabs %}

![WPF Docking Making the Window AutoHide Programmatically](Dealing-with-Windows_images/wpf-docking-making-the-window-autohide-programmatically.jpeg)

#### Making Window Float and Document programmatically

The docking window can be made to float and document using the [SetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SetState_System_Windows_DependencyObject_Syncfusion_Windows_Tools_Controls_DockState_) method with its DockState value as `Float` and `Document` respectively

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

To hide the window, set [State](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_State) property of the DockingManager as `Hidden`.

{% tabs %}

{% highlight C# %}

DockingManager.SetState(Content1, DockState.Hidden);

{% endhighlight %}

{% highlight VB %}

DockingManager.SetState(Content1, DockState.Hidden)

{% endhighlight %}

{% endtabs %}

To hide the window programmatically, call the [ExecuteClose](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ExecuteClose_System_Windows_FrameworkElement_) method with argument which refer the window need to be close.

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

To restore the closed window in the DockingManager, call [ExecuteRestore](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ExecuteRestore_System_Windows_FrameworkElement_) method.

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

[WindowClosing](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html) and `CloseButtonClick` are the two events, which can be used to get notification when the child windows are being closed. 

### Dock Window Closing

`WindowClosing` event raised whenever a child in `Float`, `Dock` and `AutoHidden` windows are closing. 

### Document Window Closing
 
[CloseButtonClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html) event raised only when close button of the `Document` child clicked. The following code describes how to handle the closing of all the children in `DockingManager`.

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

## Event to notify when a child is added or removed

If you want to know while docking child added or removed from the `DockingManager`, it can be notified by using the [ChildrenCollectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html) event. It receives an argument of type `NotifyCollectionChangedEventArgs` containing the following information about the event.

<table>
<tr>
<th>Event Data</th>
<th>Description</th></tr>
<tr>
<td>Action</td>
<td>Gets an action that determines either an item is added to the children collection or item is removed from the children collection.</td>
</tr>
<tr>
<td>NewItems</td>
<td>Gets the newly added items in the children collection.</td>
</tr>
<tr>
<td>OldItems</td>
<td>Gets the removal of the items from the children collection.</td>
</tr>
<tr>
<td>NewStartingIndex</td>
<td>Gets the index location of the newly added items from the children collection.</td>
</tr>
<tr>
<td>OldStartingIndex</td>
<td>Gets the index location of the recently removed items from the children collection.</td>
</tr>
</table>

{% tabs %}
{% highlight XAML %}

<syncfusion:DockingManager ChildrenCollectionChanged="DockingManager_ChildrenCollectionChanged"  
                           Name="dockingManager" >
    <ContentControl syncfusion:DockingManager.Header="Solution Explorer" 
                    Name="SolutionExplorer" />
</syncfusion:DockingManager>

{% endhighlight %}
{% highlight XAML %}

dockingManager.ChildrenCollectionChanged += DockingManager_ChildrenCollectionChanged;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

//Add a docking child item in the children collection of DockingManager
ContentControl contentControl = new ContentControl();
dockingManager.Children.Add(contentControl)

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight C# %}

private void DockingManager_ChildrenCollectionChanged(object sender, NotifyCollectionChangedEventArgs e) {
    //Occurs when children collection changed   
    MessgeBox.Show(“Children collection was changed”);
    if(e.Action== NotifyCollectionChangedAction.Add) {
        var added_Item = e.NewItems;
        int addedIndex = e.NewStartingIndex;
    }
    else if (e.Action == NotifyCollectionChangedAction.Remove) {
        var removed_item = e.OldItems;
        int removedIndex = e.OldStartingIndex;
    }
}

{% endhighlight %}
{% endtabs %}

## Restricting Docking in Float Window

The float window allows to dock another float window inside it by default. This behavior can be restricted by set [CanDockOnFloat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanDockonFloat) as False for that particular window.

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

## Customizing a window

A Docking window can be customized using the property [HeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_HeaderBackground), [SelectedHeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SelectedHeaderBackground), [HeaderMouseHoverBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_HeaderMouseOverBackground) with the desired brush values respectively.

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

![WPF Docking Window Appearance Customization](Dealing-with-Windows_images/wpf-docking-window-appearance-customization.jpeg)



## Customizing FloatWindow

The float window can be customized by setting [FloatWindowHeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_FloatWindowHeaderBackground), [FloatWindowHeaderForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_FloatWindowHeaderForeground), [FloatWindowSelectedHeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_FloatWindowSelectedHeaderBackground), [FloatWindowSelectedBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_FloatWindowSelectedBorderBrush) and [FloatWindowMouseOverHeaderBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_FloatWindowMouseOverHeaderBackground) properties with the required brush values respectively.

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

![WPF Docking Float Window Appearance Customization](Dealing-with-Windows_images/wpf-docking-float-window-appearance-customization.jpeg)


## Enable/Disable Dragging a Window

The attached property [CanDrag](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanDrag) that helps to enable or disable the dragging functionality of a window by setting its value as True or False respectively. By default its value is `True`, to disable this functionality turn its value to `False`.

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

To drag child window in Shadow mode, set the [DraggingType](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DraggingType) property of DockingManager as `ShadowDragging`.

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

![WPF Docking Drag Shadow of a Window](Dealing-with-Windows_images/wpf-docking-drag-shadow-of-a-window.jpeg)


## Drag Border of a Window

To drag child window in Border mode, set the [DraggingType](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DraggingType) property of DockingManager as `BorderDragging`.


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

![WPF Docking Window Border Dragging](Dealing-with-Windows_images/wpf-docking-window-border-dragging.jpeg)


## Customizing a resizing behaviors

DockingManager allows to resize the dock and float windows by default. To restrict resizing the dock and float windows respectively, set the [CanResizeInDockedState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeInDockedState) and [CanResizeInFloatState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeInFloatState) properties with it value as False.


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

To restrict resizing width for the Dock windows set the property [CanResizeWidthInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeWidthInDockedState) and [CanResizeWidthInFloatState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeWidthInFloatState) as False.

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

To restrict resizing the height for the float and dock window respectively, set the property [CanResizeHeightInFloatState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeHeightInFloatState) and [CanResizeHeightInDockedState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanResizeHeightInDockedState) as False.

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

To set the desired maximum width for the float and dock windows respectively, set their properties [DesiredMaxWidthInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredMaxWidthInDockedMode) and [DesiredMaxWidthInFloatingMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredMaxWidthInFloatingMode) with the desired values.

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


![WPF Docking Window MaxWidth and MaxHeight](Dealing-with-Windows_images/wpf-docking-window-maxwidth-and-maxheight.jpeg)


To set the maximum height for the float and dock windows respectively, set their properties [DesiredMaxHeightInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredMaxHeightInDockedMode) and [DesiredMaxHeightInFloatingMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredMaxHeightInFloatingMode) with the desired values.

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


![WPF Docking Desired Height and Width of Float Window](Dealing-with-Windows_images/wpf-docking-desired-height-and-width-of-float-window.jpeg)


## Configuring window sizing

DockingManager allows to set the desired width and height for the dock windows. The window `Width` and `Height` value set to "90" based on the container by default.

### Desire height and width

The desired height and width can be set for the Dock windows through the property [DesiredWidthInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredWidthInDockedMode) and [DesiredHeightInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DesiredHeightInDockedMode)  with the desired values.

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

![WPF Docking Desired Height and Width of Dock Window](Dealing-with-Windows_images/wpf-docking-desired-height-and-width-of-dock-window.jpeg)

### Sizing Based on the Content

To size the float window based on the children window size, set the property [SizeToContentInFloat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SizetoContentInFloat) property for the child window as True. By default, its value is False.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1"
                syncfusion:DockingManager.SizetoContentInFloat="True" Width="100" Height="24"/>             

{% endhighlight %}

{% highlight C# %}
		
DockingManager.SetSizetoContentInFloat(Content1,true);

{% endhighlight %}

{% endtabs %}

![WPF Docking Float Window Content Sizing](Dealing-with-Windows_images/wpf-docking-float-window-content-sizing.jpeg)

To size the Dock window based on the children window size, set the property [SizeToContentInDock](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SizetoContentInDock) property for the child window as True. By default, its value is False.

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

![WPF Docking Dock Window Content Sizing](Dealing-with-Windows_images/wpf-docking-dock-window-content-sizing.jpeg)


### Absolute Sizing on Dock to fill

To load the child window initially with an absolute size, set the property [DockFillMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DockFillMode) as `Absolute`. By default, the child window loaded with the default size and it can be set through [DockFillMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DockFillMode) as `Default` also.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="Item1"  
                syncfusion:DockingManager.DockFillMode="Absolute"/>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetDockFillMode(content1, DockFillModes.Absolute);

{% endhighlight %}

{% endtabs %}

![WPF Docking Absolute Sizing](Dealing-with-Windows_images/wpf-docking-absolute-sizing.jpeg)


### Customizing the Splitter appearance

The Splitter of the dock window can be customized using the [SplitterSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SplitterSize) and [SplitterBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SplitterBackground) properties depends upon its values respectively. 

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

![WPF Docking Splitter Appearance Customization](Dealing-with-Windows_images/wpf-docking-splitter-appearance-customization.jpeg)


## Occupy whole window

To arrange the dock windows to a whole available space in the DockingManager, set [DockFill](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DockFill) property of DockingManager as True. 

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

![WPF Dock Windows Occupy Whole Window](Dealing-with-Windows_images/wpf-dock-windows-occupy-whole-window.jpeg)


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

![WPF Docking DockFill Functionality](Dealing-with-Windows_images/wpf-docking-dockfill-functionality.jpeg)


### Restrict DockWindow to AutoHide while DockFill

To restrict the behavior of changing the DockWindow to AutoHide when DockFill is True, set the property [DockFillDocumentMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DockFillDocumentMode) as Normal.

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

![WPF Docking Restrict Dock Window to AutoHide](Dealing-with-Windows_images/wpf-docking-restrict-dock-window-to-autohide.jpeg)


## Applying Context Menu

You can add custom context menu items for dock and float windows through an attached property [CustomMenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CustomMenuItems) property. You can also add sub menu items for custom context menu item by adding that sub `CustomMenuItem` to the parent [CustomMenuItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html). You can check or uncheck the `CustomMenuItem` interactively or programmatically by using the `CustomMenuItem.IsChecked` property. 

You can collapse the default context menu and show only the custom context menu items by setting the [CollapseDefaultContextMenuItemsInFloat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CollapseDefaultContextMenuItemsInFloatProperty) property to `true`. The default value of `CollapseDefaultContextMenuItemsInFloat` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DockingManager
    DockFill="True"
    Name="dockingManager" >
    
    <!--Adding custom context menu items for float windows-->
    <syncfusion:DockingManager.FloatWindowContextMenuItems>
        <syncfusion:CustomMenuItemCollection>
            <!--Adding custom context menu items-->
            <syncfusion:CustomMenuItem Header="Menu 1"/>
            <syncfusion:CustomMenuItem Header="Menu 2">

                <!--Adding sub custom context menu items-->
                <syncfusion:CustomMenuItem Header="SubMenu 1"/>
                <syncfusion:CustomMenuItem Header="SubMenu 2"/>
                <syncfusion:CustomMenuItem Header="SubMenu 3" IsChecked="True"/>
            </syncfusion:CustomMenuItem>
        </syncfusion:CustomMenuItemCollection>
    </syncfusion:DockingManager.FloatWindowContextMenuItems>

    <ContentControl syncfusion:DockingManager.Header="Item 1"
                    syncfusion:DockingManager.State="Dock"/>
    <ContentControl syncfusion:DockingManager.Header="Item 2"
                    syncfusion:DockingManager.State="Dock"/>
    <ContentControl syncfusion:DockingManager.Header="Float Window"
                    syncfusion:DockingManager.CollapseDefaultContextMenuItemsInFloat="True"
                    syncfusion:DockingManager.State="Float"/>
</syncfusion:DockingManager>

{% endhighlight %}
{% highlight C# %}

//Creating custom context menu items
CustomMenuItem menu1 = new CustomMenuItem();
menu1.Header = "Menu 1";
CustomMenuItem menu2 = new CustomMenuItem();
menu2.Header = "Menu 2";

//Creating custom sub context menu items
CustomMenuItem customMenuItem1 = new CustomMenuItem() { Header = "SubMenu 1" };
CustomMenuItem customMenuItem2 = new CustomMenuItem() { Header = "SubMenu 2" };
CustomMenuItem customMenuItem3 = new CustomMenuItem() { Header = "SubMenu 3", IsChecked = true };

menu2.Items.Add(customMenuItem1);
menu2.Items.Add(customMenuItem2);
menu2.Items.Add(customMenuItem3);

//Adding custom context menu items with sub menu items
dockingManager.FloatWindowContextMenuItems.Add(menu1);
dockingManager.FloatWindowContextMenuItems.Add(menu2);

{% endhighlight %}
{% endtabs %}

![WPF Docking Custom Context Menu for Dock and Float Windows](Dealing-with-Windows_images/wpf-docking-custom-context-menu-for-dock-and-float-windows.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-docking-manager-wpf-examples/blob/master/Samples/Custom-ContextMenu) 

### Adding CustomContextMenuItems to Document window

The custom context menu items can be added in addition to default ContextMenu items for the document window through an attached property [DocumentTabItemContextMenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_DocumentTabItemContextMenuItems). 

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

![WPF Docking Adding Custom Context Menu to Document Window](Dealing-with-Windows_images/wpf-docking-adding-custom-context-menu-to-document-window.jpeg)

### CustomMenuItem as Separator

The [IsSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html#Syncfusion_Windows_Tools_Controls_CustomMenuItem_IsSeparator) property of [CustomMenuItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html) is used to display separator between CustomMenuItems. If the property [IsSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html#Syncfusion_Windows_Tools_Controls_CustomMenuItem_IsSeparator) is set to true, the [CustomMenuItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CustomMenuItem.html) will act as Separator.The default value of this property is false.

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

![WPF Docking CustomMenuItems as Separator](Dealing-with-Windows_images/wpf-docking-custom-menu-items-as-separator.png)

### Customizing ContextMenuItems Visibility

The default context menu is visible on right-clicking the different state child windows and its visibility can be customized.  

The default context menu items as shown in the following screenshot:

![WPF Docking Custom ContextMenuItems Visibility](Dealing-with-Windows_images/wpf-docking-custom-contextmenu-items-visibility.jpeg)


To collapse the default context menu, set the property [CollapseDefaultContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CollapseDefaultContextMenuItems) as True.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" CollapseDefaultContextMenuItems="True"/>

{% endhighlight %}

{% highlight C# %}

DockingManager1.CollapseDefaultContextMenuItems = true;

{% endhighlight %}

{% endtabs %}

To collapse the default context menu in Dock state window, set the property [CollapseDefaultContextMenuInDock](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CollapseDefaultContextMenuItemsInDock) as True. By default, its value is False.

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

To collapse the default context menu in Document state window, set the property [CollapseDefaultContextMenuInDocument](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CollapseDefaultContextMenuItemsInDocumentTab) asTrue. By default, its value is False.

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

To collapse the default context menu in Float state window, set the property [CollapseDefaultContextMenuInFloat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CollapseDefaultContextMenuItemsInFloat) as True. By default, its value is False.

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

## DockBehavior

[DockBehavior](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DockBehavior) has two options Default and VS2010, difference between the two modes is explained in the table below.

<table>
<tr>
<th>
DockBehavior
</th>
<th>
Default
</th>
<th>
VS2010
</th>
</tr>
<tr>
<td>
Context menu options
</td>
<td>

<Img alt="Dock window with default context menu" src="Dealing-with-Windows_images/Default-menu.jpg"/>

</td>
<td>

<Img alt="Dock window with VS2010 context menu" src="Dealing-with-Windows_images/VS2010-menu.jpg"/>

</td>
</tr>
<tr>
<td>
Different Behavior
</td>
<td>
Dockable:

A window's `Dockable` menu item represents that it may or may not be docked. 
 </td>
<td>
Dock:

You can dock a window from float or tabbed state by clicking `Dock` menu item. 
</td>
</tr>
<tr>
<td>
Same Behavior
</td>
<td>
The checked status of all other menu items is the current status of the window.
</td>
<td>
The checked status of all other menu items is the current status of the window.
</td>
</tr>
<tr>
<td>

Context menu option when window is in `Auto-Hide` state

</td>
<td>

<Img alt="Auto-Hide window with default context menu"  src="Dealing-with-Windows_images/AutoHide_Window_Default-Menu.jpg"/>

</td>
<td>

<Img alt="Auto-Hide window with VS2010 context menu"  src="Dealing-with-Windows_images/AutoHide_Window_VS2010-Menu.jpg"/> 

</td>
</tr>

</table>

{% tabs %}

{% highlight XAML %}

 <syncfusion:DockingManager  x:Name="DockingManager1" DockBehavior="VS2010" >

  <ContentControl x:Name="SolutionExplorer" syncfusion:DockingManager.DesiredWidthInDockedMode="200" syncfusion:DockingManager.Header="Solution Explorer" />

 </syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager1.DockBehavior = DockBehavior.VS2010;

{% endhighlight %}

{% endtabs %}

![WPF Docking Float Window with Context Menu](Dealing-with-Windows_images/wpf-docking-float-window-with-context-menu.png)

![WPF Docking Auto Hide Window with Context Menu](Dealing-with-Windows_images/wpf-docking-auto-hide-window-with-context-menu.png)


## Hosting a client control between windows

To add a client control in the DockingManager, set an attached property [ClientControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ClientControl).

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

![WPF Docking Hosting a Client Control Between Windows](Dealing-with-Windows_images/wpf-docking-hosting-a-client-control-between-windows.jpeg)


## DockingManager as FlatLayoutControl
 
The [EnableFlatLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_EnableFlatLayout) property of DockingManager is used to disable all the docking functionalities such as drag-and-drop functionality in document windows, resizing the child elements, hiding the dock panel options, closing the child elements from view, and floating the dock windows. If the [EnableFlatLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_EnableFlatLayout) property is true, the DockingManager control will act as LayoutControl. The default value of this property is false. 
{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" EnableFlatLayout="True">
	 <ContentControl Name="Output"
						   syncfusion:DockingManager.Header="Output"
						   syncfusion:DockingManager.SideInDockedMode="Bottom"
						   syncfusion:DockingManager.DesiredHeightInDockedMode="200" 
						   >                
            </ContentControl>
           			
			<ContentControl Name="SolutionExplorer"  
					  syncfusion:DockingManager.Header="Solution Explorer"
					  syncfusion:DockingManager.SideInDockedMode="Right"
					  syncfusion:DockingManager.DesiredWidthInDockedMode="300"                      
					  >			
			</ContentControl>
			
			<ContentControl Name="Toolbox"
					  syncfusion:DockingManager.Header="Toolbox" 
					  syncfusion:DockingManager.State="Dock" 
                            HorizontalContentAlignment="Left" 
					  syncfusion:DockingManager.DesiredWidthInDockedMode="250"
                      >			
			</ContentControl>
					
			<ContentControl Name="Features"
					  syncfusion:DockingManager.Header="Features" 
					  syncfusion:DockingManager.State="Document" 					  
                     >
			</ContentControl>
			<!-- Docking dock window -->
			<ContentControl Name="Docking"
					  syncfusion:DockingManager.Header="Docking" 
					  syncfusion:DockingManager.State="Document" 					  
                     >
			</ContentControl>
</syncfusion:DockingManager>


{% endhighlight %}

{% highlight C# %}

 DockingManager.EnableFlatLayout = true;

{% endhighlight %}

{% endtabs %}

![WPF Docking acts as Layout Control](Dealing-with-Windows_images/wpf-docking-acts-as-layout-control.jpeg)

