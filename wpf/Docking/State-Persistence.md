---
layout: post
title: State Persistence in WPF Docking control | Syncfusion
description: Learn here all about State Persistence support in Syncfusion WPF Docking (DockingManager) control and more.
platform: wpf
control: DockingManager
documentation: ug
---
# State Persistence in WPF Docking (DockingManager)

State persistence is the combined process of serialization and deserialization. 

DockingManager provides built-in state persistence functionality to save and load at different states and sides. It also provides [DeleteDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DeleteDockState().html) and [ResetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ResetState) Method to work on state functionality.

To reset the DockingManager state, call [ResetState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_ResetState) method of DockingManager instance.

N> DockingManager serializes and de-serializes the controls using `Name` property. So, ensure to set `Name` property for all child controls. The name of children in saved layout should be same as the name of children in DockingManager to load the saved layout. `LoadDockState` returns `true` or `false` to notify whether de-serialization process has been successful.

{% tabs %}

{% highlight C# %}

DockingManager1.ResetState();


{% endhighlight %}


{% highlight VB %}


DockingManager1.ResetState() 

{% endhighlight %}

{% endtabs %}

To delete the DockState of the DockingManager, call [DeleteDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DeleteDockState.html) of DockingManager instance

{% tabs %}

{% highlight C# %}

DockingManager1.DeleteDockState();

{% endhighlight %}

{% highlight VB %}

DockingManager1.DeleteDockState()

{% endhighlight %}

{% endtabs %}

## Auto Save / Load functionalities

DockingManager supports AutoSave support, that allows to persist its state automatically. To enable this functionality, set the [PersistState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_PersistState) property as `True`. The default value of the [PersistState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_PersistState) property is `False`. It saves the state of the DockingManager in an isolated storage format while [WindowClosing](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html). 

{% tabs %}

{% highlight C# %}

DockingManager1.PersistState = true;     

{% endhighlight %}

{% highlight VB %}

DockingManager1.PersistState = True

{% endhighlight %}

{% endtabs %}

To load the AutoPersist state of the DockingManager, call the [LoadDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_LoadDockState().html) method of the DockingManager in its loaded event.

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

DockingManager allows to save a complex layout also. For example, it also saves the complex layout like Nested DockingManager.

## Serialize the dynamically added children

By default, DockingManager cannot de-serialize its Saved Layout properly, when its child collection is modified after DockState is saved. 

Since the DockingManager state persistence feature implemented in such a way that the DockingManager matches the child collection of saved layout with current DockingManager layout internally and loads properly when DockingManager children collection remains same, so when any child collection changes dynamically, it results in an improper layout.

### Notification for load DockState

When the children collection of DockingManager is changed dynamically after persisting the layout, incorrect layout may load.  Success of loading of persisted state can be decided by return value of [LoadDockState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_LoadDockState().html) method. When the child count is same and then DockingManager checks the Name of the child in the collection. if the Name of the child in loaded state is different from the persisted child in the collection, DockingManager fails to load the saved layout. In such cases, `false` value will be returned by the `LoadDockState` method of DockingManager.

## Various formats to Save / Load states

DockingManager allows to save and load the DockStates of windows in DockingManager in different format.

Some of the formats are:

 * IsolatedStorage
 * BinaryFormat
 * XML file
 * XmlWriter


### Load and save the DockState using Isolated Storage:

DockingManager allows to save and load the dock state from isolated storage.  

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

DockingManager allows to save and load the XML file. It is done using binary formatter and soap formatter. The code example is below:

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

DockingManager allows to load and save the dock state in the binary format file. 

{% tabs %}

{% highlight C# %}

//Shows the load and save dock state in binary formatter.

BinaryFormatter format = new BinaryFormatter();

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\\docking_bin.bin");

BinaryFormatter format = new BinaryFormatter();

DockingManager1.SaveDockState(format, StorageFormat.Binary, "\\docking_bin.bin");


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

DockingManager allows to load and save the DockState using XMLWriter.

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

The [CanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanSerializeProperty) attached property of DockingManager decides whether the child can be serialized or not. The default value of the [CanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanSerializeProperty) property is true. When the property is false, while performing deserialization the non-serialized child will move to its default state. This can also be done programmatically by using the [SetCanSerialize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SetCanSerialize_System_Windows_DependencyObject_System_Boolean_) function of DockingManager.

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

N> Restrict state persistence does not support to children that were added at run time in DockingManager when performing serialization and de-serialization using [XmlWriter](https://help.syncfusion.com/wpf/tabbed-mdi-form/state-persistence#various-formats-to-save--load-states).

N> Docking State persistence will be applied to active Docking Children. So it must to load dynamically added controls into DockingManager before applying Deserialization process.

