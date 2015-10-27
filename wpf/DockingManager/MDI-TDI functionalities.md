---
layout: post
title: MDI/ TDI functionalities
description: MDI/ TDI functionalities 
platform: wpf
control: DockingManager
documentation: ug
---

## MDI/ TDI functionalities

The MDI and TDI functionalities are applicable for the Document window in the DockingManager.

The Document window can be displayed in both Multiple Document Interface and Tabbed Document Interface. To switch this functionality between MDI and TDI mode for the Document window, set the property **ContainerMode** with its respective values.

By default, the document state window is in TDI mode, with the display tab as tabbed document.

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True"  ContainerMode="TDI">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1" "/>   

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Document2" "

syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img1.jpeg)


To make the document child window as MDI document, set the **ContainerMode** as **MDI**

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True"  ContainerMode="MDI">        

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1"

syncfusion:DockingManager.State="Document"/>   

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Document2"

syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img2.jpeg)


### Setting MDI Window state

The differenet state for the MDI Window can be set using the **SetMDIWindowState()** method of DocumentContainer. 

* Setting MDIWindowstate as Minimized

{% highlight c# %}

DocumentContainer.SetMDIWindowState(Content1,MDIWindowState.Minimized);

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img3.jpeg)



* Setting MDIWindowstate as Maximized

