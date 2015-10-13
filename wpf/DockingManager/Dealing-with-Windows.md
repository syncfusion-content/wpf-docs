---
layout: post
title: Dealing with Windows
description: getting started
platform: wpf
control: DockingManager
documentation: ug
---
## Dealing with Windows

### Activating a window

A particular child window can be activate in DockingManager, using its name or reference through the property **ActiveWindow**  property and **ActivateWindow** method which passes the element to get activate as its argument.

{% highlight c# %}

DockingManager1.ActiveWindow = Content1;

DockingManager1.ActivateWindow("Content1");


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img1.jpeg)


### Adding Window Programmatically

Any UI elements can be added inside the DockingManager as the child windows. The windows will be add as Dock windows, since the default value of the state is **“Dock”**.  The UI element will be added in the DockingManager using the **Add** method of the **Children** property of the DockingManager.

For instance, ContentControl has added as windows for DockingManager

{% highlight c# %}

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

![](Dealing-with-Windows_images/Dealing-with-Windows_img2.jpeg)


### Setting States for Window programmatically

The states for the particular child window can be set programmatically using the **SetState** method of DockingManager containing two argument.

{% highlight c# %}

DockingManager.SetState(content1, DockState.Float);


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img3.jpeg)



* Setting state as Document – To create document window in the DockingManager, set UseDocumentContainer as True for DockingManager and set its state as Document.

{% highlight c# %}

DockingManager1.UseDocumentContainer = true;
DockingManager.SetState(content1, DockState.Document);

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img4.jpeg)


* Setting state as AutoHidden

{% highlight c# %}

DockingManager.SetState(content1, DockState.AutoHidden);

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img5.jpeg)

### Making Window AutoHide programatically

To make the window autohidden programmatically call **ExecuteAutoHide** method of DockingManager.

{% highlight c# %}

DockingManager1.ExecuteAutoHide(Content1);

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img6.jpeg)


##### Making Window Float and Document programmatically

The docking window can be made float and document using the **SetState** property with its **DockState** value as **Float** and **AutoHidden** respectively

{% highlight c# %}

//which makes the content1 to float 

DockingManager.SetState(Content1, DockState.Float);

//which makes the content1 as Document window

DockingManager.SetState(Content1, DockState.Document);



{% endhighlight %}

### Hiding Window Programmatically

To make the window to hide, set **State** property of the DockingManager as **Hidden**.

{% highlight c# %}

DockingManager.SetState(Content1, DockState.Hidden);
{% endhighlight %}

To make the window to hide programatically, call the **ExecuteClose** method which closes the window passed as an argument.

{% highlight c# %}

//Hide the element that passed as argument
DockingManager1.ExecuteClose(Content1); 
  
{% endhighlight %}
### Restore Window Programmatically

To restore the closed window in the DockingManager, call **ExecuteRestore** method.

{% highlight c# %}

//Restore the passed element with the state value as its argument

DockingManager1.ExecuteRestore(Content1, DockState.Float); 


{% endhighlight %}

### Removing Window Programmatically

The windows for the Dockingmanager can be added using the Children collection. To remove the windows from the children collection, pass the window element that need to be remove using **Remove****()** method of children property in DockingManager.

{% highlight c# %}

DockingManager dockingmanager  = new DockingManager();

ContentControl content1 = new ContentControl();

DockingManager.SetHeader(content1, "Dockwindow");

ContentControl content2 = new ContentControl();

DockingManager.SetHeader(content2,"Dockwindow2");

dockingmanager.Children.Add(content1);

dockingmanager.Children.Add(content2);

//The following code describes how to remove the child window programatically using the remove method

dockingmanager.Children.Remove(content2);

Grid1.Children.Add(dockingmanager);

{% endhighlight %}

### Restricting Docking in Float Window

The float window will allow to dock by default. To restrict this behavior set **CanDockOnFloat** as **False** for particular window.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1"  >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"

syncfusion:DockingManager.State="Float"

syncfusion:DockingManager.CanDockonFloat="False"                       

></ContentControl>  

</syncfusion:DockingManager>

{% endhighlight %}

### Restricting Docking by Drag Providers

DockingManager allows to dock the children in different side using the DragProviders. To restrict dockability of the dock children to any particular side, set the property **Dockability** with the required values.

* Setting Dockability as **Horizontal** – restrict the children to dock only on Horizontal side by providing the Horizontal Drag providers.

{% highlight xml %}

<syncfusion:DockingManager>
<ContentControl syncfusion:DockingManager.Header="Document1"                
syncfusion:DockingManager.DockAbility="Horizontal">
</ContentControl>
</syncfusion:DockingManager>

{% endhighlight %}



![](Dealing-with-Windows_images/Dealing-with-Windows_img7.jpeg)





* Setting Dockability as  Vertical  – restrict the children to dock only on Horizontal side by providing the Vertical Drag providers



{%highlight xml}

<syncfusion:DockingManager >

<ContentControl syncfusion:DockingManager.Header="Document1"  
                 
syncfusion:DockingManager.DockAbility="Vertical">

</ContentControl>

</syncfusion:DockingManager>


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img8.jpeg)


### Customizing a window

A Docking window can be customized using the property **HeaderBackground**, **SelectedHeaderBackground**, **HeaderMouseHoverbackground** with the desired brush values respectively.

{% highlight xml %}
<syncfusion:DockingManager SelectedHeaderBackground="Red" HeaderBackground="Brown" HeaderMouseOverBackground="DarkOrchid"  >

<ContentControl syncfusion:DockingManager.Header="Dock"/>

<ContentControl syncfusion:DockingManager.Header="Dock1"/>                

<ContentControl syncfusion:DockingManager.Header="Dock2"/>                     </syncfusion:DockingManager> 


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img9.jpeg)


### Customizing FloatWindow

The float window can be customized by setting**FloatWindowHeaderBackground**,**FloatWindowHeaderForeground**, **FloatWindowSelectedHeaderBackground** , **FloatWindowSelectedBorderBrush** and **FloatWindowMouseOverHeaderBackground** properties with the required brush values respectively.

{% highlight xml %}

<syncfusion:DockingManager FloatWindowHeaderBackground="Brown" FloatWindowHeaderForeground="Blue" FloatWindowMouseOverBorderBrush="Orange" FloatWindowSelectedHeaderBackground="pink" FloatWindowBorderBrush="Red" FloatWindowSelectedBorderBrush="BlueViolet" >

<ContentControl syncfusion:DockingManager.Header="Float"

syncfusion:DockingManager.State="Float"/>

<ContentControl syncfusion:DockingManager.Header="Float1"

syncfusion:DockingManager.State="Float"/>

<ContentControl syncfusion:DockingManager.Header="Float2"

syncfusion:DockingManager.State="Float"/>



</syncfusion:DockingManager>




{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img10.jpeg)


### Enable/Disable Dragging a Window




The **CanDrag** an attached property, which helps to enable or disable the dragging functionality of a window by setting its value as **True** or **False** respectively. By default its value is **True**, to disable this functionality turn its value to **False**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1"   >      

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.CanDrag="False"/>                     

</syncfusion:DockingManager>



{% endhighlight %}

### Drag Shadow of a Window

To drag the shadow of a dock window in the DockingManager, set the property **DraggingType**  as **ShadowDragging**.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" DraggingType="ShadowDragging"  >      

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img11.jpeg)


### Drag Border of a Window

To drag the border of a dock window, set the property **DraggingType**  as **BorderDragging**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" DraggingType="BorderDragging"><ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>      </syncfusion:DockingManager>

{% endhighlight %}
![](Dealing-with-Windows_images/Dealing-with-Windows_img12.jpeg)


### Customizing a resizing behaviors

DockingManager allows to resize the dock and float windows by default. To restrict resizing the dock and float windows respectively, set the **CanResizeInDockedState** and **CanResizeInFloatState** properties with it value as **False**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1">

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dockwindow"

syncfusion:DockingManager.State="Dock"                                         syncfusion:DockingManager.CanResizeInDockedState="False"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Floatwindow"

syncfusion:DockingManager.State="Float"                                        syncfusion:DockingManager.CanResizeInFloatState="False"/>    

</syncfusion:DockingManager>





{% endhighlight %}

####  Width resizing restriction 

To restrict resizing width for the Dock windows set the property **CanResizeWidthInDockedMode** and **CanResizeWidthInFloatState** as **False**.

{% highlight xml %}

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dockwindow"

syncfusion:DockingManager.State="Dock"                                       syncfusion:DockingManager.CanResizeWidthInDockedState="False"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Floatwindow"

syncfusion:DockingManager.State="Float"                                       syncfusion:DockingManager.CanResizeWidthInFloatState="False"/>





{% endhighlight %}

#### Height resizing restriction

To restrict resizing the height for the float and dock window respectively, set the property **CanResizeHeightInFloatstate** and **CanResizeHeightInDockedState** as **False**.

{% highlight xml %}
<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dockwindow"

syncfusion:DockingManager.State="Dock"                                         syncfusion:DockingManager.CanResizeHeightInDockedState="False"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Floatwindow"

syncfusion:DockingManager.State="Float"                                      syncfusion:DockingManager.CanResizeHeightInFloatState="False"/>





{% endhighlight %}

#### Setting MaxWidth and MaxHeight for Window

To set the desired maximum width for the float and dock windows respectively, set their properties **DesiredMaxWidthInDockedMode** and **DesiredMaxWidthInFloatingMode** with the desired values.

{% highlight xml %}

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dockwindow" syncfusion:DockingManager.State="Dock"                                         syncfusion:DockingManager.DesiredMaxWidthInDockedMode="1000"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Floatwindow"

syncfusion:DockingManager.State="Float"                                           syncfusion:DockingManager.DesiredMaxWidthInFloatingMode="600"/>                     



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img13.jpeg)


To set the maximum height for the float and dock windows respectively, set their properties **DesiredMaxHeightInDockedMode** and **DesiredMaxHeightInFloatingMode** with the desired values.

{% highlight xml %}
<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dockwindow"

syncfusion:DockingManager.State="Dock"                                        syncfusion:DockingManager.DesiredMaxHeightInDockedMode="300"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Floatwindow"

syncfusion:DockingManager.State="Float"                                         syncfusion:DockingManager.DesiredMaxHeightInFloatingMode="200"/>



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img14.jpeg)


### Configuring window sizing

DockingManager allows to set the desired width and height for the dock windows. The window will occupy 90 **Width** and **Height** based on the container by default.

#### Desire height and width

The desired height and width can be set for the Dock windows through the property **DesiredwidthInDockedMode** and **DesiredHeightInDockedMode**  with the desired values.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1"  >  

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"

syncfusion:DockingManager.DesiredHeightInDockedMode="400"                                        syncfusion:DockingManager.DesiredWidthInDockedMode="300"/>             

</syncfusion:DockingManager>



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img15.jpeg)

