---
layout: post
title: Paging in WPF OLAP Common control | Syncfusion
description: Learn about Paging support in Syncfusion Essential Studio WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
 documentation: ug
---

# Paging in WPF OLAP Common

Paging enables users to view large records by breaking them into smaller segments.

Paging feature can be achieved by setting the _EnablePaging_ property to _true_ in a report.



The following code snippet demonstrates how to enable paging in the current report.

{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.EnablePaging = true;
{% endhighlight  %}


{% highlight vbnet %}

olapDataManager.CurrentReport.EnablePaging = True

{% endhighlight  %}
{% endtabs %}

The user can customize the page settings such as current page and page size for both row and column.



The following code explains how to customize current page and page size settings.


{% tabs %}
{% highlight c# %}

olapDataManager.CurrentReport.PagerOptions.CategorialCurrentPage = 1;

olapDataManager.CurrentReport.PagerOptions.SeriesCurrentPage = 2;

olapDataManager.CurrentReport.PagerOptions.CategorialPageSize = 50;

olapDataManager.CurrentReport.PagerOptions.SeriesPageSize = 50;

{% endhighlight  %}

{% highlight vbnet %}

olapDataManager.CurrentReport.PagerOptions.CategorialCurrentPage = 1

olapDataManager.CurrentReport.PagerOptions.SeriesCurrentPage = 2

olapDataManager.CurrentReport.PagerOptions.CategorialPageSize = 50

olapDataManager.CurrentReport.PagerOptions.SeriesPageSize = 50

{% endhighlight  %}
{% endtabs %}
