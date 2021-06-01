---
layout: post
title: Save the report as xml file| OLAPCommon | Wpf | Syncfusion
description: save the report as xml file
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Save the report as XML file

The user can save the current report set of OlapDataManager as an XML file for the future needs by using the SaveReport method.

The following code snippet will illustrate the saving of the current report set as an XML file:

{% tabs %}
{% highlight c# %}



olapDataManager.SaveReport(@"C:\SampleReport\RevenueAnalysis.xml");


{% endhighlight  %}


{% highlight vbnet %}



olapDataManager.SaveReport("C:\SampleReport\RevenueAnalysis.xml")


{% endhighlight  %}
{% endtabs %}


## For Silverlight:

You can save the current report of OlapDataManger as an XML file for their future use by serializing the report with XmlSerializer.

The following code snippet will illustrate the saving of the current report set as an XML file:

{% tabs %}
{% highlight c# %}



private void SaveReport()
{
   SaveFileDialog dlg = new SaveFileDialog();
   dlg.Filter = "XML files (*.xml)|*.xml";

   bool? b = dlg.ShowDialog();

   if (b.HasValue && b.Value)
   {
      using (Stream stream = dlg.OpenFile())
      {
         System.Xml.Serialization.XmlSerializer serializer = new System.Xml.Serialization.XmlSerializer(typeof(OlapReport));
         serializer.Serialize(stream, this.olapDataManager.CurrentReport);             
      }
   }            
}
{% endhighlight  %}




{% highlight vbnet %}



Private Sub SaveReport()

   Dim dlg As SaveFileDialog = New SaveFileDialog()

   dlg.Filter = "XML files (*.xml)|*.xml"



   Dim b As Nullable(Of Boolean) = dlg.ShowDialog()



   If b.HasValue AndAlso b.Value Then

Using stream As Stream = dlg.OpenFile()

Dim serializer As System.Xml.Serialization.XmlSerializer = New System.Xml.Serialization.XmlSerializer(GetType(OlapReport))

serializer.Serialize(stream, Me.olapDataManager.CurrentReport)

End Using

   End If

End Sub



{% endhighlight  %}
{% endtabs %}