#### Sizing Based on the Content

To size the float window based on the children window size, set the property **SizeToContentInFloat** property for the child window as **True**. By default, its value is **False**.

{% highlight xml %}

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" Width="100" Height="24"syncfusion:DockingManager.SizetoContentInFloat="True"/>             



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img16.jpeg)


To size the Dock window based on the children window size, set the property **SizeToContentInDock** property for the child window as **True**. By default, its value is **False**.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" Width="100" Height="24" syncfusion:DockingManager.SizetoContentInDock="True"/>

</syncfusion:DockingManager>



{% endhighlight %}


![](Dealing-with-Windows_images/Dealing-with-Windows_img17.jpeg)


#### Absolute Sizing on Dock to fill

To load the child window initially with an absolute size, set the property **DockFillMode** as **Absolute**. By default, the child window loaded with the default size and it can be set through **DockFillMode** as Default also.


{% highlight xml %}

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" 

syncfusion:DockingManager.DockFillMode="Absolute"/>

{% endhighlight %}



![](Dealing-with-Windows_images/Dealing-with-Windows_img18.jpeg)


#### Customizing the Splitter appearance

The Splitter of the dock window can be customized using the SplitterSize and SplitterBackground properties depends upon its values respectively. 

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1"  UseDocumentContainer=" True" SplitterBackground="Brown" SplitterSize="10"  > 

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"></ContentControl>

