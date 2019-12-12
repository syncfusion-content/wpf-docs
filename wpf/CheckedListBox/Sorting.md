---
layout: post
title: Sorting | CheckListBox | wpf | Syncfusion
description: This section describes how to sort the Checklistbox items present in the CheckListBox and its basic features.
platform: wpf
control: CheckListBox
documentation: ug
---

# Sorting

In CheckListBox, sorting is possible , and CheckListBoxItems can be sorted using the [SortDescriptions](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~SortDescriptors.html).The CheckListBoxItems can be sorted either in ascending or descending order based on the user’s perspective. 

{% tabs %}
{%highlight xaml%}

<syncfusion:CheckListBox.SortDescriptions>
    <local:Groups>
        <componentmodel:SortDescription PropertyName="Name" Direction="Ascending"></componentmodel:SortDescription>
    </local:Groups>
</syncfusion:CheckListBox.SortDescriptions>

{%endhighlight%}

{% highlight c#%}

SortDescriptionCollection sortDescriptors = new SortDescriptionCollection
        {
            new SortDescription{ PropertyName="Name", Direction = ListSortDirection.Ascending },
        };
this.checkListBox.SortDescriptions = sortDescriptors;

{%endhighlight%}
{% endtabs %}

![Sorting](Grouping-Sorting_images/Sorting_image.png)