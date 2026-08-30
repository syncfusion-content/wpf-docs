---
layout: post
title: State Persistence in WPF DockingManager Control | Syncfusion®
description: The state persistence in DockingManager lets you save and restore the layout, state, and position of docked child windows.
platform: wpf
control: DockingManager
documentation: ug
---
# State Persistence in WPF Docking Control

State persistence is the combined process of serialization and deserialization. 

WPF Docking Control provides built-in state persistence functionality to save and load at different states and sides. It also provides [DeleteDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DeleteDockState().html) and [ResetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ResetState) Method to work on state functionality.

To reset the WPF Docking Control state, call [ResetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ResetState) method of WPF Docking Control instance.

N> WPF Docking Control serializes and de-serializes the controls using `Name` property. So, ensure to set `Name` property for all child controls. The name of children in saved layout should be same as the name of children in WPF Docking Control to load the saved layout. `LoadDockState` returns `true` or `false` to notify whether de-serialization process has been successful.

{% tabs %}

{% highlight C# %}

DockingManager1.ResetState();


{% endhighlight %}


{% highlight VB %}


DockingManager1.ResetState() 

{% endhighlight %}

{% endtabs %}

To delete the DockState of the WPF Docking Control, call [DeleteDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DeleteDockState.html) of WPF Docking Control instance

{% tabs %}

{% highlight C# %}

DockingManager1.DeleteDockState();

{% endhighlight %}

{% highlight VB %}

DockingManager1.DeleteDockState()

{% endhighlight %}

{% endtabs %}

## Auto Save / Load functionalities

WPF Docking Control supports AutoSave support, that allows to persist its state automatically. To enable this functionality, set the [PersistState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_PersistState) property as `True`. The default value of the [PersistState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_PersistState) property is `False`. It saves the state of the WPF Docking Control in an isolated storage format while [WindowClosing](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html). 

{% tabs %}

{% highlight C# %}

DockingManager1.PersistState = true;     

{% endhighlight %}

{% highlight VB %}

DockingManager1.PersistState = True

{% endhighlight %}

{% endtabs %}

To load the AutoPersist state of the WPF Docking Control, call the [LoadDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_LoadDockState().html) method of the WPF Docking Control in its loaded event.

{% tabs %}

{% highlight C# %}

void DockingManager1_Loaded(object sender, RoutedEventArgs e)
{
	DockingManager1.LoadDockState();
}

{% endhighlight %}


{% highlight VB %}

Private Sub DockingManager1_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)
	DockingManager1.LoadDockState()
End Sub 

{% endhighlight %}

{% endtabs %}

## Manipulating Save / Load functionalities

## Serialize a complex layout

The WPF Docking Control allows you to save complex layouts, including nested docking layouts. For example, layouts containing nested WPF Docking Control instances can be saved and restored.

## Serialize the dynamically added children

By default, WPF Docking Control cannot de-serialize its Saved Layout properly, when its child collection is modified after DockState is saved. 

Since the state persistence feature of the WPF Docking Control is implemented in such a way that it matches the child collection in the saved layout with the current child collection during restoration, the layout is restored correctly only when the child collection remains unchanged. When the child collection changes dynamically, it results in an improper layout restoration.

### Notification for load DockState

When the child collection of the WPF Docking Control changes dynamically after the layout is persisted, an incorrect layout may be loaded. The success of loading the persisted state can be determined from the return value of the [LoadDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_LoadDockState().html) method. If the child count remains the same, the control checks the Name of each child in the collection. If a child name in the loaded state differs from the corresponding persisted child name, the saved layout cannot be loaded. In such cases, the `LoadDockState` method returns `false`.

## Various formats to Save / Load states

WPF Docking Control allows to save and load the DockStates of windows in DockingManager in different format.

Some of the formats are:

 * IsolatedStorage
 * BinaryFormat
 * XML file
 * XmlWriter

### Where to call the Save and Load dock state:

To save the DockState of the WPF Docking Control, call the [SaveDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SaveDockState) method. You can call this method during any specific or desired scenario where preserving the layout is needed. For instance, before a window is closed or when switching between views.

{% tabs %}
{% highlight C# %}
// Saves the current dock state of the DockingManager when the window is closing event.
private void Window_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
	DockingManager1.SaveDockState();
}
{% endhighlight %}

{% highlight VB %}
' Saves the current dock state of the DockingManager when the window is closing event.
Private Sub Window_Closing(sender As Object, e As System.ComponentModel.CancelEventArgs)
	DockingManager1.SaveDockState()
End Sub
{% endhighlight %}
{% endtabs %}

To load the previously saved DockState of the DockingManager when any specific desired scenario, call the [LoadDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_LoadDockState().html) method. This method can be called in any specific or desired scenario where you need to bring back a saved layout, such as during application initialization or after resetting the layout.

{% tabs %}
{% highlight C# %}
// Loads the previously saved dock state of the DockingManager on button click event.
private void LoadButton_Click(object sender, RoutedEventArgs e)
{
	DockingManager1.LoadDockState();
}
{% endhighlight %}

{% highlight VB %}
' Loads the previously saved dock state of the DockingManager on button click event.
Private Sub LoadButton_Click(sender As Object, e As RoutedEventArgs)
	DockingManager1.LoadDockState()
End Sub
{% endhighlight %}
{% endtabs %}

### Load and save the DockState using Isolated Storage:

WPF Docking Control allows to save and load the dock state from isolated storage.  

{% tabs %}

{% highlight C# %}

// Shows the Isolated storage format.

DockingManager1.LoadDockState();

DockingManager1.SaveDockState();

DockingManager1.ResetState();


{% endhighlight %}


{% highlight VB %}

' Shows the Isolated storage format.

DockingManager1.LoadDockState()

DockingManager1.SaveDockState()

DockingManager1.ResetState() 

{% endhighlight %}

{% endtabs %}

### Save and Load using XML file 

WPF Docking Control allows to save and load the XML file. It is done using binary formatter and soap formatter. The code example is below:

{% tabs %}

{% highlight C# %}

//Shows serialization methods using XML file.

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.LoadDockState(formatter, StorageFormat.Xml, "\\docking_xml.xml");

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.SaveDockState(formatter, StorageFormat.Xml, "\\docking_xml.xml");

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\\docking_xml_soap.xml"); 

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\\docking_xml_soap.xml"); 


{% endhighlight %}



{% highlight VB %}

'Shows serialization methods using XML file.

Dim formatter As New BinaryFormatter()

DockingManager1.LoadDockState(formatter, StorageFormat.Xml, "\docking_xml.xml")

Dim formatter As New BinaryFormatter()

DockingManager1.SaveDockState(formatter, StorageFormat.Xml, "\docking_xml.xml")

Dim formatter1 As New SoapFormatter()

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\docking_xml_soap.xml")

Dim formatter1 As New SoapFormatter()

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\docking_xml_soap.xml")

{% endhighlight %}

{% endtabs %}

### Save and Load using Binary

WPF Docking Control allows to load and save the dock state in the binary format file. 

{% tabs %}

{% highlight C# %}

//Shows the load and save dock state in binary formatter.

BinaryFormatter format = new BinaryFormatter();

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\\docking_bin.bin");

BinaryFormatter saveFormat = new BinaryFormatter();

DockingManager1.SaveDockState(saveFormat, StorageFormat.Binary, "\\docking_bin.bin");


{% endhighlight %}

{% highlight VB %}

'Shows the load and save dock state in binary formatter.

BinaryFormatter format = new BinaryFormatter()

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\docking_bin.bin")

BinaryFormatter format = new BinaryFormatter()

DockingManager1.SaveDockState(format, StorageFormat.Binary, "\docking_bin.bin") 
 
 
{% endhighlight %}

{% endtabs %}


### Save and Load using XmlWriter 

WPF Docking Control allows to load and save the DockState using XMLWriter.

{% tabs %}

{% highlight C# %}

//Shows the SaveDockState method using XmlWriter.

XmlWriter writer = XmlWriter.Create("DockStates.xml");          

DockingManager.SaveDockState(writer);  

writer.Close()


//Shows the LoadDockState method using XmlWriter

XmlReader reader = XmlReader.Create("DockStates.xml");

DockingManager.LoadDockState(reader);     
       
reader.Close();       

{% endhighlight %}


{% highlight VB %}

'Shows the SaveDockState method using XmlWriter.

Dim writer As XmlWriter = XmlWriter.Create("DockStates.xml")

DockingManager.SaveDockState(writer)

writer.Close() XmlReader reader = XmlReader.Create("DockStates.xml")
'Shows the LoadDockState method using XmlWriter

DockingManager.LoadDockState(reader)

reader.Close() 
 
{% endhighlight %}

{% endtabs %}

## Restrict state persistence for specific child

The [CanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanSerializeProperty) attached property of WPF Docking Control decides whether the child can be serialized or not. The default value of the [CanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanSerializeProperty) property is true. When the property is false, while performing deserialization the non-serialized child will move to its default state. This can also be done programmatically by using the [SetCanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SetCanSerialize_System_Windows_DependencyObject_System_Boolean_) function of WPF Docking Control.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True">

<ContentControl syncfusion:DockingManager.Header="Solution Explorer" x:Name="solutionExplorer" syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.CanSerialize="False"/>

<ContentControl syncfusion:DockingManager.Header="Start Page" x:Name="startPage" syncfusion:DockingManager.State="Document" />

<ContentControl syncfusion:DockingManager.Header="Toolbox" x:Name="toolBox" syncfusion:DockingManager.State="AutoHidden"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetCanSerialize(solutionExplorer, false);

{% endhighlight %}

{% endtabs %}

N> Restrict state persistence does not support to children that were added at run time in WPF Docking Control when performing serialization and de-serialization using [XmlWriter](https://help.syncfusion.com/wpf/tabbed-mdi-form/state-persistence#various-formats-to-save--load-states).

N> Docking State persistence will be applied to active Docking Children. So it must to load dynamically added controls into WPF Docking Control before applying Deserialization process.

N> The `LoadDockState` method will return true only when all the children in WPF Docking Control match precisely with the children in the serialized file.

