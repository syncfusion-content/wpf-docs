---
layout: post
title: How to zip files by using the Syncfusion.Compression.Zip namespace | XlsIO | WPF | Syncfusion
description:  How to zip files by using the Syncfusion.Compression.Zip namespace
platform: wpf
control: Xlsio
documentation: ug
---

# How to zip files by using the Syncfusion.Compression.Zip namespace

You can use the AddFile method of ZipArchive object to compress files by using XlsIO. The following code example illustrates how to use this method.
{% tabs %} 
{% highlight C# %}
Syncfusion.Compression.Zip.ZipArchive zipArchive = new Syncfusion.Compression.Zip.ZipArchive();

zipArchive.DefaultCompressionLevel = Syncfusion.Compression.CompressionLevel.Best;

 

// Adds the file you want to zip.

zipArchive.AddFile ("Form1.cs");

 

// Zips the file name and location.

zipArchive.Save("SyncfusionCompressFileSample.zip");

zipArchive.Close();

{% endhighlight %}

{% highlight vbnet %}

'Sets the Series Names in a Legend.
Dim serieOne As Syncfusion.XlsIO.IChartSerie = shape.Series.Add()
Dim zipArchive As New Syncfusion.Compression.Zip.ZipArchive()
zipArchive.DefaultCompressionLevel = Syncfusion.Compression.CompressionLevel.Best
 
'Adds the file you want to zip.
zipArchive.AddFile("Form1.cs")
 
'Zips the file name and location.
zipArchive.Save("SyncfusionCompressFileSample.zip")
zipArchive.Close()

{% endhighlight %}
{% endtabs %}
For compressing directories, you can make use of the AddDirectory method. The AddDirectory method adds an empty directory file to a ZipArchive. When you want to add all the files inside the directory, then you should manually add these files by using the AddItem method. For example, you can use the following code example to add the file from the local drive.
{% tabs %}
{% highlight C# %}

string fileName = @"C:\Form1.cs";
Syncfusion.Compression.Zip.ZipArchive zipArchive = new Syncfusion.Compression.Zip.ZipArchive();
zipArchive.DefaultCompressionLevel = Syncfusion.Compression.CompressionLevel.Best;
Stream stream = new FileStream(fileName, FileMode.Open, FileAccess.Read);
FileAttributes attributes = File.GetAttributes(fileName);
Syncfusion.Compression.Zip.ZipArchiveItem item = new Syncfusion.Compression.Zip.ZipArchiveItem("Form1.cs", stream, true, attributes);
zipArchive.AddItem(item);
zipArchive.Save(@"c:\\SyncfusionCompressFileSample.zip");
zipArchive.Close();

{% endhighlight %}

{% highlight vbnet %}

 
Dim fileName As String = "C:\Form1.cs"
Dim zipArchive As New Syncfusion.Compression.Zip.ZipArchive()
zipArchive.DefaultCompressionLevel = Syncfusion.Compression.CompressionLevel.Best
Dim stream As IO.Stream = New IO.FileStream(fileName, FileMode.Open, FileAccess.Read)
Dim attributes As IO.FileAttributes = File.GetAttributes(fileName)
Dim item As New Syncfusion.Compression.Zip.ZipArchiveItem("Form1.cs", stream, True, attributes)
zipArchive.AddItem(item)
zipArchive.Save("c:\\SyncfusionCompressFileSample.zip")
zipArchive.Close()

{% endhighlight %}
{% endtabs %}