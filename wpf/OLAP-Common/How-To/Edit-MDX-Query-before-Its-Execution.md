---
layout: post
title: Edit MDX Query before Its Execution| OLAPCommon | Wpf | Syncfusion
description: Edit mdx query before its execution in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Edit MDX Query before Its Execution

MDX Query can be edited before its execution to retrieve the CellSet through handling the BeforeMdxQueryExecute event of OlapDataManager. The following code example illustrates this.


{% tabs %}
{% highlight c# %}



olapDataManager.BeforeMdxQueryExecute += new QueryExecuteEventHandler(olapDataManager_BeforeMdxQueryExecute);



void olapDataManager_BeforeMdxQueryExecute(object sender, QueryExecutingEventArgs e)

{

     e.MdxQuery = "Edit MDX query here";

}


{% endhighlight  %}


{% highlight vbnet %}



Private olapDataManager.BeforeMdxQueryExecute += New QueryExecuteEventHandler(AddressOf olapDataManager_BeforeMdxQueryExecute)



Private Sub olapDataManager_BeforeMdxQueryExecute(ByVal sender As Object, ByVal e As QueryExecutingEventArgs)

        e.MdxQuery = "Edit MDX query here"

End Sub

{% endhighlight  %}
{% endtabs %}
