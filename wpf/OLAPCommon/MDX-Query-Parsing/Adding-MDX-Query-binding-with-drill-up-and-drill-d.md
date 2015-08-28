---
layout: post
title: Adding-MDX-Query-binding-with-drill-up-and-drill-d
description: adding mdx query binding with drill up and drill down operations to an application 
platform: wpf
control: OLAP Common 
documentation: ug
---

# Adding MDX Query binding with drill up and drill down operations to an Application 



The following code samples are used to enable and disable the MDX to OLAP parsing and processing of an MDX query into OLAP data.

{% highlight c# %}  

     //Enable MDX to OLAP parsing.

            OlapDataManager olapDataManager = new OlapDataManager();     

            olapDataManager.MdxQuery = "MDX Query Here";

            olapDataManager.ExecuteCellSet();



     //Disable MDX to OLAP parsing.

            OlapDataManager olapDataManager = new OlapDataManager();

            olapDataManager.AllowMdxToOlapReportParse = false;

            olapDataManager.MdxQuery = "MDX Query Here";

            olapDataManager.ExecuteCellSet();

{% endhighlight  %}  

{% highlight vbnet %}

     ‘Enable MDX to OLAP parsing.

            Dim olapDataManager As New OlapDataManager()

            olapDataManager.MdxQuery = "MDX Query Here"

            olapDataManager.ExecuteCellSet()



     ‘Enable MDX to OLAP parsing.

            Dim olapDataManager As New OlapDataManager()

            olapDataManager.AllowMdxToOlapReportParse = False

            olapDataManager.MdxQuery = "MDX Query Here"

            olapDataManager.ExecuteCellSet()

{% endhighlight  %}  

