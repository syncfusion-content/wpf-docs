---
layout: post
title: State Persistence in WPF DocumentContainer | Syncfusion®
description: Persist the layout and state of the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control across application sessions using serialization.
platform: wpf
control: DocumentContainer
documentation: ug
---

# State Persistence in WPF DocumentContainer

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

This topic illustrates how to load and save the dock state in various places. It also gives information about resetting and deleting the states.

N> The examples in this topic use `BinaryFormatter` and `SoapFormatter`. Both types are marked obsolete starting in .NET 5 (`SYSLIB0011`) and will throw at runtime on .NET 5 and later unless the obsolete warning is suppressed. For new development, consider replacing them with a modern serializer (for example, `System.Text.Json`) by serializing the dock state to a `Stream` using `XmlSerializer` or `DataContractSerializer`, or by using a `BinaryWriter` over a `MemoryStream`.

## Load and Save in Isolated Storage

The simplest way to load and save the DocumentContainer state is by using its built-in Isolated Storage methods. To load, save, and reset the state, use the following code.

{% tabs %}
{% highlight C# %}
// Save the state to Isolated Storage
DocContainer.SaveDockState();

// Load the state from Isolated Storage
DocContainer.LoadDockState();

// Reset and delete the Isolated Storage used by the DocumentContainer
DocContainer.DeleteInternalIsolatedStorage();
{% endhighlight %}
{% endtabs %}

## Load and Save in a Stream

You can also save the DocumentContainer state to any `Stream` using a `BinaryFormatter` (or any other `IFormatter`). The `SaveDockState(IFormatter)` and `LoadDockState(IFormatter)` overloads accept a formatter that the DocumentContainer uses to write/read its state.

{% tabs %}
{% highlight C# %}
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

BinaryFormatter formatter = new BinaryFormatter();

using (FileStream stream = new FileStream("dockstate.bin", FileMode.Create))
{
    DocContainer.SaveDockState(formatter, stream);
}

using (FileStream stream = new FileStream("dockstate.bin", FileMode.Open))
{
    DocContainer.LoadDockState(formatter, stream);
}
{% endhighlight %}
{% endtabs %}

## Load and Save in XML

You can save and load the DocumentContainer state in XML format using either the `BinaryFormatter` or the `SoapFormatter`. The `StorageFormat` parameter selects between XML and binary storage.

{% tabs %}
{% highlight C# %}
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;
using System.Runtime.Serialization.Formatters.Soap;

string xmlPath = @"d:\docum_xml.xml";

// Save in XML using BinaryFormatter
BinaryFormatter binaryFormatter = new BinaryFormatter();
DocContainer.SaveDockState(binaryFormatter, StorageFormat.Xml, xmlPath);

// Save in XML using SoapFormatter
SoapFormatter soapFormatter = new SoapFormatter();
DocContainer.SaveDockState(soapFormatter, StorageFormat.Xml, xmlPath);

// Load XML using BinaryFormatter
DocContainer.LoadDockState(binaryFormatter, StorageFormat.Xml, xmlPath);

// Load XML using SoapFormatter
DocContainer.LoadDockState(soapFormatter, StorageFormat.Xml, xmlPath);
{% endhighlight %}
{% endtabs %}

## Load and Save in Binary

You can also save and load the DocumentContainer state in a binary file using either `BinaryFormatter` or `SoapFormatter`.

{% tabs %}
{% highlight C# %}
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;
using System.Runtime.Serialization.Formatters.Soap;

string binPath = @"d:\docum_bin.bin";

// Save using BinaryFormatter
BinaryFormatter binaryFormatter = new BinaryFormatter();
DocContainer.SaveDockState(binaryFormatter, StorageFormat.Binary, binPath);

// Save using SoapFormatter
SoapFormatter soapFormatter = new SoapFormatter();
DocContainer.SaveDockState(soapFormatter, StorageFormat.Binary, binPath);

// Load using BinaryFormatter
DocContainer.LoadDockState(binaryFormatter, StorageFormat.Binary, binPath);

// Load using SoapFormatter
DocContainer.LoadDockState(soapFormatter, StorageFormat.Binary, binPath);
{% endhighlight %}
{% endtabs %}

## Reset the State

You can reset the DocumentContainer state using the `ResetState` method.

{% tabs %}
{% highlight C# %}
// Reset the state
DocContainer.ResetState();
{% endhighlight %}
{% endtabs %}

## Delete the State

You can delete a saved state file or the Isolated Storage state using the `DeleteDockState` method overloads.

{% tabs %}
{% highlight C# %}
// Delete a state file from disk
DocContainer.DeleteDockState(@"d:\docum_xml.xml");
DocContainer.DeleteDockState(@"d:\docum_bin.bin");

// Delete the Isolated Storage state
DocContainer.DeleteDockState();
{% endhighlight %}
{% endtabs %}

## See Also

* [Getting Started](Getting-Started.md)
* [Setting Mode for Document Container](Setting-Mode-for-Document-Container.md)
* [Adding and Removing Items](Adding-and-Removing-Items-from-the-Document-Container-Control.md)