</syncfusion:DockingManager>

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img19.jpeg)


### Occupy whole window

To arrange the dock windows to whole available space in the DockingManager, set the property **DockFill** as **True**. 

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" DockFill="True">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>             

</syncfusion:DockingManager>

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img20.jpeg)


And when this functionality is enabled, DockingManager will change the Dockwindow to AutoHidden state, if any document state window is present .

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" DockFill="True">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>   <ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item1"

syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img21.jpeg)


####Restrict DockWindow to AutoHide while DockFill

To restrict the behavior of changing the Dockwindow to AutoHide when **DockFill** is **True**, set the property **DockFillDocumentMode** as **Normal**.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" DockFill="True" DockFillDocumentMode="Normal">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>   

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"

syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>


{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img22.jpeg)


### Applying Context Menu

DockingManager allows to add  CustomContextMenuItems for Dock and float windows through an attached property **CustomMenuItems**. 

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1">  
<syncfusion:DockingManager.CustomMenuItems>
<syncfusion:CustomMenuItemCollection>
<syncfusion:CustomMenuItem Header="CustomItem1"/>
<syncfusion:CustomMenuItem Header="CustomItem2"/>
</syncfusion:CustomMenuItemCollection> </syncfusion:DockingManager.CustomMenuItems>    
<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>                
</syncfusion:DockingManager>