{% highlight c# %}

DocumentContainer.SetMDIWindowState(Content1,MDIWindowState.Maximized);

{% endhighlight %}

### Getting state of the MDI window

The state for the MDI window can be detect using the **GetMDIWindowState()** method of DocumentContainer.

{% highlight c# %}

DocumentContainer.GetMDIWindowState(Content1);

{% endhighlight %}

### Detecting the maximized state of the MDI window

To get the Maximized state of the MDI window of the Document state window, set the property **IsInMDIMaximizedState** of DocumentContainer as **True**. The container can be fetched for the DockingManager using the **DocContainer** property.

{% highlight c# %}

(DockingManager1.DocContainer as DocumentContainer).IsInMDIMaximizedState = true;

{% endhighlight %}

### Resizing MDI

MDI document window can be able to resize using the navigation arrows, to restrict resizing the MDI document windows, disable the Property **IsAllowMDIResize** of the **Documentcontainer** that can be get using the **DocContainer** property of the DockingManager. By default, its values is **False**.

{% highlight c# %}

(DockingManager1.DocContainer as DocumentContainer).IsAllowMDIResize = false;

{% endhighlight %}

### Different Keyboard Navigation Modes

DockingManager allows you to navigate between the TDI and MDI windows easily using the keyboard keys with combination of **CTRL** **+** **TAB** in five different modes through the property **SwitchMode** of the Documentcontainer that can be fetched using the DocContainer in the DocumentContainer loaded event.

There are five switch modes.

* Immediate
* List
* QuickTabs
* VS2005
* Vista Flip

* Immediate – Switch the MDI document windows immediately.

{% highlight c# %}

DockingManager1.SwitchMode =SwitchMode.Immediate;

{% endhighlight %}



![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img4.jpeg)


* List – Switch the MDI document windows in list format.

{% highlight c# %}

DockingManager1.SwitchMode = SwitchMode.List;

{% endhighlight %}



![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img5.jpeg)


* QuickTabs

{% highlight c# %}

DockingManager1.SwitchMode = SwitchMode.QuickTabs;

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img6.jpeg)


* VistaFlip –

{% highlight c# %}

DockingManager1.SwitchMode = SwitchMode.VistaFlip;

{% endhighlight %}


![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img7.jpeg)


* Vs2005

{% highlight c# %}

DockingManager1.SwitchMode = SwitchMode.VS2005;

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img8.jpeg)


### Setting MDI Layout

DockingManager allows you to set the different layout for the MDI windows with the different MDILayout values such as **Horizontal****,** **Vertical****,** **and** **Cascade** layout through the property **SetLayout****()** of DocumentContainer.

* Horizontal - Arranges the MDI windows horizontally.


{%highlight c#%}

void DocumentContainer_Loaded(object sender, RoutedEventArgs e)
{
(DockingManager1.DocContainer as DocumentContainer).SetLayout(MDILayout.Horizontal);
}

{%endhighlight%}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img9.jpeg)


* Vertical – Arranges the MDI windows vertically.

{% highlight c# %}

void DocumentContainer_Loaded(object sender, RoutedEventArgs e)
{
(DockingManager1.DocContainer as DocumentContainer).SetLayout(MDILayout.Vertical);
}

{%endhighlight%}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img10.jpeg)


* Cascade - Arranges the layout in a cascade manner.

{%highlight C#%}

void DocumentContainer_Loaded(object sender, RoutedEventArgs e){(DockingManager1.DocContainer as DocumentContainer).SetLayout(MDILayout.Vertical);}

{%endhighlight%}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img11.jpeg)




### Closing a MDI Windows

To enable and disable closing of the MDI windows, set **CanClose** an attached property of DockingManager with its respective values. By default, its value is “**True****”**

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" ContainerMode="MDI"> <br/><br/><ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"<br/><br/>syncfusion:DockingManager.State="Document"                          syncfusion:DockingManager.CanClose="False"></ContentControl>                               <br/><br/></syncfusion:DockingManager><br/><br/><br/><br/></td></tr>
{%endhighlight%}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img12.jpeg)


### Indexing an Item in TDI

A document window can be placed at different index position using the **SetTDIIndex****()** method of the TDILayoutPanel. 

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True"  >        <ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1"

syncfusion:DockingManager.State="Document"/>   

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Document2"

syncfusion:DockingManager.State="Document"/> 

</syncfusion:DockingManager>

TDILayoutPanel.SetTDIIndex(Content1,0);

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img13.jpeg)


### Drag / Drop support in TDI

The TDI document index can be changed by dragging and dropping it like Visual Studio. This functionality can be enabled or disabled through the property **IsTDIDragDropEnabled** of DockingManager depends upon its value **True** or **False** respectively.

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True"  IsTDIDragDropEnabled="True" >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1"

syncfusion:DockingManager.State="Document"/>

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Document2"

syncfusion:DockingManager.State="Document"/>

<ContentControl x:Name="Content3" syncfusion:DockingManager.Header="Document3"

syncfusion:DockingManager.State="Document"/>

</syncfusion:DockingManager>

{% endhighlight %}

### Customizing Close Menu

When two or more documents used in the DockingManager the Close, CloseAll and CloseAllButThis menu items are available for the document window. To collapse the visibility of these menu item, set the property **ShowClose** , **ShowCloseAll** and **ShowCloseAllButThis** as **False**.

{% highlight xaml %}

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"  

syncfusion:DockingManager.State="Document"

syncfusion:DockingManager.ShowCloseMenuItem="False"

syncfusion:DockingManager.ShowCloseAllMenuItem="False" syncfusion:DockingManager.ShowCloseAllButThisMenuItem="False"

/>                                                 



<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"  

syncfusion:DockingManager.State="Document"

syncfusion:DockingManager.ShowCloseMenuItem="False"

syncfusion:DockingManager.ShowCloseAllMenuItem="False"

syncfusion:DockingManager.ShowCloseAllButThisMenuItem="False"/>             





{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img14.jpeg)


### Grouping Document Tab Group

TDI document can be grouped like VisualStudio. It can be grouped by drag and Drop and also using the options in context menu items.

#### Creating Vertical Tab Group 

To create a vertical tab group in the Tabbed document, select the **New** **Vertical** **Tab** **Group** context menu item and also it can be created programmatically by calling the method **CreateVerticallTabGroup(UIElement)** of the DocumentContainer in its loaded event.

{% highlight c# %}

(DockingManager1.DocContainer as DocumentContainer).Loaded += DocumentContainer_Loaded;

private void DocumentContainer_Loaded(object sender, RoutedEventArgs e)
{
(DockingManager1.DocContainer as DocumentContainer). CreateVerticalTabGroup(Content1) (Content1);
}

{% endhighlight %}

#### Creating Horizontal Tab Group 

To create a horizontal tab group in the Tabbed document, select the **New** **Horizontal** **Tab** **Group** context menu item and also it can be created programmatically by calling the method **CreateHorizontalTabGroup(UIElement)** of the DocumentContainer in its loaded event.

{% highlight c# %}

(DockingManager1.DocContainer as DocumentContainer).Loaded += DocumentContainer_Loaded;

private void DocumentContainer_Loaded(object sender, RoutedEventArgs e)
{
	(DockingManager1.DocContainer as DocumentContainer).CreateHorizontalTabGroup(Content1);
}


{% endhighlight %}

#### Adding Tab in a Group 

In TDI document, a new tab group can be created by dragging the TabItem into the Document area and click the **New** **Tab** **Group** Menu from context menu item.

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img15.jpeg)


![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img16.jpeg)


#### Disable TabGroups

Vertical and Horizontal Tab Grouping feature can be enabled or disabled using the property TabGroupEnabled in DockingManager. 

TabGroupEnabled
Enables or disables the ability to create tab groups. It is a boolean property.
 
Disabling Tab Groups
Setting TabGroupEnabled=”False” does not display New Horizontal Tab Group and New Vertical Tab Group context menu items even when ShowHorizontalTabGroupMenuItem is true. Drag and drop support to create new tab group is also restricted. TabGroupEnabled property can be set as shown here:

{% tabs %}
{% highlight c# %}
dockingManager.TabGroupEnabled = false;

{% endhighlight %}

{% highlight xaml %}

<syncfusion:DockingManager x:Name="dockingManager" TabGroupEnabled="False" >
</Syncfusion:DockingManager>

{%endhighlight %}
 
{% endtabs %}


### VS2010 Behavior of TDI

TDI document of DockingManager can be changed to Float while dragging its TDI header like the Visual Studio. This functionality can be enabled or disabled using the property **IsVs2010DraggingEnabled** depends upon its value **True** or **False** respectively. 

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" IsVS2010DraggingEnabled="True"   >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1"

syncfusion:DockingManager.State="Document"/>

</syncfusion:DockingManager>

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img17.jpeg)


### TDI Header Renaming Support

To enable the functionality of editing the TDI document header when you double click the document header at runtime, set the property **EnableDocumentTabHeaderEdit** of the DockingManager as **True**. By default, its value is **False**.

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" EnableDocumentTabHeaderEdit="True">

{% endhighlight %}

### Hiding TDI Header

To hide the TDI document header when a single document child present in a DockingManager set the property **HideTDIHeaderOnSingleChild** as **True**. By default its value is **False**.

{% highlight xaml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" HideTDIHeaderOnSingleChild="True">

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1"                                          syncfusion:DockingManager.State="Document" />

</syncfusion:DockingManager>

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img18.jpeg)


### Add new button in Header Panel

In DockingManager, the new button can be added in the Document state windows using the **IsNewButtonEnabled** property of the DocumentTabControl. To achieve this, the DocumentTabControl must be fetched from the DockingManager using the VisualUtils in Document container loaded event.

{%highlight c#%}

//shows the loaded event for the DocumentContainer.
(DockingManager1.DocContainer as DocumentContainer).Loaded += DocumentContainer_Loaded;<br/><br/>void DocumentContainer_Loaded(object sender, RoutedEventArgs e)<br/><br/>{<br/><br/>DocumentTabControl tab = VisualUtils.FindDescendant(DockingManager1,<br/><br/>typeof (DocumentTabControl)) as DocumentTabControl;
if (tab != null)
{
tab.IsNewButtonEnabled = true;
tab.NewButtonBackground = Brushes.Green;}}

{% endhighlight %}

![](MDI_TDIfunctionalities_images/MDI_TDIfunctionalities_img19.jpeg)


