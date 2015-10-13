

---
layout: post
title: State Persistence
description: State Persistence
platform: wpf
control: DockingManager
documentation: ug
---
## State Persistence

State persistence is the combined process of serialization and deserialization. 

DockingManager provides built in state persistence functionality to save and load at different states and sides. And it also provides DeleteDockState and Reset Method to work on state functionality

To reset the DockingManager state, set the **ResetState()** method for DockingManager instance.

{% highlight c# %}

DockingManager1.ResetState();





{% endhighlight %}

To delete the Dockstate of the DockingManager, set the **DeleteDockState()** for DockingManager instance

{% highlight c# %}

DockingManager1.DeleteDockState();





{% endhighlight %}

### Auto Save / Load functionalities

DockingManager supports AutoSave support, which allows to persist its state automatically. To enable this functionality, set the **PersistState** property as **True**. The default value of the **PersistState** property is **False**.

To implement the auto save functionality, set the **PersistState** property as **True**. It will save the state of the DockingManager in an isolated storage format while WindowClosing. The same has been explained in the following code 

{% highlight c# %}
DockingManager1.PersistState = true;     





{% endhighlight %}

To load the AutoPersiststate of the DockingManager, call the **LoadDockState** method of the DockingManager in its loaded event.

{% highlight c# %}
void DockingManager1_Loaded(object sender, RoutedEventArgs e)

{

DockingManager1.LoadDockState();

}





{% endhighlight %}

### Manipulating Save / Load functionalities

### Serialize a complex layout

DockingManager allows to save a complex layout also. For example, it also save the complex layout like Nested DockingManager.

### Serialize the dynamically added children

By default, DockingManager can’t serialized its Saved Layout, when its children collection modified after DockState is saved. Since in the DockingManager, the state persistance feature implemented in such a way that the DockingManager will matches the children collection of saved layout with current DockingManager layout internally and loaded only the same state of  the DockingManager  of the  children collection which is same as saved layout, so if any children collections changes dynamically, it would result in improper layout.

To save the dynamically added children, we need to use dispatcher, but it has some limitation. For this case, we should maintain serialized files in application level and deserialize if needed.

### Various formats to Save / Load states

DockingManager allows to save and load the Dockstates of windows in DockingManager in different format.

Some of the formats are find as below:

<table>
<tr>
<td>
 IsolatedStorage<br/>BinaryFormat<br/> XML file<br/> XmlWriter<br/><br/><br/><br/></td></tr>
</table>

**Load and save the Dockstate using Isolated Storage:**

DockingManager allows to save and load the dockstate using isolated storage  

{% highlight c# %}

// Shows the Isolated storage format

DockingManager1.LoadDockState();

DockingManager1.SaveDockState();

DockingManager1.ResetState();



{% endhighlight %}

**Save** **and** **Load** **using** **BinaryFormatter**

DockingManager allows to save and load the state of the DockingManager using binary formatter

{% highlight c# %}

// Shows the Load and save method performs in BinaryFormatter

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.LoadDockState(formatter);

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.SaveDockState(formatter);





{% endhighlight %}

**Save** **and** **Load** **using** **Xml** **file** 

DockingManager allows to save and load the xml file. And it is done using binary formatter and sop formatter. The code has been explained below:

{% highlight c# %}

//Shows serialization methods using xml file

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.LoadDockState(formatter, StorageFormat.Xml, "\\docking_xml.xml");

BinaryFormatter formatter =  new BinaryFormatter();

DockingManager1.SaveDockState(formatter, StorageFormat.Xml, "\\docking_xml.xml");

SoapFormatter formatter1 = new SoapFormatter(); DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\\docking_xml_soap.xml"); 

SoapFormatter formatter1 = new SoapFormatter(); DocContainer.SaveDockState(formatter1, StorageFormat.Xml, "\\docking_xml_soap.xml"); 





{% endhighlight %}

.

**Save** **and** **Load** **using** **Bin**

DockingManager allows to load and save the dock state in the bin file. 

{% highlight c# %}

//Shows the load and save dockstate in bindary formatter

BinaryFormatter format = new BinaryFormatter();

DockingManager1.LoadDockState(format, StorageFormat.Binary, "\\docking_bin.bin");

BinaryFormatter format = new BinaryFormatter();

DockingManager1.SaveDockState(format, StorageFormat.Binary, "\\docking_bin.bin");



{% endhighlight %}

**Save** **and** **Load** **using** **Xmlwriter** 

DockingManager allows to load and save the dock state using XMLWriter

{% highlight c# %}

//Shows the SaveDockSte method using xmlwriter

XmlWriter writer = XmlWriter.Create("DockStates.xml");            DockingManager.SaveDockState(writer);  

writer.Close()



{% endhighlight %}

{% highlight c# %}

//Shows the Loaddockstate method using xmlwriter
XmlReader reader = XmlReader.Create("DockStates.xml");            DockingManager.LoadDockState(reader);            
reader.Close();       

{% endhighlight %}