{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img23.jpeg)


#### Adding CustomContextMenuItems to Document window

The custom context menu items can be added in addition to default contextmenu items for the document window through an attached property **DocumentTabItemContextMenuItems** 

{% highlight xml %}

<syncfusion:DockingManager UseDocumentContainer="True" x:Name="DockingManager1"   >  

<syncfusion:DockingManager.DocumentTabItemContextMenuItems>

<syncfusion:DocumentTabItemMenuItemCollection>

<syncfusion:CustomMenuItem Header="CustomItem1"/>

<syncfusion:CustomMenuItem Header="CustomItem2"/>

</syncfusion:DocumentTabItemMenuItemCollection>

</syncfusion:DockingManager.DocumentTabItemContextMenuItems>    

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Document"/>                

</syncfusion:DockingManager>



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img24.jpeg)


#### Customizing ContextmenuItems Visibility

The default context menu will be visible on right clicking the different state child windows and it visibility can be customized.  

The default context menu items shown as in the following screenshot:

![](Dealing-with-Windows_images/Dealing-with-Windows_img25.jpeg)


To collapse the default context menu, set the property **CollapseDefaultContextmenu** as **True**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" CollapseDefaultContextMenuItems="True"/>



{% endhighlight %}

To collapse the default context menu in Dock state window, set the property **CollapseDefaultContextMenuInDock** as **True**. By default, its value is **False**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True"  >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="DockWindow"

syncfusion:DockingManager.State="Dock"                     syncfusion:DockingManager.CollapseDefaultContextMenuItemsInDock="True"/>

</syncfusion:DockingManager>



{% endhighlight %}

To collapse the default context menu in Document state window, set the property **CollapseDefaultContextMenuInDocument** as **True**. By default, its value is **False**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" <ContentControl x:Name="Content1" syncfusion:DockingManager.Header="DockWindow" syncfusion:DockingManager.State="Document" syncfusion:DockingManager.CollapseDefaultContextMenuItemsInDocumentTab="True" > 

{% endhighlight}
To collapse the default context menu in Float state window, set the property **CollapseDefaultContextMenuInFloat** as **True**. By default, its value is **False**.

{% highlight xml %}
<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="DockWindow"

syncfusion:DockingManager.State="Float"                                       syncfusion:DockingManager.CollapseDefaultContextMenuItemsInFloat="True"/>





{% endhighlight %}

### Hosting a client control between windows

To add a client control in the DockingManager, set an attached property **ClientControl**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="False">

// A client control TextBox has been added

<syncfusion:DockingManager.ClientControl>

<TextBox x:Name="Text1" Width="100" Height="23" Text=" ClientControl" Background="Black" Foreground="White"/>

</syncfusion:DockingManager.ClientControl>

<ContentControl syncfusion:DockingManager.Header="Top"

syncfusion:DockingManager.SideInDockedMode="Top"/>

<ContentControl syncfusion:DockingManager.Header="Left"

syncfusion:DockingManager.SideInDockedMode="Left"/>

<ContentControl syncfusion:DockingManager.Header="Bottom"

syncfusion:DockingManager.SideInDockedMode="Bottom"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](Dealing-with-Windows_images/Dealing-with-Windows_img26.jpeg)




![](Dealing-with-Windows_images/Dealing-with-Windows_img27.jpeg)


