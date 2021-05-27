---
layout: post
title: State Persistence in WPF Tabbed MDI Form control | Syncfusion
description: Learn here all about State Persistence support in Syncfusion WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: wpf
control: DocumentContainer
 documentation: ug
---

# State Persistence in WPF Tabbed MDI Form (DocumentContainer)

This topic illustrates loading and saving the dock state in various places. It also gives information about resetting and deleting the states.

## Load and Save in Registry

In the Document Container, you can save and load dock states into the Registry using the SaveDockState and LoadDockState methods. Refer to the following code snippet for setting these methods.



{% highlight C# %}



// Code to Save State:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.SaveDockState(formatter1);



// Code to Load State:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.LoadDockState(formatter1);


{% endhighlight %}

## Load and Save in Isolated Storage

In the Document Container you can Load/Save/Reset the dock state in the Isolated Storage. To Load, Save and Reset, use the following code snippet.



{% highlight C# %} 



// Code to Save:

DocContainer.SaveDockState();



// Code to Load:

DocContainer.LoadDockState();



// Code to Reset:

DocContainer.DeleteInternalIsolatedStorage();
{% endhighlight %}


## Load and Save in XML

You can save and load the data for the Document Container in XML also. To Load and Save data in XML use the following code snippet. This is done by using both Binary Formatter as well as Soap Formatter as follows.



{% highlight C# %}



 // Code to Save in XML using Binary Formatter:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, @"d:\docum_xml.xml");



// Code save in XML using SOAP formatter:

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Xml, @"d:\docum_xml.xml");



// Code to Load XML using Binary formatter:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.LoadDockState(formatter1, StorageFormat.Xml, @"d:\docum_xml.xml");



// Code to Load XML using Soap Formatter:

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.LoadDockState(formatter1, StorageFormat.Xml, @"d:\docum_xml.xml");

{% endhighlight %}

## Load and Save in Bin

Document Container enables the user to save and load the data in BIN. Refer to the following code snippet for saving or loading data in BIN. This is achieved by using Binary Formatter and Soap Formatter as well.



{% highlight C# %}



// Code to Save Using Binary Formatter:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Binary, @"d:\docum_bin.bin");



// Code to Save Using Soap Formatter:

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.SaveDockState(formatter1, StorageFormat.Binary, @"d:\docum_bin.bin");



// Code to Load using Binary Formatter:

BinaryFormatter formatter1 = new BinaryFormatter();

DocContainer.LoadDockState(formatter1, StorageFormat.Binary, @"d:\docum_bin.bin");



// Code to Load using Soap Formatter:

SoapFormatter formatter1 = new SoapFormatter();

DocContainer.LoadDockState(formatter1, StorageFormat.Binary, @"d:\docum_bin.bin");

{% endhighlight %}

## Reset the states in Document Container

You can easily reset the states in Document Container by using the ResetState method as in the below code snippet.



{% highlight C# %}



DocumentContainer DocContainer = new DocumentContainer();



// Reset the states

DocContainer.ResetState();

{% endhighlight %}

## Delete the State

You can delete all the states you have created in the Document Container by using the DeleteDockState property. Refer to the below code example.



{% highlight C# %}



DocContainer.DeleteDockState(@"d:\docum_xml.xml");

DocContainer.DeleteDockState(@"d:\docum_bin.bin");

DocContainer.DeleteDockState();


{% endhighlight %}
