---
layout: post
title: State Persistence in WPF DocumentContainer | Syncfusion®
description: Persist the layout and state of the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control across application sessions using serialization.
platform: wpf
control: DocumentContainer
documentation: ug
---

# State Persistence in WPF Document Container

This topic illustrates how to load and save the dock state in various places. It also gives information about resetting and deleting the states.

## Load and Save in Isolated Storage

The simplest way to load and save the WPF Document Container state is by using its built-in Isolated Storage methods. To load, save, and reset the state, use the following code.

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

You can also save the WPF Document Container state to any `Stream` using a `BinaryFormatter` (or any other `IFormatter`). The `SaveDockState(IFormatter)` and `LoadDockState(IFormatter)` overloads accept a formatter that the WPF Document Container uses to write/read its state.

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

You can save and load the WPF Document Container state in XML format using either the `BinaryFormatter` or the `SoapFormatter`. The `StorageFormat` parameter selects between XML and binary storage.

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

You can also save and load the WPF Document Container state in a binary file using either `BinaryFormatter` or `SoapFormatter`.

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

You can reset the WPF Document Container state using the `ResetState` method.

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
