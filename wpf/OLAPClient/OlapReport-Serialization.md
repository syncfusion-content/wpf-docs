---
layout: post
title: OlapReport Serialization| OlapClient | Wpf | Syncfusion
description: olapreport serialization
platform: wpf
control: OlapClient 
documentation: ug
---

# Report Serialization

This feature allows the user to store the current session as a stream anywhere and also user can load the saved stream back to populate the OlapClient control. 

The following code sample describes to get the report as stream.

{% tabs %}

{% highlight c# %}   

    Stream stream = this.olapClient1.GetReportStream();

{% endhighlight %}

{% highlight vbnet %} 

    Dim stream As Stream = Me.olapClient1.GetReportStream()

{% endhighlight %} 

{% endtabs %}

The following code sample illustrates to load the report which is in stream type to OlapClient. 

{% tabs %}

{% highlight C# %}  

    this.olapClient1.LoadReportStream(reportStream);

{% endhighlight %}

{% highlight vbnet %} 

    Me.olapClient1.LoadReportStream(reportStream)

{% endhighlight %}
 
{% endtabs %}

The following code sample describes 

 * storing of the report as stream in database and 
 * retrieving the report as stream from the database and loading it back to OlapClient.

**STORING REPORT AS STREAM IN DATABASE**

{% tabs %}

{% highlight c# %}  
    
    Stream stream = this.olapClient1.GetReportStream();
    if (stream!= null)
    {
        MemoryStream reportStream = stream as MemoryStream;
        ReportNameWindow saveReport = new ReportNameWindow(this.ReportNames);
        saveReport.WindowStartupLocation = WindowStartupLocation.CenterOwner;
        saveReport.Owner = App.Current.Windows[0];
        if (saveReport.ShowDialog() == true)
        {
            string repotName = saveReport.reportName;
            con.Open();
            SqlCeCommand sqlCmd = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Report)", con);
            sqlCmd.Parameters.Add("@ReportName", repotName);
            sqlCmd.Parameters.Add("@Report", reportStream.ToArray());
            sqlCmd.ExecuteNonQuery();
            con.Close();
            this.ReportNames.Add(saveReport.reportName);
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
          Dim cmd1 As SqlCeCommand = New SqlCeCommand("insert into ReportsTable Values(@ReportName,@Report)", con)
          cmd1.Parameters.Add("@ReportName", repotName)
          cmd1.Parameters.Add("@Report", reportStream.ToArray())
          cmd1.ExecuteNonQuery()
          con.Close()
       End If
    End If

{% endhighlight %}

{% endtabs %}

**LOADING REPORT AS STREAM FROM DATABASE**

{% tabs %}

{% highlight C# %} 

    string reportname ="RevenueReport";
    Stream reportStream = null;
    con.Open();
    SqlCeDataAdapter da = new SqlCeDataAdapter("Select * from ReportsTable", con);
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
    Dim da As SqlCeDataAdapter = New SqlCeDataAdapter("Select * from ReportsTable", con)
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

A sample demo is available at the following link:

[system drive]:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapClient.WPF\Samples\Serialization\Report Serialization
