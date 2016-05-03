---
layout: post
title: State Persistence of Syncfusion DockingManager control for WPF
description: Learn how to serialize and de-serialize the state of DockingManager child windows
platform: wpf
control: DockingManager
documentation: ug
---
# Getting Started

State persistence is the combined process of serialization and deserialization. 

DockingManager provides built-in state persistence functionality to save and load at different states and sides. It also provides `DeleteDockState()` and `ResetState()` Method to work on state functionality.

To reset the DockingManager state, call `ResetState()` method of DockingManager instance.

{% tabs %}

{% highlight C# %}

DockingManager1.ResetState();


{% endhighlight %}


{% highlight VB %}


DockingManager1.ResetState() 

{% endhighlight %}

{% endtabs %}

To delete the DockState of the DockingManager, call `DeleteDockState()` of DockingManager instance

{% tabs %}

{% highlight C# %}

DockingManager1.DeleteDockState();

{% endhighlight %}

{% highlight VB %}

DockingManager1.DeleteDockState()

{% endhighlight %}

{% endtabs %}
## Auto Save / Load functionalities

DockingManager supports AutoSave support, that allows to persist its state automatically. To enable this functionality, set the `PersistState` property as `True`. The default value of the `PersistState` property is `False`. It saves the state of the DockingManager in an isolated storage format while WindowClosing. 

{% tabs %}

{% highlight C# %}

DockingManager1.PersistState = true;     

{% endhighlight %}

{% highlight VB %}

DockingManager1.PersistState = True

{% endhighlight %}

{% endtabs %}

To load the AutoPersist state of the DockingManager, call the `LoadDockState()` method of the DockingManager in its loaded event.

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

# Manipulating Save / Load functionalities

## Serialize a complex layout

DockingManager allows to save a complex layout also. For example, it also saves the complex layout like Nested DockingManager.

## Serialize the dynamically added children

By default, DockingManager cannot de-serialize its Saved Layout properly, when its child collection is modified after DockState is saved. 

Since the DockingManager state persistence feature implemented in such a way that the DockingManager matches the child collection of saved layout with current DockingManager layout internally and loads properly when DockingManager children collection remains same, so when any child collection changes dynamically, it results in an improper layout.

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

//Shows serialization methods using xml file.

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

'Shows serialization methods using xml file.

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

//Shows the load and save dockstate in bindary formatter.

BinaryFormatter format = new BinaryFormatter();

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\\docking_bin.bin");

BinaryFormatter format = new BinaryFormatter();

DockingManager1.SaveDockState(format, StorageFormat.Binary, "\\docking_bin.bin");


{% endhighlight %}

{% highlight VB %}

'Shows the load and save dockstate in bindary formatter.

BinaryFormatter format = new BinaryFormatter()

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\docking_bin.bin")

BinaryFormatter format = new BinaryFormatter()

DockingManager1.SaveDockState(format, StorageFormat.Binary, "\docking_bin.bin") 
 
 
{% endhighlight %}

{% endtabs %}


### Save and Load using XmlWriter 

DockingManager allows to load and save the dock state using XMLWriter.

{% tabs %}

{% highlight C# %}

//Shows the SaveDockSte method using xmlwriter.

XmlWriter writer = XmlWriter.Create("DockStates.xml");          

DockingManager.SaveDockState(writer);  

writer.Close()


//Shows the Loaddockstate method using xmlwriter

XmlReader reader = XmlReader.Create("DockStates.xml");

DockingManager.LoadDockState(reader);     
       
reader.Close();       

{% endhighlight %}


{% highlight VB %}

'Shows the SaveDockSte method using xmlwriter.

Dim writer As XmlWriter = XmlWriter.Create("DockStates.xml")

DockingManager.SaveDockState(writer)

writer.Close() XmlReader reader = XmlReader.Create("DockStates.xml")
'Shows the Loaddockstate method using xmlwriter

DockingManager.LoadDockState(reader)

reader.Close() 
 
{% endhighlight %}

{% endtabs %}


