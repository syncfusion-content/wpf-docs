---
layout: post
title: Storing and Retrieving Report as Stream in WPF OlapClient | Syncfusion
description: Storing and retrieving report as stream in Syncfusion Essential Studio WPF OlapClient Control, its elements, and more.
platform: wpf
control: OLAP Client
documentation: ug
---

# Storing and Retrieving Report as Stream

The OLAP client allows users to store the current session as a stream anywhere and load the saved stream to populate the controls. By this, the OLAP client can be used as an OLAP report creator and OLAP report viewer, where a user can create a report set and push it to the server. The user can also view the reports.

The following code describes getting the report as stream.

{% tabs %}
{% highlight C# %}




Stream stream = this.olapClient1.GetReportStream();


{% endhighlight %}


{% highlight vbnet %} 




Dim stream As Stream = Me.olapClient1.GetReportStream()

{% endhighlight %} 
{% endtabs %}


The following code illustrates how to load a stream to OLAP client.

{% tabs %}
{% highlight C# %}  





this.olapClient1.LoadReportStream(reportStream);

{% endhighlight %}



{% highlight vbnet %} 




Me.olapClient1.LoadReportStream(reportStream)

{% endhighlight %} 
{% endtabs %}


The following sample code describes storing of stream in the database, retrieving a report as stream from the database, and loading the stream to the OLAP client.

The following code illustrates storing report as a stream to the database.

{% tabs %}
{% highlight C# %}  

 



//// Getting Report as Stream

Stream stream = this.olapClient1.GetReportStream();



if (stream!= null)

{

  MemoryStream reportStream = stream as MemoryStream;



      string repotName ="SalesReport";



     con.Open();

     SqlCeCommand sqlCmd = new SqlCeCommand("insert into ReportsTable

                         Values(@ReportName,@Report)", con);

     sqlCmd.Parameters.Add("@ReportName", repotName);

     sqlCmd.Parameters.Add("@Report", reportStream.ToArray());

     sqlCmd.ExecuteNonQuery();

     con.Close();

   }

}

{% endhighlight %}



{% highlight vbnet %} 

 



Dim stream As Stream = Me.olapClient1.GetReportStream()



If stream IsNot Nothing Then

reportStream = TryCast(stream, MemoryStream)

Me.saveReport = New ReportNameWindow(Me.reportNames)

If saveReport.ShowDialog() = True Then

Dim repotName As String = "SalesReport”



con.Open()

Dim cmd1 As SqlCeCommand = New SqlCeCommand("insert into ReportsTable

                                   Values(@ReportName,@Report)", con)

cmd1.Parameters.Add("@ReportName", repotName)

cmd1.Parameters.Add("@Report", reportStream.ToArray())

cmd1.ExecuteNonQuery()

con.Close()

End If

End If

{% endhighlight %}
{% endtabs %}

Loading Report as a stream to OLAP Client. 

{% tabs %}
{% highlight C# %} 





string reportname ="RevenueReport";

Stream reportStream = null;

con.Open();



SqlCeDataAdapter da = new SqlCeDataAdapter("Select * from 

ReportsTable", con);

DataSet dSet = new DataSet();

da.Fill(dSet);

DataTable table = dSet.Tables[0];



foreach (DataRow row in table.Rows)

 {

  if ((row.ItemArray[0] as string).Equals(reportname))

   {

     reportStream = new MemoryStream(row.ItemArray[1] as byte[]);

     break;

   }

 }

this.olapClient1.LoadReportStream(reportStream);

con.Close();


 {% endhighlight %} 


{% highlight vbnet %} 





Dim reportname As String = ="RevenueReport"                    

Dim reportStream As Stream = Nothing

con.Open()



Dim da As SqlCeDataAdapter = New SqlCeDataAdapter("Select * from

                                                  ReportsTable", con)

Dim dSet As DataSet = New DataSet()

da.Fill(dSet)

Dim table As DataTable = dSet.Tables(0)



For Each row As DataRow In table.Rows

If (TryCast(row.ItemArray(0), String)).Equals(reportname) Then

  reportStream = New MemoryStream(TryCast(row.ItemArray(1), Byte()))

  Exit For

 End If

Next row

Me.olapClient1.LoadReportStream(reportStream)

con.Close()


{% endhighlight %} 
{% endtabs %}



Samples that demonstrate this feature is available in the following sample installation location.

&lt;Install Location&gt;\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapClient.WPF\Samples\OLAP Client\

