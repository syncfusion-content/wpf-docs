---
layout: post
title: Load xml report file| OLAPCommon | Wpf | Syncfusion
description: load xml report file
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Load XML report file

You can load the XML report set by using the LoadReport method.

The following code snippet will illustrate the loading of the report:
{% tabs %}
{% highlight c# %}



olapDataManager.LoadReport(@"C:\SampleReport\RevenueAnalysis.xml");
{% endhighlight  %}


{% highlight vbnet %}



olapDataManager.LoadReport("C:\SampleReport\RevenueAnalysis.xml")

{% endhighlight  %}
{% endtabs %}

## For Silverlight:



The saved report file can be used with OlapDataManager by serializing it to type OlapReport with XmlSerializer.

The following code snippet will illustrate the loading of a saved XML report file:

{% tabs %}
{% highlight c# %}



 private void LoadReport()
 {
    OpenFileDialog dlg = new OpenFileDialog();
    dlg.Filter = "XML files (*.xml)|*.xml";
 bool? b = dlg.ShowDialog();

    if (b.HasValue && b.Value)
    {
        OlapReport report = null;

        using (FileStream stream = dlg.File.OpenRead())
        {
           System.Xml.Serialization.XmlSerializer serializer = new System.Xml.Serialization.XmlSerializer(typeof(OlapReportCollection));
           OlapReportCollection olapReportCollection = serializer.Deserialize(stream) as OlapReportCollection;
          report = olapReportCollection[0];                       
        }
        olapDataManager.SetCurrentReport(report);         
    }            
}


{% endhighlight  %}
{% highlight vbnet %}



Private Sub LoadReport()

Dim dlg As OpenFileDialog = New OpenFileDialog()

dlg.Filter = "XML files (*.xml)|*.xml"

Dim b As Nullable(Of Boolean) = dlg.ShowDialog()



If b.HasValue AndAlso b.Value Then

Dim report As OlapReport = Nothing



Using stream As FileStream = dlg.File.OpenRead()

Dim serializer As System.Xml.Serialization.XmlSerializer = New System.Xml.Serialization.XmlSerializer(GetType(OlapReportCollection))

Dim olapReportCollection As OlapReportCollection = TryCast(serializer.Deserialize(stream), OlapReportCollection)

report = olapReportCollection(0)

End Using

olapDataManager.SetCurrentReport(report)

End If

 End Sub

{% endhighlight  %}
{% endtabs %}
